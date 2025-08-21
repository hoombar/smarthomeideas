+++
date = '2025-08-02T00:00:00Z'
title = 'Troubleshooting zigbee networks'
+++

Note: _This is generated from a transcript from one of my [YouTube videos](https://www.youtube.com/@BensSmartHomeIdeas)_

---

# Troubleshooting Zigbee Networks

<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00008.jpg" alt="Troubleshooting Zigbee Networks demonstration at 8.0s" style="width: calc(33.333% - 3.33px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Troubleshooting Zigbee Networks at 8.0s" onclick="openImageModal('frame_00008.jpg', 'Troubleshooting Zigbee Networks demonstration at 8.0s')">
<img src="frame_00018.jpg" alt="Troubleshooting Zigbee Networks demonstration at 18.0s" style="width: calc(33.333% - 3.33px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Troubleshooting Zigbee Networks at 18.0s" onclick="openImageModal('frame_00018.jpg', 'Troubleshooting Zigbee Networks demonstration at 18.0s')">
<img src="frame_00021.jpg" alt="Troubleshooting Zigbee Networks demonstration at 21.0s" style="width: calc(33.333% - 3.33px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Troubleshooting Zigbee Networks at 21.0s" onclick="openImageModal('frame_00021.jpg', 'Troubleshooting Zigbee Networks demonstration at 21.0s')">
</div>
Want to build a solid ZigBee network that works reliably? Or perhaps you're currently battling an existing mesh network that just won't cooperate. Either way, you've landed in the right spot! Today, I'm going to walk you through everything from the absolute basics, like why your coordinator's placement is so crucial, all the way through to deciphering errors in your log files. We'll cover coordinators, the difference between routers and end devices, channel selection, interference, and yes, we'll even dive into those log files that people often overlook. Trust me, they play a key role in diagnosing issues and building a rock-solid setup. As we go, the topics will get progressively more advanced, so stick with me!

## The Foundation: Your ZigBee Coordinator

<img src="frame_00085.jpg" alt="The Foundation: Your ZigBee Coordinator demonstration at 85.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="The Foundation: Your ZigBee Coordinator at 85.0s" onclick="openImageModal('frame_00085.jpg', 'The Foundation: Your ZigBee Coordinator demonstration at 85.0s')">
<img src="frame_00125.jpg" alt="The Foundation: Your ZigBee Coordinator demonstration at 125.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="The Foundation: Your ZigBee Coordinator at 125.0s" onclick="openImageModal('frame_00125.jpg', 'The Foundation: Your ZigBee Coordinator demonstration at 125.0s')">
Let's dive straight into the foundation of your network: your coordinator. I truly can't stress this enough: your coordinator is essentially the brain of your entire ZigBee network. Pick a poor one, and you'll likely be fighting connectivity issues for months. Choose a good one, and everything just seems to work – well, mostly! We'll get into the nuances.

When it comes to selecting a coordinator, you absolutely need to do your research. And I mean *properly* research it. Don't just grab the first cheap USB stick you find on Amazon. Instead, read reviews, check compatibility, and explore community forums. The few extra pounds you spend here will save you weeks of frustration down the line.

Currently, I'm using the SLZB 06M. I'll include a link for it in the description below. It's not actually a USB stick; it's a Power over Ethernet (PoE) coordinator, and I absolutely love it. I would highly recommend it. It's been incredibly rock-solid for me, and the range is fantastic.

But here's the thing: even if you have the best coordinator in the world, its placement matters more than you might think. We'll cover that in a bit more detail later in this post.

### The USB Extension Cable Lifesaver

If you're using a USB coordinator – and many of you are – you absolutely need to use a USB extension cable. Why? Because USB 3 ports can cause electromagnetic interference (EMI) that disrupts your ZigBee channel. This isn't some theoretical problem either; it's a very real issue. There's an excellent video demonstrated by the team at Nabu Casa that clearly shows how moving a USB 3 cable closer to a coordinator can actually stop it from working.

This is the kind of subtle issue that will drive you absolutely mad, trying to figure out why your devices keep dropping offline. It's often erratic and incredibly difficult to troubleshoot. So, definitely make sure you're using a shielded extension cable. A simple extension cable costs next to nothing, and it can literally save your entire network.

### Optimal Coordinator Placement

Beyond the cable, think about placing your coordinator away from USB 3 ports and ideally somewhere central in your home. Consider your home's layout: where are your devices actually going to be, and what obstacles will be between them? A central location on the ground floor might not help much if half of your devices are upstairs. If the middle of your house is surrounded by solid walls, remember that 2.4 GHz signals might not travel through them particularly well.

## Understanding Device Limits and Mesh Networks

<img src="frame_00189.jpg" alt="Understanding Device Limits and Mesh Networks demonstration at 189.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Understanding Device Limits and Mesh Networks at 189.0s" onclick="openImageModal('frame_00189.jpg', 'Understanding Device Limits and Mesh Networks demonstration at 189.0s')">
<img src="frame_00204.jpg" alt="Understanding Device Limits and Mesh Networks demonstration at 204.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Understanding Device Limits and Mesh Networks at 204.0s" onclick="openImageModal('frame_00204.jpg', 'Understanding Device Limits and Mesh Networks demonstration at 204.0s')">
Now, here's something that catches a lot of people out: connecting devices directly to your coordinator might seem fast and convenient, but be aware that coordinators have a device limit. You should always check the documentation for your specific coordinator to find its exact device limit. This is generally fine when you're just starting out with your ZigBee network and have a handful of devices. However, if you get hooked and end up with 80 devices on your network, you'll start to see problems. What you're ultimately aiming for is a robust mesh network.

## Channel Selection: A Critical Decision

<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00226.jpg" alt="Channel Selection: A Critical Decision demonstration at 226.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Channel Selection: A Critical Decision at 226.0s" onclick="openImageModal('frame_00226.jpg', 'Channel Selection: A Critical Decision demonstration at 226.0s')">
<img src="frame_00229.jpg" alt="Channel Selection: A Critical Decision demonstration at 229.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Channel Selection: A Critical Decision at 229.0s" onclick="openImageModal('frame_00229.jpg', 'Channel Selection: A Critical Decision demonstration at 229.0s')">
</div>
Let's talk about something that will save you massive headaches if you get it right from the start: channel selection. ZigBee operates on the 2.4 GHz frequency, which is the same frequency as your Wi-Fi, your microwave, and half the other electronics in your house. The key is finding a channel that doesn't clash with everything else.

I highly recommend using an app like Wi-Fi Analyzer (again, there's a link in the description) to check what channels your surrounding 2.4 GHz Wi-Fi networks are using. You want to pick a ZigBee channel that's as far away from busy Wi-Fi channels as possible.

Here's the critical bit: make this decision at the very beginning. If you change your ZigBee channel later, you'll have to re-pair every single device in your network. Trust me, you absolutely don't want to have to do that with 50-plus devices!

## ZigBee Device Types: Routers vs. End Devices

<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00261.jpg" alt="ZigBee Device Types: Routers vs. End Devices demonstration at 261.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="ZigBee Device Types: Routers vs. End Devices at 261.0s" onclick="openImageModal('frame_00261.jpg', 'ZigBee Device Types: Routers vs. End Devices demonstration at 261.0s')">
<img src="frame_00262.jpg" alt="ZigBee Device Types: Routers vs. End Devices demonstration at 262.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="ZigBee Device Types: Routers vs. End Devices at 262.0s" onclick="openImageModal('frame_00262.jpg', 'ZigBee Device Types: Routers vs. End Devices demonstration at 262.0s')">
</div>
<img src="frame_00314.jpg" alt="ZigBee Device Types: Routers vs. End Devices demonstration at 314.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="ZigBee Device Types: Routers vs. End Devices at 314.0s" onclick="openImageModal('frame_00314.jpg', 'ZigBee Device Types: Routers vs. End Devices demonstration at 314.0s')">
Now, let's get into the integrity of how the network actually works. You've got three types of devices: your coordinator (which we've covered), and then you also have routers and end devices. Understanding the difference is crucial for building a reliable network.

**Routers** are typically devices that have constant power, such as your smart plugs, light switches, and smart bulbs. Be careful, though, because not all powered devices are routers. You should definitely check the documentation for each device, as it's a dangerous assumption to make that all powered devices will be routers. Some manufacturers make mains-powered devices that only act as end devices, which is pretty useless for building a strong mesh network. I got caught out here by buying some of the Eukara H1 light switches, assuming they would work as routers.

**End devices** are your battery-powered sensors, like motion sensors, door sensors, and temperature sensors – that kind of stuff. These little guys don't route traffic like other devices. They simply connect to your network and send their data, but they won't route packets for other devices.

Typically, devices can connect to any router in range. However, some devices can be quite picky about which routers they connect to. If you try to pair your device in its final position, that tends to help with the routing. Don't pair them next to your coordinator and then move them across the house. They'll try to maintain that original connection, even if there's a better route nearby.

## The ZigBee Mesh: Patience is Key

<img src="frame_00397.jpg" alt="The ZigBee Mesh: Patience is Key demonstration at 397.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="The ZigBee Mesh: Patience is Key at 397.0s" onclick="openImageModal('frame_00397.jpg', 'The ZigBee Mesh: Patience is Key demonstration at 397.0s')">
<img src="frame_00408.jpg" alt="The ZigBee Mesh: Patience is Key demonstration at 408.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="The ZigBee Mesh: Patience is Key at 408.0s" onclick="openImageModal('frame_00408.jpg', 'The ZigBee Mesh: Patience is Key demonstration at 408.0s')">
Now, the mesh itself is where ZigBee gets really clever. ZigBee devices form their mesh automatically. It sounds great, and it is, but there's something that most people don't realize: it takes time. And I'm not just talking hours or even days; some ZigBee networks can take weeks to fully establish themselves and become optimized. This is probably the hardest part for most people because everyone wants things to work perfectly right away. But your devices are constantly learning about each other, figuring out the best routes, and adapting to changes in their environment. Patience is absolutely key here.

### Dealing with "Sticky" Devices

Something that may well save you hours of troubleshooting is knowing that some devices are what I call "sticky." Aqara devices are notorious for this. They latch onto the first router they connect to and refuse to jump to a better router, even if the signal strength is terrible. That's why pairing in the final position for these kinds of devices is especially important.

Also, don't overload your routers. They have limits on how many devices they can handle, typically. The good news is you can actually pair end devices with specific routers if you know what you're doing. I use Zigbee2MQTT, and there's an option to open up pairing on the network for specific devices, so I highly encourage trying that out.

## Advanced Troubleshooting: Diving into Log Files

<img src="frame_00436.jpg" alt="Advanced Troubleshooting: Diving into Log Files demonstration at 436.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Advanced Troubleshooting: Diving into Log Files at 436.0s" onclick="openImageModal('frame_00436.jpg', 'Advanced Troubleshooting: Diving into Log Files demonstration at 436.0s')">
<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00441.jpg" alt="Advanced Troubleshooting: Diving into Log Files demonstration at 441.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Advanced Troubleshooting: Diving into Log Files at 441.0s" onclick="openImageModal('frame_00441.jpg', 'Advanced Troubleshooting: Diving into Log Files demonstration at 441.0s')">
<img src="frame_00462.jpg" alt="Advanced Troubleshooting: Diving into Log Files demonstration at 462.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Advanced Troubleshooting: Diving into Log Files at 462.0s" onclick="openImageModal('frame_00462.jpg', 'Advanced Troubleshooting: Diving into Log Files demonstration at 462.0s')">
</div>
<img src="frame_00568.jpg" alt="Advanced Troubleshooting: Diving into Log Files demonstration at 568.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Advanced Troubleshooting: Diving into Log Files at 568.0s" onclick="openImageModal('frame_00568.jpg', 'Advanced Troubleshooting: Diving into Log Files demonstration at 568.0s')">
Okay, this is what separates the beginners from the advanced users: deep diving into log files. Most people tend to ignore their logs, but the logs are basically telling you a story about what's happening on your network. Trust me, once you know how to read them, troubleshooting becomes so much easier.

Let me show you an example. Here, I have the entire database with all of my ZigBee devices. We've got the configuration, which basically gives us a mapping of those ZigBee devices to a friendly name, and then we have the log file, which is where all the fun things are happening.

If we look at a "root error many to one failures" entry, and use this as an example of something that's going wrong, you'll see it happens quite a lot throughout the logs. This is one of the things we wanted to dive into, but there are so many instances of this log entry, and we don't really want to go through and manually figure out how often this is happening.

So, what we're going to do is take the log file, and we're going to use the ID that we get from here. We'll figure out from that ID that it's a particular manufacturing device or a device with this manufacturing name. It's going to give us an IEEE address, and then we can use that IEEE address to look up in here what the friendly name is. For example, you can see here it's the "Snug LED Vance socket." So, we can map this error, which happens a lot for this particular ID, all the way back to the Snug LED Vance socket.

I don't want to do that manually, so I'm going to use my friend Claude (an AI assistant). Here's what I made earlier: I've uploaded a bunch of my old log files and old configurations so you can see the "before and after." I've basically taken this prompt and said, "Using the old logs, the old configurations, and the old database, find this particular error and various other errors, and then go through and basically do all of that mapping." This way, we can figure out what it looks like. Claude is going to go through and do its magic, and we're basically going to get this artifact. It's going to tell us the friendly name, the IEEE address, and basically the errors, how critical those errors are, how often they're occurring in the logs, and stuff like that. So, you can leverage this quite easily to figure out what's going on with your network.

I also used, if I go back to my network, the newer version after I've basically gone through and fixed a bunch of my issues. I ran the same analysis and basically got a similar result, but you can see here the numbers are much lower. There are basically only some very, very low-severity errors. Some of them were actually due to things like configuration timeouts, and Claude is very useful here and basically tells me this is not much of an issue. It's a fairly transient issue that happens during startup, and it's going to give me a few recommendations. In conclusion, the cleanup was highly successful – brilliant!

So, I'm still going to use the logs, and I'm going to look through them to get some hints on what I might be looking for. Then, I'm just going to use AI to help me enumerate those instances and figure out what needs to happen next.

## Final Thoughts

Look, building a reliable ZigBee network isn't rocket science, but it does require a bit of patience and understanding of how these devices actually work together. Start with a good coordinator, choose your channels carefully, understand the difference between routers and end devices, and most importantly, learn to read your logs. Do this right, and you'll have a great network that's incredibly reliable, responsive, and just works. Get it wrong, and you'll be constantly fighting connectivity issues and wondering why your smart home feels like a dumb home.

If this post helped you out, don't forget to hit that like button and subscribe for more smart home content. Check out the description for links I mentioned, and leave a comment down below: what's your biggest ZigBee challenge? Did I cover everything, or do you think I missed anything? Let me know! I read every comment and often turn them into future videos, so don't be shy. Until next time, happy automating, and I'll catch you in the next one!

# Links:
Here are the links mentioned in the video:
- WiFi analyser - https://play.google.com/store/apps/details?id=abdelrahman.wifianalyzerpro&hl=en_GB
- SMLight slzb06m - https://s.click.aliexpress.com/e/_om72EQS
- Home Assistant video showing USB 3 interference - https://www.youtube.com/watch?v=tHqZhNcFEvA

Here are some of the zigbee devices I'm using in my network:
- Innr smart plugs - https://amzn.to/44EqjDC
- Sonoff USB coordinator - https://amzn.to/4lyLA7x
- Candeo dimmer switches - https://amzn.to/4lCR957
- LEDVance smart plug - https://amzn.to/44U9zH7
- Aqara vibration sensors - https://s.click.aliexpress.com/e/_omTArqA
- Tuya motion sensors - https://s.click.aliexpress.com/e/_o2EC0dY
- Tuya buttons - https://s.click.aliexpress.com/e/_olnvxnY
- Tuya contact sensors - https://s.click.aliexpress.com/e/_oDzeGXy
- Aqara motion sensors - https://s.click.aliexpress.com/e/_onEYiiw
- Aqara buttons - https://s.click.aliexpress.com/e/_ooUGcXy
- Aqara door sensors - https://s.click.aliexpress.com/e/_oB3h0gI

# Video

You can watch the full video on YouTube here:
{{< youtube hksjJxe2hcY >}}

# Support me to keep making videos

{{< figure src="/img/ko-fi-stamp.png" width="300" alt="Ko-Fi" class="float-right" link="https://ko-fi.com/smarthomeideas" >}}
  
If you like the work I'm doing, please drop a like on the video, or consider subscribing to the channel.

In case you're in a particularly generous mood, you can fund my next cup of coffee over on [Ko-Fi](https://ko-fi.com/smarthomeideas)

The links from some of my videos are affiliate links, which means I get a small kickback at no extra cost to you. It just means that the affiliate knows the traffic came from me.

<!-- Image Modal for Click-to-Enlarge -->
<style>
/* Modal responsive styles for better mobile experience */
#imageModal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.8);
    cursor: pointer;
}

#imageModal .modal-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    max-width: 98%;
    max-height: 95%;
    padding: 0;
    margin: 0;
}

#imageModal #modalImage,
#imageModal .modal-content #modalImage,
.post-content #imageModal #modalImage {
    width: auto;
    height: auto;
    max-height: 92vh;
    max-width: 95vw;
    min-width: 80vw;
    min-height: 60vh;
    object-fit: contain;
    border-radius: 8px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.5);
    display: block;
}

