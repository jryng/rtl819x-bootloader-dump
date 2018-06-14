# bootloader-dump tools
Collection of tools for dumping the memory or backing up the flash chip using the **memory read** native  
command present in bootloaders of some devices (not all) like routers.

Usually you access to the bootloader command line using an UART adapter, and then if the command is  
available dump small portions of the memory in plain text, this tools automate the process for getting  
a full backup in binary format. It deals through the serial port with the bootloader sending the command  
**memory read** and captures the output dumping it into a binary file.


## brntool
This tool can, so far, given a serial port connected to a device with **brnboot / amazonboot**, dump its flash into a file.  
Homepage: https://github.com/rvalles/brntool  
  
**Example:**  
`python3 brntool.py --read=AR4518PW_whole.dump --addr=0xB0000000 --verbose --size=0x400000`  

   --addr: Memory Address  
   --size: Memory Size  
   --block: Buffer size (Default: 10240 -> 10Kb)  
   
## cfetool
This tool can dump the flash of a device with CFE bootloader into a file.  
It's compatible with all CFE bootloaders with "dm" command usually found in **BCM63xx SoCs**.  
  
**Example:**  
`python2 cfetool.py --read=test.bin --addr=0xB8000000 --size=0x20000 --block=0x10000`  
  
--addr: Memory Address  
--size: Memory Size  
--block: Buffer size (Default: 10240 -> 10Kb)  
  
**Zyxel variants:**  
zyx1tool.py, zyx2tool.py

## rt63365tool
For **Ralink RT63365** (Trendchip) based SoCs running the tcboot bootloader. Tested on Huawei HG532s  
  
**Example:**  
`python2 rt63365tool --read=test.bin --addr=0xB0000000 --size=0x800000 --block=0x10000`  
  
--addr: Memory Address  
--size: Memory Size  
--block: Buffer size  

## rtl8186tool

This tool can dump the flash memory of a **Realtek RTL8186** based device running the btcode bootloader  

**Example:**  
`python2 rtl8186tool.py --read=test.bin --addr=0xbfc00000 --size=0x200000 --block=0x10000`  
  
   --addr: Memory Address  
   --size: Memory Size  
   --block: Buffer size (Default: 10240 -> 10Kb)  

**Note:** the default baud rate used by the tool is 38400 bps  

   
---

All tools are based on the original brntool (@rvalles): Homepage: https://github.com/rvalles/brntool