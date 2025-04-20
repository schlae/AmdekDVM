# Amdek DVM Clone

The Amdek DVM allowed RGB digital monitors to be connected to Apple II
computers (which normally output composite video).

This project is a mostly-complete reverse engineered version of this card.

It uses readily-available TTL logic chips, with no programmable devices at
all.

## Cables

To build this card, you will need a video output cable wired as follows. Plug
it into J2 (nearest the edge connector).

| Pin | Description |
|-----|-------------|
| 1   | Red output |
| 2   | Blue output |
| 3   | Green output |
| 4   | Horizontal sync (positive) |
| 5   | Horizontal sync (negative) |
| 6   | Vertical sync (positive) |
| 7   | Vertical sync (negative) |
| 8   | No connect |
| 9   | Ground |
| 10  | No connect |
| 11  | Apple II text - connect to Apple II header K14 pin 2 |
| 12  | Horizontal sync from 80-column card |
| 13  | Video signal from 80-column card |
| 14  | Vertical sync from 80-column card |

You will also need a cable connected to J1 (furthest from the edge connector)
wired to two daughterboards. The daughterboards act as interposers, tapping
various signals on the Apple II motherboard.

* One daughterboard sits on motherboard positions D11, D12, D13, and D14,
hosting the four 74LS161 chips that the Apple II uses to generate the video
timing signals. It intercepts three horizontal counter bits and five vertical
counter bits.

* The other daughterboard sits on motherboard positions B6 and B7, hosting
two 74LS257 chips. This intercepts the eight digital video bits before
they go through encoding to composite video.