#modalCaption {
    color: white;
    text-align: center;
    margin-top: 10px;
    font-size: 16px;
    padding: 0 10px;
}

.modal-close {
    position: absolute;
    top: 15px;
    right: 20px;
    color: white;
    font-size: 40px;
    font-weight: bold;
    cursor: pointer;
    user-select: none;
    z-index: 1001;
}

/* Mobile optimizations */
@media (max-width: 768px) {
    #imageModal .modal-content {
        max-width: 99%;
        max-height: 98%;
    }
    
    #imageModal #modalImage,
    #imageModal .modal-content #modalImage,
    .post-content #imageModal #modalImage {
        max-height: 95vh;
        max-width: 98vw;
        min-width: 90vw;
        border-radius: 4px;
    }
    
    #modalCaption {
        font-size: 14px;
        margin-top: 8px;
    }
    
    .modal-close {
        top: 10px;
        right: 15px;
        font-size: 35px;
    }
}

/* Ultra-small screens (phones in portrait) */
@media (max-width: 480px) {
    #imageModal .modal-content {
        max-width: 100%;
        max-height: 100%;
    }
    
    #imageModal #modalImage,
    #imageModal .modal-content #modalImage,
    .post-content #imageModal #modalImage {
        max-height: 98vh;
        max-width: 100vw;
        min-width: 95vw;
        border-radius: 2px;
    }
    
    .modal-close {
        top: 5px;
        right: 10px;
        font-size: 30px;
    }
}
</style>

