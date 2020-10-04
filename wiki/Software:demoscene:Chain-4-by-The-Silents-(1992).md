<img src="images/Demoscene:Chain-4-by-The-Silents-(1992).gif" width="640" height="400"><br>
[[1992|Guide:MS‐DOS:demoscene:1992]] demoscene entry.

# Demo description

Basic 3D object demo with music. It uses a flawed VGA unchained "mode X" implementation.

# Recommended DOSBox-X configuration

    [dosbox]
    machine=svga_et4000
    memsize=1
    
    [cpu]
    cycles=12000
    core=normal
    cputype=386
    
    [sblaster]
    sbtype=sbpro2
    sbbase=220
    dma=1
    irq=7

Demo uses VGA unchained "[Mode X](http://en.wikipedia.org/wiki/Mode_X)" but forgets to program the [byte/word/dword](http://www.osdever.net/FreeVGA/vga/crtcreg.htm#14) mode of the CRTC for the [Mode X](http://en.wikipedia.org/wiki/Mode_X) rendering to display, which will cause it to misrender if VGA emulation other than [Tseng ET4000](http://en.wikipedia.org/wiki/Tseng_Labs_ET4000) is used. [Mode X appears to be used for fast polygon filling and page flipping](http://en.wikipedia.org/wiki/Mode_X). Sound Blaster support assumes IRQ 7, demo will not produce sound otherwise.

[[images/Demoscene:Chain-4-by-The-Silents-(1992)-et4000-vs-vga.png]]

A cycles count between 5000 and 12000 is recommended to avoid flickering and visible redraw. If the cycles count is too high, the audio clip played during the opening logo may skip over the first 1-2 seconds.

# Further testing

I would like to run this demo on actual hardware to see if it has problems on non-ET4000 SVGA cards in the same way that it fails to work under DOSBox.

## Test results

I have tested the demo on the following hardware so far. "OK" means the demo renders correctly (as shown in machine=svga_et4000 screenshot). "Failed" means the demo rendered incorrectly (as shown in machine=vgaonly screenshot) where for every group of 16 pixels the first 4 are read. Result field will contain more descriptive text in the event anything else happens.

|Mfg.|Card/Hardware|Result|
|----|-------------|------|
|Chips & Tech|CT65550|Failed|
|Chips & Tech|CT65554|Failed|
|Cirrus Labs|CL-GD7543|Failed|

# More information

[More information (Pouet)](http://www.pouet.net/prod.php?which=8735)