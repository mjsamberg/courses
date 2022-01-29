---
layout: page
title: "Images and Embedded Content"
course: "webdev"
unit: 3
---

While there's a lot that we will be doing in order to style images with CSS, basic insertion of images into HMTL is very easy.

	<img src="https://brand.ncsu.edu/assets/logos/ncstate-type-2x2-red-max.png" alt="NC State University Logo" style="width: 25%; height: auto;" />

<img src="https://brand.ncsu.edu/assets/logos/ncstate-type-2x2-red-max.png" alt="NC State University Logo" style="width: 25%; height: auto;" />

The ```img``` tag is the tag used to insert an image. Note that it is not a container tag, so it ends with a trailing slash ```/``` at the end of the tag. The ```src``` attribute is the URL of the image to be added. Like with links, URLs may be relative (in the same folder structure) or absolute (a full URL).

The ```alt``` attribute is a textual representation of what the image is. This is used for people who use assistive devices such as screen readers, low-resolution devices like Kindles or on low-bandwidth connections where images aren't downloaded. The text in the ```alt``` attribute should describe the contents of the image such that someone who couldn't see the image has an understanding of the meaning of the image. 

We will get into the ```style``` attribute much more with CSS, but for now, the big thing to know is that images, unless styled by CSS, images need a ```style``` attribute with a width and height if the images need to be resized or scaled down. You can put either width OR height, and put auto for the other, and the image will resize while maintaining aspect ratio. Widths/heights can be in percentages (100% width being 100% of the container/screen OR the full-size image, whichever is less) or they can be specific pixels. If you're using pixels, you would put in the format of ```style="width: 200px; height: auto;```.

**Sidebar**: A pixel is a unit of screen measurement. Behind the scenes, your computer is made up of a grid of pixels with certain [widths and heights](https://www.droidviews.com/screen-resolution-sizes-hd-fhd-qhd-uhd-4k-5k-8k/). For example, a 1080p HD tv is 1920 pixels wide by 780 pixels in height for a total of 1,497,600 pixels. Whether you're using a 15" 1080p laptop or watching football on a 90" 1080p TV, the number of pixels is the same. On larger screens, this is likely why you can see the individual pixels on a 1080p screen up close, but possibly not on a 4K TV (3840x2160 or 8,294,400 total pixels). So assuming a 1080p screen, a 500px wide image would take up roughly one-quarter of that screen regardless of the size. Most higher resolution screens use "pixel doubling" technology where three or four pixels display the same image to mimic a 1080p screen since the pixels on a 4K screen or too small to be useful in business applications. This means that while the image may appear the same size on a 4K monitor vs a 1080p monitor, the pixel-doubling allows for extra sharpness and detail to be displayed in an image, resulting in a clearer image.

## Embedded Content
Likely many of you have embedded a YouTube video or other content in an LMS or in a website before. This is done through a tag called ```iframe```. ```iframe``` is short for Inline Frame. The format for iframe is similar to images with exception of a ```title``` attribute instead of an ```alt``` attribute. Also, you must specify both a height and a width. While there are some other attributes that will be used for things like YouTube, these are the primary tags that will be used. As a rule, using iFrames for anything other than embedded content like videos is discouraged for security reasons (so that people know that they're putting their content into the site they think they are). But, in some circumstances, it can be useful. 

For example: 

	<iframe src="https://www.ncsu.edu" title="Google" style="width: 85%; height=300px;">

<iframe src="https://www.ncsu.edu" title="Google" style="width: 85%; height: 600px;">