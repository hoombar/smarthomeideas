+++
date = '2025-02-24T00:00:00Z'
title = 'Using Chat GPT to create home assistant automations'
+++

_This is a transcript from one of my [YouTube videos](https://www.youtube.com/@BensSmartHomeIdeas)_

---

# Video
You can watch the full video on YouTube here:
{{< youtube agaB10PI2Fc >}}

# Transcript

I'm sure you're already aware of Chat GPT, and some of the things it's capable of. I'm going to show you how I use it to help me with home automations, from getting help with Home Assistant templates, to writing code to generate output I can use in scripts..

There's some things you should be aware of. I'm going to dive in to some topics like how up to date the information is, what a context window is, custom GPTs, and what RAG, or retrieval augmented generation is.

If that sounds interesting, stick around, and we'll dive in.

Let's start with how up to date the information is. We're going to give Chat GPT a very simple prompt, we're going to ask it "Can you turn off encryption for specific locations in a Home Assistant backup?". And, you can see, straight out of the box, it says no, it's not possible. However, if you look at one of the more recent releases of Home Assistant, you can see that one of the feature that was actually added, was the ability to turn of encryption for specific locations.

Because that text wasn't available at the time the model was built, that means that the model doesn't include that knowledge, and it doesn't understand that it is actually possible to do this.

That begs the question "how up to date _is_ the information?".
Well, that's a hard question to answer, because it will depend on the model you are running, and the interface or software layer that is interacting with the model. You might get a different answer between Chat GPT, Deepseek, and Claude. Actually, since I started making this video, Open AI, the company behind Chat GPT have actually released an update that will web search and augment the answer with the results. Ultimately, if you're running your own LLM locally through Ollama, then you will still need to be aware of this, but if you're using something like Chat GPT, it shouldn't be a concern unless you're looking at something cutting edge. 

Next, let's take a quick look at what a context window is.

If you enter some text in to the chat, you'll notice that the LLM "learns" from the text you input. As a simple example, if I tell it my name, it can then augment answers later on with that knowledge. Context windows have a limited size, which is where RAG, or Retrieval Augmented Generation comes in. You can add a lot more context using RAG, for example, I wrote a Python script to scrape the releases from the Home Assistant blog, and write the content in to Markdown files using `Crawl4AI`.

With all of the markdown files downloaded, I can add them as knowledge to Open Web UI. You can also create custom GPTs in Chat GPT if you pay for it, which will effectively do the same thing. Open Web UI is free, and I'm interested in running LLMs locally, so that's what I'm using, but it's the same concept.
You can see I've uploaded all of the markdown files, and now I can query specifically that collection to augment the generation of text using the knowledge in those markdown files.. Now it knows, without having to tell it in a context window, that you can turn off encryption for specific locations.

Ok, now that the quick primer on expectations around the LLMs knowledge is out of the way, let's dive in to some actual automation generation. I'm just going to use Chat GPT for this, as it's open, accessible, and free. The topics in this video aren't advanced enough to require specific coding models, like Qwen2.5-coder, so there isn't any need to complicate things with that, as Chat GPT actually does a fantastic job.

Imagine you want to create an automation with a condition which checks whether the automation has been run in the last 5 minutes. In the past, I might have trawled the Home Assistant forums looking for an answer, but by asking Chat GPT the correct prompt, it will generate the YAML for me.

Look at that. It's even given me an explanation of what the condition is doing, and why it works.
It tells me how to get the number of seconds from the timestamp.
Neat.

Maybe you aren't so familiar with YAML. That's not a problem, you can just use the current context to ask it some questions around the automation, like what does the opening `{{` and closing `}}` in the YAML mean?

And if we really want to get in to the weeds, we can just keep asking it questions, like "tell me more about template expressions".
Just like that, it's telling me that it's a template expression, and it's using Jinja2. This is a useful feature, because it now means that we're fuelled with the knowledge of what it is, and we can make our future prompts more specific, which will generally give you better results.

Ok, cool. So what else.

Something that could be quite fiddly and hard to get right first time would be sending a notification to your phone from a camera in your home assistant instance.
Let's see how well it fends here. Ok, it's given us the steps, and given us the YAML that we need for the automation. It's done a pretty decent job, it's definitely a good start, but I'd like the have the notification open the reolink app on my Android phone. I can ask it how to do that..

It's pretty impressive that it can get the package ID of the Reolink Android app. Even if you Google that, there's a reasonable amount of noise to sift through before you get the answer. If you ask Chat GPT that exact same question, there's a much clearer path to getting the answer.

Both of those automations are pretty neat, but you can do even more.

I have a setup that allows me to tap this kids button on my dashboard, which will power on the TV and choose a TV show for the kids to watch. A part of that script will pull up the keyboard on the TV and search for the show by effectively sending remote control commands to the TV. This basically means sending a lot of "right", "right", "down", "down", "down" commands, depending on what key you want to select on the keyboard. As you can imagine, it's quite a laborious task figuring out what combination of key presses are needed to punch in the text to search for a specific show, so I used Chat GPT to create some code that will generate the inputs.

It uses the Android TV Home Assistant integration, and the commands that need to be sent are, for example, `DPAD_LEFT` to move left, and `DPAD_CENTER` to select.

This is the prompt that I gave Chat GPT:
```
Given the following table, write a script in javascript that will start at 'q',
 and move one position for each selection of a letter. 
For each new letter selection, it will start at q. 
For each move, output the corresponding text:
- for right, output "- DPAD_RIGHT"
- for down, output "- DPAD_DOWN"

| q   | w   | e   | r   | t   | y   | u   | i   | o   | p   |
| a   | s   | d   | f   | g   | h   | j   | k   | l   |     |
|     | z   | x   | c   | v   | b   | n   | m   |     |     |

```

I expect the output of this prompt to generate the code which will let me paste in the outputs directly in to an automation.

I chose Javascript, because there's a bunch of online websites where you can just paste in javascript code and have it immediately execute, without the need to install anything. I'm going to run this in VSCode, as that's what I prefer, and this is just for educational purposes.

This is the output that it produced. Looks pretty good to me, and I can just tweak the show at the end of the script if I want to generate the inputs for another show. Now all I need to do it go back over to the kids tv script, find one of the existing shows, grab the yaml, duplicate it, and paste in the output I copied.

Just for kicks, we can also run the javascript code inside the LLM and get the output as well.

Let's see if it worked. 

Looks good to me!

This is a really broad topic, and I've already made a video about how I use AI to turn on my porch light. I plan on covering a lot more on how AI can be used around your smart home, so if that's something that interests you, then be sure to subscribe.

# Support me to keep making videos

{{< figure src="/img/ko-fi-stamp.png" width="300" alt="Ko-Fi" class="float-right" link="https://ko-fi.com/smarthomeideas" >}}
  
If you like the work I'm doing, please drop a like on the video, or consider subscribing to the channel.

In case you're in a particularly generous mood, you can fund my next cup of coffee over on [Ko-Fi](https://ko-fi.com/smarthomeideas)

The links from some of my videos are affiliate links, which means I get a small kickback at no extra cost to you. It just means that the affiliate knows the traffic came from me.