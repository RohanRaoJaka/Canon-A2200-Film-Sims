# Canon-A2200-Film-Sims
11 Film Simulations for Canon Powershot A2200, Built on the existing CHDK files for the model.

- The file you attached is my 4th iteration of my own build. **Replacing DISKBOOT.BIN alone should be enough**, but there are a few conditions.

- **Why one file is enough** the film code, picker, badge and settings are compiled into DISKBOOT.BIN itself. None of it lives in the CHDK folder, so the original CHDK folder works, and so do your existing PS.FI2/boot setup and card.
- **Delete CHDK/CCHDK4.CFG the first time.** My build adds the film settings to the config file. An old CFG from the stock CHDK may not have them, and it can leave the film badge off or the settings at odd values. CHDK writes a new file on its own.
-**Use the CHDK folder from the matching official A2200 100d build if you can.** The modules (.flt files in CHDK/MODULES) are tied to the exact CHDK version. If the official CHDK on your card is a different version from the one my source is based on, a module can fail to load, such as the file browser or scripts. The film features don’t depend on any module. The CHDK folder in my zips is built to match, so use that one if something in the menu misbehaves.
- **The camera must be set up as before** the card is bootable (locked, or started from the Firmware Update menu), the same as for your working CHDK.
You can undo it by putting the original DISKBOOT.BIN back. Nothing is written to the camera itself.

- The Build has 11 Film sims with varying(Customisable) level of Grain to match the original Film stock characters:
- **Kodak Portra 400**
- **Kodak Ektar 100**
- **Kodak Gold 200**
- **Fujifilm Superia 400**
- **Fujifilm Velvia 50**
- **Kodak Ektachrome E100**
- **Cinestill 800T**
- **Kodak Tri-X 400**
- **Ilford HP5 Plus**
- **Kodak T-Max 100**
- **Expired Lomo(Special sim- Vignette)**

The **grain can be adguested on screen in camera when selecting the film sim** and the info shown on screen when shooting can be modified according to preference, similar to how its down on the basic CHDK screen/build.

The **average time** taken for the film sim to cook into the jpeg and for the camera to be 'usable' or ready for the next shot is **4.7 Secs** (brought down from 28 Secs)

Hope this helps, Have Fun and Take Care.

-Ro
