# Valorant Overlay

[![https://github.com/fill30/valorant-overlay/blob/master/LICENSE](https://img.shields.io/github/license/fill30/valorant-overlay)](https://github.com/fill30/valorant-overlay/blob/master/LICENSE)  
This is an overlay for the Riot game VALORANT.
This branch is the java version of the overlay which uses java to host a webserver which allows the dashboard and graphics to communicate using http requests.
The master branch uses a nodejs framework called nodecg. This is much better for writing broadcast graphics systems.
Big shout out to [modmuss50](http://github.com/modmuss50) for teaching me a lot of the java and javascript.

![Example 1](https://i.imgur.com/J4wtqhp.jpg)

## How it works

The overlay consists of 3 sections:

- Graphics (html, js, css)
- Dashboard (html, js, css)
- Webserver (java)

#### Graphics

The graphics are written in HTML, CSS and Javascript. It can be added into OBS as a simple browser source like most overlays. The graphics are updated by reading a json file every seceond and replacing the data on screen with what is written in the json file.

Here are 2 examples of the graphics: [Example 1](https://i.imgur.com/J4wtqhp.jpg), [Example 2](https://i.imgur.com/eOLh8Mi.jpg).  
Graphics elements:

- Top Bar (to hide ingame stats such as fps counter, ping and packet loss)
- Team Logos
- Team Names
- Player Names
- Images of which character each player is playing as

#### Dashboard

The dashboard, as shown [here](https://i.imgur.com/1r2k7lY.png), is written in HTML, CSS and Javascript. This is how the user changes the data shown in the graphics. To add a team logo put a `.png` in the `logos` folder. Then in the dashboard type the name of the `.png` file. Remember data will only update when the "Set" button is pressed. 

#### Webserver

The webserver, as shown [here](https://i.imgur.com/T868rq4.png), is what locally hosts the graphics and dashboard pages. It also handles the getting and setting of the json file which transfers data between the dashboard and the graphics. It is written in java and uses a web framework called "Javalin".

## How to use

This can be added into any broadcast software (e.g. OBS, Xsplit, vMix) as a browser source.

1. Download the lastest release of the overlay from the [releases page](https://github.com/fill30/valorant-overlay/releases).
2. Export the contents of the zip file into any folder on your computer.
3. Start the overlay by running the start.bat file (This opens the jar file using the included OpenJDK so that users are not required to have java already installed).
4. If the backend server has started correctly you should now be able to go to http://localhost:7000/dashboard and http://localhost:7000/graphics.

To add a team logo put a `.png` in the `logos` folder. Then in the dashboard type the name of the `.png` file. Remember data will only update when the "Set" button is pressed.  
