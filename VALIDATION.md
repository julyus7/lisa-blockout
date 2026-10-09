# Recorded validation

## Hardware target and test scope

The program is a native Motorola 68000 application for Apple Lisa 2 hardware
(Lisa 2/5 and Lisa 2/10) running Lisa Office System 3. The released tagged
DC42 image can be written to a native Lisa floppy for use on those machines.
The checks below were performed in LisaEm. No physical Lisa 2 hardware test
is recorded in this release; emulator results are not a physical-hardware
test result.


These are results from the local development sessions in September–October
2026. This publication reused the already tested final files; it did not run
a new native compile or new emulator session.

- Waiting: 900 sampled frames, 300 rapid A/D presses, zero changes to
  the static board and zero missing-border frames.
- Playing repeat: 900 sampled frames, 300 presses, zero changes to the static
  board and zero missing-border frames. The paddle moved, the ball launched,
  bricks disappeared and losing the ball reduced lives.
- An earlier playing run contained two fully white host frames; the repeat
  did not reproduce them. This is not a claim that every host GUI artifact is
  impossible. The release uses changing 16-pixel markers outside the board
  to make LisaEm refresh its cached frame.
- October 6: native LOS duplication into the shared games hard disk succeeded,
  retaining Minesweeper, Amőba and the existing games alongside BlockOut.

## Final release identity

- Floppy: `BlockOut.dc42`, 419,284 bytes, 800 tagged sectors.
- LOS tool number: **240**; volume UID suffix: **D602**.
- Executable: **18944 bytes**, SHA-256 `0ffd4682127c2b4b524c7fcb49056c3a9e7780fde8e4af3dfaf2af614cc4c8e6`.
- Floppy SHA-256: `43b9a4a02d1369a5a5e11d519dd743aa64703466853c6a57c0ffdaa818b447ad`.
- The original 800 native donor tags were retained unchanged; both DC42
  container checksums were recalculated. The three native icon resources
  (`ICON`, `ICON.BACKUP`, lowercase-prefix `icon2`) are identical.

Selected original measurement logs are in `validation/`. You can inspect
the published floppy with `python tools/inspect_image.py`.
