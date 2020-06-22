# Enigma-Machine
Enigma Machine for encryption and decryption , with UI built using c++ with curses library for graphics

compile the file by
    $ g++ enigma.cpp -l curses
    this will generate a.out file 

Run 
    $ ./a.out

There is only one file for enigma machine simulator and GUI divided into 6 portions
It uses curses library for GUI

Warning :-
    -- if your system not support coloring then GUI will have colorless screen (limitation of library only for colors)
    -- speed up code process put delay = 0 (seconds) in encryption(),decryption() function (has a function call enigma.machine(...., delay)) in portion no.3,4
    -- delay use for speed control of program to visualize it. currently delay=1(sec) total 8(sec) per character.
    -- don't use backspace while inputing file name because in some cases it works but not in all cases.
    -- Hit enter after puting filename with extension because the function getstringval() accept string until it get a '\n' character at end.

#Then it works perfectly .

Comments :- code contain Comment to make it understandable(easy to understand)

Portion no.1
    --statWind() function for GUI of Reflector and Entry wheel
    --rotorWind() function for GUI of all three Rotors
    --installMachine() function for installing the all wheels on main screen
    --resetscr() function for set the screen as blank
    --printingscr() main function for GUI providing in cpp it initialize the screen & Enable use of system colors

Portion no.2 
    --Class for enigma machine
        -- variables for storing instances so that we can reuse values
        -- EnigmaMachine() constructor for starting machine with GUI with initial conditions
        -- randomgenerator() function to generate alphabets randomly (a to z all) and fill into a set for future use in wheels
        -- resetMachine() function call to reset the wheels to initial conditions to decipher the text
        -- statMaping() function for creating maping in Reflector wheel
        -- mapingRotor() function for creating maping in Rotors wheels
        -- position() function for finding position of the alphabet in a rotor so that at correct position other wheel can be trigger to proceed
        -- rpositon()  similar as position() but in reverse direction
        -- blinkcolor() indicate where are we (when we are encrypting/decrypting a single character) in enigma machine
        -- blinkcolorrev()  similar as blinkcolor() but in reverse direction
        -- converson() function perform complete conversion of a single character from plain to cipher and vice-versa
        -- machine() function heart of EnigmaMachine class operate whole conversion machanism conversion of characters ,rotation of rotors,where we are, what to do next

Portion no.3
    --encryption() function
        --take inputs from file as string
        --convert string into words
        --word to characters
        --then pass it to enigma machine() function
        --and get encrypted characters
        --then reverse above process -> characters to words -> words to string -> string to output file

Portion no.4
    --decryption() function
        --take inputs from file as string
        --convert string into words
        --word to characters
        --then pass it to enigma machine() function
        --and get decrypted characters
        --then reverse above process -> characters to words -> words to string -> string to output file

Portion no.5
    --getstringval() take input form GUI because there normal cin/cout would not work properly with curses library screen

Portion no.6
    --main() main function
        --interconnect all created element simulator + GUI for enigma
        --make EnigmaMachine class object to make a fresh new machine
        --start taking input from GUI
        --What we want to perform encryption/decryption then press 1 or 0 respectively otherwise you will exit
        --Then provide file names for input/output in encryption/decryption scenario
        --(In my case filein.txt as input and fileout.txt as output file)
