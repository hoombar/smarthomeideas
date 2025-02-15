+++
date = '2024-12-23T00:00:00Z'
title = 'Boost hot water while exercising!'
+++

_This is a transcript from one of my [YouTube videos](https://www.youtube.com/@BensSmartHomeIdeas)_

---

# Video

You can watch the full video on YouTube here:
{{< youtube 95_d6OqZk4E >}}

# Transcript
You know it, I know it, and despite what some nutters out there on the internet will tell you, cold showers suck! Home Automation doesn’t have to be reserved for when you’re at home. In fact, I love that my house takes care of things while I’m not there!

I train something called Brazilian Jui Jitsu, and because it's a workout, I want a hot shower when I get home, but I don't want to have to remember to pull out my phone and press a button to boost the hot water when I'm there. 

Instead, I set up a zone around the dojo, so that my smart home knows when I'm training, and will do it for me. 
This automation also has a high family approval factor, because it will also boost the hot water while my wife is at the climbing wall so that she can have a hot shower when she gets back. 

If you’re new to the channel, my name's Ben, and I’m a software engineer who's spent, probably a little too much time automating my house with home assistant. If you like exploring new home automation ideas, then you’re in the right place. 

Zones are basically just geofences that you can set up in home assistant, and they're baked in by default, so there's no need to go installing anything extra in order to start using them. A zone is considered active for a user, when their device running the home assistant companion app is in that geofence. There's some potential for them to be flaky, because of some devices trying to optimise their battery by limiting location updates, but we'll get in to that in more detail later on in the video. 

To set up a zone, you navigate to Settings, Areas, labels and zones, select the `zones` tab, and tap the `add zone` button. That'll let you draw a circle to create a geofence around the area you are interested in, and setting an appropriate icon. 

The companion app needs to be running on your phone as well, and you need to make sure it has access to location services. If you open settings, companion app, manage sensors, scroll down to location sensors, and turn on `Location Zone` and `Background Location` 

Now you're set up with zones, and the companion app, you can start using them in your automations. I've got a hive thermostat, and I'm using that, but this would of course work for something like an Ecobee or a Nest. 

My automation is set up to make sure that I've been dwelling in the zone for a while before the hot water is boosted. I don't want to be driving past the dojo and for my boiler to kick in and waste energy. After a little bit of trial and error, I realised that you have to explicitly set enabled to true in the trigger step for the automation for the geofence to actually work when you add in some dwelling time.  

Now after 30 minutes of dwelling in one of these exercise spots, the hot water will kick in. 

There's a few other automations that I have which don't use a dwell time, but still use zones. 
One of these automation's will turn off potty reminders when I'm at the school drop off. The idea is that if I've dropped the kid off at nursery, then I don't want to be reminded about using the potty. 
Another automation will turn the heating off when we head to the inlaws. They live quite far away, and we normally visit for a couple of days, so it makes sense to turn off the hot water while we're there. The automation will of course do the reverse as well, so that hot water gets turned on as we head home. This is superior to the home and away automations that you can set up with smart thermostats, because you can add in some smart geographic considerations around how long it will take the hot water to heat, and how long for the house to warm up. 
You don't want your heating to turn back on when you get home, you want it to turn on so that it's warm when you arrive back home. 

If you're using an Android phone, it's worth knowing that it has a feature called `doze mode`. I'll add in some links down in the description if you want to read more about it, but basically, in a nutshell, if your phone detects that the screen is off, and not doing anything, it will put it in to a deeper sleep, and then batch actions when it wakes up again. 
This means notifications can be delayed, and, relevant to this video, location updates won't happen. 
There's a few things to change to make sure that geofences are tripped in a timely manner.
First, go in to app info, and make sure you have turned off `pause app activity if unused` 
Next, under app battery usage, make sure you've turned on `allow background usage` 
Finally, go in to `battery`, and `battery saver`, open up `adaptive battery`, and make sure `use adaptive battery` is turned off.   
This will affect your battery life, because your phone won't be entering doze mode, but it will mean you get notifications quicker in some cases, and will also trigger zones much quicker. 
Depending on your setup, this might be a problem for you, but I'm still getting a full day with this setup - you can see I turned it on a few months ago, and there's a noticeable dip in the battery level I'm finishing a day on, but your mileage may vary depending on how you use your phone.  

# Support me to keep making videos

{{< figure src="/img/ko-fi-stamp.png" width="300" alt="Ko-Fi" class="float-right" link="https://ko-fi.com/smarthomeideas" >}}
  
If you like the work I'm doing, please drop a like on the video, or consider subscribing to the channel.

In case you're in a particularly generous mood, you can fund my next cup of coffee over on [Ko-Fi](https://ko-fi.com/smarthomeideas)

The links from some of my videos are affiliate links, which means I get a small kickback at no extra cost to you. It just means that the affiliate knows the traffic came from me.