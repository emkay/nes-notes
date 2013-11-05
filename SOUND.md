## APU (Audio Processing Unit)

APU: $4000-$4015, $4017

### Channels

* Square 1
* Sqaure 2
* Triangle
* Noise
* DMC (samples)

To enable the channels you need to set the bits of $4015. The channel bits are right to left in the order they appear in the list above.

Pro-tip:  
```
    lda #$0F
    sta $4015
```
Enables everything except but DMC, which you probably don't want.
