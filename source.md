# Thesis
Artificial Intelligence will completely change broadcasting because it will make humans obsolete in the performance of many tasks.

# Outline
- [Thesis](#thesis)
- [Outline](#outline)
  - [Basic Info](#basic-info)
  - [Abstract](#abstract)
  - [A Brief Note on Content and Formatting](#a-brief-note-on-content-and-formatting)
- [Introduction](#introduction)
- [Automation](#automation)
- [Quality](#quality)
- [Restoration/Remastering](#restorationremastering)
- [Post-production](#post-production)
  - [Fixing bad footage](#fixing-bad-footage)
    - [The camera's a bit shaky](#the-cameras-a-bit-shaky)
  - [Deepfakes](#deepfakes)
- [Risks](#risks)
- [Feasability](#feasability)

## Basic Info
Title:
Author: Tibet Tornaci
Date: June X, 2020

## Abstract
TBA

## A Brief Note on Content and Formatting
This paper is written and formatted using Markdown, so that it is easy for pretty much anyone to read/write in any context, whether it be through print, the internet, or a screen reader. LaTeX applied for the print version. Length is determined by how long to get the point across instead of an arbitrary page or word count, because I’d rather not waste your time nor mine with needless fluff.

---
# Introduction
Creating video used to be prohibitively expensive, requiring specialised equipment and a dedicated team. This changed in 1999
 - Video Toaster released, changed everything
 - Ever since then the process has been getting more and mroe automated
 - Content has also becoime more and more accessible
 - Discovery networks have been used for years in order to facilitate content reccomendations. 
So clearly, there is a trend of broadcasting technologies becoming cheaper and more accessible over time. But what's next in broadcasting? What new technologies are in the horizon?

# Automation


# Quality


# Restoration/Remastering
A single frame of 35mm film has a resolution of (by some calculations[^filmresolution]) 156MP. We don't digitize it anywhere near that, of course, with 4K footage containing around 8.5-9MP[^4kres], depending on which standard you use. This is made worse by chroma subsampling, where colour information is stored at half the video resolution[^chromasimple]. This means that film is a really great *ground truth* to create "lower quality" versions out of, and the quality we can derive from film will only keep going up from here.

However, this is not the case with video/television, where WYSIWYG. You fimed something at 525 or 625 scanlines? It's interlaced? Stored on magnetic tape? Good luck restoring that.

You'd need to add detail that was never in the original source to begin with.

But what if you *could* do just that? So far, attempts to do so have been dodgy at best:

![via the [matplotlib documentation](https://matplotlib.org/gallery/images_contours_and_fields/interpolation_methods.html)](interpolation.webp)

Not anymore though, thanks to advances in artificial intelligence/deep learning:

(Bicubic is one of the methods demonstrated in the above image, and is the de-facto industry-standard scaling algorithm. HR is the original image.)

![via [xinntao/ESRGAN](https://github.com/xinntao/ESRGAN)](esrgan1.jpg)

![via [xinntao/ESRGAN](https://github.com/xinntao/ESRGAN)](esrgan2.jpg)

| Of course, nothing stops these same methods from being used on being used when remastering and especially colorizing film:
| <video controls="" src="http://iizuka.cs.tsukuba.ac.jp/projects/remastering/data/remastering_siggraphasia2019.mp4" width="512"></video>

Another recent development is real-time upscalers, which, as the name suggests, upscale video (or other graphics) as they're being played.

![via [bloc97/Anime4K](https://github.com/bloc97/Anime4K/)](anime4k.png)

Here's an explanation and demo from NVIDIA about their DLSS upscaling technology, which upscales games in real-time in the same exact way you would video:

> <iframe width="560" height="315" src="https://www.youtube.com/embed/BeScfkCm3b4?start=73" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
> This is particularly impressive as games are very latency intensive, meaning that every millisecond spent processing counts.

# Post-production
Restoring old content is great and all, but making new content is much more exciting, is it not?

## Fixing bad footage
Sometimes things go wrong and you aren't able to do a retake. 

### The camera's a bit shaky
>top: frame from original video
>bottom: after running through the **S**cale-**I**terative **U**pscaling **N**etwork for Image Deblurring
>![](deblur.png)
>adapted from [minyuanye/SIUN](https://github.com/minyuanye/SIUN)



## Deepfakes


# Risks


# Feasability
At this point, you're probably thinking *"This all sounds great, but can I actually use it?"*

[^filmresolution]: [@RealResolutionFilm]

[^4kres]: 3840*2160 = 8,294,400‬px or 8.2944MP

[^chromasimple]: This is a major oversimplification of the chroma subsampling process.
