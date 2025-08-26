+++
date = '2024-12-23T00:00:00Z'
title = 'Home Assistant zones'
+++

Note: _This is generated from a transcript from one of my [YouTube videos](https://www.youtube.com/@BensSmartHomeIdeas)_

---

# Unlock Your Smart Home's Potential: Mastering Home Assistant Zones

<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00006.jpg" alt="Unlock Your Smart Home's Potential: Mastering Home Assistant Zones demonstration at 6.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Unlock Your Smart Home's Potential: Mastering Home Assistant Zones at 6.0s" onclick="openImageModal('frame_00006.jpg', 'Unlock Your Smart Home's Potential: Mastering Home Assistant Zones demonstration at 6.0s')">
<img src="frame_00019.jpg" alt="Unlock Your Smart Home's Potential: Mastering Home Assistant Zones demonstration at 19.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Unlock Your Smart Home's Potential: Mastering Home Assistant Zones at 19.0s" onclick="openImageModal('frame_00019.jpg', 'Unlock Your Smart Home's Potential: Mastering Home Assistant Zones demonstration at 19.0s')">
</div>
You know it, I know it: home automation isn't just for when you're physically present. In fact, I love that my house takes care of things even when I'm not there. I train something called Brazilian Jiu-Jitsu, and after a workout, I always want a hot shower when I get home. But I don't want to have to remember to pull out my phone and press a button to boost the hot water while I'm there. Instead, I set up a zone around my Dojo, so my smart home knows when I'm training, and it just handles it for me. This automation also has a high family approval factor, because it will boost the hot water while my wife is at the climbing wall, ensuring she can have a hot shower when she gets back.

If you're new to the channel, my name's Ben. I'm a software engineer who's probably spent a little too much time automating my house with Home Assistant. If you like exploring new home automation ideas, then you're definitely in the right place.

## What Are Home Assistant Zones?

<img src="frame_00063.jpg" alt="What Are Home Assistant Zones? demonstration at 63.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="What Are Home Assistant Zones? at 63.0s" onclick="openImageModal('frame_00063.jpg', 'What Are Home Assistant Zones? demonstration at 63.0s')">
Zones are essentially geofences that you can set up directly within Home Assistant. They're included by default, so there's no need to install anything extra to start using them. A zone is considered active for a user when their device, running the Home Assistant companion app, is within that geofence. There's some potential for them to be a little bit flaky, because some devices try to optimize their battery usage by limiting location updates. But don't worry, we'll get into that in more detail later in this post.

## Setting Up Your First Zone

<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00092.jpg" alt="Setting Up Your First Zone demonstration at 92.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Setting Up Your First Zone at 92.0s" onclick="openImageModal('frame_00092.jpg', 'Setting Up Your First Zone demonstration at 92.0s')">
<img src="frame_00097.jpg" alt="Setting Up Your First Zone demonstration at 97.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Setting Up Your First Zone at 97.0s" onclick="openImageModal('frame_00097.jpg', 'Setting Up Your First Zone demonstration at 97.0s')">
</div>
<img src="frame_00111.jpg" alt="Setting Up Your First Zone demonstration at 111.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Setting Up Your First Zone at 111.0s" onclick="openImageModal('frame_00111.jpg', 'Setting Up Your First Zone demonstration at 111.0s')">
To set up a zone, you'll navigate to **Settings**, then **Areas, Labels & Zones**. Select the **Zones** tab and tap the **Add Zone** button. This will let you draw a circle to create the geofence around the area you're interested in.

The companion app needs to be running on your phone, and it's crucial to ensure it has access to location services. To do this, open the companion app's settings, go to **Manage Sensors**, scroll down to **Location Sensors**, and turn on both **Location Zone** and **Background Location**. Now that you're set up with zones and the companion app, you can start using them in your automations!

## Practical Automation Examples with Zones

<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00128.jpg" alt="Practical Automation Examples with Zones demonstration at 128.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Practical Automation Examples with Zones at 128.0s" onclick="openImageModal('frame_00128.jpg', 'Practical Automation Examples with Zones demonstration at 128.0s')">
<img src="frame_00137.jpg" alt="Practical Automation Examples with Zones demonstration at 137.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Practical Automation Examples with Zones at 137.0s" onclick="openImageModal('frame_00137.jpg', 'Practical Automation Examples with Zones demonstration at 137.0s')">
</div>
<img src="frame_00170.jpg" alt="Practical Automation Examples with Zones demonstration at 170.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Practical Automation Examples with Zones at 170.0s" onclick="openImageModal('frame_00170.jpg', 'Practical Automation Examples with Zones demonstration at 170.0s')">
I've got a high-efficiency hot water system, and I'm using zones to manage it, but this would, of course, work for something like an Ecobee or similar smart thermostat. My automation is set up to make sure I've been dwelling in the zone for a little while before the hot water is boosted. I don't want to be driving past the dojo and have the boiler kick in and waste energy.

After quite a bit of trial and error, I realized that you have to explicitly set `enabled: true` in the trigger step for the automation for the geofence to actually work when you're adding some dwelling time.

I have a few other automations that don't use a dwell time, but they still leverage zones effectively. One of these automations will turn off potty reminders when I'm at the school drop-off. The idea is, if I've dropped the kid off at nursery, then I don't want to be reminded about using the potty. You know the drill: "Don't forget to let the tiny human take a potty break before it's a puddle party!"

Another automation will turn the heating off when we head to the in-laws. They live quite far away, and normally we visit for a couple of days, so it makes sense to turn off the hot water while we're there. The automation, of course, will do the reverse as well, so that the hot water gets turned on as we head home. This is superior by far to the basic home and away automations that you get with typical smart thermostats, because you can add in some smart geographic considerations around how long it will take the hot water to heat and how long for the house to warm up. You don't really want your heating to be turning back on *as* you get home; you want it to turn on so it's warm by the time that you arrive back.

## Optimizing Zone Performance on Android Devices

<img src="frame_00212.jpg" alt="Optimizing Zone Performance on Android Devices demonstration at 212.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Optimizing Zone Performance on Android Devices at 212.0s" onclick="openImageModal('frame_00212.jpg', 'Optimizing Zone Performance on Android Devices demonstration at 212.0s')">
<img src="frame_00238.jpg" alt="Optimizing Zone Performance on Android Devices demonstration at 238.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Optimizing Zone Performance on Android Devices at 238.0s" onclick="openImageModal('frame_00238.jpg', 'Optimizing Zone Performance on Android Devices demonstration at 238.0s')">
<div style="display: flex; justify-content: center; gap: 5px; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; width: 50%; float: right; flex-wrap: wrap;">
<img src="frame_00244.jpg" alt="Optimizing Zone Performance on Android Devices demonstration at 244.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Optimizing Zone Performance on Android Devices at 244.0s" onclick="openImageModal('frame_00244.jpg', 'Optimizing Zone Performance on Android Devices demonstration at 244.0s')">
<img src="frame_00249.jpg" alt="Optimizing Zone Performance on Android Devices demonstration at 249.0s" style="width: calc(50% - 2.5px) !important; height: auto !important; object-fit: cover; border-radius: 4px; display: block !important; margin: 0 !important; cursor: pointer !important;" title="Optimizing Zone Performance on Android Devices at 249.0s" onclick="openImageModal('frame_00249.jpg', 'Optimizing Zone Performance on Android Devices demonstration at 249.0s')">
</div>
<img src="frame_00266.jpg" alt="Optimizing Zone Performance on Android Devices demonstration at 266.0s" style="width: 50%; float: right; margin-left: 20px; margin-bottom: 15px; margin-top: 10px; border-radius: 4px; cursor: pointer;" title="Optimizing Zone Performance on Android Devices at 266.0s" onclick="openImageModal('frame_00266.jpg', 'Optimizing Zone Performance on Android Devices demonstration at 266.0s')">
If you're using an Android phone, it's worth knowing that there's a feature called Doze Mode. I'll add some links down in the description if you want to read more, but basically, in a nutshell, if your phone detects that the screen is off and you're not doing anything, it will put it into a deeper sleep and then batch actions when it wakes up. Again, this means notifications can be delayed, and relevant to this video, location updates won't happen as frequently.

There are a few things you can change to make sure that your geofences are tripped in a timely manner.
1. First, go into the app info for the Home Assistant companion app and make sure you've turned off **Pause app activity if unused**.
2. Next, under **App battery usage**, make sure that you've turned on **Allow background usage**.
3. Finally, go into **Battery** and **Battery Saver** settings, open up **Adaptive Battery**, and make sure **Use adaptive battery** is turned off.

This will, of course, affect your battery life because your phone won't be entering Doze Mode as aggressively, but it will mean that you get notifications quicker in some cases and it will also trigger zones much more quickly. Depending on your setup, this might be a problem for you, but I'm still getting a full day of battery life with this setup. I enabled this setting a few months ago, and while there's a noticeable dip in the battery level, the improved responsiveness is worth it for me.

If you enjoyed this video, please throw a thumbs up down below – it really helps the channel out! And what are you using zones for if you've implemented them? Let me know down below in the comments. Until next time, I'll see you!

# Support me to keep making videos

{{< figure src="/img/ko-fi-stamp.png" width="300" alt="Ko-Fi" class="float-right" link="https://ko-fi.com/smarthomeideas" >}}
  
If you like the work I'm doing, please drop a like on the video, or consider subscribing to the channel.

In case you're in a particularly generous mood, you can fund my next cup of coffee over on [Ko-Fi](https://ko-fi.com/smarthomeideas)

The links from some of my videos are affiliate links, which means I get a small kickback at no extra cost to you. It just means that the affiliate knows the traffic came from me.

# Video

You can watch the full video on YouTube here:
{{< youtube 95_d6OqZk4E >}}


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
        max-width: 100%;
        max-height: 100%;
        padding: 5px;
    }
    
    #imageModal #modalImage,
    #imageModal .modal-content #modalImage,
    .post-content #imageModal #modalImage {
        max-height: 95vh;
        max-width: 98vw;
        min-width: 90vw;
        min-height: 70vh;
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
        padding: 2px;
    }
    
    #imageModal #modalImage,
    #imageModal .modal-content #modalImage,
    .post-content #imageModal #modalImage {
        max-height: 98vh;
        max-width: 99vw;
        min-width: 95vw;
        min-height: 80vh;
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
const transcriptData = [["You know it, I know it, and despite what some nutters out there on the internet will tell you, culture is so. Home automation doesn't have to be reserved when you're at home, in fact. I love that my house takes care of things while I'm not there. I train something called", "Brazilian Jiu-Jitsu and because it's a workout, I want a hot shower when I get home, but I don't want to have to remember to pull out my phone and press a button to boost the hot water while I'm there. Instead, I set up a zone around with Dojo, so my smart home knows when I'm training,", "and it will just do it for me. This automation also has a high family approval factor, because it will boost the hot water while my wife is at the climbing wall, so that she can have a hot shower when she gets back. If you're new to the channel, my name's Ben, I'm a software engineer", "who's spent probably a little bit too much time automating my house with home assistant. If you like exploring new home automation ideas, then you're in the right place."], ["Zones are basically just geofences that you can set up in home assistant, and they're baited in by default, so there's no need to go installing anything extra in order to start using them. A zone's considered active for a user when their device running the home assistant companion app", "is in that geofence. There's some potential for them to be a little bit flaky, because some devices try to optimize their battery usage by limiting location updates, but we'll get into that in a little more detail for everyone in the video. To set up a zone, you navigate to settings,", "areas, labels and zones, select the zones tab and tap the add zone button, and that will let you draw a circle to create the geofence around the area that you're interested in. The companion app needs to be running on your phone as well, it needs to make sure it has access to location services.", "Few open settings, companion app, manage sensors, scroll down to location sensors, and turn on a location zone and background location. Now you're set up with zones and the companion"], ["and turn on a location zone and background location. Now you're set up with zones and the companion app, you can start using them in your automations. I've got a high firm start and I'm using that, but this would of course work for something like an eco-via one. My automation set up to make", "sure I've been dwelling in the zone for a little while before the hot water's boosted. I don't want to be driving past the dojo and for the boiler to kick in and waste energy. After literally as a trial and error, I realised that you have to explicitly set enabled to true in the trigger step", "for the automation for the geofence to actually work when you're adding some dwelling time. There's a few other automations that I have which don't use a dwell time, but they still use zones. One of these automations will turn off potty reminders when I'm at the school drop off.", "The idea is if I've dropped the kid off at nursery, then I don't want to be reminded about using the potty. Don't forget to let the tiny human take a potty break before it's a puddle party. Another automation will turn the heating off when we head to the in-laws. They live quite far away", 'and normally we visit for a couple of days, so it kind of makes sense to turn off the hot water'], ["and normally we visit for a couple of days, so it kind of makes sense to turn off the hot water while we're there. The automation of course will do the reverse as well, so that the hot water gets turned on as we head home. This is superior by far to the home and away automations that you get", "with typical smart thermostats, because you can add in some smart geographic considerations around how long it will take, the hot water to heat and how long for the house to warm up. You don't really want your heating to be turning back on as you get home. You want it to turn on", "so it's warm by the time that you arrive back. If you're using an Android phone, it's worth knowing that there's a feature called Does Mode. I'll add in some links down in the description if you want to read more, but basically in a nutshell, if your phone detects, let the screen is off and you're", "not doing anything, it will put it into a deeper sleep and then back shactions when it wakes up. Again, this means notifications can be delayed and relevant to this video location updates won't"], ["Again, this means notifications can be delayed and relevant to this video location updates won't happen. There's a few things to change to make sure that the geofences are tripped in a timely manner. First, go into the app info and make sure you've turned on pause app activity if unused.", "Next, under app battery usage, make sure that you've turned on allow background usage. Finally, go into battery and battery saver up, open up adaptive battery and make sure use adaptive battery is turned off. This will of course affect your battery life because your", "phone won't be entering Does Mode, but it will mean that you get notifications quicker in some cases and it will also trigger zones much more quickly. Depending on your setup, this might be a problem for you, but I'm still getting a full day with this setup. You can see I tend it on a few months ago,", "but there's a noticeable dip in the battery level. If you enjoyed the video, throw a thumbs up, down below really helps the channel out and what are you using zones for if you use them? Let me know down below in the comments. Until next time, I'll see you."]];

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