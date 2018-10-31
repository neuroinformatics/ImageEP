# ImageEP - the Elevated Plus Maze test plugin for ImageJ

ImageEP is an ImageJ plugin for the Elevated Plus Maze test.
This program can work with Image J 1.46 or above on Windows 7 or 10 (32-bit).

## How to build

### prepare

#### LabJack U12
Download java inteface for LabJack U12

```shellscript
 $ curl -LO https://labjack.com/sites/default/files/2012/08/LabJackJavaV40.zip 
 $ unzip -p LabJackJavaV40.zip labjack.jar > lib/labjack.jar
```

#### Scion Frame Grabber FG-7
Download java package for Scion Frame Grabber FG-7

```shellscript
 $ curl -LO https://imagej.nih.gov/ij/download/tools/ScionDrivers.zip
 $ unzip -p ScionDrivers.zip ScionImageJDrivers/FG-7/ImageJ/SFG_ImageJ_Update64.exe > SFG_ImageJ_Update64.exe
 $ cabextract -p -F scion.jar SFG_ImageJ_Update64.exe > lib/scion.jar 
```

#### Apple QuickTime 7
Download java interface for Apple QuickTime 7

http://www.apple.com/quicktime/download/

```shellscript
 $ curl -OL https://secure-appldnld.apple.com/QuickTime/031-43075-20160107-C0844134-B3CD-11E5-B1C0-43CA8D551951/QuickTimeInstaller.exe
 $ cabextract -F QuickTime.msi ./QuickTimeInstaller.exe
 $ msiinfo extract ./QuickTime.msi QuickTime.cab > QuickTime.cab
 $ cabextract -p -F QTJava.zip ./QuickTime.cab > lib/QTJava.zip
```

### compile
Build jar package using Maven

```shcellscript
 $ mvn package
 $ file target/behavior_EP121112.jar
```

## Binary distribution

https://cbsn.neuroinf.jp/modules/xoonips/detail.php?id=ImageEP

Distributed by Keizo Takao and Tsuyoshi Miyakawa.

In publication of data that is analyzed with Image EP, cite the following article that describes the method of the elevated plus maze test using this software.

Komada M, Takao K, Miyakawa T."Elevated plus maze for mice." J Vis Exp. 2008 Dec 22;(22). doi:pii: 1088. 10.3791/1088.
http://www.jove.com/video/1088/elevated-plus-maze-for-mice?ID=1088

To get revisions info about Image EP, please see http://www.mouse-phenotype.org/software.html.

For usage instructions, see readme.txt file.
