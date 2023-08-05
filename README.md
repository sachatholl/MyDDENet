# MyDDE-Net
MyDDE-Net is a set of utilities to transport the MyDDE protocol used by Orbitron Satellite Tracker, Maiden Voyage Deep Space Tracker, and ARMCS over the network to allow control of radio equipment, Rotor, HamLib devices, and Orbitron2WebSDR typically used for amateur radio satellite ground stations.

Satellite trackers such as Orbitron, Maiden Voyage Deep Space Tracker, and ARMCS (Amateur Radio Mission Control System) use a driver protocol called MyDDE to transmit the receive/transmit frequencies and local horizon coordinates for antenna pointing via DDE.

In computing, DDE or Dynamic Data Exchange is an inter-process communication technology used in early Microsoft Windows and OS/2 versions. However, it is still used by many Amateur radio satellite tracking systems like Orbitron. DDE allows programs to manipulate objects provided by other programs and to respond to user actions that affect those objects.

	**bold text** MyDDE2TCP 	**bold text**
MyDDE-Net consists of 2 applications. The first application is MyDDE2TCP. This application receives commands from a satellite tracker via DDE using the MyDDE protocol. It makes these command strings available by launching a TCP/IP server. This server accepts several simultaneous TCP2MyDDE client connections.

The second application TCP2MyDDE is a TCP/IP client running essentially on another machine in the ground station's network to receive the commands and make them available again using the MyDDE protocol on a DDE channel to MyDDE compatible devices such as radio and rotor equipment such as HDSDR, Orbitron2WebSDR, GNU-Radio, Slfa-Spid rotor, HamLib-Rotor&Radio-Control...

In a nutshell, MyDDE2TCP repeats the MyDDE protocol from one IP to one or several TCP2MyDDE clients, which are located at another IP using the same TCP port. Since the MyDDE2TCP server accepts multiple client connections, the endpoint devices, such as  Radios, Rotors, and WebSDRs... can run on different bare metal or virtual machines. Also, the TCP2MyDDE client allows multiple myDDE-compatible connections on the same bare metal machine or VM.

MyDDE2TCP and TCP2MyDDE are completely written in LabVIEW. I provided the sources in LV2013, so they can be opened at least in every LV version until the time of release (04.08.2023). I provided executables for LabVIEW Runtime Engine 2013, to be used in Windows7 - 10, and LabVIEW Runtime Engine 2021 for Windows >= 10
