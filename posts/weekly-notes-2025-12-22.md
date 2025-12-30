---
title: "Weekly Notes (Dec 22 – Dec 28): Year in Review & What's Next for Niklas Notes"
slug: "weekly-notes-2025-12-22"
date: "2025-12-30"
category: "Weekly Notes"
description: "The quietest week of 2025 becomes a look back at what's been built. New recommendation system, developer analytics, OAuth login, Stripe payments, review timeline improvements, and thoughts about the future"
tags: ["Weekly Notes", "Steam Releases", "Steam Trends", "Year in Review", "Product Updates", "Recommendation System", "Developer Analytics", "Game Discovery", "OAuth", "Stripe", "Review Timeline", "2025 Recap", "Roadmap 2026"]
image: "https://media.githubusercontent.com/media/NiklasBorglund/niklasnotes-blog/main/posts/weekly-notes-2025-12-22/hero.png"
---

Christmas week turned out to be the week with the least amount of releases since I started. 
The top list is at the bottom, but since it was so few I thought I'd take the opportunity to talk a bit about the site.

I'll be going through a bit what's been done since the site was released, and what is ahead.

---

## "More Like This" Recommendation System

The "More like this" on Steam is not very good and this is my latest release on the website.

#### What this will unlock

Apart from just giving better recommendations and actually have a good way of finding similar games - 
I could then later on create more indepth competitor analysis, finding unreleased games that are similar, creating personalized recommendations and much more.
Just by thinking about what I could do with it gives me a thousand ideas.

#### The problem
Let's say you've just finished playing Goat Simulator 3 and you want to play something similar.
So you check the "More Like This" section on Steam and you get these:
- PEAK
- Enshrouded
- The Last Caretaker
- BeamNG drive
- SnowRunner
- Sons of the Forest

None of these would qualify at all if we asked someone to create a handpicked selection.

I do get why these come up, since Goat Sim 3 has quite generic tags that actually say something about the gameplay: Casual, Exploration, Open World, Adventure, Simulation, Sandbox, Action-Adventure.

And lots of games share similar tags. So how do we find something similar among this vast ocean of candidates?

#### My approach
I've been working towards this long term by creating several systems. And I focused on combining two of them.

First is the categorization of user generated tags into something useful and use the ones I think defines the genres and not just fluff. Then I pick out 3 of them as primary for that game with a semi-complex system using the data I have for that game.

I also tag every single game analyzed according to visual style and vibe (with the help of AI).

Using these two systems, I can check overlaps in both gameplay and vibe.
Roughly put, it's this:
- Do a wide search to get 1500 candidates for a game with ANY of these tags
- Check the tag overlap and give higher score on specificity
- If the genres are vague (like Goat sim), then give more weight to the VIBE.
- If the compared game share a publisher/developer - it gets a slight score boost.
- If the compared game has a huge difference in playtime, then they will get a penalty.

I still have some issues that I need to solve for this to be better. 
I think perhaps the developer/publisher boost is too large and the playtime penalty is too unforgiving - but it's promising.

With my system now, these are the "More like this" for Goat Simulator 3:
- Goat Simulator: Remastered
- Goat Simulator
- LEGO Worlds
- Human Fall Flat
- A Hat in Time
- Slime Rancher
- Totally Accurate Battle Simulator

This is still very much a work in progress and I'd love any feedback you might have. 
It's live on all games on the site right now, you don't even need an account.

Below you can see the difference between Steam's recommendations and Niklas Notes:

![SteamRecommendations](./goatsim-recommendations-steam.png)
![NiklasNotesRecommendations](./goatsim-recommendations-niklasnotes.png)

---

## More in-depth developer/publisher analytics (PRO feature)

Another very recent (still work in progress) feature, but I'm starting to have all the data I want on it.

Instead of just seeing the list of products, you can now see total accumulated data, an extensive track record and an audience estimation based on reviews.

![ElectronicArtsTotalOverview](./electronic-arts1.png)

You can also see a graph over all the releases and their impact (in terms of positive reviews) in a graph timeline and an extensive breakdown of their tags.

![ElectronicArtsTotalOverview](./electronic-arts2.png)

