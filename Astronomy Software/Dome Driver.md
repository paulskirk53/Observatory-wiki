
this document is current and replaces the version on google docs

I wrote the Dome Driver with some initial help from Tom How (who created the driver videos on the ASCOM website). He's a friend of Greg Parker and that's how I got in touch. ASCOM drivers are essentially an abstraction layer, which facilitates a standard set of commands and processes which all clients can use. The driver is on github [here](https://github.com/paulskirk53/Dome). It's built using the ASCOM Developer driver templates. It has no user interface, excepting when at startup, if he user chooses 'properties', a Setup() dialog is shown. It's essential to access the dialog when connecting the Dome as it use

The driver is a DLL which targets a particular version of the dot net framework and it has to be registered in the MS Windows registry. Visual Studio takes care of this when the code is compiled. 

**Dome Driver Registration with RegAsm on NUC and Dev**
## Current location for NUC Dome Driver

The upshot of the above is that whereas previously the dome driver was transferred from the dev machine and pasted into NUC C:\Dome, this is no longer necessary since visual studio is now on the NUC and the Dome Driver is registered in: 

c:\users\paul\documents\GitHub\Dome\PaulDomeinc\bin\debug
### GUID Note

Note that the guid has been changed - as per Peter Simpson’s advice. The new GUID works on both NUC and Dev machines (tried on both by clean, rebuild and run to see the driver load and setup dialog shown 15-10-23)
## Problem of Dome Driver failing to load

From Peter Simpson 6th Aug 2023

Hi Paul,
Thanks for the link to your repo. I see the same issue you are seeing and have a fix, but you will also need to fix a compounding issue regarding registration that is making life very difficult for you:

- You are using a wildcard for the assembly version number: "6.2.*" in the Assembly Information dialogue.
    

This means that every build will have a different assembly version number and that the RegAsm commands you are using are invalidated after every build because the assembly version number is different every time, hence the need to re-register after every build.

You have checked the "Register For Com Interop" option on the VS "Build Tab" so are presumably running VS as administrator. This ensures that VS registers your driver on every build BUT VS2022 is a 64bit application, unlike earlier versions that were 32bit. This means that the registration is in the 64bit part of the registry but this does not make the driver object accessible to 32bit applications.

The error message you posted appears because your test application is set to compile as x86 i.e. 32bit. Yes, your driver is compiled as AnyCPU and so will run in a 32bit process, but COM is preventing this because the driver is only registered as a 64bit object. COM knows that 64bit objects don't work in 32bit applications so no attempt is made to load your driver into your test application and an error is raised instead.

So, to get on an even keel, I suggest that you complete these steps in order:

- Start VS as admin
    
- Clean the build
    
- Change the assembly version number to something fixed like 6.2.0.0
    
- Create and apply a further new GUID for the driver (important to avoid assembly version number confusion with previous builds)
    
- Build a debug version (this will create a 64bit COM registration)
    
- Register the driver in the 32bit portion of the registry using this command from a command prompt in the bin\debug folder.
    

- C:\Windows\Microsoft.NET\Framework\v4.0.30319\Regasm ascom.gowercdome.dome.dll /codebase

- Run the 32bit test program and you should now be able to set the driver properties from the Chooser dialogue.

As a by-product of the steps above you should no longer need to run VS as administrator nor register after every build.

Best wishes, Peter

## Older initial Background

copied the driver files from the dev machine  bin\debug folder all files including the driver dll and placed them in the NUC c:\dome driver folder. My attempt at RegAsm seemed to work with a success message, but when picking the gowerdome from SGP and trying to access the setup, an error occurred.

From Rick on ASCOM dev Talk:

Your steps seem basically correct. 

The Setup  Dialog functionality should all be in dome DLL, so this is likely the file that is "missing". It could also be registered incorrectly, or not able to be loaded because some required software is also missing and that is preventing the driver from loading

The error message shows a GUID for the Class Factory...{0EDCF62A-9D7A-4A63-B8C2-F2F151C93BA7}. You should be able to find that GUID in the Windows Registry and see where the registered location is and verify if that location is correct.

It could also be that the NUC does not have the required .NET Framework installed. This would depend on what Framework version you targeted in your Visual Studio project.

There are typically multiple versions of REGASM on your system and you may have chosen the wrong version to do your registration. On a 64-bit computer, a managed driver DLL can be loaded as either 32-bit or 64-bit, depending on whether the application (SGP) is running as 32-bit or 64-bit. This means that your driver must be registered twice (for both 32 and 64-bit operation). This means that you would need to register your DLL twice with two different copies of REGASM that are in two different folders on the PC.

The 32-bit version of REGASM is in C:\Windows\Microsoft.NET\Framework\v4.0.30319

  

The 64-bit version of REGASM is in C:\Windows\Microsoft.NET\Framework64\v4.0.30319.

I believe that you should also use the /codebase switch during registration.

So 32-bit registration would look like this:

"C:\Windows\Microsoft.NET\Framework\v4.0.30319\RegAsm.exe" /register /codebase "C:\dome driver\ASCOM.GowerCDome.Dome.dll"

NB - the above worked on the NUC

  

### 64-bit registration 

64 bit registration would look like this:

"C:\Windows\Microsoft.NET\Framework64\v4.0.30319\RegAsm.exe" /register /codebase "C:\dome driver\ASCOM.GowerCDome.Dome.dll"

  

The customised file path for the Gower dome is:

"C:\Windows\Microsoft.NET\Framework64\v4.0.30319\RegAsm.exe" /register /codebase "C:\Dome Driver GIT Repository\Dome\PaulDomeInC\bin\Debug\ASCOM.GowerCDome.Dome.dll"

I would also say that when you create a skeleton driver project from the Visual Studio templates, the driver project has references to the most commonly needed Platform assemblies. The way these references are created, the assemblies are copied into the project's build folder. Since you would typically install the ASCOM Platform on the NUC, the ASCOM.* files in the Build folder do not need to be copied to the NUC. The 4 files for your driver with file extensions of .dll, .dll.config, .pdb, and .tlb are the only files that you need to copy.

I hope this helps.

﻿ Rick B

  
  

Text below based on the above, posted to stack exchange, as I’d asked for help there too Aug ‘23

Background

The Visual studio solution was originally built in 2015 using VS 2015 community it consists of two components - the driver DLL and a test console exe used to test and debug the dll. In that version of VS the applications were built as 32 bit. It all worked fine. The code is on Github.com

  

New circumstances

So now on the different machine where I cloned the repo, the version of VS is VS 2022 community which is of course a 64 bit application. The test application was set to compile as x86 (32 bit). The driver was compiled as AnyCPU but is registered as a 64 bit object - which of course won’t run in a 32 bit application.

  

Steps taken to resolve the issue

- Start VS as admin
    
- Clean the build
    
- Change the assembly version number to a fixed version with no wildcard
    
- Create and apply a new GUID for the driver 
    
- Build a debug version which create a 64bit COM 
    
- Register the driver in the 32bit portion of the registry using the following command from a command prompt in the bin\debug folder.
    

- C:\Windows\Microsoft.NET\Framework\v4.0.30319\Regasm <theDriverName>.dll /codebase
    

Following the above steps the code now runs as expected.

I am grateful to Peter Simpson at the ASCOM initiative for help with the above.