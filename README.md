# BufferOverFlow
Keep Track of some of the scripts and tools I have used for Buffer Overflows

## Working_ASLR_BufferOverflow_Got_Flag.py:

A buffer overflow for the Praetorian tech challenge. Used format strings to get the first memory address to bypass ASLR. Launched a netcat reverse shell to a host in Digital Ocean on port 4444. 

The ROT13 function of the code affected the payload so all shellcode(bytecode) that was equivalent to ASCII A-Z had to be pre-rotated in order to get the payload correct. 

The Payload order goes: Padding -> memory address to ret to (Found using format string and adding offset to hit NOP sled -> NOP Sled -> Shellcode.  (padding + updatedPivot + nopSled + updatedSC + b"\x4e" * 100)
