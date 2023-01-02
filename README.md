# VideoToPixelart

![Example Image](/assets/example1.png)

Here is my guide on how you can semi-easily convert videos to pixelart. This guide also works for images, just scroll down to the Gimp processing chapters. 

*Im working on a single gimp plugin to do all the image processing. This should speed up processing time for each individual image*

## PREREQUISITES

In order to convert your videos to pixelart, you will need to have thes programs/plugins installed:

- Blender: https://www.blender.org/download/
- Gimp: https://gimp.org/downloads/
- Bimp (Gimp plugin): https://alessandrofrancesconi.it/projects/bimp/
- Additional files

## CREATING FOLDERS

Before we start making the video, I advise you to make these folders before we get started:

- Main folder. This will be the place we output all are files to. I recommend naming it something related to the video. The next folders will be inside of the main folder.
- Frames folder. This will be the place all the individual frames will be rendered to.
- Pixelated folder. This is the folder where the bimp pixelation gets outputted.
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
