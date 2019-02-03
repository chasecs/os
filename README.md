# operating system

step 1 

```
cd boot/
nasm main.asm -f bin -o main.bin
```

step 2

```
cd ../kernel/

gcc --ffreestanding -c kernel.c -o kernel.o

ld -o kernel.bin -Ttext 0x1000 kernel.o --oformat binary
```

step 3

```
cd .. 
cat boot/main.bin kernel/kernel.bin > os-image

```

step 4 
```
qemu-system-x86_64 -fda os-image
```
