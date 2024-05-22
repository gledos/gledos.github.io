---
title: ascii art 图表设计
layout: post
published: false
---

```text
[Sun] -- [Pear]
[Apple] --> [Pear]
[Pear] -- [fruit] --> [Pineapple]
[Pear] --> [Cherry]
[fruit] ==> [Done]
```

转化为:

```text
                +--------+
                | Cherry |
                +--------+
                  ^
                  |
                  |
  +-------+     +--------+     +-------+     +-----------+
  | Apple | --> |  Pear  | --- | fruit | --> | Pineapple |
  +-------+     +--------+     +-------+     +-----------+
                  |              H
                  |              H
                  |              v
                +--------+     +-------+
                |  Sun   |     | Done  |
                +--------+     +-------+
```

```text
    ,----------------.
    | Round-cornered |
    |      boxes     |
    `----------------'

    -+
     |
     >- Stretchy braces
     |
    -+
```

```text
    ( Buttons )

    [ Dropdown lists |v]

    [X] Checkboxes

    (o) Radio buttons

    Sliders: ---|---------- 

    +-------------^
    | Scroll bars #
    |             #
    |             |
    |             v
    <----######-->

    Spin-boxes: [ 37.0 |:]
```

[ASCII diagram creator](https://news.ycombinator.com/item?id=2651745)

---------

```text
 ---------------------------------------
 Test stage defaults for some features:
NPA - Dial 760            914 NPA       - Dial 990
 DTMF ! Pulse ! Description of Service
 ---------------------------------------
  *66 !  1166 ! Reconnect last caller
 ---------------------------------------
  *63 !  1163 ! Selective Call Forward
 ---------------------------------------
  *60 !  1160 ! Nuisance Call Blocking
 ---------------------------------------
  *57 !  1157 ! Customer "Trace"
 ---------------------------------------
```

```text
 +---------------------------------------------------------------------------+
 !  +---------------------+       +-------------------------------------+    !
 !  !   (Ticket Box)      !       !            ( Display )              !    !
 !  +---------------------+       +-------------------------------------+    !
 !                                                                           !
 !                          (NonCoin)    (--- Coin 1-----)    (-- Hotel --)  !
 !  VFY OVR SCN INW EMR     Sta 0+ 0-    Sta 0+ 0- Pst Tne    Sta 0+ 0- Gst  !
 !      SES         INT                            Pay                       !
 !                                                                           !
 !  (Outgoing trunk)     (--- Ring Designation --- )  (Release)              !
 !  DA  R&R  SWB  OGT    BAK FWD CAL T&C Nfy Chg Key   BAK FWD  SR MB Mt PT  !
 !                               BAK         due clg                         !
 !                                                                           !
 ! +-----+     Cw                  (Station)  PA CL SP SP AT DDD             !
 ! ! M B !                                          CG CD CT                 !
 ! ! u u !                                                                   !
 ! ! l l !                         (Person )  PA CL SP SP    NO              !
 ! ! t l !                                          CG CD    AMA             !
 ! ! i e !                                                                   !
 ! !   t !    (Coin 2)  (AMA Timing)   (Loop Ctl)                            !
 ! ! L i !    COL  RET  CA   ST        Cg Cg Cg                              !
 ! ! e n !              TMG  TMG                  (Kpls key)  (Num pad)      !
 ! ! a   !                             Cd Cd Cd   KP KP KP    1  2  3        !
 ! ! f T !              CA   REC                  TB RT HO                   !
 ! !   r !              CAL  MSG       HD HD HD               4  5  6   ST   !
 ! !   a !                                           KP KP                   !
out - 54"H x 40"W x12"D), with some newer size F, H, and some 3M series-
 ! !     !    RLS                                                            !
 ! !     !        (Display Ctrl)                     KP KP       0           !
 ! +-----+    tim chg CLG CLD SPL                    BK FD          +--------!
 !                min NUM NUM NUM                                   ! Number !
 !                                                                  ! Plate  !
 +---------------------------------------------------------------------------+
```

```text
 +--------------------------------+
 |   Building Your Own Blue Box   |
 +--------------------------------+
 |               By               |
 |          Jester Sluggo         |
 |     Released: Nov. 27, 1986    |
 +--------------------------------+
```

```text
Qty.  Item                 Part No.      Place
---------------------------------------------------
 1  | 4 x 4 Keypad       |             | Digi-Key
 6  | Inverter Chip      | 74C04       |
 32 | Potentiometer      |             |
 1  | 4-16 Converter Chip| 74LS154     |
 1  | 16 Key Decoder     | 74C922      |
 2  | 2207 VCO           | XR2207CP    | Exar Corp.
 3  | .01 uf Capacitor   | 272-1051    | Radio Shack
 5  | .1 uf Capacitor    | 272-135     | Radio Shack
 2  | 1.5K Ohn Resistor  |             | Radio Shack
 2  | 1.0K Ohm Resistor  |             | Radio Shack
 1  | Speaker            |             | From an old Autovon fone.
 1  | 9 Volt Battery     |             | Anywhere
