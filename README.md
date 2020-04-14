Inspired by: https://github.com/diehardsk/Volumio-OledUI

### 14.04.2020 End of this Project
---
luma.oled is not compatible with python 2.7 anymore.
migrated to python 3.5.2 -> [Maschine2501/NR1-UI](https://github.com/Maschine2501/NR1-UI)

# Volumio-OledUI MK2

Im building a Network Hifi Receiver from scratch.
An old Braun T2 Tuner serves as case for the player.
To keep as much as possible from the look of the device i needed an Interface for Volumio.
And especialy one that supports a 3,2" ssd1322 SPI Oled with 256x64Pixel.
After doing some research i found diehrdsk/Volumio-OledUI.
It fullfills many points on my "wishlist" but not nearly all.
As we all know, the way is the destination, i spent some time (much time....) in modifying the original code.
The project is not finished yet...

## Features of Maschine2501/Volumio-OledUI:

* 4 Button Interface (Button function depends on "State" of the screen, e.g. playback, menu...)
* 1 Rotary with buttons (function also depends on "State")
* Playback Screen with Artist, Song, file-format, samplerate and bitdepth
* Standby-Screen with Time, Date and IP-Adress
* 3 Menu Screens (Media-Library, Playlists, Queue)
* Button Layout-Icons on each Screen (depending on "State")
* Media-Library-Information Screen (Statistics about your Media-Library -> Artists, Albums, Songs, total Playtime)
* Boot and Shutdown Logo
* maybe more features will come... ^^

* Some bugs will (not often) happen. Will debug it soon.

## To-Do: 

* Tune the whole UI (fonts, positions... etc. / will be done when everything else is running properly)
* Maybe integrate "CAVA" to display a bargraph spectrum? (hot topic!!!)

## Allready Done:

* Standby-Screen (when Playback is stoped, Time, Date and IP is Displayed)
* Automatic stop when playback is paused (value could be defined / declared)
* display Fileformat/Samplerate/Bitdepth in the NowPlayingScreen
* Scroll Text stops before shown completly -> text was defined as scrollText, which makes "black"-boxes arround the text
* one rotary removed
* 4 more Buttons via GPIO (needs some fine tuning)
* MediaInformationScreen (volumio.local/api/v1/collectionstats)

## Demo Video from nightly-build (05.03.2020):

[![Video-Sample](http://img.youtube.com/vi/9TtgO0_KqNk/0.jpg)](http://www.youtube.com/watch?v=9TtgO0_KqNk "Video-Sample")

## "Screenshots":

![Standby-Screen](https://i.ibb.co/Sr2xK8H/Screenshot-05-03-2020-20-08-25.jpg)
![Now-Playing-Screen](https://i.ibb.co/ZKGB3Wb/Screenshot-05-03-2020-20-08-47.jpg)
![Playlist-Menu](https://i.ibb.co/tbM3JNf/Screenshot-05-03-2020-20-09-05.jpg)
![Queue-Menu](https://i.ibb.co/HrRhxJL/Screenshot-05-03-2020-20-09-29.jpg)
![Media-Library-Info](https://i.ibb.co/P9ZtKsc/Screenshot-05-03-2020-20-09-59.jpg)

## Why is the first part of the display empty?

The cutout in the front of the device is smaller as the ssd1322 display -> so the display actually don't use the first 42 pixels.

![hifi-tuner case](https://i.ibb.co/WpsSd5z/Entwurfszeichnung-NR1-500px.jpg)

## [Project on Volumio-Forum](https://forum.volumio.org/256x64-oled-ssd1322-spi-buttons-rotary-interface-t14098.html#p72945)

## But you want it on the whole Display?

Simply change the value's from "42" to "0" (self.text1Pos = (42, 2))... that's it! (Tutorials/Guides will follow...)

## [installation steps (stable release)](https://github.com/Maschine2501/Volumio-OledUI/wiki/Installation-steps-(stable-release))

## [installation steps (nightly build)](https://github.com/Maschine2501/Volumio-OledUI/wiki/Installation-steps-(nightly))

## Check the logs

#### for the stable build

sudo journalctl -fu oledui.service

#### for the nightly build:

sudo journalctl -fu oledui-nightly.service

## [Hints](https://github.com/Maschine2501/Volumio-OledUI/wiki/hints---tricks---nice-to-know)

## [wiring / button-layout / truthtable](https://github.com/Maschine2501/Volumio-OledUI/wiki/Wiring---Button-Truthtable)

### [hardware](https://github.com/Maschine2501/Volumio-OledUI/wiki/Hardware)

### [dependencies](https://github.com/Maschine2501/Volumio-OledUI/wiki/Dependencies)

### [Sources & font-info](https://github.com/Maschine2501/Volumio-OledUI/wiki/Sources---font-information)

