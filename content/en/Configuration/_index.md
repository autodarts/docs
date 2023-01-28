---
draft: true
language: "English"
author: "Steve_Mutter"
---


## In this section you will learn how to Configure the Parts of the System


[comment]: <> (Maybe using this kind of switchable Table to keep things organized?)

{{< tabs "Install Tab" >}}
{{< tab "Board Manager" >}} 

# Board Manager Config Tab

I want to share a couple of words on the config settings under`Motion Detection` and `Dart Detection` so you can better adjust them to your needs.

Let us start with the two most important ones first.
The `Diff Image > Threshold` both under "Motion Detection" and "Dart Detection" is used to calculate the difference between the image before the dart hit and the image right after.
For optimal results this image should be crystal clear.
That is, there should be a clear outline of the dart visible but there shouldn't be any artifacts in the background.
You can check that best while throwing some darts and observing the `Motion` tab in the Board Manager.
Higher `Threshold` will typically result in less visible dart contours but also in less background.
Lower `Threshold` values will result in clearer dart contour but at the expense of picking up background.
Set it so that you are right in between.

I think it is best when you keep the `Diff Image > Threshold` the same for `Motion Detection` and `Dart Detection`, though it can have a positive effect to set them differently.
In `0.16.0` I have set the default value for `Dart Detection` to be `12`.
This turns out to be a bit too low for most people, so I will change that back to `16` (the value in `Motion Detection`) with the next patch.

Play with these values to optimize the diff image.
It will have quite a big impact on the detection overall.

Next is the `Gaussian Kernel`.
It is used to blur the diff image to get rid of background noise.
You can only set it to odd values.
Higher values will take more time to compute, which is why I default them to `3` and `5` for `Motion Detection` and `Dart Detection`, respectively.
They do not have a big impact on the detection, so you should keep them as is, if you do not face any problems related to it.

The `Object Detection` holds the config parameters related to the differentiation between dart and hand.
Very simplistically spoken, a dart is smaller than a hand, and that is how the software detects it (believe it or not).
So the `Dart Size: Min` and `Dart Size: Max` are values that define the boundaries of how small an object at least has to be to be detected as a dart as well as how large it is allowed to be at max.
These values are representing areas in the image but you can think of them as the total number of pixels in your image that makes up the dart.
I typically put the `Hand Size: Min` to be a lot higher than the `Dart Size: Max` but there is no real reason for it.
Once an object has more pixels than this value, it is considered to be a hand.

In the `Dart Detection`, there is a sub-section called `ROI Detection`.
The ROI is the region-of-interest in the full-resolution image.
I use the motion detection which runs on a much smaller resolution (to be fast) to calculate where the dart would be in the full-resolution image.
To figure out the ROI, I combine all the so-called blobs (objects in the image made up of pixels) that exceed a certain size (again in pixels).
The ROI is simply the bounding box (a rectangle) of those combined blobs.
I typically set this quite low, lower than the `Dart Size: Min`.
Keep in mind that the number of pixels here refer to the motion resolution, which is `4` times smaller than the detection resolution.

Lastly, there is the `Hough Line Detection`.
This sub-section holds all the values around the algorithm that fits the line into the dart barrel.
The `Threshold` is quite important and I have not really figured out how to scale it properly with the chosen resolution.
I typically use values in the `50`s for my setups (running at `800x600` and `1280x720`).
If you set this value higher, the algorithm will find fewer lines because only lines with a certain number of votes are considered.
The threshold defines how many votes a line needs.
The `Min Line Length` and `Max Line Gap` should be quite self-explanatory.
Again, they refer to values in pixels.
So, how long a line at least has to be, to be considered, as well as how far apart two lines are allowed to be, to be combined into one single, long line.
{{< /tab >}}


{{< tab "Other Stuff" >}} 
# Other Stuff Content 
{{< /tab >}}
{{< tab "More Other Stuff" >}}
# More Other Stuff Content 
{{< /tab >}}
{{< /tabs >}}