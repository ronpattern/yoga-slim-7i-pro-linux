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

### Fix screen refresh issue

**Symptom :** Screen flickering. The display refresh does not seem to be synchronized. In my case, KDE crash after a few seconds.

**Solution :** Add the following kernel paprameter: 

`i915.enable_psr=0`
