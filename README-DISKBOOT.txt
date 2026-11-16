chdk-film for Canon PowerShot A2200 (firmware 1.00D)  -  TEST BUILD 2  (speed)
==============================================================================

What changed
  Same film looks, same grain, same colours as test 1: the photos should come out
  IDENTICAL to test 1. Only the time to save a shot changes.

  Why test 1 was slow: the CHDK build compiles with "no inlining" and "optimise for
  size", so every tiny helper in the per-pixel loop became a real function call (about
  a dozen per pixel) and the raw data was read one byte at a time. Test 2 rewrites that
  loop: no calls, 16-bit reads/writes, and white balance, black level and clamping
  folded into the look-up tables. Checked by running the compiled ARM code in an
  emulator: output is bit-for-bit the same as test 1 across 144 look/grain/vignette
  combinations, using about 2.5x fewer instructions per pixel (A) and about 3.5x
  fewer (B). That is the work done, not seconds: I cannot time a real A2200 from here.

Two versions, because I cannot tell which the camera prefers
  DISKBOOT_A_THUMB.BIN   compact code (like the rest of CHDK)
  DISKBOOT_B_ARM.BIN     fewer instructions but bigger code
  Which is faster depends on how the camera's CPU caches code, so please try both.

Install (nothing else to copy: the CHDK folder and settings from test 1 stay as they are)
  1. On the card, delete DISKBOOT.BIN.
  2. Copy DISKBOOT_A_THUMB.BIN to the card and rename it to  DISKBOOT.BIN
  3. Start CHDK the usual way. Shoot. Then repeat with DISKBOOT_B_ARM.BIN.

The develop time is now shown for you
  After each shot, the badge at the top of the shooting screen shows how long it took,
  for example  LOMO G7 7.2s . It appears once the camera is back to the shooting screen
  and you are not half-pressing the shutter.

Test list - please send back
  For BOTH versions, with the same scene and the same settings, shoot Portra 400,
  Expired Lomo and Tri-X 400 and note the time on the badge for each:
        version A:  Portra ___ s   Lomo ___ s   Tri-X ___ s
        version B:  Portra ___ s   Lomo ___ s   Tri-X ___ s
  Also tell me:
   - Does the look match test 1 (same colours, grain, vignette)? It should.
   - Any freeze, reboot or odd photo? (If B misbehaves, A is the safe one.)
   - Roughly what was test 1's time for Portra, for comparison?

If something goes wrong: power off, remove the card or unlock it, and the camera is
stock again. To go back to test 1, put its DISKBOOT.BIN back on the card.

SHA-256 (first 16 hex):  A 4c59e9825011d67f   B b4902595fdf6c7c7