```

```text
    Keypad      Key Assignments   Multiplex Pattern
  +---------+   +-------------+    +------------+
  | 1 2 3 A |   | 1  2  3  4  |    | 1  2  3  A |----Y1=8   X1=3
  | 4 5 6 B |   | 5  6  7  8  |    | 4  5  6  B |----Y2=1   X2=5
  | 7 8 9 C |   | 9  10 11 12 |    | 7  8  9  C |----Y3=2   X3=6
  | * 0 # D |   | 13 14 15 16 |    | *  0  #  D |----Y4=4   X4=7
  +---------+   +-------------+    +------------+
                                     |  |  |  |
                                     X1 X2 X3 X4
```

```text
                     +-------------------+
                     | Schematic Diagram |
                     +-------------------+

             +--------------+            +-------------+
             |  1  2  3  A  |            |  Figure #1  |
             |  4  5  6  B  |            +-------------+
             |  7  8  9  C  |            | Logic Side  |
             |  *  0  #  D  |            +-------------+
             ++-+-+-+-+-+-+-+
              1 | 3 | 5 | 7 |           (VCC)
              | 2 | 4 | 6 | 8           (+5 Volts)    +----+
              | | | | | | | |             [+]         |   _|_
              | | | | | | | |              |          |   X_/GND
           +--+-+-+-+-+-+-+-+----+      +--+----------+---+
           |  2 | 11| 10| 7 |    |      |  14         7   |
   (.01C)  |  | 3 | 4 | 8 | 1  12+------+1                |
   +--||---+5                  13+------+2   (*74C04*)    |
  _|_      |                     |      |                 |
  X_/GND   |     (*74C922*)      |      +-----------------+
     +--||-+6                    |
     |(.1C)|                     |
    _|_    |                     |
    X_/GND |   9  17 16 15 14  18|
           +--+--+--+--+--+---+--+
              |  |  |  |  |   |
             _|_ A  B  C  D   |
          GNDX_/ |  |  |  |  [+] (VCC)      [+] (VCC)
                 |  |  |  |      (+5 volts)  |  (+5 volts)
                 |  |  |  |                  |
          -------+--+--+--+------------------+-----------------
          |      23 22 21 20                 24             18+-+
    +-----+12                                                 | +--+
    |     |                 (*74LS154*)                     19+-+ _|_
   _|_    |                                                   |   X_/
   X_/GND |  1  2  3  4  5  6  7  8  9 10 11 13 14 15 16 17   |   GND
          +--+--+--+--+--+--+--+--+--+-+--+--+--+--+--+--+----+
             1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16
             |  |  |  |  |  |  |  |  | |  |  |  |  |  |  |
                                                         |    (Connects)
                                                         | +---------->
                                +------------------------+ |  (Figure 2)
                                |       +--+       +-------+
                                |       |  |       |
                             +--+-------+--+-------+---+
                             |  3--|>o--4  5--|>o--6   |
                             |   (Invtr.)   (Invtr.)   |
             +---------------+7                        |
            _|_              |        (*74C04*)        |
         GNDX_/   (VCC) [+]--+14                       |
                (+5 volts)   |                         |
                             +-------------------------+



    +-------------+                                  _
    |  Figure #2  |                                 / |
+---+-------------+----+          +----------------+  |
| Tone Generation Side |         _|_               |  | SPKR
+----------------------+      GNDX_/    +---+--+---+  |
                                        |   |       X_|
                                        |   |
                                        |   |  +---------------+
           +-------+                    |   |  |               |
           |      _|_                   |   +--+14             |
           |      X_/GND                |      |  (Repeat of)  |
           |                            |      |    (First)    |
         ----- (.1C)                    |      |   (Circuit)   |
         -----                          |      |               |
           |                            |      | (*XR2207CP*)  |
           |       +-----------------+  |   +--+6              |
           |       |                 |  |   |  |               |
   [+]-----+-------+1              14+--+   |  +---------------+
  (VCC)            |                 |      +--------------------+
 (+9 Volts)   +----+2                |                           |
              |    |               12+---------------------+     |
     (.01C) -----  |                 |                    _|_    |
            -----  |  (*XR2207CP*)   |                    X_/GND |
              |    |                 |       1.5K Ohms           |
              +----+3              11+---+---X/XRx/X/---+--+     |
                   |                 |   |              | _|_    |
                   |                 |   +---X/XRx/X/---+ X_/GND |
                   |                 |       1.0K Ohms           |
                   |               10+----+                      |
     +-------------+6               9+----+---+                  |
     |             |                8+----+   |                  |
     |             |                 |      ----- (.1C)          |
     |             +-----------------+      -----                |
     +---------+                             _|_      +----------+
     |         | Pot.                     GNDX_/ Pot. |          |
     |        X/X/X/X/--+-----------------------X/X/X/X/         |
     |         1400 Hz. |                        1600 Hz.        |
     +---------+        |                             +----------+
     |         | Pot.   |                        Pot. |          |
     |        X/X/X/X/--+----------------+------X/X/X/X/         |
     |         1500 Hz. |                |       900 Hz.         |
     |                  |                |                       |
     |     14 more      |                |       14 More         |
     |   Potentiometers |                |     Potentiometers    |
     |     in this      |                |       in this         |
     |   area left out  |                |     area left out     |
     |   for simplicity |                |     for simplicity    |
     |                  |                |                       |
     |                  |                |                       |
                        |
            (Connects)  |
          <-------------+
            (Figure 1)
