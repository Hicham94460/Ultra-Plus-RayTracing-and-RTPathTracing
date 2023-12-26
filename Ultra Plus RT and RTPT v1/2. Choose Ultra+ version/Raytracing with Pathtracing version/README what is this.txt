NOTE: Make sure you don't have any other path tracing or RT mods installed for this to work.

NOTE2: Do *not* enable path tracing in-game. The mod requires just raytracing to be enabled, and will
       will force PT all by itself.


Why would I want normal raytracing with path tracing??
======================================================

Path tracing still costs a lot of FPS in 2.1, and while ghosting is improved, ReSTIR has some artifacts.

Instead, I found a half-way method. This uses regular raytracing, however you would normally use it, but
adds a layer of path tracing over the top. This has a few advantages:

    1. Adds a layer of detail that's not normally there to ray tracing
	2. Is not 'too dark' in some areas like path tracing can be
	3. Is very performant, costs almost nothing vs. regular ray tracing, so it's close to 'free'
	4. Minimal to no visible ghosting

So it's kind of the best of both worlds. It doesn't look *as* physically based as PT, but it's close,
and if you can barely run PT due to the performance cost, RT with PT is possibly your new best friend 😊

How does it work?
=================

Ray tracing is normally done in several layers (called multilayer) drawn over the image. This simply forces
part of the path tracing over the top as well (ReBLUR indirect diffused, for the moment). This darkes parts
of the image in some areas, and lightens in others. The overall effect is like adding a more sophisticated,
higher detail global illumination.


How do I use it?
================

1. Install just this mod. Don't use other RT, or mods that adjust shadows or lighting
2. Set your game to use *normal raytracing* however you normally like it (do *not* enable pathtracing)
3. From my tests, enabling ray reconstruction on 2.1 looks better in dark scenes. This will work without
   RR if you don't want to use it, however it does not have the regular problems with RR (they are hidden
   by the regular raytracing)
4. Enjoy the better visuals! 😎


What's the difference between Fast, Full, and High
==================================================

Fast - Is close to vanilla with some performance optimisations that should not cause significant visual
       quality loss, but should give you a few more FPS, even with the path tracing
Full - Extends the raytracing reflections farther for lakes, and enables shadows on objects below 10cm. It
       should improve visual quality at fairly low FPS cost
High - Everything in full, and enables all lights and shadows on all objects. It shouldn't cost more than
       about 10% FPS


Boss mode
=========

If you want to see what it's doing, or test that it's working, you can disable it in the CET console with:
GameOptions.SetBool("RayTracing/NRD","UseReblurForIndirectRadiance",false)

And re-enable with:
GameOptions.SetBool("RayTracing/NRD","UseReblurForIndirectRadiance",true)


SammiLucia x