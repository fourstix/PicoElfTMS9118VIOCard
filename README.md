# PicoElfTMS9118VIOCard
This is a TMS9118 Video Card with Hexadecimal Data Output and Input for the Pico/Elf v2 by Mike Riley. Information about the Pico/Elf v2 is available at [Elf-Emulation.com](http://www.elf-emulation.com/).

Video Hardware
--------------
The TMS9118 video display processor uses ports 1 and 5 as the VDP Data port and VDP register port.  The video interrupt is tied to /EF1.   A push button provides the VDP reset when pressed.

Video Driver
------------
The Pico/Elf TMS9918 VIO card video hardware is supported by the [TMS9x18 Video Driver](https://github.com/fourstix/Elfos-TMS9X18-Driver) with a version of this driver named [vdp_video_N15.bin](https://github.com/fourstix/Elfos-TMS9X18-Driver/blob/main/bin/tms9x18_N15.bin). (N = No group, port 1 and port 5.)

Examples
---------
With this driver loaded, the [TMS9118 demo programs](https://github.com/fourstix/Elfos-TMS9118-Demos) can run using the [TMS9X18 Video Library](https://github.com/fourstix/Elfos-TMS9X18-Library) to communicate to the video hardware.

<table class="table table-hover table-striped table-bordered">
  <tr align="center">
   <td><img src="https://github.com/fourstix/PicoElfTMS9118VIOCard/blob/main/pics/picoelf_vio.jpg"></td>
  </tr>
  <tr align="center">
    <td>Pico/Elf TMS9118 Video I/O Card.</td>   
  </tr>
  <tr align="center">
  <td><img src="https://github.com/fourstix/PicoElfTMS9118VIOCard/blob/main/pics/picoelf_full.jpg"></td>
  </tr>
  <tr align="center">
  <td>Pico/Elf v2 running with the TMS9118 Video I/O Card and an STG RTC/NVR card connected by an IDE cable.<td>    
  </tr>
  <tr align="center">
     <td><img src="https://github.com/fourstix/PicoElfTMS9118VIOCard/blob/main/pics/schematic.jpg"></td>
  </tr>
  <tr align="center">
     <td>Pico/Elf TMS9118 Video I/O Card Hardware Schematic</td>
  </tr>
</table>


Data I/O Hardware
-----------------
Data can be entered on the hexadecimal keypad and read as input on Port 4. The input button will bring /EF4 low  when pressed. The display is updated with the hexadecimal value on the data bus whenever data is input or output to Port 4. The LED indicates the status of the 1802 Q-bit on the Pico/Elf data bus.

Ports
------
<table>
<tr><th>Port</th><th>Function</th></tr>
<tr><td>1</td><td>VDP Data</td></tr>
<tr><td>4</td><td>Data I/O</td></tr>
<tr><td>5</td><td>VDP Register</td></tr>
</table>

External Flags
--------------
<table>
<tr><th>Flag</th><th>Function</th></tr>
<tr><td>/EF1</td><td>VDP Interrupt</td></tr>
<tr><td>/EF4</td><td>Input Button</td></tr>
</table>

Schematic
---------
TBD

Repository Contents
-------------------
* **/brd/** -- Printed Circuit Board layout for PicoElfTMS9118VIOCard
  * PicoElfTMS9118VIOCard-KiCad5.zip -- KiCad5 project files for Pico/Elf TMS9118 Video I/O PCB.
  * PicoElfTMS9118VIOCard-gerbers.zip -- Gerber files for Pico/Elf TMS9118 Video I/O PCB.
* **/docs** -- documentation files
  * PicoElfTMS9118VIOCard.pdf -- schematic for Pico/Elf TMS9118 Video I/O Card.
  * PicoElfTMS9118VIOCard-BOM.csv -- Bill of Materials for Pico/Elf TMS9118 Video I/O Card.
* **/pics/** -- example pictures for readme

Pico/Elf v2 Expansion Connector
-------------------------------
<table>
<tr><td>A0</td><td>1</td><td>2</td><td>D0</td></tr>
<tr><td>A1</td><td>3</td><td>4</td><td>D1</td></tr>
<tr><td>A2</td><td>5</td><td>6</td><td>D2</td></tr>
<tr><td>A3</td><td>7</td><td>8</td><td>D3</td></tr>
<tr><td>A4</td><td>9</td><td>10</td><td>D4</td></tr>
<tr><td>A5</td><td>11</td><td>12</td><td>D5</td></tr>
<tr><td>A6</td><td>13</td><td>14</td><td>D6</td></tr>
<tr><td>A7</td><td>15</td><td>16</td><td>D7</td></tr>
<tr><td>TPA</td><td>17</td><td>18</td><td>TPB</td></tr>
<tr><td>/INP</td><td>19</td><td>20</td><td>EF1</td></tr>
<tr><td>/OUT</td><td>21</td><td>22</td><td>EF2</td></tr>
<tr><td>PORT1</td><td>23</td><td>24</td><td>EF3</td></tr>
<tr><td>/DMA_IN</td><td>25</td><td>26</td><td>EF4</td></tr>
<tr><td>/DMA_OUT</td><td>27</td><td>28</td><td>INT</td></tr>
<tr><td>/MRD</td><td>29</td><td>30</td><td>/MWR</td></tr>
<tr><td>SC0</td><td>31</td><td>32</td><td>SC1</td></tr>
<tr><td>Q</td><td>33</td><td>34</td><td>GND</td></tr>
<tr><td>PORT2</td><td>35</td><td>36</td><td>PORT5</td></tr>
<tr><td>PORT3</td><td>37</td><td>38</td><td>PORT6</td></tr>
<tr><td>PORT4</td><td>39</td><td>40</td><td>PORT7</td></tr>
</table>

Bill of Materials
-----------------
<table>
<tr><th colspan = "2">Part #</th><th>Qty</th><th>Description</th></tr>
<tr><td colspan = "2">U1</td><td>1</td><td>74HC08 Quad AND Gate</td></tr>
<tr><td colspan = "2">U2</td><td>1</td><td>74HC32 Quad OR Gate</td></tr>
<tr><td colspan = "2">U3</td><td>1</td><td>LM7805 5v Regulator</td></tr>
<tr><td colspan = "2">U4</td><td>1</td><td>TMS9118 Video Display Processor</td></tr>
<tr><td colspan = "2">U5,U6</td><td>2</td><td>TMS4464 64k x 4 DRAM</td></tr>
<tr><td colspan = "2">U7</td><td>1</td><td>74C922 16-key Encoder</td></tr>
<tr><td colspan = "2">U8</td><td>1</td><td>74HC541 Octal Buffer</td></tr>
<tr><td colspan = "2">Q1, Q2</td><td>2</td><td>2N2222A NPN Transistors</td></tr>
<tr><td colspan = "2">Y1</td><td>1</td><td>10.7635 MHz Crystal</td></tr>
<tr><td colspan = "2">R1,R6</td><td>2</td><td>22k ohm 1/4 Watt Resistors</td></tr>
<tr><td colspan = "2">R2</td><td>1</td><td>68 ohm 1/4 Watt Resistor</td></tr>
<tr><td colspan = "2">R3,R7</td><td>2</td><td>330 ohm 1/4 Watt Resistors</td></tr>
<tr><td colspan = "2">R4</td><td>1</td><td>560 ohm 1/4 Watt Resistor</td></tr>
<tr><td colspan = "2">R5</td><td>1</td><td>1k ohm 1/4 Watt Resistor</td></tr>
<tr><td colspan = "2">C1-C4,C6,C7,C10-C12</td><td>9</td><td>0.1 uF Capacitors</td></tr>
<tr><td colspan = "2">C5</td><td>1</td><td>0.33 uF Capacitor</td></tr>
<tr><td colspan = "2">C8,C9</td><td>2</td><td>33 pF Capacitors</td></tr>
<tr><td colspan = "2">C13</td><td>1</td><td>1 uF Capacitor</td></tr>
<tr><td colspan = "2">C14</td><td>1</td><td>0.1 uF Capacitor</td></tr>
<tr><td colspan = "2">D1</td><td>1</td><td>5mm Red LED</td></tr>
<tr><td colspan = "2">DS1,DS2</td><td>1</td><td>TIL311 Hex Displays</td></tr>
<tr><td colspan = "2">J1</td><td>1</td><td>PJ-202A 2x5.5mm 3 pin Power Jack</td></tr>
<tr><td colspan = "2">J2</td><td>1</td><td>2x20 40 Pin Header, 2.54mm spacing</td></tr>
<tr><td colspan = "2">J3</td><td>1</td><td>2 pin Screw Terminal Block, 5mm spacing</td></tr>
<tr><td colspan = "2">J4</td><td>1</td><td>Kobe Yellow Phono Jack</td></tr>
<tr><td colspan = "2">J5,J8-J10</td><td>4</td><td>Male  2Pin Connectors, 2.54mm spacing</td></tr>
<tr><td colspan = "2">J6</td><td>1</td><td>Male 6 Pin Connector, 2.54mm spacing</td></tr>
<tr><td colspan = "2">J7</td><td>1</td><td>Male 4 Pin Connector, 2.54mm spacing</td></tr>
<tr><td colspan = "2">SW1</td><td>1</td><td>6mm Push Button Switch, 9mm post, Grey Cap</td></tr>
<tr><td colspan = "2">SW2-SW17</td><td>16</td><td>6mm Push Button Switches, 5mm post</td></tr>
<tr><td colspan = "2">SW18</td><td>1</td><td>6mm Push Button Switch, 9mm post, Yellow Cap</td></tr>
</table>

License Information
-------------------
This code is public domain under the MIT License, but please buy me a beer
if you use this and we meet someday (Beerware).

References to any products, programs or services do not imply
that they will be available in all countries in which their respective owner operates.

Other company, product, or services names may be trademarks or services marks of others.

All libraries used in this code are copyright their respective authors.

The Pico/Elf v2 1802 microcomputer hardware and software
Copyright (c) 2004-2022 by Mike Riley.

Elf/OS and RcAsm Software
Copyright (c) 2004-2022 by Mike Riley.

Many thanks to the original authors for making their designs and code available as open source.

This code, firmware, and software is released under the [MIT License](http://opensource.org/licenses/MIT).

The MIT License (MIT)

Copyright (c) 2022 by Gaston Williams

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

**THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.**
