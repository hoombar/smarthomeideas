+++
date = '2025-02-01T20:56:07Z'
title = 'Govee and Frigate Porch Light'
+++

_This is a transcript from one of my [YouTube videos](https://www.youtube.com/watch?v=SlhU_mDVFgw)_

---

# Transcript

This is quite possibly one of the most over engineered things in my house. You know those little porch lights you get. 
The ones with the with the PIR sensor, which turns on the light when someone walks in front of it. 
The super reliable ones, that "just work". Well. I got rid of mine, and replaced it with with an AI powered porch light. 
Not because I like making things difficult for myself, but because I think these lights are really neat! 

This isn't just clickbait either, I'm actually using detection through Frigate, powered by a Google Coral, to decide when to turn my porch light on. 

If you don't know what any of those things are, then stick around, and I'll explain everything.

Let's start with Frigate. To quote the Frigate site, Frigate is an open source NVR built around real-time AI object detection. All processing is performed locally on your own hardware, and your camera feeds never leave your home. 
Frigate will connect up to home assistant, and provide occupancy sensors for all of the models you set up. 

I've connected up a Google Coral, which is a TPU, or, Tensor Processing Unit, to evaluate the stream and run it against the models I want to detect. The main reason for adding in the TPU is to take the load off of the CPU. 

With Frigate integrated in to Home Assistant, it's super easy to create an automation that will react to Frigate detecting something. In this particular case, I want the porch light to turn on  when Frigate has detected a person. Frigate will detect cats, dogs, vehicles, and many more objects, but I don't need any of those for this automation. 

I want to rule out false positives, as I don't want the porch light turning on when someone walks past the house, so I created some motion masks and a zone to make sure that it's not turning on too much. 
The zone will make sure that it will only match objects in that part of the video, and the motion masks will make sure that the frames aren't processed unless there is something that happens outside of that mask. 
This saves on CPU processing time, and means that models don't have to be passed off to the coral if they're in that region.

Now that the porch light is wired up to my smart home, now I can make it even smarter! One of the things that irritated me with the dumb porch light, was that I actually needed to be in front of the light to make it turn on. 
The arrangement of our house means that we can leave the front door and not be in front of the porch light for a couple of seconds, but we'd still like it to turn on before we get there so that it can light the way. 
Because I have a reolink camera on the door as well, I can detect when someone is in front of the door and turn on the light before they get in front of the house! 

The light itself is made by Govee. I already have a few Govee products around the house, 
so I picked up a porch light in the knowledge that it would probably come with the high quality I expect from Govee. 
It was about as easy as it could be to mount it on the wall. They come with mounting brackets, and once they're on the wall, you just slot them on. 
The lights even come with these little WayGo clips that make connecting up the wires a snap. 

To hook up the Govee products to Home Assistant, I'm using Govee2MQTT. I'll link below in the description some instructions on how to set that up.

Setting up Govee2MQTT is too long to get in to in this video, but if you're enjoying the video, be sure to leave a thumbs up, it really helps YouTube know it's a good video, and if you're interested in hearing me go in to more details on how to set up Govee2MQTT, or my Frigate setup, leave a comment letting me know! 

You can set the colour temperature on the wall lights. I prefer 5500 Kelvin, as that's close to natural sunlight. 
They claim 1500 lumen, and I'm always skeptical with such claims, as one lumen is supposed to be the equivalent of one candle, though I would say, these things on full brightness are uncomfortable to look at. 

I actually liked this light so much, I put one in my back garden as well! 

If you fancy picking up one (or two!) of these lights, I'll have an affiliate link in the description, which will give me a small kickback at no extra cost to you.

They also have a range of different `scenes`, which means you can set them up to look pretty and themed when there are seasonal events light Halloween or Christmas.

# Video links:
- Google Coral: https://amzn.to/49Ze8SS
- Govee wall lights: https://amzn.to/3DFGrtu
- Govee2MQTT: https://github.com/wez/govee2mqtt

# Video

You can watch the full video on YouTube here:
{{< youtube SlhU_mDVFgw >}}

# Support me to keep making videos

{{< figure src="/img/ko-fi-stamp.png" width="300" alt="Ko-Fi" class="float-right" link="https://ko-fi.com/smarthomeideas" >}}
  
If you like the work I'm doing, please drop a like on the video, or consider subscribing to the channel.

In case you're in a particularly generous mood, you can fund my next cup of coffee over on [Ko-Fi](https://ko-fi.com/smarthomeideas)

The links from some of my videos are affiliate links, which means I get a small kickback at no extra cost to you. It just means that the affiliate knows the traffic came from me.