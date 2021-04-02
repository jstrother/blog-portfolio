---
title: Towards A Greener Web
description: How coders can help fight climate change
img: /img/blog/Climate_Change.png
alt: Climate Change
author:
  name: Jim Strother
  bio: A full-stack JavaScript developer who focuses on making the web as eco-friendly as possible
hashtag: ClimateChange
---

## The Issue at Hand

Many of us, and rightly so, are concerned about the effects of the changing climate and how that affects our planet. This has spurred many attempts at averting potential disaster from solar cells and wind turbines to carbon sequestration and nuclear fusion. But, what can we as web developers do to help? After all, the web is just a collection of 1's and 0's, right? You might be forgiven for thinking there isn't much we can do in this industry and that we should continue business as usual.

And what exactly is the issue with those 1's and 0's anyway? In and of themselves, nothing. But, by 2025, [20% of the world's electricity][1] is expected to be consumed by data centers creating about 3.5% of global emissions. With the internet not going anywhere anytime soon, it seems like our industry is destined to be one of the largest perils to our planet and there's no way to counter that.

## Suggestions for Solutions

But, what if I told you there are three simple things we could do to help out? These  really only require a few minutes of extra effort for the most part. First, we need to measure the estimated emissions our sites produce. This lets us know, instead of guess, how good or bad things are. Second, we need to be more efficient with our coding practices. More data transferred means more electricity used, and if that's from dirty sources it's a problem. Last, we have to find green web hosts who either get their energy from renewable sources or compensate in one way or another for emissions created.

### Getting a Feel for the Problem

Unless you know how big the problem is, how do you know how to go about fixing it? I'll admit, it has been difficult for us as developers, and even designers, to know the impact our sites are having. In the past few years, a new tool was released to help us: [Website Carbon Calculator][2]. I ran it on [my site][3] the other day and it showed me that I'm not doing too bad, but then again, I'm not exactly running [ESPN][4] either. It makes sense that a simple portfolio site with an attached blog is pretty efficient, especially as compared to the behemoth that covers the world of sports. But, now we know, right?

(Note: give those last two links a few seconds to load, the carbon calculator runs each time you click the link.)

### Getting Better at What We Do

Ok, so now we have an idea of how much our own sites contribute to the problem. What do we do now? Honestly, a lot of the same things we've been doing so far to increase the speed of our sites- optimization and minification. Even sending a site to a user's computer takes electricity. The bigger the site, the more energy it takes to send. So, we can use a lot of the same tools we've been using for years to improve user experience.

Great! So, we're done with this part, right? Well,not exactly. There are other things we could do. Front-end frameworks like React and Vue are great at what they do. The main issue I take with them is that they bundle a lot of extra code you didn't write along with your site. This increases the amount that your server has to ship, and your user to load. Quite possibly the best framework is the relatively new, yet quickly growing in popularity, [Svelte][5]. A great breakdown between the various front-end frameworks can be found [here at Dev.to][6].

In short, Svelte has a compile step where it takes all of your component code and, well, _compiles_ it into pure HTML, CSS, and JS. And only the fully optimized code for your site to work. The overall bundle size is less than the other three, thereby reducing not only the amount your user needs to load, but also the amount of energy needed to ship it. And THAT means energy savings, no matter how small, that add up with each page view. Imagine if ESPN built itself in Svelte and how much they could save!

### Getting Ourselves Out There

Now, we need to host our site so people can find it, and here we are coming back to those same data centers we first talked about in the opening paragraphs. With these places sucking up so much energy, how do we find the diamonds in the rough? What are we even looking for?

The most obvious thing, which you've already thought of because you're a genius like me, is to find a web host who is powered solely by green energy. Boom. Problem solved. Wait, not so fast! There is another option to just plain ol' green energy- [renewable energy credits (RECs)][7]. Quickly, a REC is a certificate (or credit) that guarantees that the electricity you bought is from a renewable source and encourages the growth of renewable power. As only a certain amount of energy is produced this way, there is a limited number at any time. Also, they are non-transferrable, which makes sense because you use the power they represent. Click the link above for a better explanation than I can give.

According to this [TechRadar article][8], one of the best, if not the best, green web host is [GreenGeeks][9]. These guys offset their carbon output by 300%. (300%!!) Mainly, they do this via those RECs. Worth a look!

What if you need something more than a simple web host, like some sort of cloud server? [Google Cloud][10] might be the answer here. Google purchases enough RECs to offset [the entire company's carbon output][11]. That's a lot of energy.

## Conclusion

I hope I've given you something to think about, at least, when it comes to how our industry impacts global climate change, and the actual level of impact we have. Some things we've already been doing and didn't know it was the right thing in more ways than one (minimization and optimization). Others maybe something we haven't considered before, maybe because we weren't aware that a solution existed.

I know I have room for improvement on this site alone. At the time I'm writing this, it is hosted on Heroku and, for all my talk above, is not currently built in Svelte. But as I go along, I'll write further articles that detail the progress I'm making in going greener, and hopefully **inspire** you as well.

In the end, the solution to climate change will take more than just the simple actions I've outlined here. It will take action from all of us, in every way possible, to solve the existential threat climate change poses. Maybe, _hopefully_, this article gives you a piece of the road map out of this crisis.

[1]: https://www.theguardian.com/environment/2017/dec/11/tsunami-of-data-could-consume-fifth-global-electricity-by-2025

[2]: https://www.websitecarbon.com/

[3]: https://www.websitecarbon.com/website/jimstrother-com/

[4]: https://www.websitecarbon.com/website/espn-com-2/

[5]: https://svelte.dev/

[6]: https://dev.to/hb/react-vs-vue-vs-angular-vs-svelte-1fdm

[7]: https://www.energysage.com/other-clean-options/renewable-energy-credits-recs/

[8]: https://www.techradar.com/web-hosting/best-green-web-hosting

[9]: https://www.greengeeks.com/

[10]: https://cloud.google.com/

[11]: https://cloud.google.com/blog/topics/inside-google-cloud/announcing-round-the-clock-clean-energy-for-cloud
