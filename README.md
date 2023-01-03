# ![Logo](/assets/logo.png)

![Example Image](/assets/example1.png)

Here is my guide on how you can semi-easily convert videos to pixelart. This guide also works for images, just scroll down to the Gimp processing chapters. 

*Im working on a single gimp plugin to do all the image processing. This should speed up processing time for each individual image*

## PREREQUISITES

In order to convert your videos to pixelart, you will need to have thes programs/plugins installed:

- Blender: https://www.blender.org/download/
- GIMP: https://gimp.org/downloads/
- BIMP (Gimp plugin): https://alessandrofrancesconi.it/projects/bimp/
- Additional files

## CREATING FOLDERS

Before we start making the video, I advise you to make these folders before we get started:

- Main folder. This will be the place we output all are files to. I recommend naming it something related to the video. The next folders will be inside of the main folder.
- Frames folder. This will be the place all the individual frames will be rendered to.
- Pixelated folder. This is the folder where the BIMP pixelation gets outputted.
- Edge folder. This is an extra file for people who want edges on the video.

## CONVERTING VIDEO TO INDIVIDUAL FRAMES

**If you want to use my preset files, make sure that the videos framerate is in the 24fps range, but this is standard for most videos.**

To start the converstion open up the file downscale.blend in blender. 

Import the video you want to pixelate under Add>Movie in the sequencer window. 

![c1](/assets/addmovie.png)

Change the end frame to the video's frame length under FrameRange>End in the properties tab. You can see the frame length by clicking on the edge of the video. *An optional change is to change the frame step. Right now, it's on 2, which renders every other frame, to recreate the style animators use by animating on 2's. If you want to keep the fluidity of the video change it to 1*

![c2](/assets/framelength.png)
![c2](/assets/frameend.png)

Under output in the properties tab, change the output destination to the destination of the frames folder.

![c3](/assets/outputframes.png)

To render the frames go to Render>RenderAnimation.

![c4](/assets/renderframes.png)

## CONVERTING FRAMES TO PIXELART

> ### ADDING PALETTES
> To add a palette you want to use, open up the Palettes window by pressing the "/" key, search for palette and open up the Palettes window.
> Import the palette by right clicking the newly opened widow on the right side and right click and open ImportPalette.
> In the new import window, change the source to PaletteFile and open up the aap.gpl file, and rename the palette name to "aap". *This palette isn't required, but is the one I have had best results with. You can find more free palettes at: https://lospec.com/palette-list.*
> ![ip](/assets/importpalette.png)

We will be using the BIMP plugin to mass convert the images. *Note that the plugin isn't the fastest for this task and is another reason for rendering every other frame, so the processing time is faster.*

To start open up the BIMP plugin in GIMP. You can do so by going to File>BatchImageManipulation.

![p1](/assets/openbimp.png)

In the BIMP menu, add all the frames by going into AddImages>AddFolders and add the frames folder. Change the output folder to the destination of the pixelated folder.

![p2](/assets/addinputoutputbimp.png)

Load in the pixelator.bimp preset by going to Add>LoadSet and find the pixelator.bimp file.

![p3](/assets/loadbimppreset.png)

The next choice is the most important choice for the final style of the output. You will have to choose between if you want dithering enabled or disabled.

![p4](/assets/dithercompare.png)

As you can see, the image with dithering keeps more detail than the one without. You may want to disable dithering though, if you want to have a more toonish style to your video. 

> ### CHANGE DITHERING
> The dithering is enabled by default, but to disable it, click on the first item in the manipulation set and click EditProperties. Change the dither to none by clicking on the first tab in the edit menu and select: CONVERT-DITHER-NONE (0).

![p5](/assets/editmanip.png)
![p5](/assets/changedither.png)

> ### APPLY CUSTOM PALETTE
> If you're using a custom palette, you will want to open the EditProperties tab and scroll down to the bottom, where you can type out the name of the pallete you want to use.

![p6](/assets/changepalette.png)

After all the final settings have been set, click apply and let the images process.

## GENERATING EDGES (*OPTIONAL*)
