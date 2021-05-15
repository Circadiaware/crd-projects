# Pupillary light reflex screener of photosensitivity

* NEW OBJECTIVE SCREENING TOOL: a cross-platfrom iOS and Android smartphone app using camera and LED to do pupillometry, to maybe diagnose circadian rhythm disorders AND assess response to light therapy:
	* REFS: Other potential avenues are occular tests, by checking the pupils area or the pupil's contraction reflex to sudden bright light exposure, since it's the same ipRGC cells and their melanopsin photopigment that control both pupil's contraction reflex and circadian rhythm shifting in response to light exposure. Indeed, genetically muting the melanopsin pigment severely impairs both the pupillary light reflex and circadian alignment. In practice, pupillometry can be done with measuring either or both the amplitude and speed of contraction post light exposure as they are both highly correlated, with the light intensity, starting size of the pupils before the test and the age of the participant being irrelevant. This makes sense since the ipRGC cells have a low dynamic range of 2 orders of magnitude, so they are easily saturated with a moderately bright light. However, a study on DSPD found that brighter light was more effective to diagnose. Smartphone-based camera and LED flash apps have been demonstrated to provide an objective and equivalent assessment as infrared-based pupillometry, with reduced cost and increased versatility (see here which explains how they did with pictures, and here for a similar iOS app).
		* Second paper app on iOS: http://www.sensitometer.com/
		* another dedicated tool: https://www.reflexapp.io/wp-content/uploads/2020/05/EvaluationofReflexanditsApplicationsinMedicine_KS_RR_JS_V2..pdf
		* ME: "In practice, I expect some tweaking will have to be done after we see the first results in use, but given the WebGL app simply uses the screen (setting it white and at full brightness) instead of a LED and it's sufficient to elicit the PLR, I think that a phone's LED will be more than enough to elicit the same response under virtually any indoor condition, which is what the app will expect (because of course when outdoors, the user will already have their pupil contracted)"
	* BEST REF: The pupillary light reflex distinguishes between circadian and non-circadian delayed sleep phase disorder (DSPD) phenotypes in young adults https://doi.org/10.1371/journal.pone.0204621
		* "Circadian DSPD patients showed a significantly faster pupillary light reflex than both non-circadian DSPD patients and healthy controls. Non-circadian patients and healthy controls did not differ significantly."
		* "The strongest predictor of DSPD phenotype was the mean constriction velocity to bright light (AUC = 0.87)."
			* Other methods were max pupil constriction to dim and bright light.
		* TODO: But dspd pupil at what time they took the measurements? Maybe the circadian DSPD had a different response simply because they were exposed to the test during their circadian night? Does melatonin/circadian rhythm modulate pupil light reflex?
	* PLAN: record a video if enough quality, or photos otherwise and interpolate, and autodetect and calculate pupil size AND velocity to recontract after bright light. Initial pupil size irrelevant. Using both allows to double check, because they are highly correlated, so by measuring both we have less chances of mistake.
	* Implement survey: allow to send data to researchers, ask what disorders they have, if formally diagnosed or suspected. Will be anonymous, or can put e-mail address if agree to be recontacted if additional infos required. Agree that may be used in a research study (anonymized data of course, and no personal data is ever collected nor transmitted except e-mail address if provided but will not be communicated to anybody apart from this study's researchers).
	* GOAL: will at least allow to assess responsiveness to ligh therapy, but potentially also diagnose circadian rhythm disorders??? Objectively???
	* Other refs:
		* Modeling human pupil dilation dynamics: https://doi.org/10.1515/phys-2019-0047
	* BEST CRITICAL LIBRARIES:
		* NO, it's NOT OPENSOURCE: WebGL autosegmentation pupillometry, can be integrated in react-native? Also shows we can use the screen (white and black background) to simulate a flash: https://github.com/jeeliz/jeelizPupillometry#experimental-results
			* It's not opensource: https://github.com/jeeliz/jeelizGlassesVTOWidget/issues/2
		* Compatibility with react-native maybe through expo-gl: https://github.com/expo/expo/tree/master/packages/expo-gl#expo-gl
	* Assessment of feasibility by yetscrape: feasable, but we'll have to implement everything. Difficult. See the discussion below for more infos.

### Additional scientific context, excerpt from Vlidacmel protocol

What if light therapy does not work for you? Well in the future definitely researchers and clinicians should try to devise test of circadian photosensitivity, to check if an individual is likely responsive to light therapy before they acquire such a device. One way, that the individuals can already do by themselves, is to maintain a sleep diary, and observe if a pattern of [relative coordination](https://pubmed.ncbi.nlm.nih.gov/23814347/) can be observed (ie, faster freerunning when out of phase with the day-night cycle, and slower when in phase). Since relative coordination is due to sunlight exposure, this is strongly suggestive of responsiveness to light therapy. Other potential avenues are occular tests, by checking the [pupils area](https://www.ncbi.nlm.nih.gov/pubmed/30311830) or the [pupil's contraction reflex to sudden bright light exposure](https://doi.org/10.1371/journal.pone.0204621), since it's [the same ipRGC cells and their melanopsin photopigment that control both pupil's contraction reflex and circadian rhythm shifting in response to light exposure](https://pubmed.ncbi.nlm.nih.gov/28656675/). Indeed, [genetically muting the melanopsin pigment severely impairs both the pupillary light reflex and circadian alignment](https://pubmed.ncbi.nlm.nih.gov/27992553/). In practice, [pupillometry can be done with measuring either or both the amplitude and speed of contraction post light exposure as they are strongly correlated, with the light intensity, starting size of the pupils before the test and the age of the participant being irrelevant](https://doi.org/10.1167/iovs.12-10881). [A study on DSPD found that the pupil light reflex could diagnose circadian DSPD, as they had a faster pupil contraction speed than those without a circadian misalignment, and with brighter light being more effective to diagnose](https://doi.org/10.1371/journal.pone.0204621). This strongly suggest that individuals with DSPD are hyper photosensitive, and it's safe to assume the same for non-24. Interestingly, [individuals with autism were also found to display a pupillary light reflex with more amplitude and correlated with their sensitivity to stimuli (sensory processing disorder)](https://doi.org/10.1016/j.ridd.2014.11.019), which is even more intriguing considering [circadian rhythm disorders are very common for people with autism to the point some scientists suggest that circadian rhythm disorders underlie autism](https://www.spectrumnews.org/news/sleep-struggles-autistic-people-may-genetic-basis/). Smartphone-based camera and LED flash apps have been demonstrated to provide an objective and equivalent assessment as infrared-based pupillometry, with reduced cost and increased versatility (see [here](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4950215/) and [here](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6166694/)).

### Feasibility assessment by yetscrape

```
yetscrape Snoovatar
yetscrape01:39
Moreover I'd be interested in joining in on the development of the React Native application. While I have no real experience in React Native, I recently learned the basics, and I think it would be the ideal framework for developing such an application.

Is there a central place of coordination for all those projects? Like a Discord server, telegram group, IRC?
26 janv.
lrq3000 Snoovatar
lrq300005:24
Hello again! Great to see you excited about our collective project!
lrq3000 Snoovatar
lrq300005:30
So unfortunately I am responsible for launching this collective project and... I'm currently ill with yet another disease worse than N24 that I acquired recently, so this delayed all my work... But I'm getting treated and it seems to finally work, so hopefully I can get back to N24 projects soon (but I can give no ETA unfortunately yet).

So the plans is that there will be a dedicated website and github organization, editable by the community. It's almost done, I just need to make the finishing touches, which I estimate to take ~ a week of work, but no ETA since I stopped working on N24 projects since December unfortunately.

For live chat and coordination, apart from the github organization for developers, we are discussing on our discord, here is the invite: https://discord.gg/dzzT546

If you are interested in the charting library, ask Kizari there, I'm sure he must still be around. I will be back there too as soon as I can. And feel free to talk about n24 (not just software development), we've got a lovely community there full of very nice people :-)

So to be updated when I'll be back on it, you can either hang around the discord or I can tell you by chat here as you prefer.
BTW I also had another idea: an objective diagnosis tool for DSPD and non-24 using smartphones and their LEDs to measure the pupil's contraction reflex to sudden bright light. I have found studies showing the feasability and a WebGL library to do this along with autodetecting the pupil size using deep learning from a webcam feed, so this could be used as a basis I think for a react-native app that would run on smartphones and desktop
If that's a project you'd like to give a shot I can give you more infos and links to resources, as I won't work on it right now (more urgent projects such as the circadian rhythm estimator from biosignals - that's something only I can do for now since it costs a lot to get the devices...)
yetscrape Snoovatar
yetscrape20:20
Thanks for the info! I hope you can recover from your other disease soon.

In regards to the diagnosis tool for DSPD and Non-24: Is it really possible to realiably diagnose those disorders using bright light only? Is there any evidence to suggest that Non-24 is caused primarily or solely due to differences in light processing? I'm not aware of all the research out there, but I'd be interested to learn more about it.
27 janv.
lrq3000 Snoovatar
lrq300002:47
yes!
don't worry if you're not aware of all the research, there is just so much information and buried deep in scientific journals archives, even after more than a year of almost exclusively studying the scientific literature (and being a trained scientist myself), I still have so much to read and discover! The research on sleep and circadian rhythm sciences is HUGE!
lrq3000 Snoovatar
lrq300002:56
For the infos about using bright light to diagnose circadian rhythm disorders, see what I wrote (with links to the studies):

* https://lrq3000.github.io/non24article/SleepNon24VLiDACMel.html#diagnosis-methods-for-circadian-rhythm-disorders

* https://lrq3000.github.io/non24article/SleepNon24VLiDACMel.html#light-therapy-parameters,-luminette-and-photic-history
to summarize, it's the same eyes cells, the ipRGC cells, that control the circadian rhythm and the pupil contraction response to bright light
so by analyzing the pupil's contraction speed and amplitude, we can infer that someone may be more or less sensitive to bright light, which applies to their circadian rhythm too
we know that, there are studies, now the question is what values determine what circadian rhythm disorders
but we have a big community of N24 and DSPD, so it would be very easy to share the app, and ask people to report their results (or just add an anonymous survey in the app)
We can easily reach 20 to 30 N24 and much more for DSPD, then I can certainly find typical sleepers who would be willing to participate, and that would be more than sufficient to derive meaningful statistics and values to differenciate each group
after there is always a possibility this will not work in practice, but there is already one study which has done that for DSPD and it worked
so I'm not sure this will be able to differenciate between DSPD and non24, but at least it should be able to detect a circadian rhythm disorder, which would already be awesome! But I highly suspect that non24 will be differentiable
lrq3000 Snoovatar
lrq300003:34
Anyway, this app would have another purpose: to detect if the user is responsive to light therapy. This is the best therapy we have available, but too often people are afraid of buying the relatively costly device because they don't know if it will work for them. The pupil light reflex allows to know if this will work, without them having to spend a dollar.
So to summarize, the pupil light reflex app would serve to: 1- potentially diagnose a circadian rhythm disorder, 2- detect if the user is responsive to bright light therapy.
wow sorry I talk too much lol, I stop here, please let me know if you have any other question :-)
yetscrape Snoovatar
yetscrape05:37
Hey,

this sounds like a really interesting idea. I have took a quick glance at the DSPD qPLR study, and I have a few concerns regarding the technical feasability of your proposal:

1. The study uses a professional pupilometer to measure the PLR. The only qPLR app I found on the internet is [Reflex](https://www.reflexapp.io/). According to its [whitepaper](https://www.reflexapp.io/wp-content/uploads/2020/05/EvaluationofReflexanditsApplicationsinMedicine_KS_RR_JS_V2..pdf), it uses the flashlight on the back of the device in order to initiate the PLR response.

In order to achieve any meaningufl adoption of the app, even among a very small N24 / DPSD community, most Android devices need to be supported. And here's the catch:
The iOS camera API, which the Reflex app uses, allows apps to regulate the brightness of the flash light on the back, which would be necessary to measure PLR given different brightnesses.
Android on the other hand does not offer such an API due to the inconsistent camera implementations among different vendors, so you cannot manually set the LED brightness to a specific setting. And worse even: You likely cannot determine the brightness of the LED.
So in the case of qPLR using the flashlight on Android phones, not only would you not be able to change or influence the brightness of the light stimuli during PLR measurement, you also couldn't account for differences in brightness levels among different phone manufactures. The only way I can think of to counteract this problem would be to try to measure the brightness of the flashlight using the rear camera of the device, but I think the results would be extremely poor.

What I don't know is how important the brightness of the light stimuli is when measuring PLR, or if it could be ignored completely.
Since I lack any biology background I cannot answer this question, but maybe you have an opinion on that?

2. Realizing a project of such dimensions could prove very hard, especially if we aren't experienced developers.
I think that we could quickly reach the limitations of React Native and would need to do a lot of native module development in Java and Swift (or Objective C), especially when it comes to interacting with device APIs (such as the camera API).

That's not to say I wouldn't give it a try - this might be a fantastic (preliminary?) diagnostic tool (and quite frankly vastly superior than any diagnostic tools available in my country).
I'm also on your Discord server (Quinn#4449) if you prefer this means of communication, and on [GitHub](https://github.com/quinn-dev).
And unfortunately Reddit's chat doesn't seem to use Markdown, so the links are ugly... :/
yetscrape Snoovatar
yetscrape05:50
I'll try to dig deeper into your Notebook and the studies related to light therapy after my next sleep session.
And btw, the work you already did on Non-24 is awesome! I have already stumbled upon some of your writings on melatonin onset therapy in the past.
lrq3000 Snoovatar
lrq300007:14
thank you very much for your kind words :-)
And thank you very much for doing this feasability research and your feedback!
lrq3000 Snoovatar
lrq300007:26
About your first point, I also had a look at existing or previously done pupillometry apps, and I have found at least two:

* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4950215/
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6166694/
* the 2nd paper's iOS app is still online at: http://www.sensitometer.com/

So it seems feasible. Now about the 2 technical issues: LED brightness and pupil image segmentation. The second is already solved by the WebGL project I linked before, so the question is whether it can be implemented in a mobile app.

About the first issue of LED brightness, theoretically this shouldn't matter: indeed, the ipRGC cells have only a low dynamic range of 2 orders of magnitude, so they are easy to saturate with a moderately bright LED. In addition, a study shown that the light intensity, during the test and prior, are apparently irrelevant: https://doi.org/10.1167/iovs.12-10881
In practice, I expect some tweaking will have to be done after we see the first results in use, but given the WebGL app simply uses the screen (setting it white and at full brightness) instead of a LED and it's sufficient to elicit the PLR, I think that a phone's LED will be more than enough to elicit the same response under virtually any indoor condition, which is what the app will expect (because of course when outdoors, the user will already have their pupil contracted)
about your 2nd question, yes, the core issue is that we will be using the smartphone camera and not an infrared one to capture the pupil, so we need to do image segmentation. It can be quite complicated, so that's why the feasability of this project relies on whether we can reuse the WebGL library. If yes, the rest is easy (making an app that activates the LED or turns the screen white at full brightness if the phone doesn't have a LED for a precise duration, then switches it off and records the pupil's contraction as a video or a set of photos).
for reminders I am referring to this WebGL library: https://github.com/jeeliz/jeelizPupillometry#experimental-results
so yeah I am myself new to react native development so I don't know if WebGL can be used, especially on phones
mmmm seems like it should be possible using expo-gl
and yes sorry for the inconvenience, I'll try to get back to the Discord as soon as possible, I like to go there but currently my vigilance is so fleeting that I cannot plan any period where I will be sufficiently conscious for long enough to hold a conversation
so I work very asynchronously
whenever my vigilance permits
yetscrape Snoovatar
yetscrape20:25
So first of all, it's great if we don't have to worry about LED brightness. This would be an absolute nightmare...
yetscrape Snoovatar
yetscrape20:45
Second, I don't think we can reuse the mentioned WebGL library:
- The library relies heavily on browser APIs which are not available in React Native
- The library does not appear to be "really" open-source. You can only find a minimized version of the library in the repository, and the source code is not provided. So if we had to do significant chances (which we will), we are pretty much out of luck. The best chance we have would be to either contact the developer and ask them to release the full source, or mock the browser APIs and use the library, which would require an absolutely monstrous amount of work (similar to implementing your own headless web browser in React Native).
- Without the source code, one cannot say if the WebGL part will work in React Native. In my opinion, it could work with a significant amount of tweaking.

Jeeliz, the library's developer, made it quite clear that they do not plan to fully open-source it: https://github.com/jeeliz/jeelizGlassesVTOWidget/issues/2
Even if they open-sourced it, it might not help us that much when implementing it in React Native, since the source code currently isn't user-friendly, according to their statements, which also implies a lack of documentation.

But even if all those obstacles could be dealt with, we have one final problem with the library which we might not be able to overcome: We cannot meet the hardware requirements.
The project advises using a 4K CCTV camera (which doesn't block infrared light) together with a dedicated GPU (recommendation is GTX960M).
They also note: "Indeed, the video processing is quite heavy and most mobile devices won't be powerful enough. Moreover, a mobile device may move too much and the tracking may be lost from time to time."

These are obstacles we might not be able to overcome, at least with this library.
I will do some further research, especially regarding performance maximization. Given the WebGL implementation already uses a very-low level algorithm for GPU-accelerated computations, I have my doubts that we will be able to improve performance significantly.
Also: Feel free to answer whenever you have the time and capacity. It sounds like your other disease is really rough, so prioritize your health and wellbeing.
yetscrape Snoovatar
yetscrape21:04
This study does seem to indicate quite clearly that even tech from the stone age (Galaxy S4) is sufficient to measure PLR: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4950215/
I think the algorithms and technologies used are very different when comparing the WebGL library to said study. So in other words: I think it's definitely technically feasable to implement what we need. But we likely won't profit from the WebGL library - I presume we will need to implement most of the algorithms ourselves.
Today
lrq3000 Snoovatar
lrq300005:17
yetscrape, thank you so much!
you did a wonderful job! thank you very much for all your research on this!
mmmm it's sad that they don't really opensource it, I thought Apache 2.0 was an opensource license, my bad...
so yeah that complicates things, but I think it's still doable, but it's just going to be a lot more time consuming
in this app they had to use fancy neural networks because they acquire images from the webcam, including the participants' full head
with a smartphone camera, it can be positioned close to the eyes so as to limit the complexity of the captured scene
this is what we would target I think
and I think it's what the apps that already succeeded in implementing mobile pupillometry did
```
