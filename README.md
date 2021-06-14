
# Arcade Offset (Patched MRA Files)	

This repository will include encrypted patches for titles available on **[jotego's](https://github.com/jotego/)** Capcom Play System cores. In the future, I may continue patching other titles for various cores playable on **[MiSTerFPGA](https://github.com/MiSTer-devel)**. 

These patches are designed to work with encrypted roms from **[mame 0229](https://archive.org/details/mame.0229)** or higher. The intent is to alleviate the need for additional roms in `games/mame`.


## Patched Titles
This section will be expanded at a later date. 

Title           |  Core     | Information
---------------|-------------|----------
Super Street Fighter II: The New Legacy [Beta 0.4]   | CPS-2        | [**View Readme**](https://github.com/atrac17/CPS2_MRA_Patches/blob/main/Readme/Super%20Street%20Fighter%20II%20The%20New%20Legacy%20%5BBeta%200.4%5D.md)
Super Street Fighter II: The New Legacy [Beta 0.5] | CPS-2   | [**View Readme**](https://github.com/atrac17/CPS2_MRA_Patches/blob/main/Readme/Super%20Street%20Fighter%20II%20The%20New%20Legacy%20%5BBeta%200.5%5D.md)
Progear Red Label Halfway to Hell (Japan 160117) | CPS-2         | [**View Readme**](https://github.com/atrac17/CPS2_MRA_Patches/blob/main/Readme/Progear%20Red%20Label%20Halfway%20to%20Hell%20%28Japan%20160117%29.md)


# Patched MRA Format

While most of this should be self explanitory, this is the provided layout used. Patches are applied to the loaded roms from `rom index="0"`. Addional information may be provided from "soft dip" settings in the eeprom or nvm (nvram) save file. The hex is taken from "soft dip" settings and appllied to `rom index="02"`.


        <misterromdescription>
            <about author=/>
            <name></name>
            <setname></setname>
            <rbf>core</rbf>
            <mameversion></mameversion>
            <year></year>
            <manufacturer></manufacturer>
            <players></players>
            <joystick></joystick>
            <rotation></rotation>
            <region></region>
            <platform></platform>
            <category></category>
            <catver></catver>
            <mraauthor></mraauthor>
            <mratimestamp></mratimestamp>
            <rom index="0" zip="rom1.zip|rom2.zip" type="merged" md5="None" address="0x30000000">
                <part>
                Example encryption / configuration
                </part>
                <!-- example rom - starts at 0x0 -->
                <part name="example.00" crc="12345678"/>
                <!-- example - starts at 0x14 -->
                <part name="example.01" crc="91011121"/>
                <!-- Total 0x2C42014 bytes - XXXXX kBytes -->
                <patch 0x0>"hex information"</patch>
            </rom>
            <rom index="1">
                <part>00=horizontal / 01=vertical / 02= 4-Way Joystick</part>
            </rom>
            <rom index="2">
                <part>"soft dip" information</part>
            </rom>
            <nvram index="2" size="128"/>
            <buttons names="B1,B2,B3,B4,B5,B6,Start,Coin,Core Credits" default="Y,X,B,A,L,R,Select,Start,-" count="6"/>
        </misterromdescription>

