---
layout: post
title: Why We Hate Responsive Images
---

##It's true, We all hate working with images.
&nbsp;&nbsp;&nbsp;  I remember when I first added an image to a website. I wrote out a simple image tag and copied a URL from Google images and was on my way. I didn't even bother with an ALT tag I was bad.   
&nbsp;&nbsp;&nbsp;  Then came smart phones and images became to be a problem. You have this beautiful picutre of a pony and you want to get it out to all the pony lovers, but what if they all have different devices. *PonyLover_87* has an iPad so he can view the ponies in all it's glory on his retina display but *PonyBr0* only has a Nokia2 and might only get a glimpse of that wonderful mane.  
&nbsp;&nbsp;&nbsp;  So what do we do about this? We the very minimum we can do is putting an image in a figure tag and setting that baby to a width of 100%. With this strategy you will be able to load an image and let the user zoom in and out and pan around. 

###CSS
  ```
  figure{
  width: 100%
  }
  ```
&nbsp;&nbsp;&nbsp; This is the very minimum you can do for an image you're really proud of and want to share regardless of its size.Images can be difficult to use because of the different viewports people have. We have an image that we want to share with everyone but when you start to shrink it down it starts to loose its intergrity. So what can we do?

##PICTUREFILL.JS

&nbsp;&nbsp;&nbsp; I know what you're thinking... *"I have to use Javascript just to showcase my pony pictures??"* It's really not as hard as you think. The wonderful people at [Filament group](http://filamentgroup.com/) maintain and helped make responsive images easier. It is worth noting that we will need to make different images to display on different viewports. Don't worry, I'll hold your hoof during all of this.
Let's look at some code here:
###Basic Script Tags

```
<!--This bad boy will go inside the head tag, preferably at the end. -->
  <script>
    // Picture element HTML5 shiv
    document.createElement( "picture" );
  </script>
  
  <script src="picturefill.js" async>
  </script>
```

&nbsp;&nbsp;&nbsp; After downloading the picturefill.js [file](http://scottjehl.github.io/picturefill/) and adding it to your project you can easily copy and paste the above snippet into your HTML file. That's the easy part. 
###The Good Stuff

```
<picture>
	<source srcset="images/desktop.jpg" media="(min-width: 1000px)">
	<source srcset="images/tablet.jpg" media="(min-width: 786px)">
	<img srcset="images/mobile.jpg" alt="Ponies 2014 Calendar Example">
</picture>
```

&nbsp;&nbsp;&nbsp; Like above when we put our picture in a `<figure>` tag, here we are putting our images in a `<picture>` tag. we place the `<img>` at the bottom incase the browers doesn't know what do to do with our `<source srcset>`, it can atleast display something to the user which is better than nothing.

&nbsp;&nbsp;&nbsp; Working our way up we see that `<source>`tag with a `srcset="images/large.jpg` after it. This would be a medium image that would be displayed on a tablet. The `<media>` tag asks the browser what the size is and if it matches up it will display the correct image. Not only will it display the correct image in the browser, **It also doesn't download the bigger images onto your phone, making it easier on bandwith!**

&nbsp;&nbsp;&nbsp; Hope that helps! :green_apple:

