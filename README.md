# MyDDE-Net Overview
MyDDE-Net is a toolkit designed to enable the transmission of the MyDDE protocol over a network. It's primarily used to control antenna rotors and radio equipment in amateur radio satellite ground stations, with applications such as Orbitron, WX-Tracker, Maiden Voyage Deep Space Tracker, and ARMCS (Amateur Radio Mission Control System).

# DDE and MyDDE protocol
DDE (Dynamic Data Exchange) is an inter-process communication technology that originated in early Microsoft Windows and OS/2 versions. It allows programs to manipulate other program objects and respond to user actions that affect those objects. Many amateur radio satellite tracking systems still use it today. The MyDDE protocol consists of formatted string commands containing data such as propagation time, uplink and downlink frequencies, and local horizon coordinates for antenna pointing, all transported over a DDE channel.

# Application components
MyDDE-Net consists of two applications, MyDDE2TCP and TCP2MyDDE, written entirely in LabVIEW.

## MyDDE2TCP
This application receives commands from a satellite tracker using the MyDDE protocol via DDE, then makes these commands available on a TCP/IP server, allowing multiple simultaneous connections.

## TCP2MyDDE
TCP2MyDDE works as a TCP/IP client on another machine within the ground station's network. It receives commands and sends them back on a DDE channel using the MyDDE protocol to control the radios and rotor equipment of the ground station. The MyDDE2TCP server and TCP2MyDDE client support multiple client connections, allowing endpoints to run on bare metal or virtual machines.

# Code and executables
Sources for both applications are provided in LV2013 format and can be opened in any LV version until release (04/08/2023). Executables are available for LabVIEW 32bit Runtime Engine 2013 SP1 (compatible with Windows Vista, XP, Windows 7, and Windows 8) and LabVIEW 32bit Runtime Engine 2021 for Windows 10.
