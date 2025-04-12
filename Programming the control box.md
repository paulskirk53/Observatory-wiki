  

## This page now maintained on Obsidian wiki as of April 2025

## Jtag2updi programmer for AVR4809

  

[https://www.youtube.com/watch?v=yWb7qHI0YN4](https://www.youtube.com/watch?v=yWb7qHI0YN4) 

1. Use an Arduino UNO as the updi programmer
    
2. **NB the target board AVR4809 in the control box MUST BE POWERED BY INSERTING THE usb CABLES. The UPDI upload will not work if the target board is not powered.**
    
3. [https://github.com/ElTangas/jtag2updi](https://github.com/ElTangas/jtag2updi)
    
4. Just need the source folder from the extract - copy to desktop and rename the same as the sketch inside - arduino needs the same sketch and folder name etc
    
5. Open the jtag2updi sketch - I used the Arduino IDE for this part.
    
6. Select the UNO board and upload the sketch - remove capacitor temporarily for this part to work. Then replace capacitor as it’s needed for the UNO to program the AVR UPDI
    
7. Pick the target board avr4809 and its parameters (clock, No pins etc)
    
8. If using arduino IDE, Choose jtag2updi as the programmer. PIO.ini has the correct options set - see PIO.ini for Control box for a working example.
    
9. Make the updi and gnd physical connections. The jtag2updi programmer needs a 10uf cap (rst to gnd) on the UNO and 4k7 resistor inline with UPDI lead.
    
10. The programmer code uses D6 on the UNO programmer board see the jtag2updi site.
    
11. Open user’s sketch e.g. ‘control box’
    
12. Upload using programmer - if using Arduino IDE, or just upload if using PIO.
    

  

Notes:

The above process worked and uploaded a blink led sketch to an avr4809 12-5-23 - you must use upload using programmer from the menu if using Arduino IDE (the forum says the programmer will be detected in future versions, so a straightforward upload will work then).

14-10-23 the above also worked from dev machine to upload code amendments, but a line was removed from pio.ini to get it to work. See github desktop for comment and change.

  

PIO works with jtag2updi. See the PIO.ini for the control box project.

  

Pio forum 14-10-23

I posted because all of the above DOES NOT WORK on the NUC, only on DEV m/c - check the board is powered

  
  

docker run -d -p 8080:3000 --name wiki --restart unless-stopped -e "DB_TYPE=postgres" -e "DB_HOST=db" -e "DB_PORT=5432" -e "DB_USER=wikijs" -e "DB_PASS=wikijsrocks" -e "DB_NAME=wiki_db-data" ghcr.io/requarks/wiki:2