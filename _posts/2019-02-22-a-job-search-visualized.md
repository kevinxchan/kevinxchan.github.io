---
layout: post
title:  "A job search visualized"
description: Graphs, statistics, and summaries
date:   2019-02-22 09:35:00 -0800
categories: jekyll update
---

As eluded to on an earlier [post][job-search-journey-link] reflecting on my job search, I logged some data while I was applying to visualize it at the end. To keep things short, for each application I kept track of:

- the company name
- the position title
- the location
- the date applied
- whether or not I wrote a cover letter
- where I found the job
- the final response from the company
- the furthest stage of interviewing I got to 

I'll start off by exploring the latter three categories in more depth, and finish off with some other things I found interesting. All code to generate plots can be found [here][r-script-link], with the exception of the Sankey diagram, which I made [here][sankey].

In total, I applied to 98 jobs - let's see what this really looks like.

## Where to begin?

![source][source-final-img]
*All job posting outlets utilized, sorted from most to least amount of applications through that outlet.*

Conventional wisdom tells me that my chances of having a successful application would be maximized if I applied more frequently through my school's (UBC) job portal, but I tried not to limit myself. Instead, I tried to maximize my opportunities by browsing around some popular websites, applying where I saw fit. The data shows that the majority of my applications went through well known outlets such as LinkedIn, Glassdoor, and StackOverflow, accounting for 41.8% of my total applications. There doesn't appear to be any significance between which outlet I used and the final outcome, so the lesson here is to search far and wide.

Another source I used heavily was Neuvoo. I believe this is a lesser known website, and to be completely honest I don't remember how I stumbled upon it. Nevertheless, I signed up for job alerts through Neuvoo, where I was able to add fields tailored to me such as location and position title. At the time of writing this article, the alerts could only be set on a daily frequency, so every morning around 6 am I received emails about new (and sometimes old) postings which fit my search criteria. Now, waking up to emails with new job alerts everyday can be daunting (and can clutter your email), so it likely isn't for everyone. However, I found job alerts useful by cutting down the time I needed to spend manually looking for postings myself. 

Some last comments I'll make are on whether I applied online or in person. 15 of my applications were from contacting the company directly, rather than using third party outlets. However, some of those 15 were sent in person by attending my school's career fairs. Just simply speaking to a recruiter or engineer representing the company, handing out my resume, and leaving my contact information with them greatly improved my chances of getting an invitation to interview. When you speak to a company representative, you get the luxury of asking all your questions about the company's goals, culture, interview process, etc. and receive instant answers. At the same time, this gives you a chance to make a good impression and network. 

## The interview process

![stage][stage-final-img]
*Plot of frequency vs the furthest interview stage I got to. "Application" is synonomous with no response/no invitation to interview.*

Only 15 out of 98 applications resulted in some sort of secondary contact, whether it was an initial coding assessment, a phone screen, or an onsite interview. This may look like a low success rate, and it is. The reality is that there are lots of graduating students out there with brilliant minds all competing for the same jobs. Moreover, there has been an influx of people entering the software engineering industry, which further increases competition. But I don't believe competition is the only factor which plays a role here. There could be many reasons for a rejection - culture fit, skillset, experience, the list goes on. I tried not to focus too much on the numbers, and instead invested energy on bettering myself. Which brings me to my next point...

## The final decisions

![response][response-final-img]
*Final decisions from companies and their frequencies. Number of official offers are bolded in gray.* 

**Ouch**. Not my most proudest moment. Rejection hurts, but after a couple of times, I started to view it less under a hurtful lense. It's okay to fail, and I found myself learning a lot more from my mistakes, and started to become more prepared for subsequent interviews. On top of this, I also gained a ton more experience interviewing, and getting used to answering technical questions and questions about my past experience. Ultimately I (potentially) could've had more offers, but I don't think the number is important. There were 3 interviews where I decided to end the process early because I didn't think it was the right fit for me. On the topic of rejection, I actually found myself applying too early to several companies, which resulted in the rejection. These were all smaller companies which likely didn't have the resources to interview and accept someone applying in the fall, and starting in the summer. In hindsight, this makes a lot of sense...

And of course I had to make a Sankey diagram depicting the final decisions as well. Here's an alternative visualization:

![response-flow][response-flow-img]
*The flow starting from applications to their final decisions.*

## Final comments

There are two things I wanted to mention: cover letters, and how long this whole process took. On the note of cover letters, I wrote 9 in total. When I first began applying, I wrote cover letters for every application, regardless of whether or not they were mandatory. However, once school started picking up, I found myself with less time, and so I stopped writing them unless they were mandatory. Now, similar to resumes, cover letters are subjective, and their usefulness has been debated before. I don't think it can ever hurt an application, but it takes time to write out a genuine cover letter, and time is a precious resource, so I had to weigh out the pros and cons. Ultimately I stopped writing them, and I observed no difference with or without them. On a related note, I did not write a cover letter for the position I accepted.

My final comment is on how long I spent applying. The first and last application I sent out was on August 24 and January 6, respectively. So this was about 5 months of applying in total. However, not all of it was spaced out evenly, as I applied more often early on in the school year (September/October/January), and less frequently the deeper into the school term I was. I think the lesson here is to start early and pace yourself.

And there you have it. Everyone's experience is different, and I'm just sharing mine. Hopefully one day I can look back at this post to see where it all began.

[job-search-journey-link]: https://www.kevinxchan.me/a-job-search-journey/ 
[source-final-img]: {{site.baseurl}}/assets/img/2019-02-22-a-job-search-visualized/source_fig_final.png
[stage-final-img]: {{site.baseurl}}/assets/img/2019-02-22-a-job-search-visualized/stage_fig_final.png
[response-final-img]: {{site.baseurl}}/assets/img/2019-02-22-a-job-search-visualized/response_fig_final.png
[response-flow-img]: {{site.baseurl}}/assets/img/2019-02-22-a-job-search-visualized/response_sankey.png
[r-script-link]: https://gist.github.com/kevinxchan/006bebfa85e538286dff9f6988c08682
[sankey]: http://sankeymatic.com/
