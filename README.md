# Linux on Yoga Slim 7i Pro ( Intel )

### Laptop model / Hardware :

- Processors: 8 × 11th Gen Intel® Core™ i7-11370H @ 3.30GHz
- Memory: 16 Gio of RAM
- Graphics Processor: NVIDIA GeForce MX450

### Sofware environment :

- Operating System: Manjaro Linux
- KDE Plasma Version: 5.24.6
- KDE Frameworks Version: 5.96.0
- Qt Version: 5.15.5
- Kernel Version: 5.15.60-1-MANJARO (64-bit)
- Graphics Platform: X11


## Fix screen refresh issue

**Symptoms :** Screen flickering. The display does not seem to be well synchronized. In my case, KDE crash after a few seconds.

**Solution :** Add the following kernel paprameter: 

`i915.enable_psr=0`


## Fix internal keyboard detection issue

**Symptoms :** The laptop keyboard is unresponsive on boot. The keyboard is not detected immediately, it works sometimes after a long period of time.

**Solution :** Add the following parameters to the kernel : 

`i8042.direct i8042.dumbkbd`


## Fix black screen on resume issue ( KDE only )

**Symptoms :** Resume from suspend / hibernate works properly. But when the computer is not in a sleeping state and the screen is turned off, the screen stays black on resume.

**Solution :** Add the following parameter to the kernel : 

`acpi_backlight=vendor`