And finally, you can also see a profile in what this developer/publisher is good at and known for. A breakdown of what tags they consistently creates hits with as well as the top tags most used in their products.

![ElectronicArtsTotalOverview](./electronic-arts3.png)

This is also live right now, but only for PRO-members. Just search on any developer in the search bar to find it.

#### What this will unlock

I will start to create a solid database-schema for this once I have exactly what I want on these pages.
My thought is that most of it could be searchable. 

I could extract top developers and publishers in different timeframes to track who is doing what. I could check groups of tags and see which developers or publishers are industry leading within that subset.

## Login options with Oauth

I like security, and I don't want to make it that easy for bots to signup on my page. So I have quite strict password requirements to signup on the page.

However, that creates a hurdle. And many legitimate users might drop here and not signup.
So now you can sign up by using your Google, Github or Patreon account.

![Oauth Signup](./oauth-signup.png)

## Payment options with Stripe

Some of you wrote to me and expressed that you didn't want to use Patreon as a payment service. 
So when I had just before implemented Oauth login, which had a similar logic to it, it felt quite easy to implement payments through Stripe.

Patreon is still available and works just as before, but you can also checkout using Stripe at the [upgrade page](https://niklasnotes.com/dashboard/upgrade).

## Review Timeline improvements

I added several features to the review timeline a while ago. It's a feature where you can track review counts over time and compare Steam games.

New features:
- Align to Release: Compare trajectories from launch in different granularities (daily, weekly, monthly, quarterly)
- Cumulative view: Total trajectory instead of daily counts
- Language filters: Isolate a graph to a single audience (can also be compared with other games!)
- Steam Deck filter: Isolate a review set to only reviews that are marked as "played primarily with steam deck".
- Score tracking: Apart from review count, you can also check positive score over time.

The basic review count graph is available to free members, but the advanced filters and features are available to Pro-members. 
The screenshot is comparing the three DLCs of Kingdom Come Deliverance II with cumulative and align to release turned on. This way you can compare trajectories of different DLCs and make predictions.

![ReviewTimeline](./review-timeline.jpg)

## Many many minor tweaks and updates

I constantly update the site with minor (and sometimes major) background tweaks.
They are too many to mention here, but it's everything from frontend ui updates to optimizing backend services.

Some worth mentioning:

- Updated the cache system on the backend. Before I had more synchronous fetches that I should've, even with Redis. But even that needed an update with the sheer amount of games on the site.
- Ability to flip between dark/light mode in the profile section
- Updated if a game is delisted/removed/redirected from Steam
- and much more!

## So what's next?

First off, I want to finish the 'More like this' feature. I want to have a solid base for a recommendation/similarity engine - it just unlocks so many things.
Same goes with the advanced developer/publisher analytics, so I can retrieve more interesting data.

After that I have this list of things in the semi-short term. This list can and probably will change a bit though:

- **Lists & Notifications** - Ability to create lists of different kinds. Lists of games/developers/publishers to track. For any reason you might want, and hopefully a notification system along with that to notify you with any change you might like.
- **Advanced Search UX** - Update the advanced & visual search with mainly UI/UX updates, but also a way to use a specific game as a base for a search.
- **Price & Follower Tracking** - Track price & steam follower count (to see highly anticipated games)
- **Revenue Estimation** - Possibly also do a simple revenue estimation to be able to do searches with it. I'm hesitant though, since other sites do it so well already.
- **Tag Analytics** - Just as the developer/publisher analytics, I would like to have analytics for a group of tags chosen by the user.

---

## Full List: Top Releases for Dec 22 - Dec 28 (2025)

```customlist
{
  "listName": "top-releases-week-2025-12-22_to_2025-12-28",
  "visibleColumns": ["impactScore", "index", "positivePercentageScore", "totalReviews", "estPlayTime", "age"]
}
```

---


And that's it for 2025!

Thank you for following along this year. I'm excited to keep building and improving Niklas Notes in 2026.

If you enjoyed this, feel free to share it with someone who you think it'd bring value to - or get your hands on the advanced, visual search, timeline (and other features) by [upgrading your account to a PRO membership](https://niklasnotes.com/dashboard/upgrade).