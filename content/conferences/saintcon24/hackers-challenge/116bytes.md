So this looks to be an executable that can be run with bin/sh. Tried file on it and it said "shellcode: data". Strings gave nothing other than
'/bin/sh'
looking how to get into the code. not sure how quite yet

learned a new command that can be used 'od' or octal dump. This will show the data in different formats including octal

I get this output when running "od shellcode"
0000000 040400 164455 020000 161640 010001 161640 000002 161640
0000020 070431 161400 000000 167400 100000 160640 020020 161640
0000040 010074 161217 070433 161400 000000 167400 110000 161640
0000060 010011 160640 000010 160640 070077 161640 000000 167400
0000100 110001 161211 000003 161531 177770 135377 020000 161640
0000120 010002 160640 000020 161217 070013 161640 000000 167400
0000140 100400 164275 000002 002710 012325 157145 061057 067151
0000160 071457 000150
0000164

if you use binwalk -A on the file then you figure out that it is ARM processor compilation. Arm is 32 bit, arm 64 is 64 bit(obviously). Always look to understand the processor 

Shellcode is small code that is to be run as an exploit for a system. We can do the same types of analysis however it is not a full blown executable. We need to know what architecture it is for. 
