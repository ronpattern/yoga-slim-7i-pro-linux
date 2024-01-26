# Manjaro on Yoga Slim 7i Pro ( 14IHU5 O )

### Laptop model / Hardware :

- Processors: 8 × 11th Gen Intel® Core™ i7-11370H @ 3.30GHz
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


## ~~Fix black screen on resume issue ( KDE only )~~ ( Fixed )

**Symptoms :** Resume from suspend / hibernate works properly. But when the computer is not in sleep mode and the screen is turned off, the screen stays black on resume.

**~~Solution~~ :** ~~Add the following parameter to the kernel~~ :

`acpi_backlight=vendor`

**UPDATE :** This solution has a drawback. The screen brightness adjustment no longer works after that. The brightness still can be changed manually :

`sudo nano /sys/class/backlight/intel_backlight/brightness`

**New temporary solution :**

`System Settings > Power Management > Energy Saving > Buttons Event Handling > When Power Button pressed > Turn Off Screen`


## Fix audio issue

With recent kernel, sound should work out of the box. But if its not the case and the speaker device is not detected, be sure to have your kernel **version >= 5.14** and the following packages installed :

 `alsa-firmware, sof-firmware, alsa-ucm-conf, alsa-tools` 


 ## Fix choppy animations / video sluttering on KDE ( NVidia )
 
 1) Enable NVidia persistent mode
 
 `sudo systemctl enable nvidia-persistenced.service`
 
 2) Change compositor latency setting
 
 `Plasma settings > Display > Compositor > Latency > Force smoothest animations`
 
 3) Enable triple buffuring
 
**N.B :** It is recommended to prefer intel to nvividia, because there is none of these symptoms, the battery will have a better autonomy and the temperature will be stable. To be able to switch between the integrated and the dedicated graphic card, install **optimus-manager**.

