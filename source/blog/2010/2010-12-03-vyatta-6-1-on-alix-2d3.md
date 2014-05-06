---
status: publish
published: true
title: Vyatta 6.1 on Alix 2D3.
date: 2010-12-03 04:15:28
categories:
- Linux
tags:
- ALIX
- Linux
- Vyatta
- dmesg
---
手こずるかなと思いきやあっさり。ethも3つ認識されています。

VMware Fuisonを使いました。USBリーダにCFを差しVMwareに接続。インストールの際sdbとして認識され、sdbを指定するのみ。Grubも同じく。あと聞かれたのはパスワードぐらいだったかな。以下dmesg.

Welcome to Vyatta - vyatta ttyS0

vyatta login: vyatta
Password:
Last login: Thu Dec 2 18:43:54 GMT 2010 on ttyS0
Linux vyatta 2.6.32-1-586-vyatta #1 SMP Thu Sep 23 12:42:33 PDT 2010 i586
Welcome to Vyatta.
This system is open-source software. The exact distribution terms for
each module comprising the full system are described in the individual
files in /usr/share/doc/*/copyright.
vyatta@vyatta:~$ dmesg
[ 0.000000] Linux version 2.6.32-1-586-vyatta (root@vyatta) (gcc version 4.3.2 (Debian 4.3.2-1.1) ) #1 SMP Thu Sep 23 12:42:33 PDT 2010
[ 0.000000] KERNEL supported cpus:
[ 0.000000] Intel GenuineIntel
[ 0.000000] AMD AuthenticAMD
[ 0.000000] NSC Geode by NSC
[ 0.000000] Cyrix CyrixInstead
[ 0.000000] Centaur CentaurHauls
[ 0.000000] Transmeta GenuineTMx86
[ 0.000000] Transmeta TransmetaCPU
[ 0.000000] UMC UMC UMC UMC
[ 0.000000] BIOS-provided physical RAM map:
[ 0.000000] BIOS-e820: 0000000000000000 - 00000000000a0000 (usable)
[ 0.000000] BIOS-e820: 00000000000f0000 - 0000000000100000 (reserved)
[ 0.000000] BIOS-e820: 0000000000100000 - 0000000010000000 (usable)
[ 0.000000] BIOS-e820: 00000000fff00000 - 0000000100000000 (reserved)
[ 0.000000] DMI not present or invalid.
[ 0.000000] last_pfn = 0x10000 max_arch_pfn = 0x100000
[ 0.000000] initial memory mapped : 0 - 01800000
[ 0.000000] init_memory_mapping: 0000000000000000-0000000010000000
[ 0.000000] 0000000000 - 0000400000 page 4k
[ 0.000000] 0000400000 - 0010000000 page 2M
[ 0.000000] kernel direct mapping tables up to 10000000 @ 7000-c000
[ 0.000000] RAMDISK: 0b77f000 - 0c03f30c
[ 0.000000] ACPI Error: A valid RSDP was not found (20090903/tbxfroot-219)
[ 0.000000] 0MB HIGHMEM available.
[ 0.000000] 256MB LOWMEM available.
[ 0.000000] mapped low ram: 0 - 10000000
[ 0.000000] low ram: 0 - 10000000
[ 0.000000] node 0 low ram: 00000000 - 10000000
[ 0.000000] node 0 bootmap 00002000 - 00004000
[ 0.000000] (9 early reservations) ==&gt; bootmem [0000000000 - 0010000000]
[ 0.000000] #0 [0000000000 - 0000001000] BIOS data page ==&gt; [0000000000 - 0000001000]
[ 0.000000] #1 [0000001000 - 0000002000] EX TRAMPOLINE ==&gt; [0000001000 - 0000002000]
[ 0.000000] #2 [0000006000 - 0000007000] TRAMPOLINE ==&gt; [0000006000 - 0000007000]
[ 0.000000] #3 [0001000000 - 0001428d04] TEXT DATA BSS ==&gt; [0001000000 - 0001428d04]
[ 0.000000] #4 [000b77f000 - 000c03f30c] RAMDISK ==&gt; [000b77f000 - 000c03f30c]
[ 0.000000] #5 [000009f000 - 0000100000] BIOS reserved ==&gt; [000009f000 - 0000100000]
[ 0.000000] #6 [0001429000 - 000142f000] BRK ==&gt; [0001429000 - 000142f000]
[ 0.000000] #7 [0000007000 - 0000008000] PGTABLE ==&gt; [0000007000 - 0000008000]
[ 0.000000] #8 [0000002000 - 0000004000] BOOTMAP ==&gt; [0000002000 - 0000004000]
[ 0.000000] Zone PFN ranges:
[ 0.000000] DMA 0x00000000 -&gt; 0x00001000
[ 0.000000] Normal 0x00001000 -&gt; 0x00010000
[ 0.000000] HighMem 0x00010000 -&gt; 0x00010000
[ 0.000000] Movable zone start PFN for each node
[ 0.000000] early_node_map[2] active PFN ranges
[ 0.000000] 0: 0x00000000 -&gt; 0x000000a0
[ 0.000000] 0: 0x00000100 -&gt; 0x00010000
[ 0.000000] On node 0 totalpages: 65440
[ 0.000000] free_area_init_node: node 0, pgdat c1344700, node_mem_map c1430000
[ 0.000000] DMA zone: 32 pages used for memmap
[ 0.000000] DMA zone: 0 pages reserved
[ 0.000000] DMA zone: 3968 pages, LIFO batch:0
[ 0.000000] Normal zone: 480 pages used for memmap
[ 0.000000] Normal zone: 60960 pages, LIFO batch:15
[ 0.000000] Using APIC driver default
[ 0.000000] SFI: Simple Firmware Interface v0.7 http://simplefirmware.org
[ 0.000000] SMP: Allowing 1 CPUs, 0 hotplug CPUs
[ 0.000000] No local APIC present or hardware disabled
[ 0.000000] APIC: disable apic facility
[ 0.000000] nr_irqs_gsi: 16
[ 0.000000] PM: Registered nosave memory: 00000000000a0000 - 00000000000f0000
[ 0.000000] PM: Registered nosave memory: 00000000000f0000 - 0000000000100000
[ 0.000000] Allocating PCI resources starting at 10000000 (gap: 10000000:eff00000)
[ 0.000000] NR_CPUS:32 nr_cpumask_bits:32 nr_cpu_ids:1 nr_node_ids:1
[ 0.000000] PERCPU: Embedded 13 pages/cpu @c1800000 s32536 r0 d20712 u4194304
[ 0.000000] pcpu-alloc: s32536 r0 d20712 u4194304 alloc=1*4194304
[ 0.000000] pcpu-alloc: [0] 0
[ 0.000000] Built 1 zonelists in Zone order, mobility grouping on. Total pages: 64928
[ 0.000000] Kernel command line: BOOT_IMAGE=/boot/vmlinuz quiet root=UUID=0eb9909c-8a87-426e-a816-bb0013160617 ro console=ttyS0,9600 console=tty0
[ 0.000000] PID hash table entries: 1024 (order: 0, 4096 bytes)
[ 0.000000] Dentry cache hash table entries: 32768 (order: 5, 131072 bytes)
[ 0.000000] Inode-cache hash table entries: 16384 (order: 4, 65536 bytes)
[ 0.000000] Initializing CPU#0
[ 0.000000] Initializing HighMem for node 0 (00000000:00000000)
[ 0.000000] Memory: 245844k/262144k available (2308k kernel code, 15596k reserved, 1085k data, 344k init, 0k highmem)
[ 0.000000] virtual kernel memory layout:
[ 0.000000] fixmap : 0xffd56000 - 0xfffff000 (2724 kB)
[ 0.000000] pkmap : 0xff400000 - 0xff800000 (4096 kB)
[ 0.000000] vmalloc : 0xd0800000 - 0xff3fe000 ( 747 MB)
[ 0.000000] lowmem : 0xc0000000 - 0xd0000000 ( 256 MB)
[ 0.000000] .init : 0xc1351000 - 0xc13a7000 ( 344 kB)
[ 0.000000] .data : 0xc1241154 - 0xc1350868 (1085 kB)
[ 0.000000] .text : 0xc1000000 - 0xc1241154 (2308 kB)
[ 0.000000] Checking if this processor honours the WP bit even in supervisor mode...Ok.
[ 0.000000] SLUB: Genslabs=13, HWalign=32, Order=0-3, MinObjects=0, CPUs=1, Nodes=1
[ 0.000000] Hierarchical RCU implementation.
[ 0.000000] NR_IRQS:2304 nr_irqs:256
[ 0.000000] Console: colour dummy device 80x25
[ 0.000000] console [tty0] enabled
[ 0.000000] console [ttyS0] enabled
[ 0.000000] Fast TSC calibration using PIT
[ 0.000000] Detected 497.988 MHz processor.
[ 0.004009] Calibrating delay loop (skipped), value calculated using timer frequency.. 995.97 BogoMIPS (lpj=1991952)
[ 0.004093] Security Framework initialized
[ 0.008024] SELinux: Disabled at boot.
[ 0.008058] Mount-cache hash table entries: 512
[ 0.008509] CPU: L1 I Cache: 64K (32 bytes/line), D cache 64K (32 bytes/line)
[ 0.008530] CPU: L2 Cache: 128K (32 bytes/line)
[ 0.008567] Performance Events: no PMU driver, software events only.
[ 0.008591] Checking 'hlt' instruction... OK.
[ 0.024138] SMP alternatives: switching to UP code
[ 0.033844] Freeing SMP alternatives: 19k freed
[ 0.034012] Enabling APIC mode: Flat. Using 0 I/O APICs
[ 0.034029] weird, boot CPU (#0) not listed by the BIOS.
[ 0.034042] SMP motherboard not detected.
[ 0.034056] Local APIC not detected. Using dummy APIC emulation.
[ 0.034071] SMP disabled
[ 0.034411] Brought up 1 CPUs
[ 0.034429] Total of 1 processors activated (995.97 BogoMIPS).
[ 0.034469] CPU0 attaching NULL sched-domain.
[ 0.036681] regulator: core version 0.5
[ 0.037053] NET: Registered protocol family 16
[ 0.039224] PCI: PCI BIOS revision 2.10 entry at 0xfced9, last bus=0
[ 0.039243] PCI: Using configuration type 1 for base access
[ 0.046366] bio: create slab &lt;bio-0&gt; at 0
[ 0.046716] ACPI: Interpreter disabled.
[ 0.047199] vgaarb: loaded
[ 0.048488] PCI: Probing PCI hardware
[ 0.048504] PCI: Probing PCI hardware (bus 00)
[ 0.048771] pci 0000:00:01.0: reg 10 io port: [0xac1c-0xac1f]
[ 0.048958] pci 0000:00:01.2: reg 10 32bit mmio: [0xefff4000-0xefff7fff]
[ 0.049153] pci 0000:00:09.0: reg 10 io port: [0x1000-0x10ff]
[ 0.049181] pci 0000:00:09.0: reg 14 32bit mmio: [0xe0000000-0xe00000ff]
[ 0.049254] pci 0000:00:09.0: supports D1 D2
[ 0.049274] pci 0000:00:09.0: PME# supported from D0 D1 D2 D3hot D3cold
[ 0.049296] pci 0000:00:09.0: PME# disabled
[ 0.049367] pci 0000:00:0a.0: reg 10 io port: [0x1400-0x14ff]
[ 0.049395] pci 0000:00:0a.0: reg 14 32bit mmio: [0xe0040000-0xe00400ff]
[ 0.049466] pci 0000:00:0a.0: supports D1 D2
[ 0.049485] pci 0000:00:0a.0: PME# supported from D0 D1 D2 D3hot D3cold
[ 0.049506] pci 0000:00:0a.0: PME# disabled
[ 0.049578] pci 0000:00:0b.0: reg 10 io port: [0x1800-0x18ff]
[ 0.049606] pci 0000:00:0b.0: reg 14 32bit mmio: [0xe0080000-0xe00800ff]
[ 0.049676] pci 0000:00:0b.0: supports D1 D2
[ 0.049695] pci 0000:00:0b.0: PME# supported from D0 D1 D2 D3hot D3cold
[ 0.049716] pci 0000:00:0b.0: PME# disabled
[ 0.049833] pci 0000:00:0f.0: reg 10 io port: [0x6000-0x6007]
[ 0.049898] pci 0000:00:0f.0: reg 14 io port: [0x6100-0x61ff]
[ 0.049963] pci 0000:00:0f.0: reg 18 io port: [0x6200-0x623f]
[ 0.050041] pci 0000:00:0f.0: reg 20 io port: [0x9d00-0x9d7f]
[ 0.050107] pci 0000:00:0f.0: reg 24 io port: [0x9c00-0x9c3f]
[ 0.050302] pci 0000:00:0f.2: reg 20 io port: [0xff00-0xff0f]
[ 0.050495] pci 0000:00:0f.4: reg 10 32bit mmio: [0xefffe000-0xefffefff]
[ 0.050656] pci 0000:00:0f.4: PME# supported from D0 D3hot D3cold
[ 0.050681] pci 0000:00:0f.4: PME# disabled
[ 0.050826] pci 0000:00:0f.5: reg 10 32bit mmio: [0xefffd000-0xefffdfff]
[ 0.050992] pci 0000:00:0f.5: PME# supported from D0 D3hot D3cold
[ 0.051017] pci 0000:00:0f.5: PME# disabled
[ 0.054537] Switching to clocksource tsc
[ 0.058092] pnp: PnP ACPI: disabled
[ 0.058109] PnPBIOS: Scanning system for PnP BIOS support...
[ 0.058335] PnPBIOS: PnP BIOS support was not detected.
[ 0.060419] pci_bus 0000:00: resource 0 io: [0x00-0xffff]
[ 0.060443] pci_bus 0000:00: resource 1 mem: [0x000000-0xffffffff]
[ 0.060615] NET: Registered protocol family 2
[ 0.061160] IP route cache hash table entries: 2048 (order: 1, 8192 bytes)
[ 0.063134] TCP established hash table entries: 8192 (order: 4, 65536 bytes)
[ 0.063349] TCP bind hash table entries: 8192 (order: 4, 65536 bytes)
[ 0.063566] TCP: Hash tables configured (established 8192 bind 8192)
[ 0.063583] TCP reno registered
[ 0.063909] NET: Registered protocol family 1
[ 0.064296] Trying to unpack rootfs image as initramfs...
[ 2.292890] Freeing initrd memory: 8960k freed
[ 2.302140] platform rtc_cmos: registered platform RTC device (no PNP device found)
[ 2.303925] audit: initializing netlink socket (disabled)
[ 2.303977] type=2000 audit(1291315325.301:1): initialized
[ 2.321879] Registering unionfs 2.5.4 (for 2.6.32.9)
[ 2.322605] msgmni has been set to 498
[ 2.323778] alg: No test for stdrng (krng)
[ 2.324032] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 253)
[ 2.324053] io scheduler noop registered
[ 2.324067] io scheduler anticipatory registered
[ 2.324084] io scheduler deadline registered
[ 2.324452] io scheduler cfq registered (default)
[ 2.326448] isapnp: Scanning for PnP cards...
[ 2.681930] isapnp: No Plug &amp; Play device found
[ 2.697243] Serial: 8250/16550 driver, 4 ports, IRQ sharing enabled
[ 2.697566] serial8250: ttyS0 at I/O 0x3f8 (irq = 4) is a NS16550A
[ 2.698058] serial8250: ttyS1 at I/O 0x2f8 (irq = 3) is a NS16550A
[ 2.709139] brd: module loaded
[ 2.709569] Fixed MDIO Bus: probed
[ 2.710610] PNP: No PS/2 controller found. Probing ports directly.
[ 2.711496] i8042.c: No controller found.
[ 2.759966] mice: PS/2 mouse device common for all mice
[ 2.760624] rtc_cmos rtc_cmos: rtc core: registered rtc_cmos as rtc0
[ 2.760681] rtc0: alarms up to one day, 114 bytes nvram
[ 2.760841] cpuidle: using governor ladder
[ 2.760856] cpuidle: using governor menu
[ 2.760879] No iBFT detected.
[ 2.763469] TCP cubic registered
[ 2.763486] NET: Registered protocol family 17
[ 2.763758] Using IPI No-Shortcut mode
[ 2.764431] registered taskstats version 1
[ 2.765151] rtc_cmos rtc_cmos: setting system clock to 2010-12-02 18:42:06 UTC (1291315326)
[ 2.765347] Freeing unused kernel memory: 344k freed
[ 2.766176] Write protecting the kernel text: 2312k
[ 2.766325] Write protecting the kernel read-only data: 872k
[ 5.398412] SCSI subsystem initialized
[ 5.580351] via-rhine.c:v1.10-LK1.4.3 2007-03-06 Written by Donald Becker
[ 5.580444] via-rhine 0000:00:09.0: setting latency timer to 64
[ 5.587436] eth0: VIA Rhine III (Management Adapter) at 0x11000, 00:0d:b9:17:9a:ac, IRQ 10.
[ 5.588175] eth0: MII PHY found at address 1, status 0x7849 advertising 05e1 Link 0000.
[ 5.588247] via-rhine 0000:00:0a.0: setting latency timer to 64
[ 5.595241] eth1: VIA Rhine III (Management Adapter) at 0x11400, 00:0d:b9:17:9a:ad, IRQ 11.
[ 5.595979] eth1: MII PHY found at address 1, status 0x7849 advertising 05e1 Link 0000.
[ 5.596043] via-rhine 0000:00:0b.0: setting latency timer to 64
[ 5.603140] eth2: VIA Rhine III (Management Adapter) at 0x11800, 00:0d:b9:17:9a:ae, IRQ 15.
[ 5.603877] eth2: MII PHY found at address 1, status 0x7849 advertising 05e1 Link 0000.
[ 5.634171] usbcore: registered new interface driver usbfs
[ 5.634325] usbcore: registered new interface driver hub
[ 5.639060] usbcore: registered new device driver usb
[ 5.658576] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
[ 5.658718] ohci_hcd 0000:00:0f.4: setting latency timer to 64
[ 5.658742] ohci_hcd 0000:00:0f.4: OHCI Host Controller
[ 5.658848] ohci_hcd 0000:00:0f.4: new USB bus registered, assigned bus number 1
[ 5.658919] ohci_hcd 0000:00:0f.4: irq 12, io mem 0xefffe000
[ 5.683054] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
[ 5.683075] Warning! ehci_hcd should always be loaded before uhci_hcd and ohci_hcd, not after
[ 5.910493] usb usb1: New USB device found, idVendor=1d6b, idProduct=0001
[ 5.910520] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
[ 5.910543] usb usb1: Product: OHCI Host Controller
[ 5.910562] usb usb1: Manufacturer: Linux 2.6.32-1-586-vyatta ohci_hcd
[ 5.910583] usb usb1: SerialNumber: 0000:00:0f.4
[ 5.910954] usb usb1: configuration #1 chosen from 1 choice
[ 5.911149] hub 1-0:1.0: USB hub found
[ 5.911195] hub 1-0:1.0: 4 ports detected
[ 5.914789] ehci_hcd 0000:00:0f.5: setting latency timer to 64
[ 5.914816] ehci_hcd 0000:00:0f.5: EHCI Host Controller
[ 5.914872] ehci_hcd 0000:00:0f.5: new USB bus registered, assigned bus number 2
[ 5.938555] ehci_hcd 0000:00:0f.5: irq 12, io mem 0xefffd000
[ 5.950457] ehci_hcd 0000:00:0f.5: USB 2.0 started, EHCI 1.00
[ 5.950572] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002
[ 5.950597] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
[ 5.950619] usb usb2: Product: EHCI Host Controller
[ 5.950639] usb usb2: Manufacturer: Linux 2.6.32-1-586-vyatta ehci_hcd
[ 5.950660] usb usb2: SerialNumber: 0000:00:0f.5
[ 5.951041] usb usb2: configuration #1 chosen from 1 choice
[ 5.951242] hub 2-0:1.0: USB hub found
[ 5.951288] hub 2-0:1.0: 4 ports detected
[ 6.161960] libata version 3.00 loaded.
[ 6.179082] scsi0 : pata_cs5536
[ 6.180417] scsi1 : pata_cs5536
[ 6.180614] ata1: PATA max UDMA/100 cmd 0x1f0 ctl 0x3f6 bmdma 0xff00 irq 14
[ 6.180633] ata2: DUMMY
[ 6.354989] ata1.00: CFA: SILICON POWER, Ver2.20, max UDMA/100
[ 6.355017] ata1.00: 3940272 sectors, multi 0: LBA
[ 6.355131] ata1.00: limited to UDMA/33 due to 40-wire cable
[ 6.362981] ata1.00: configured for UDMA/33
[ 6.378960] ata1.00: configured for UDMA/33
[ 6.378979] ata1: EH complete
[ 6.379395] scsi 0:0:0:0: Direct-Access ATA SILICON POWER Ver2 PQ: 0 ANSI: 5
[ 6.630824] sd 0:0:0:0: [sda] 3940272 512-byte logical blocks: (2.01 GB/1.87 GiB)
[ 6.631056] sd 0:0:0:0: [sda] Write Protect is off
[ 6.631079] sd 0:0:0:0: [sda] Mode Sense: 00 3a 00 00
[ 6.631201] sd 0:0:0:0: [sda] Write cache: disabled, read cache: enabled, doesn't support DPO or FUA
[ 6.635212] sda: sda1
[ 6.637661] sd 0:0:0:0: [sda] Attached SCSI removable disk
[ 6.942050] md: linear personality registered for level -1
[ 6.978395] md: multipath personality registered for level -4
[ 7.009777] md: raid0 personality registered for level 0
[ 7.056746] md: raid1 personality registered for level 1
[ 7.162815] raid6: int32x1 71 MB/s
[ 7.231428] raid6: int32x2 82 MB/s
[ 7.298812] raid6: int32x4 76 MB/s
[ 7.367436] raid6: int32x8 74 MB/s
[ 7.434925] raid6: mmxx1 153 MB/s
[ 7.502934] raid6: mmxx2 226 MB/s
[ 7.570739] raid6: sse1x1 151 MB/s
[ 7.638755] raid6: sse1x2 219 MB/s
[ 7.638771] raid6: using algorithm sse1x2 (219 MB/s)
[ 7.663442] xor: measuring software checksum speed
[ 7.682762] 8regs : 394.000 MB/sec
[ 7.702759] 8regs_prefetch: 333.000 MB/sec
[ 7.722764] 32regs : 244.000 MB/sec
[ 7.742767] 32regs_prefetch: 220.000 MB/sec
[ 7.762767] pII_mmx : 872.000 MB/sec
[ 7.782775] p5_mmx : 681.000 MB/sec
[ 7.782793] xor: using function: pII_mmx (872.000 MB/sec)
[ 7.843065] md: raid6 personality registered for level 6
[ 7.843085] md: raid5 personality registered for level 5
[ 7.843101] md: raid4 personality registered for level 4
[ 8.083423] md: raid10 personality registered for level 10
[ 8.298795] kjournald starting. Commit interval 5 seconds
[ 8.298839] EXT3-fs: mounted filesystem with writeback data mode.
[ 9.544068] udevd version 125 started
[ 13.244013] cs5535_gpio: base=0x6100 mask=0xb003c66 major=252
[ 13.295136] AMD Geode RNG detected
[ 13.444272] input: PC Speaker as /class/input/input0
[ 14.265315] padlock: VIA PadLock not detected.
[ 14.717499] geode-aes: GEODE AES engine enabled.
[ 15.697979] EXT3 FS on sda1, internal journal
[ 17.446133] IPv4 FIB: Using LC-trie version 0.409
[ 19.796779] NET: Registered protocol family 10
[ 19.800499] lo: Disabled Privacy Extensions
[ 19.917597] warning: `zebra' uses 32-bit capabilities (legacy support in use)
[ 22.333588] udev: renamed network interface eth0 to eth3
[ 65.546430] nf_conntrack version 0.5.0 (4096 buckets, 32768 max)
[ 65.547298] CONFIG_NF_CT_ACCT is deprecated and will be removed soon. Please use
[ 65.547317] nf_conntrack.acct=1 kernel parameter, acct=1 nf_conntrack module option or
[ 65.547335] sysctl net.netfilter.nf_conntrack_acct=1 to enable it.
[ 66.915953] ip_tables: (C) 2000-2006 Netfilter Core Team
[ 67.600343] ip6_tables: (C) 2000-2006 Netfilter Core Team
[ 71.823003] eth3: link down
[ 71.825074] ADDRCONF(NETDEV_UP): eth3: link is not ready
[ 73.392989] eth2: link down
[ 73.394509] ADDRCONF(NETDEV_UP): eth2: link is not ready
[ 74.911846] eth1: link down
[ 74.913360] ADDRCONF(NETDEV_UP): eth1: link is not ready
[ 82.134572] md: linear personality unregistered
[ 82.138278] md: multipath personality unregistered
[ 82.145062] md: raid0 personality unregistered
[ 82.150371] md: raid1 personality unregistered
[ 82.155332] md: raid6 personality unregistered
[ 82.155351] md: raid5 personality unregistered
[ 82.155365] md: raid4 personality unregistered
[ 82.163638] md: raid10 personality unregistered
vyatta@vyatta:~$ exit
