# Assembly x86_64 Excercises
A collection of Assembly x86_64 ( NASM ) made by me.

## Installation

``` bash
# Install nasm on Ubuntu
sudo apt-get install nasm

# Install nasm on Mac OSX
brew install nasm

# Install nasm on Windows
## Download the version you want

```

[nasm releases](https://www.nasm.us/pub/nasm/releasebuilds/)

```bash
## Go to the win32 / win64 directory
## Get the installer.exe
## double-click installer and follow the steps
```



## Build Bash

### Without Script

``` bash
# Create compiled file
nasm -f elf64 -o filename.o filename.asm

# Create executable file
ld -o filename filename.o

# Execute file
./filename
```



### With Script

```bash
# arg1 = filename without extension
# arg2 = delete if you want to remove output/execution files otherwise empty

# Without delete
./build filename

# With delete
./build filename delete


```