<div id="imageModal" onclick="closeImageModal()">
    <div class="modal-content">
        <img id="modalImage" src="" alt="">
        <div id="modalCaption"></div>
    </div>
    <span class="modal-close" onclick="closeImageModal()">&times;</span>
</div>

<script>
function openImageModal(src, alt) {
    document.getElementById('imageModal').style.display = 'block';
    document.getElementById('modalImage').src = src;
    document.getElementById('modalCaption').textContent = alt;
    document.body.style.overflow = 'hidden';
}

function closeImageModal() {
    document.getElementById('imageModal').style.display = 'none';
    document.body.style.overflow = 'auto';
}

// Close modal on Escape key
document.addEventListener('keydown', function(event) {
    if (event.key === 'Escape') {
        closeImageModal();
    }
});
</script>

<!-- Transcript Toggle Functionality -->
<div id="contentToggle" style="position: fixed; top: 20px; right: 20px; z-index: 999; background: rgba(0,0,0,0.8); padding: 10px; border-radius: 5px;">
    <button id="toggleBtn" style="background: #667eea; color: white; border: none; padding: 8px 16px; border-radius: 4px; cursor: pointer; font-size: 14px;">
        Toggle Transcript
    </button>
</div>

<script>
let showingTranscript = false;
const toggleBtn = document.getElementById('toggleBtn');

