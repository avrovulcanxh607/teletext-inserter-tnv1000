# Teletext Inserter
## specifically, the TNV1000

I designed this board in 2022. It's based on the same basic philosophy as [Peter Kwan's VBIT-Pi](https://github.com/avrovulcanxh607/vbit-pi3), but using smaller, modern ICs.

The short version is a Video Decoder chip (ADV7182) is used to convert analogue video to digital Rec.656 (SDI only parallel). This is then fed straight back into an encoder chip (ADV7391) which converts back to analogue video and also adds the teletext and WSS signals. It's also capable of doing some digital noise reduction.

A number of these have been integrated into projects of mine, and a number were even sold.

This repo is an attempt to open-source the design and code. You are now free to do whatever you like with this design and the driver code.

**Disclaimer: the design and firmwares are offered completely as-is, with no warranty of any kind. I will no longer be offering support or assistance on this project, if you want to build one you must figure it out from the resources provided here.**

The Code folder has two drivers, one for a Raspberry Pi and one for an Orange Pi Zero. Both versions rely on [VBIT2](https://github.com/peterkvt80/vbit2) to generate a teletext service datastream for transmission.

The Raspberry Pi version requires the teletext be provided with the bytes in reverse order. I can't remember if the Orange Pi version does or not.

The PCB files were exported from EasyEDA - I'm not especially sure how one goes about re-importing them for use... but that sounds like a you problem. If it proves too impossible this is one situation where I may look into it if someone asks.

Oh yeah, the ATTiny13... That was a crude solution to a problem I had sequencing the power supplies coming up. Basically all it does is bring up each rail about 500ms apart. I can't find the code for it, but if you've figured everything else out you should have no problem figuring that out. Or just tie all the power supplies permanently on, hope for the best..!

If you do decide to do something cool with this design, please consider posting photos of it to Bluesky and tagging "@nmsni.co.uk", I would love to see it!

Also... consider kicking a quid or two my way at [Ko-Fi](https://ko-fi.com/avrovulcanxh607). It took a fair bit of time to figure this out.

Useful Resources:

[ADV7182a Product Info](https://www.analog.com/en/products/adv7182a.html)

[ADV7391 Product Info](https://www.analog.com/en/products/adv7391.html)

[TNV1000 Manual/Notes](https://internal.nathanmediaservices.co.uk/downloads/TNV-1000%20manual.pdf)
