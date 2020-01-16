# bashsong
Compose original 8-bit music using a shell script.

# Command to use:

'''bash
echo "Insert text here." | hexdump -v -e '/1 "%u\n"' | awk '{ split("0,2,4,5,7,9,11,12",a,","); for (i = 0; i < 1; i+= 0.0001) printf("%08X\n", 300*sin(64*exp((a[$1%8+1]/12)*log(2))*i)) }' | xxd -r -p | aplay -c 8 -f S32_LE -r 16000
'''
