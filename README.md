nes-notes
=========

Notes about the Nintendo Entertainment System

## NES Numbers

### Binary

prefixed with a %

### Hex

prefixed with a $

## NES System Architecture

### CPU

The CPU is a modified 6502. Has a 16-bit address bus. That means 2^16 bytes of mem. 16-bit digits are 4 hex digits.

* internal RAM is at $0000-0800 ($0800 = 2048 or 2KB)
* PPU IO Ports is at $2000-$4000
* APU/Conroller IO Ports $4000-$6000
* 8KB Cartridge RAM (WRAM) $6000-$8000
* 32KB Cartridge ROM $8000-$FFFA
* NMI/Reset/IRQ vectors $FFFF

### PPU

The PPU is a custom chip that does graphics display.

* 4KB Cartridge RAM/ROM - Pattern Table 0 - 256 tiles - $0000-$1000
* 4KB Cartridge RAM/ROM - Pattern Table 1 - 256 tiles - $1000-$2000
* Name Table 0 - 32x30 tiles - $2000-$23C0
* Attribute Table 0 - $23C0-$2400
* Name Table 1 - 32x30 tiles - $2400-$27C0
* Attribute Table 1 - $27C0-$2800
* Name Table 2 - 32x30 tiles - $2800-$2BC0
* Attribute Table 2 - $2BC0-$2C00
* Name Table 3 - 32x30 tiles - $2C00-$2FC0
* Attribute Table 3 - $2FC0-$3000
* Background Palette - $3F00-$3F10
* Sprite Palette - $3F10-$3F20

### Graphics

#### Tiles
All graphics are made up of 8x8 tiles.

#### Sprites
The PPU can hold 64 sprites in memory. 8 sprites per scanlines are allowed.

## NES Assembly Language Notes

### CPU Registers

All registers are 8-bit. 

- A the accumulator

- X the index register

- Y another index register

### Instructions

#### LD

lda for example will load into the A register.

lda #$20 will load A with 20 in hex. # means immediate value, not a address in memory, and $ means hex. % means binary. Nothing just means plain old decimal.

#### ST

sta will store whatever is in the A register into memory. 

### Banks

Banks are where data goes.

#### Bank 0

Where the code goes. It starts at $8000.

#### Bank 1

Inturrupt table. Starts at $FFFA.

#### Bank 2

Sprite and background data. Starts at $0000.


### INES Header

#### .inesprg

How many code banks there are.

#### .ineschr

How many picture banks there are.


