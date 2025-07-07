---
title: "Weekly Notes (Jun 30 – Jul 06): Summer Lulls and Niklas Notes Updates"
slug: "weekly-notes-2025-06-30"
date: "2025-07-07"
category: "Weekly Notes"
description: "The Steam Summer Sale quieted releases this week, so I’m sharing what I’ve been building behind the scenes on Niklas Notes, from genre tagging improvements to advanced search, PDF reports, and what’s next."
tags: ["Weekly Notes", "Steam", "Game Development", "Game Industry", "Steam Trends", "Indie Dev", "PC Games"]
image: "https://media.githubusercontent.com/media/NiklasBorglund/niklasnotes-blog/main/posts/weekly-notes-2025-06-30/hero.jpg"
---

Hello!

The Steam Summer Sale is in full swing, with everyone clearing out their wishlists.

It’s not the best time to release a game, and the charts show it. They’re pretty much empty.

That makes a good week to share what I’ve been working on for Niklas Notes and where the site is heading.

Below are the top releases from last week, along with the top releases for all of June, for those tracking market movements.

## 📊 Full List: Top Releases for June 30 - July 06 (2025)

```customlist
{
  "listName": "top-releases-week-2025-06-23_to_2025-06-29",
  "visibleColumns": ["impactScore", "index", "positivePercentageScore", "totalReviews", "estPlayTime", "age"]
}
```
---

## 🔥 BONUS: Top Releases for all of June

We just passed into July - so here's also the full list of top releases in June 2025

```customlist
{
  "listName": "top-releases-2025-06",
  "visibleColumns": ["impactScore", "index", "positivePercentageScore", "totalReviews", "estPlayTime", "age"]
}
```

---

## Behind the Scenes at Niklas Notes

### What I've been doing lately
Lately I've been in part optimizing the site and monitoring traffic in Google Analytics - seeing a bit what works and what does not.

### Traffic Cleanup
I noticed a lot of organic traffic was coming from Google searches for adult/NSFW Steam games with analysis pages. These visitors left the site just as quickly as they arrived, which wasn’t quality traffic.

I redirected these pages to a separate URL (adult/game instead of game/) and excluded them from SEO indexing. Traffic numbers are down, but the readers who remain are the ones who find the site useful. This gives me better insight into what actually brings value to you.

---

### Taking a pass at improving genre classifications

Going through and analyzing all of this data made me take a harder look at the field called "Genre" that I get from the Steam data.

They are all technically correct, but super broad and vague.

For example, Terraria is listed as:
- Action, Adventure, Indie, RPG

ELDEN RING?
- Action, RPG

Wildly different games, but nearly identical genres. The real genre is usually buried in the user-defined tags. But those are a messy mix of tone, features, and memes.

So I took a shot at trying to fix it. I used the cheapest model in the open AI api (4.1-mini) and asked it to categorize all the tags into three different sub categories.

After reading a lot of them, I felt they all fit in one of the following:

- Genre: An actual genre. RPG, Turn-Based Strategy, Soulslike, FPS etc.
- Feature: A feature of the game. Controller Support, Co-op, Multiplayer, Singleplayer etc.
- Descriptor: Pretty much a catch-all, but mainly something that describes the game as a whole. Cosy, Classic, Story Rich, Stylized etc.

Still a work in progress - but the results are a bit better now I think:
- Terraria: Building, Open World Survival Craft, Platformer
- Elden Ring: Action RPG, Open World, Souls-like

The goal is to make discovery and analysis more meaningful, especially for developers looking for comparable games

---

### Optimizing the site

Since this is my first web project, I’ve been learning as I go. I use Google Lighthouse to guide improvements, rolling out updates gradually to improve performance and usability.

I've also optimized the UI & UX quite a bit, often in small places one step at a time - things like internal linking, making sure the important information is shown first, and checking everything works as well on mobile.

The goal is to make the site as fast and clear as possible for anyone using it.

---

### Cost of use

I've managed to keep all of this fairly cost efficient, especially since the large amount of games analyzed and the data required. The whole website is hosted on a Hetzner Server running Linux, they had cheap options with lots of storage and decent hardware.
And the AI analysis itself runs on a cheap model, but with a prompt I have changed, and altered, and changed again for utmost accuracy. Right now, it's often around 1 dollar a day - depending on the traffic.

---

## What’s coming next

### Weekly and Quarterly Notes

I plan to keep publishing these Weekly Notes. Writing them helps me stay connected to the industry and share insights with you. I hope you find them useful.

I’m also working on a more detailed Q2 2025 analysis, looking beyond top release lists to see which games get the most attention by market, since audience splits vary widely between games.

For example:

* [Schedule I](https://niklasnotes.com/dashboard/game/72681/schedule_i) primarily has a 71% English-speaking audience.
* [Split Fiction](https://niklasnotes.com/dashboard/game/61387/split_fiction) has 50% Chinese players and 30% English.

Both are top performers, and the reason for the difference might be as simple as localization, but looking only at global lists hides important details.

---

### User Accounts & Switching from Buy Me A Coffee to Patreon

I’m testing user account functionality to provide real value for supporters. This aligns with a gradual move from Buy Me a Coffee to Patreon, which offers better integration and perks for backers.

They also have an API so I can unlock perks on the site through it.

The goal is to keep the site sustainable and reward those who support it with meaningful benefits.

---

### Advanced Search

Right now, I only have a few search types available. Simple text search by name, developer, publisher and steam id. This is very optimized, uses Redis caching to give autocomplete and simple searches.

The dashboard lists use a separate, parameter-rich search system that can create highly specific searches. As curiosity strikes, I add new parameters.

![Image of the WIP advanced search](./advanced-search-wip.png)

This will always be slower & cause more strain on the server, but after I've optimized it I want to be able to give this search to backers.

---

### Detailed PDFs

I’ve been working on generating detailed PDF reports for any game analyzed on the site, isolating sentiment by language and time frame.

I shared an early example with newsletter subscribers last week: [Persona 5 - The Phantom X Detailed Analysis](https://drive.google.com/file/d/1NFo-RWJ9EpIVwzFE9rqtv40vozMv2qbl/view?usp=drive_link)

They will be available as a perk for backers, but I can generate them now upon request if you reach out.

I see these PDFs becoming a practical tool for developers and researchers wanting to understand player sentiment in detail.

---

### Call for feature requests
If there's anything you'd like to see on the site - I'm all ears.

---

That’s it for this week. Thanks for reading and following along!

Stay tuned!
If you enjoyed this, feel free to share it with someone who you think it'd bring value to - or [buy me a coffee](https://buymeacoffee.com/niklasnotes) to support more data-driven game breakdowns like this one.
Thanks for following along.
