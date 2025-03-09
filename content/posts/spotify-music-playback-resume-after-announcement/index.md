+++
date = '2025-01-25T00:00:00Z'
title = 'Resume Spotify music after an announcement'
+++

_This is a transcript from one of my [YouTube videos](https://www.youtube.com/@BensSmartHomeIdeas)_

---

# Video

You can watch the full video on YouTube here:
{{< youtube OIIvjIJT8Vk >}}

# Transcript
My wife listens to music using around the house on Google Home's, and very helpfully told me how annoying it was that any announcements stopped the music playback.
We have a few different announcements that happen throughout the house  and getting the music to resume afterwards was a little more tricky than I was expecting it to be. 

It basically involves 4 different parts:
- The official Spotify integration
- HACS, which is the Home Assistant Community Store
- The Spotcast integration from HACS ^c84645
- A yaml script, written by a fairly active community member that goes by TheFes

The Spotify integration is fairly straight forward to get set up for a single account. 
- Go to the Spotify developer dashboard
-  tap `create app`
- set the redirect to your home assistant instance
- agree to the terms
- and finally tap save

If you have multiple accounts, it's a little more complicated, and the instructions aren't actually very clear.
If you load up an incognito window, and log in to Spotify, then go in to Home Assistant, go to the Spotify integration and tap on add service again, then it will add the other use account that you are logged in to Spotify with.

Once you have the Spotify integration set up, you'll need to set up Spotcast. This is a little bit more involved, but shouldn't take longer than a few minutes.

There's two cookies that you need to scoop up from a logged in Spotify session. They are `sp_key`, and `sp_dc`. The key is your identifier for your logged in session, and you should make sure you keep this secret. I believe the `dc` cookie tells it which data centre to use, but you should also make sure you keep this secret.

Multiple accounts here doesn't have any gotcha's, so you can just grab the cookies for each user, add them to your secrets and then link them to your Home Assistant configuration.

It's worth giving Spotcast a quick check once you've got it set up, and check that it works for each user. 
You can do this by heading over to developer tools, and creating a "start spotcast" action for each of the users that you have set up.

Now you have the ability to control Spotify from Home Assistant, and specifically you can control Spotify on any cast devices on your network, too! 

You're now in a good position to set up the script so it can resume after an announcement. What the script is basically doing is taking a snapshot of the user playing a Spotify item, playing the announcement, then setting the state of the user playing the item back on to the cast device.

You need to have packages enabled in Home assistant, if you haven't done this yet, you can just add these lines in to your home assistant `configuration.yaml`
Grab the script from the repo, and dump it in your packages folder, or create a new file, and copy the contents over.
It might look big and scary at first, but it's just the first 40 lines or so that are configurable, and it's actually pretty straight forwards.
This is how I configured mine.
I set my primary spotcast user.
I created some speaker groups that match what I have in Google Home. They are using the entity names from the Cast integration in Home Assistant.
I enabled the automation. 
In the docs, it says the automation can be flaky, but from my experience, it works pretty much every time.
I commented out the volume change, because I set the volumes on a nightly automation for the different rooms.

And now, when you send announcements, your music will keep playing after!

Which means your automation will be.

If you made it this far in the video, thank you for watching, and I wish you well on your home automation journey!

# Support me to keep making videos

{{< figure src="/img/ko-fi-stamp.png" width="300" alt="Ko-Fi" class="float-right" link="https://ko-fi.com/smarthomeideas" >}}
  
If you like the work I'm doing, please drop a like on the video, or consider subscribing to the channel.

In case you're in a particularly generous mood, you can fund my next cup of coffee over on [Ko-Fi](https://ko-fi.com/smarthomeideas)

The links from some of my videos are affiliate links, which means I get a small kickback at no extra cost to you. It just means that the affiliate knows the traffic came from me.