1MB cache module for the Biostar MB-8433-UUD mainboard
======================================================

This adapter PCB enables you to install cache using SOJ32 chips, which are still in production. Furthermore,
with a modification of the mainboard, you can install up to 1MB of cache. To support 1MB of cache, you need
to grab A19 from the CPU and route it to the square header pin at the corner of this PCB.

Assembly hints
=========
For U1 to U8 (data RAM): Use 128k x 8 SRAM chips - the layout is not meant for 32k x 8 chips:
Neither does the address line ordering omit the "correct" lines if you install 32k x 8 chips,
nor is there sufficient bypassing at the Vcc pin for SOJ28 chips.

U9 can be a 128k x 8 or 64k x 8 SRAM chip. In case you just need 512K of cache, you can downgrade
U9 to 32k x 8. Sufficient bypassing for a 32k x 8 chip is present at this location. You can *not* downgrade
the data RAM to 64k x 8, though, as the address routing in version 1.1 is not adapted to this scenario.

Make sure to use sufficiently thin pins for plugging into the cache sockets.

Pay attention to the orientation of the memory chips: Pin 1 is always to the edge of the PCB, i.e.
U1-U4 are oriented the other way as U5-U9.