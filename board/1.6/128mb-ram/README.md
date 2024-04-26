 Be warned: this is more difficult that a 1.0 - 1.5 RAM upgrade

Tutorial

Required items

    Everything mentioned in the 1.0 - 1.5 RAM upgrade tutorial: https://consolemods.org/wiki/Xbox:RAM_Upgrade
    4x 90mm long mod-wire. I used enamelled wire from a transformer.
    ~8 hours spare time :)

Step 1: flash the modified XBlast OS BIOS

XBlast OS (as a BIOS) is super helpful in doing this install correctly. It will boot with any number of extra RAM chips and includes a test for the additional RAM. XBlast OS will not show the 128MB test option on a v1.6 Xbox, so I've gone ahead and rebuilt it from source with that check removed.

xblast_os_v0.60.bin 256 kB · 22 downloads

Alternative Download Link: https://mega.nz/file/eeAwTZKQ#aaFcbACj3htA6cEtKwoiy1L7uK93o4YwUSqkGBEsUz8

If you don't trust my build, this is the line of code that needs removing:

image.png.f1e50e5fdb7ca9d22dfdf1320dba1a62.png

At this point, I suggest booting it up and running the test. The test is under Settings > Tools > 128MB RAM test

Step 2: Remove the motherboard from the Xbox

Step 3: Place the new RAM chip on top of an existing chip

You'll want to solder down the corner pins first to get a good mechanical bond and so that you can adjust the alignment. I do this by pushing down pins 30 and 31 and soldering them down to the chip below. Then I check the alignment of the rest of the pins. If it's bad, then the chip can be nudged into position while reflowing the two pins. Then solder the two pins opposite.

Step 4: Push down the rest of the pins

Except pin 28! That is the chip select pin and it is unique for each RAM chip. Leave this pin floating in the air and don't solder it yet. Pin 30 is marked on the PCB.

The pins come in a kind of ‾‾\__ shape. When you push them down, the whole pin will rotate around this end -> ‾‾\__ . I like to also push down the tail ‾‾\__ <- of the pin to get more contact with the chip below.

Step 5: Start soldering all the pins

Very little extra solder is required. Use lots of flux. I like the tacky flux that usually comes in syringes. I also like the drag-soldering method. If there's any excess solder, you will get shorts between pins and this extra solder can be wicked away.

The new pins won't naturally touch the pins below even after pushing them down.

Step 6: Check for shorts and missing connections

For the first pass, I like to go in with a microscope and nudge each pin (of the new chip) with a cold soldering iron tip. If the pin moves easily, it is not soldered. Also check for shorts at the same time.

If you have the patience (and want it to work first try without frying your Xbox), check for shorts and continuity with a multimeter. I skipped this the first time and got bitten! Best to clean the pins and pads with IPA before checking with the multimeter.

Step 7: Add the chip-select wire

First, figure out which bank you are adding:

image.thumb.png.654086b9e06e27d448f74af1e506dd77.png\

Then, find the chip-select solder point:

image.thumb.png.1a3a8dec4c47118b97162291ee98a3ad.png

Bank 1 CS is left of the label for C4P10

Bank 2 CS is between the labels for C4R12 and C4R13

Bank 3 CS is left and above the label for C4P21

Bank 4 CS is between and above the labels C4R1 and C3R1

For banks 2 and 3, the chip-select wire can go through the hole to the left of the GPU. For bank 2, 90mm may be too short, so check the wire length and cut it as short as possible. I removed the GPU heatsink to access this hole.

At this point, it should look something like this:

image.thumb.png.21d9dfd789f8cbe7cbe91bc1649995ec.png

Step 8: Reassemble and test in XBlast

For a quick test, I don't bother with adding the fan, GPU heatsink, HDD, or DVD drive.

The test in XBlast should look like what I first posted on reddit:

If the Xbox reboots twice and FRAGs, check the bios selection (if you have one available). A normal BIOS will not accept between 1 and 3 extra RAM chips.

If the Xbox reboots three of four times (and it's faster than a normal FRAG sequence) check for shorts. This happened to me.

Step 9: Repeat for the other 3 chips

The first one is the hardest.

image.thumb.png.97200de00acb9fb31d9303ffcbdabdc9.png

Step 10: Reflash with your favourite BIOS

Some 1.6 BIOSs won't support 128MB. Cerbios and X3 BIOS are tested and works just fine.

Credits for tutorial goes to Prehistoricman on the ogxbox forums.





image.png

image.png

image.png 