// Store transcript data for sections
const transcriptData = [["Right, so you want to know how to build a proper Zigbee network that actually works reliably, or maybe you're doing battle with your current existing mesh network. Either way, you're in the right place because today we're going to cover everything from", "the absolute basics, like why your coordinates placement matters, all the way through to numerating errors in your logs. We'll talk coordinators, routers versus end devices, channel selection, interference, and yes, we'll even dive into log files which", "often people tend to ignore but they play a key role in diagnosing a shins and building a block solid setup. So as the video goes on, topics are going to get progressively more advanced. Let's dive straight into the foundation, your coordinator. Now, I can't stress this enough.", "The coordinators basically the brain of your entire Zigbee network. Pick a rubbish one and you're going to be fighting connectivity issues for months. Pick a good one and everything just works. Well, kind of. We'll get into that.", "So when it comes to choosing a coordinator, do your research and I mean properly research it. Don't just grab the first USB stick you find on Amazon because it's cheap. Read reviews, check compatibility, look at the community forums. The few extra pounds that you spend here", "is going to save you weeks of frustration later. What I'm using right now is the SLZB 06M. I'll pop the link down in the description for that. It's actually not a USB stick."], ["I'll pop the link down in the description for that. It's actually not a USB stick. It's a power over Ethernet coordinator and I absolutely love it. I would highly recommend them. It's been absolutely rock solid for me and the range is fantastic but here's the thing. Even if", "you've got the best coordinator in the world, placement matters more than you might think. We'll cover that a little bit more later on in the video. If you're using a USB coordinator and there's lots of people out there who are, you absolutely need to use a USB extension cable. Why? Because", "USB 3 ports can cause electromagnetic interference through your Zigbee channel. This isn't some theoretical problem either. It's actually real. There's a really good video that was demonstrated by the people at Nabakaza who show that moving USB cable closer to a coordinator actually stops it", "from working. This is the sort of thing that will drive you absolutely mad, trying to figure out why your devices keep on dropping off line and it's going to be very erratic and difficult to troubleshoot. So definitely make sure that you're using a shielded extension cable. A simple", "extension cable costs next to nothing and it can literally save your entire network. Get the USB 3 ports and ideally somewhere central in your home. Think about your home's layout. Where are the devices actually going to be and what's going to be between them. A central location on", 'the ground floor might not help much if half of your devices are upstairs. In the middle of your house is surrounded by solid walls then considered at 2.4 gigahertz signals might not travel through them'], ["house is surrounded by solid walls then considered at 2.4 gigahertz signals might not travel through them particularly well. Now here's something that catches a lot of people out. Connecting directly to your coordinator might seem fast and like a good idea but be aware there is a device limit on coordinators.", "You should check the documentation exactly for what the device limit is on your coordinator. This is generally okay when you're just starting out in your Zigbee network and you've got a handful of devices on them but if you get the bug and you end up with 80 devices on your network", "you'll start to see problems. What you're ultimately aiming for is a mesh network. Right let's talk about something that will save you massive headaches if you get it right from the start which is channel selection. Zigbee works on 2.4 gigahertz which is the same frequency as your Wi-Fi,", "your microwave and half the electronics in your house. The key is finding the channel doesn't clash with everything else. Use an app like Wi-Fi analyzer. Again there's a link down in the description to check what channels you're surrounding 2.4 gigahertz Wi-Fi they're using. You want to pick a Zigbee", "channel that's far away from busy Wi-Fi channel as possible. Here's the critical bit. Make the decision at the start. If you change your Zigbee channel later you'll have to repair every single device in your network and trust me you don't want to have to do that with 50 plus devices.", "Now let's get into the integrity of how the network actually works. You've got three types of devices. You've got your coordinator which we've covered and you've also got routers and end"], ["devices. You've got your coordinator which we've covered and you've also got routers and end devices. Understanding the difference is crucial for a reliable network. Routers are typically devices that have constant power so your smart plugs, your light switches, your smart bulbs.", "Be careful though because not all powered devices are routers. You should definitely check the documentation for that and it's a dangerous assumption to make that all powered devices will be routers. Some manufacturers make mains powered devices that only act as end devices which is pretty", 'useless for building a strong mesh network. I got caught out here by buying some of the Eukara H1 light switches assuming that they would work as routers. End devices are your battery powered sensors like motion sensors, door sensors, temperature sensors, that kind of stuff. These little guys', "don't route traffic like other devices. They just connect your network and send their data but they won't route packets to other devices. Typically devices can connect to any router in range. Some bit can be quite picky about which routers they connect to though. If you try and pair your device", "in their final position that tends to help with the routing. Don't pair them next to your coordinator and then move them across the house. They'll try and maintain the original connection even if there's a better route nearby. Now the mesh itself is where ZigBee gets really clever.", "ZigBee devices form their mesh automatically. It sounds great and furry. There's something that most people don't realise though. It takes time and I'm not just talking hours or even days but"], ["most people don't realise though. It takes time and I'm not just talking hours or even days but some ZigBee networks can take weeks to establish themselves so that they're fully optimised. This is probably the hardest part for most people because everyone wants things to work perfectly", 'right away but your devices are constantly learning about each other and figuring out the best routes and adapting changes in their environment. Patience is absolutely key here. Something that may well save you hours of troubleshooting is knowing that some devices are', "what I call sticky so a car or devices in the tourist for this. They latch onto the first router they connect to and they're refused to jump to a better router even if the signal strength is terrible. That's why pairing in the final position for these kind of devices is especially", "important. Don't overload routers either. They have limits on how many devices they can handle typically. The good news is you can actually pair and devices with specific routers if you know what you're doing. I use ZigBee to MQTT and there's an option to open up pairing on the network for", "specific devices so I highly encourage trying that out. Okay this is what separates the beginners from the advanced users is deep diving into log files. Most people will tend to ignore their logs but the logs are basically telling me a story about what's happening on your network and trust me once", "you know how to read them troubleshooting becomes so much more easy. Okay so here we have the entire database with all of the ZigBee devices in. We've got the configuration which will basically give us"], ["database with all of the ZigBee devices in. We've got the configuration which will basically give us a mapping of those ZigBee devices over to a friendly name and we have the log file which is where all the fun things are happening. So if we look at the root error many to one failures and we look at", "this as an example of one of the things that's going wrong. You can see it happens quite a lot throughout the logs and this is one of the things that we wanted to dive into but there is all of these log file instances and we don't really want to go through and manually figure out how often", "this is happening. So what we're going to do is take the log file and we're going to use the ID that we get from here and we're going to figure out from here what that ID is and that will tell us it's this particular manufacturing device or device with this manufacturing name it's going to give", "us an i-triple address and then we can use that i-triple address to look up in here what the friendly name is so you can see here it's the snug LED Vance socket so we can map this error which happens a lot for this particular ID all the way back to the snug LED Vance socket. So I don't"], ["which happens a lot for this particular ID all the way back to the snug LED Vance socket. So I don't want to do that manually so I'm going to use my friend Claude and here's what I made earlier. What I've done is I've uploaded a bunch of some of the old log files and the old configurations", "so you can see it before and after and I've taken basically this prompt and I've said using the old logs the old configurations and the old database find this particular error and various other errors and then go through and basically do all of that mapping so we can figure out what it looks like.", "It's going to go through and do its magic and we're basically going to get this artifact and it's going to tell us what the friendly name is the i-triple address and basically the errors and how critical those errors are, how often they're occurring in the logs and stuff like that.", "So you can leverage this quite easily to figure out what's going on with your network. I also used, I'll go back to my network, the newer version after I've basically gone through and fixed a bunch of my issues and I ran the same analysis and basically got a similar result", "but you can see here the numbers are much lower. There's basically only some very very low severity errors. Some of them were actually due to things like configuration timeouts and Claude's going to be very useful here and basically tell me this is basically not much an issue."], ["Claude's going to be very useful here and basically tell me this is basically not much an issue. It's a fairly transient issue that happens during startup and it's going to tell me a few recommendations and in conclusion the cleanup was highly successful, brilliant. So I'm still going", "to use the logs and I'm going to look through the logs to get some hints on what I might be looking for and then I'm just going to use AI to help me enumerate those instances and figure out what needs to happen next. Look, building a reliable Zigbee network isn't rocket science but it does require", "a bit of patience and understanding on how these devices actually work together. Start with a coordinator, choose your channels carefully, understand the difference between routers and end devices and most importantly, let them read your logs. Do this right and you'll", "have a great network that's incredibly reliable, responsive and just works. Get it wrong and you'll be constantly fighting connectivity issues and wondering why your smart home feels like a dumb home. If this video helped you out don't forget to hit that like button and subscribe for more smart", "home content. Check out the description for links I mentioned and leave a comment down below, what's your biggest Zigbee challenge, did I cover everything, do you think I missed anything, let me know. I read every comment and I often turn them into future videos so don't be shy.", "Until next time, happy automating and I'll catch you in the next one."]];

