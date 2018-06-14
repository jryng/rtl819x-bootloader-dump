# bootloader-dump tools
Collection of tools for dumping the memory or backing up the flash chip using the **memory read** native  
command present in some devices (not all) like routers.

Usually you connect to the bootloader command line using an UART adapter, and this is how these tools  
work, automating the process of reading the memory. It deals through the serial port with the bootloader  
sending the command **memory read** present in the bootloader and captures the output dumping it into a  
binary file.

## cfetool
todo

## rt63365tool
Tool for backing up this trendchip based SoCs running the tcboot bootloader. Tested on Huawei HG532s

## rtl8186tool

This tool can dump the flash memory of a **Realtek RTL8186** based device running the btcode bootloader  

**Example:**  
`python2 rtl8186tool.py --read=test.bin --addr=0xbfc00000 --size=0x200000 --block=0x10000`  
  
   --addr: Memory Address  
   --size: Memory Size  
   --block: Buffer size (Default: 10240 -> 10Kb)  

**Note:** the default baud rate used by the tool is 38400 bps  

## brntool
todo

##
Based on brntool (@rvalles): Homepage: https://github.com/rvalles/brntool