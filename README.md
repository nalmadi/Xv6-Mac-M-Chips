# Installing and Running xv6 on macOS (M chips)
Thanks to Cathy Fan for preparing the Makefile and instructions below:

## 1. Install Homebrew https://brew.sh/ (Skip if already installed)  

Check if installed and update:
```sh
brew --version
brew update
```

## 2. Install QEMU
QEMU is required to run xv6. Install it via Homebrew:
```sh
brew install qemu
brew install i686-elf-gcc
```

## 3. Clone the Repository
Clone the following repository in your terminal:
```sh
git clone https://github.com/nalmadi/Xv6-Mac-M-Chips.git
```

## 4. Build and Run xv6
Navigate to the cloned repository in the terminal and execute the following commands one by one:
```sh
make
make qemu-nox
```

After running the last command, your terminal should display the Xv6 shell, confirming that it’s working.

## 5. Test xv6
Run the following command inside the xv6 shell to list files:
```sh
ls
```

## 6. Terminate xv6
To terminate xv6, first press:
**`Ctrl + A`**  
Then press **`X`**

## 7. Updates (2026) - Rishit
On M5 Macs, this repository should be built with the `i686-elf-*` toolchain.  
Using `x86_64-elf-*` or `i386-elf-*` for this codebase may cause build or boot issues.

Verify required tools:
```sh
which i686-elf-gcc
which qemu-system-i386
```

If `i686-elf-gcc` is missing, install it:
```sh
brew install i686-elf-gcc
```

If the Makefile was modified to use a different cross-compiler prefix, restore it to `i686-elf-`, then rebuild:
```sh
make clean
make
make qemu-nox
```