```

```text
+----------------+
| Schematic Help |
+----------------+

     This is the Key to the diagrams in the schematic.  I hope that they help
more then they might hurt.

    _|_
    X_/GND   is the Ground symbol

     | |
  ---| |--   is the Capacitor symbol
     | |     (.1C)  stands for a .1 uf Capacitor
             (.01C) stands for a .01 uf Capacitor
     |
   -----
   -----     is another Capacitor symbol
     |

--X/XRx/X/-- is the Resistor symbol (The 1.5K Ohm and 1.0K Ohm
                                     Resistors are at +/- 5% )
---+
   |
  X/X/X/X/-- is the Potentiometer symbol (The frequncies I supplied
                                          above are just examples.)
 --|>o--     is the Inverter symbol
```

```text
*********************************

      The Legion of Doom!
           Presents:

         -------------

  LOD Reference Guide  Vol. I

Outside Loop Distribution Plant

        --------------

Written 12/86       Phucked
Revision III          Agent
                         04

*********************************
```

http://textfiles.com/100/lod-1

---------------------

```text
                 #-----------#
                 | Publisher |
                 +-----------+
                 |    PUB    |
                 '-----------'
                     bind
           tcp://192.168.55.210:5556
                       |
                       |
      .----------------+----------------.
      |                |                |
      |                |                |
   connect           connect          connect
.------------.   .------------.   .------------.
|    SUB     |   |    SUB     |   |    SUB     |
+------------+   +------------+   +------------+
| Subscriber |   | Subscriber |   | Subscriber |
#------------#   #------------#   #------------#
```

https://9vx.org/post/simplistic-diagrams-with-ascii-art/

------

```text
    +--------+   +-------+    +-------+
    |        | --+ ditaa +--> |       |
    |  Text  |   +-------+    |diagram|
    |Document|   |!magic!|    |       |
    |     {d}|   |       |    |       |
    +---+----+   +-------+    +-------+
        :                         ^
        |       Lots of work      |
        +-------------------------+
```

http://ditaa.sourceforge.net/

-------

```text
                                      +----------------+
                                 +--->| PNG Image File |
+-------------+      +-------+   |    +----------------+
| Text Source +----->| dihaa +---+
+-------------+      +-------+   |    +-------------------+
                         ^       +--->| UTF-8 Box Drawing |
Commandline Options -----+            +-------------------+
```

http://hackage.haskell.org/package/dihaa

---

```text
 Association:   ^   Aggregation:    O   Composition:    @   Inheritance:    #
                |                   |                   |                   |
              <-+->               O-+-O               @-+-@               #-+-#
                |                   |                   |                   |
                V                   O                   @                   #
```

```text
 +--------+       +---------------------+ *
 | Client |------>| Component           |<-----------------------------+
 +--------+       +---------------------+                              |
                  | Operation()         |                              |
                  | Add(Component)      |                              |
                  | Remove(Component)   |                              |
                  | GetChild(int)       |                              |
                  +---------------------+                              |
                            #                                          |
                            |                                          |
                     +----------+--------------+                       |
                     |                         |                       |
                  +------+------+   +----------+----------+  children  |
                  | Leaf        |   | Composite           |O-----------+
                  +-------------+   +---------------------+
                  | Operation() |   | Operation()         |
                  +-------------+   | Add(Component)      |
                                    | Remove(Component)   |
                                    | GetChild(int)       |
                                    +---------------------+
```

```text
       A
       |
       |
 <|----+----|>
       |
       |
       _
       V
