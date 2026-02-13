To use the kernel: Create the bootable USB drive with Rufus (3.21) in ISO mode (DD mode will not work).
An ISO image of TinyCore or CorePlus should work, but be aware that the DOM may only be 128MB. The DOM could be left with only the kernel and boot files, and the extensions stored on a separate USB drive.
Tip: Artificial Intelligence can guide you through the step-by-step process.


#### Replace the USB drive kernel with the custom SX0 kernel (rename).

For example
- The original vmlinuz can be renamed to keep both if desired.
- The custom vmlinuzSx0_11 change to vmlinuz.

- - The original kernel is unable to boot on the S30.

Note: When trying to install SSH (dropbear.tcz) on versions lower than 11, it started asking for dependencies; it might be worth checking this before deciding on the final version to use. An AI recommended using version 7, but I used version 11 because I needed SSH and version 12 seemed unstable.


> Tiny Core on the Sx0

> Source: https://www.parkytowers.me.uk/thin/wyse/s10/tc_kernel.shtml

> As it is a neat thin client that I sometimes press into service I occasionally revisit the Sx0 and build an up-to-date Sx0 specific Tiny Core kernel for it. You will find the builds below. I must admit these haven't been extensively tested, but they do work for me. All you need to do is download the new kernel and add it to the boot directory on the Tiny Core USB pen drive (or whatever). You can either overwrite the existing vmlinuz file or add a new entry to the menu system to let you select the Wyse Sx0 specific kernel
> 
> Notes:
> April 2021, Tiny Core 12.x: Worked out how to remove the i8042 driver removing the need for any specific kernel boot parameters.
> 
> March 2020, Tiny Core 11.x: I found that I couldn't easily remove the i8042 driver. The work-around was to include the kernel boot parameters: i8042.noaux i8042.nokbd. It has since been rebuilt without the i8042 driver.
> 
> May 2019: Tiny Core 10.x & 9.x:I found that the latest versions of Tiny Core using Linux kernels 4.14.10 (v9.x) and 4.19.10 (v10.x) did not run. With v9 the kernel crashed towards the end of the boot process, with v10 it was about half way through. I tracked this down to the i8042 driver which is the legacy PS/2 port driver. The CS5535 and CS5336 do emulate the i8042 but the Sx0 itself does not have any PS/2 ports, so my solution was to remove the driver from the build.
> 
> January 2018, Tiny Core 8.x: The timing problem during CS5536 initialisation appears to have returned so that mod is back in. Also, towards the end of the startup sequence, I'm seeing some delay with messages about floppy drives...repeated a number of times. I don't know why this happens and I haven't spent much time looking into it. It does increase the startup time but otherwise doesn't appear to affect the system.
> 
> February 2017: Tiny Core 7.x: It looks like the CS5336 initialisation timing problem has been fixed.
> 
> May 2015: Tiny Core 5.x: First release. Added CS5335 driver and patched CS5336 driver to fix the timing problem and to enable the IDE interface.
> 
> 

 
