---
layout: post
title: "Telegram Bots - BouldaBot"
date: 2021-08-30
---
## TLDR
> I built a bot on Telegram to manage events. It's still far from what I envisioned, but this project was fun for ideation and tinkering. This also kickstarted a couple of other bots that I've built for personal use.

## The Background
Recently I've been spending quite a lot of time on building Telegram bots. 

The motivation started another hobby I picked up early this year, actually. Since the start of February, I've been bouldering with my boyfriend, brother, and some of our friends. 

As we went for more and more climb sessions at more and more different gyms, it became slightly confusing to keep track of which event was coming soon, who would be going, and where it was going to be. See, we have a limited number of entry passes purchased at each gym, and we'd have to book slots to go each time.

Another slight problem was simple event tracking - my boyfriend is not that great at keeping track of his calendar events. I've had to send email invitations to remind him of dinner dates and weekend plans. :-) Which is fine for on a weekly basis, but as we all started going bouldering more often, it became quite tedious to keep track of all our events. 

## The Solution
As with any tedious, manual process - I thought it would be great to automate this. Have some sort of event tracker built in a chatbot which we could interact with easily. 

### Chat Bots
Disclaimer - I've never worked with chatbots before. I've studied Text Analytics but parsing texts is vastly different from the process of building bot interactions to receive and work with those texts in the first place. *Thank God for all the great documentation and tutorials out there.*
Since this is my first try, I made it a simple, literal parser - no fancy NLP (yet?). 

The code was written in **Python**, with the use of a fantastic package that taps on the Telegram API: **python-telegram-bot**.

### Data Storage
I explored various ideas for data storage, like Google Sheets or Notion 'databases' (so I could link it to even more of my personal data trackers), but came across some roadblocks in terms of security access. 
Importantly, since this was meant to be a toy project and for personal use only, I eventually used **SQLite** (a personal database) to store the data. 

## What the Bot can do (for now)
- Create events including details such as date time, venue, attendees.
- Update any specific detail of any event
- Delete events
- View lists of all upcoming events

## The Future
Other features I really wanted to include: 
- Ping reminders based on upcoming events (which I've accomplished to do in another separate bot, another post about it maybe soon)
- "Open Jio"
    - In a group chat, when one person creates an event, others in the group can comment or indicate if they're joining as well. Similar to how group event attendances are collated in WhatsApp, minus the copying and pasting of the entire attendance list to add your name and plus one very helpful bot :-) 
- Bouldering specific features
    - Tracking the number of remaining entry passes wqe have after each event has passed (I put this on the backburner since it's super specific)
    - Provide links to booking pages once the booking window has opened

A close friend pointed out she wanted something similar to keep track of family dinner attendances, I realised this could be something worth sharing with friends. So that's definitely an eventual goal.. but to do that, I'll need to make it way more secure ;) 