// Store original content for each section
const originalSectionContent = {};

// Initialize: find all sections and store their original content
document.addEventListener('DOMContentLoaded', function() {
    const sections = document.querySelectorAll('h2, h3');
    sections.forEach((header, index) => {
        // Find all content between this header and the next header
        const sectionContent = [];
        let nextElement = header.nextElementSibling;
        
        while (nextElement && !nextElement.matches('h2, h3')) {
            if (nextElement.tagName === 'P' || nextElement.tagName === 'DIV') {
                sectionContent.push(nextElement);
            }
            nextElement = nextElement.nextElementSibling;
        }
        
        // Store original content for each paragraph in this section
        const sectionId = header.textContent.toLowerCase().replace(/[^a-z0-9]/g, '-');
        originalSectionContent[sectionId] = [];
        
        sectionContent.forEach(element => {
            originalSectionContent[sectionId].push({
                element: element,
                originalHTML: element.innerHTML
            });
        });
    });
});

toggleBtn.addEventListener('click', function() {
    const sections = document.querySelectorAll('h2, h3');
    
    sections.forEach((header, sectionIndex) => {
        const sectionTitle = header.textContent.trim();
        const sectionId = sectionTitle.toLowerCase().replace(/[^a-z0-9]/g, '-');
        
        // Find paragraphs in this section
        const sectionContent = [];
        let nextElement = header.nextElementSibling;
        
        while (nextElement && !nextElement.matches('h2, h3')) {
            if (nextElement.tagName === 'P' || nextElement.tagName === 'DIV') {
                // Skip image containers
                if (!nextElement.querySelector('img') && nextElement.innerText.trim().length > 20) {
                    sectionContent.push(nextElement);
                }
            }
            nextElement = nextElement.nextElementSibling;
        }
        
        if (showingTranscript) {
            // Switch back to formatted content
            if (originalSectionContent[sectionId]) {
                originalSectionContent[sectionId].forEach(item => {
                    item.element.innerHTML = item.originalHTML;
                });
            }
        } else {
            // Switch to transcript content
            const transcriptForSection = transcriptData[sectionIndex] || [];
            
            sectionContent.forEach((element, paragraphIndex) => {
                if (transcriptForSection[paragraphIndex]) {
                    element.innerHTML = transcriptForSection[paragraphIndex];
                }
            });
        }
    });
    
    showingTranscript = !showingTranscript;
    toggleBtn.textContent = showingTranscript ? 'Show Formatted' : 'Toggle Transcript';
});
</script>