#MAKO Kernel

## USB-OTG

Manually applied ziddey's otg patches for mako on `msm_otg` driver from franko's kernel and replaced the `msm_otg` driver in CyanogenMod's kernel.

A dirty hack, but it works :)

Credit goes to ziddey!

See:
 
 * https://github.com/ziddey/mako/tree/nightlies-4.3-JSS
 * http://forum.xda-developers.com/nexus-4/orig-development/usb-otg-externally-powered-usb-otg-t2181820

ziddey's commit messages:

>Commit: `11d942511239dd4093533d578cab592ab601e019`  
Enable debugfs /sys/kernel/debug/msm_otg/mode for manual otg mode manipulation.
Always force requested mode (none, peripheral, host).  
Use ID_A bit instead of ID for host mode.

Note: There are no provisions for charger detection when setting host mode manually.

>Commit: `a78f59835568ffde6f1242f36be9a8b8c8d99da4`  
Force ID_A (host mode + charging) on detection of proprietary charger (Apple-compatible charger with voltage on D+/D-).  
Unforce ID_A on PMIC: BSV clear (detection of loss of charger).  
Use charger type ACA_DOCK and allow up to 1.5A charge rate in host mode.
