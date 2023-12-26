Sharpen textures but not edges
==============================

I've included this simply because I'm unhappy with DLSS sharpening in this game and prefer something similar to Contrast Adaptive Sharpening (CAS).

CAS is enabled in the game by default, however I can't control the strength of it easily (currently looking for a way).

So for now, when I play personally I'm disabling CAS by setting ConstrastAdaptiveSharpening = false in the Ultra+ ini (note, the spelling error is _correct_, don't change it) and using this Reshade instead.

It applies LumaSharpen which is visually similar to CAS (you could use CAS as well) and then uses a very fast SMAA antialias. The effect is, it noticably sharpens tesxtures without making their edges too sharp.

(It doesn't modify colour or the look of the game, only texture sharpness.)