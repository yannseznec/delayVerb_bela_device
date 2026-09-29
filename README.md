# delayVerb Bela device
simple reverb and delay system for my mixer

This is a pure data patch designed to run on a Bela. I am using a Bela Mini for this, but any Bela board should work: https://bela.io

It uses 2 audio inputs and has 2 audio outputs. I use it with the Aux Send and return on my mixer. With that in mind, the patch does not pass any signal through dry, it is either wet or nothing.

The reverb uses freeverb: https://github.com/sinshu/freeverb
Specifically it uses the freeverb~ object for Pure Data compiled for 32-bit Bela boards available here: https://github.com/BelaPlatform/Bela/issues/621

The audio signal passes into both a delay system and a reverb system simultaneously. The wet level of each of these is independently controllable. The delayed audio can also be passed into the reverb - the amount of delayed signal passed into the reverb is controllable. This means you can either use the reverb only, or the delay only, or some combination of the two. 

It uses 8 analog inputs and two digital inputs for control. The controls are as follows:

- Analog 1: wet delay amount
- Analog 2: delay time (between 0 and 1800ms, via the scaling switch)
- Analog 3: delay feedback amount (0-100%, roughly)
- Analog 4: "fake width", a lazy way of adding some stereo space to the delay by just slightly adjusting the delay times sent to the two channels
- Analog 5: amount of delayed signal sent to reverb
- Analog 6: wet reverb amount
- Analog 7: reverb "room size"
- Analog 8: master filter, switches between low pass and high pass
- Digital input 1 (pd 12): switch between short (0-200ms) and long (200-1800ms) delay times
- Digital input 2 (pd 13): button for reverb "freeze"

As you can probably tell, I made this patch and the device specifically for my own purposes, and most of the design decisions were made with my own constraints and desires in mind. I never made any schematic or anything, I just used stripboard inside the box. 

Let me know if you have any questions or suggestions or anything: yann@yannseznec.com