```

http://wiki.c2.com/?UmlAsciiArt

------

```text
 [Edit Text]
 -- type the address of the graph url into the text field below at the place you want it --
 |Wiki Page Title
 |  +-----------------------------------+
 |  |                                   |
 |  |_http://<urladdressofgraphpicture>_|
 |  |                                   |
 |  +-----------------------------------+
 |__[Save]
 [<-Back]
 [<-Back]
 [F5]

 |    -- multiline page
 |__    -- end of multiline page
    +------- text input area
    |
```

-----------------------------------------------------------------------------------------

```text
                                             ,-.                                                   |
                                             `-'                                                   |
               ,-------------.               /|\                                                   |
               |Bob on       |                |             ,----.                                 |
               |several lines|               / \            |Last|                                 |
               `------+------'              Alice           `-+--'                                 |
                      |        hello          |               |                                    |
                      |---------------------->|               |                                    |
                      |                       |               |                                    |
                      |                       | ,--------------!.                                  |
                      |                       | |this is a note|_\                                 |
                      |                       | `----------------'                                 |
                      |Is it ok               | ,----------------!.                                |
                      |with a message that is | |This other note |_\                               |
                      |on several lines?      | |should work       |                               |
                      |<----------------------| |on several lines  |                               |
                      |                       | `------------------'                               |
                      |                       |               |                                    |
                      |              ======================== |                                    |
====================================== This is a separation =======================================|
                      |              ======================== |                                    |
                      |                       |               |                                    |
                      |            Yes it works!              |                                    |
                      |-------------------------------------->|                                    |
                      |                       |               |                                    |
                      |                       ,------------!. |----.                               |
                      |                       |this is     |_\|    | working in progress           |
                      |                       |another note  ||<---'                               |
                      |                       `--------------'|                                    |
                      |                       |               |- - .                               |
                      |                       |               |    | working in progress           |
                      |                       |               |< - '                               |
                      |                       |               |                                    |
                      |                 done  |               |                                    |
                      |<- - - - - - - - - - - - - - - - - - - |                                    |
                      |                       |               |                                    |
     ______________________________________________________________________                        |
     ! OPT  /  dummy comment                  |               |            !                       |
     !_____/          |                       |               |            !                       |
     !                |                       |               |            !                       |
     !                |               Error   |               |            !                       |
     !                |               On      |               |            !                       |
     !                |               Several |               |            !                       |
     !                |               Line    |               |            !                       |
     !                |-------------------------------------->|            !                       |
     !                |                       |               |            !                       |
     !                |                 None  |               |            !                       |
     !                |<- - - - - - - - - - - - - - - - - - - |            !                       |
     !~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~!                       |
     !                |                       |               |            !                       |
     !                |                 None  |               |            !                       |
     !                |<- - - - - - - - - - - - - - - - - - - |            !                       |
     !                |                       |               |            !                       |
     !                |                 None  |               |            !                       |
     !                |<--------------------------------------|            !                       |
     !~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~!                       |
     ! [other]        |                       |               |            !                       |
     !                |                 None  |               |            !                       |
     !                |<--------------------------------------|            !                       |
     !                |                       |               |            !                       |
     !                |                    ,-------------------!.          !                       |
     !                |                    |This is a long note|_\         !                       |
     !                |                    |over Alice and Last  |         !                       |
     !                |                    `---------------------'         !                       |
     !                |                 None  |               |            !                       |
     !                |<--------------------------------------|            !                       |
     !                |                       |               |            !                       |
     !                |                 None  |               |            !                       |
     !                |<--------------------------------------|            !                       |
     !~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~!                       |
               ,------+------.              Alice           ,-+--.                                 |
               |Bob on       |               ,-.            |Last|                                 |
               |several lines|               `-'            `----'                                 |
               `-------------'               /|\                                                   |
                                              |                                                    |
                                             / \                                                   |
```

```text
+----------+---------+------------------------+----------------+
|   Col1   |  Col2   |          Col3          | Numeric Column |
+----------+---------+------------------------+----------------+
| Value 1  | Value 2 | 123                    | 10.0           |
| Separate | cols    | with a tab or 4 spaces | -2,027.1       |
+----------+---------+------------------------+----------------+
```

+   <https://ozh.github.io/ascii-tables/>
+   <https://www.dokuwiki.org/plugin:a2s>
+   <https://github.com/dhobsd/asciitosvg>
+   <https://metacpan.org/pod/distribution/App-Asciio/lib/App/Asciio.pm>
+   <https://github.com/walsh9/asciibots>
+   <https://www.jianshu.com/p/1256e2643923>
+   <http://wiki.c2.com/?UmlAsciiArt>
+   <http://plantuml.com/ascii-art>

```text
@startuml
participant Bob
actor Alice

Bob -> Alice : hello
Alice -> Bob : Is it ok?
@enduml
```
