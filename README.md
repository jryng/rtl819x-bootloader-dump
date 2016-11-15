# btctool

This tool can dump the flash memory of a **Realtek RTL8186** based device running the btcode bootloader  
  
It deals through the serial port with the bootloader sending the command **D** present in the  
bootloader and captures the output dumping it into a binary file.

**Example:**  
`python2 cfetool.py --read=test.bin --addr=0xbfc00000 --size=0x200000 --block=0x10000`  
  
   --addr: Memory Address  
   --size: Memory Size  
   --block: Buffer size (Default: 10240 -> 10Kb)  

**Note:** the default baud rate used by the tool is 38400 bps  

Based on brntool (@rvalles): Homepage: https://github.com/rvalles/brntool