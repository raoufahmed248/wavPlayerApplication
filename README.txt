Dependencies:
Install required packages before running build steps (if jackd2 asks to enable realtime, select yes):
sudo apt install jackd2
sudo apt install libjack-jackd2-dev
sudo apt install cmake


To clone this project:
1.) git clone https://github.com/raoufahmed248/wavPlayerApplication.git
2.) cd wavPlayerApplication
3.) git submodule update --init --recursive

To build:
1.) mkdir build
2.) cd build
3.) cmake ..
4.) make


To run:
1.) Make sure JACK is running (I recommend using QJackCtl)
1. a.) IF USING RPI INTEGRATED AUDIO, YOU HAVE TO RUN A SPECIAL COMMAND TO START JACK:
JACK_NO_AUDIO_RESERVATION=1 jackd -R -P40 -d alsa -d hw:0 -P -S -p 1024 -n 2 -r 44100 -i 0 -o 2
Then in another terminal run qjackctl to make connections (DO NOT CLICK START IN QJACKCTL!!)
1. b.) IF USING A USB AUDIO INTERFACE THEN YOU CAN USE QJACKCTL TO BOTH START AND MAKE CONNECTIONS, JUST MAKE SURE YOU SELECT RIGHT DEVICES IN SETUP
2.) cd resources
3.) ../build/app/myApp
