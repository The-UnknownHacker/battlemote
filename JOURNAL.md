---
Title: "Battlemote"
Author: "Aarav J"
Description: "Battlemote is an ESP32 powered battlebot controller"
Created_On: "27/7/2025"
---

# July 27th - August 1st: Started choosing components and integrating them with the PCB and adding them to the schematic

For this project I want to make an all in one remote that uses a xiao esp32 to control a battlebot that I made earlier
For components I am going with the following

- Xiao ESP32-c3 for the main board
- 8x Buttons for controls
- AMS1117-5.0 for the voltage regulator
- Adafruit 1.8" screen for the screen
- 7.4v Lipo Battery

I started by placing all the components into the schematic editor and organizing into groups like so

<img width="1027" height="688" alt="image" src="https://github.com/user-attachments/assets/40d3bb8c-98c7-4821-981b-feab18f48f9a" />

Once that was done I started adding gpio inputs and ouputs to the microcontroller like so

<img width="911" height="503" alt="image" src="https://github.com/user-attachments/assets/8e72f0e8-ab3c-4130-987a-239c88f276c5" />

I then wired up all the buttons to the ESP

<img width="668" height="556" alt="image" src="https://github.com/user-attachments/assets/dbe7aa10-b368-425e-8010-55d01d367ca7" />

After that I added the 4 mounting holes

<img width="311" height="666" alt="image" src="https://github.com/user-attachments/assets/d918075f-af75-4997-a3c2-56b0e460f3b3" />

Then the battery inputs and test points

<img width="438" height="650" alt="image" src="https://github.com/user-attachments/assets/e35fed03-88c4-4bfb-a586-821ef4cca4fa" />

Now for the 2 hardest things - The screen and the voltage regulator, After sifting through god knows how many datasheets I finally found the symbol and footprint for the screen (Adafruit doesnt like to share symbols)

<img width="956" height="501" alt="image" src="https://github.com/user-attachments/assets/913ac803-739e-43cb-8ba0-481674a670a0" />

And finally for the hardest part - the voltage regulator, After a bit of help from youtube, datasheets and chatgpt I finally got this part done!

<img width="968" height="548" alt="image" src="https://github.com/user-attachments/assets/afb68072-7c58-4970-8238-486a19ec6c33" />

After all this my finished schematic looked something like this

<img width="924" height="623" alt="image" src="https://github.com/user-attachments/assets/834c5cfd-305b-4be0-97bf-447d6f5cdee7" />

This itself took around 8-12 hours as I messed up multiple times with the screen and voltage reg wiring 😭

**Time Taken : 10h**


# August 1st - Started the PCB

Today I started the PCB by stealing the outline from the sprig because I liked the remote shape a lot, I also liked a lot of their components so I took the power button as well as the same buttons and screen
To achieve this I copied the edge.cuts layer of the sprig over to my project

<img width="1176" height="633" alt="image" src="https://github.com/user-attachments/assets/d913c0c1-b715-4f7e-b890-2e17943b3dac" />


After this I had to assign all the footprints in the schematic editor to tell KiCad how big everything was

<img width="787" height="586" alt="image" src="https://github.com/user-attachments/assets/ce8e7e02-5bac-48e6-b1ed-d88b77971259" />

I then did the layout of the PCB and ended up with something like this

<img width="1189" height="631" alt="image" src="https://github.com/user-attachments/assets/f4ffc796-81a7-4662-b584-9907e80fc67b" />

After this I added all the silkscreen to the board (Silkscreen is like little designs and features that go on your board for fun!)

<img width="1176" height="625" alt="image" src="https://github.com/user-attachments/assets/d166f44e-f309-45b8-9a6d-4ec4521b63c3" />

After completing this it was time for the hardest part of the project to start - The routing 😭
This can usually take more than a couple hours so I decided to leave it for the next day

**Time spent 8h**

# August 2nd - Started and finished the routing

Today I started the scariest part of this project - the routing, This was going to take a long time as it looks easy but I want to keep the design asthetic as well
After I finshed routing I ended up with something like this

<img width="1190" height="660" alt="image" src="https://github.com/user-attachments/assets/afeb44ac-85eb-4d94-87bc-c7c0b2cd328f" />

This proccess took around 4h counting all the revisinons to the board as well as accounting for mistakes

After that you may notice that some components are still unrouted - This is because we need to create something called a ground pour and 3v3 pour that connects these power rails over a certain region eliminating noise
After adding the ground board and touching up connections my finished board looks something like this

<img width="1124" height="631" alt="image" src="https://github.com/user-attachments/assets/c2ede75a-eda1-4969-8957-b749b25a80ea" />

I also spent around 20min finding 3d models for each of the components to make the 3d render of the board look good like so

<img width="881" height="467" alt="image" src="https://github.com/user-attachments/assets/b47d99ce-d622-41ed-8124-05cf6ceb9fd2" />

In black it looks like this

<img width="975" height="570" alt="image" src="https://github.com/user-attachments/assets/821daa6c-9afe-43ae-a083-732912576e90" />

I also added this cool silkscreen to the back like so that gives a cool effect

<img width="919" height="538" alt="image" src="https://github.com/user-attachments/assets/19551349-0f5b-4cc2-b07b-5d469c99b674" />



**Time taken 4.5h**

# August 6th - Whent back to the schematic to make some changes

After further review I realised I didnt have any xiao's on hand so I needed to modify the schematic to use the ones I did have - ESP32-supermini

I imported the footprint like so 

<img width="329" height="512" alt="image" src="https://github.com/user-attachments/assets/3f089901-ccf8-412e-9c86-67131c207fc5" />

After replacing the wiring for the new symbol it looks something like this

<img width="850" height="475" alt="image" src="https://github.com/user-attachments/assets/f7338159-f124-442d-b058-1584b26f77c7" />


After this I rerouted everthing which took me another 4 hours

<img width="1137" height="609" alt="image" src="https://github.com/user-attachments/assets/ce7ce70b-4ea7-4d1f-b83c-ec46a32dead6" />

**Time Taken : 4.5h**
