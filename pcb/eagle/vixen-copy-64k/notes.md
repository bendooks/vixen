This is a version of the 16K Vixen that uses 64Kx4 DRAM parts to provide a full 35K memory map (not quite 64K ok).

To do this we have the issue of A14 and A15 not being provided directly by the expansion port, so these need to be re-created somehow. The A14 is probably the and of /BLK2 and /BLK3 and A15 could just equate to /BLK5. This combination should work to give the DRAM the necessary address lines.

We do not care about the mapping of address lines to DRAM addresses as we are the only ones generating them and the 64K parts are 8x8 addressed so there are no holes in the address mapping to worry about (see 16KiB version)

## Memory map

- /BLK1 is 0x2000-0x3fff (8KiB)
- /BLK2 is 0x4000-0x5fff (8KiB)
- /BLK3 is 0x6000-0x7fff (8KiB)
- /BLK5 is 0xA000.0xBFFF (8KiB)
- /RAM1../RAM3 are all in hte 0x400.0xfff lines

## Notes

- IA14/A8 swapped for easier routing
