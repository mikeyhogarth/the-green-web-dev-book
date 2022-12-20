# Adopt a data budget

Choose a data budget for your application and stick to it. Research such as the [lean ITC report](https://theshiftproject.org/wp-content/uploads/2019/03/Lean-ICT-Report_The-Shift-Project_2019.pdf) by [Shift Project](https://theshiftproject.org/en/home/) asserts that there is a direct correlation between the amount of data an application uses and the amount of energy it consumes.

Here we are specifically talking about the amount of data that needs to be sent back and forth over the wire in order for our application to function - this is a statistic over which we have a large amount of control, but it is often a neglected optimisation, at least until it starts to affect our application's performance (be that our own build times or a perceivable sluggage in the application itself).

The energy footprint of our applications is directly proportional to visitor numbers, so smart decisions about data can result in massive energy savings for our application as the number of users increases. This all carries the added benefits of faster and cheaper overall performance, as your hosting provider is likely charging you by the byte for data transfer.

We're using the term **data budget** here to describe a limit which you choose to set on some aspect of data usage. One example of this is to measure the amount of data trasfer required before a page becomes interactive (it's so called "time to interactive" or TTI, according to Google's [web vitals](https://web.dev/vitals/) initiative). This is often called the "page weight", or the number of KB downloaded before the page becomes interactive. The concept of a data budget is not purely limited to page weights however - any part of your application that transmits data — even things that the user never sees - may benefit from the introduction of a data budget.

There are many tools that can show the estimated energy footprint of your application based on the data it uses:

- [The Carbonalyser browser extension](https://theshiftproject.org/en/carbonalyser-browser-extension/)
- [CodeCarbon](https://github.com/mlco2/codecarbon) - track emissions from compute
- [CO2.js](https://github.com/thegreenwebfoundation/co2.js) - a Javascript library for calculating bytes-to-carbon
- [Various tools by the Green Web Foundation](https://github.com/thegreenwebfoundation)
- [NPM Size Limit](https://github.com/ai/size-limit/) - a tool to monitor NPM bundle size limits

Many of these let you choose a data budget strategy and then **enforce it through automation**. Doing this needn't be a massive overhead for your team; simply install the tooling, check what your current page weight or bundle size is, add 10%, and that's your starting budget. You can then work towards reducing that budget over time, and—more importantly—making sure you never exceed it without **making the conscious decision to do so**.

> For example: Your team has been looking after a NodeJS application for a few years which relies on several external dependencies which you manage with `npm`. You examine the size of your post-build bundle and note that it clocks in at around `1MB`. You collectively decide that you are going to set a data budget of `1.1MB` and aspire to stay underneath that limit for the remainder of the application's life cycle.

Setting a data budget turns data usage into a _conversation_. Any decision that would cause you to exceed your data budget is now transformed into a _conscious decision_.

## Setting a page weight

You can see what the internet average page weight is using the [page weight report tool](https://httparchive.org/reports/page-weight) from _httparchive_. This lets you break down page weights by type and by date. For example, in 2021 the average web page for the top 100,000 sites on the internet measured approximately 1700KB (or 1.7 MB), of which 540KB were images and 570KB was JavaScript (these are typically the biggest areas for improvement). If you can get under the average then great, but try to be bold in your page weight decisions rather than just shooting to be below the average - 1.7MB is still pretty high for a single page.

**You can be as granular as you want to be** with your own page weight budgets, either setting a weight limit for the whole page, or setting individual budgets for different aspects of the page (such as an image data budget, a CSS data budget, etc.).

## Alternative: Set a "story weight"

Sometimes it won't make sense to use a page weight, so you might instead want to adopt a 'story weight' for your application by calculating the overall weight of a complete user journey, rather than doing it on a page-by-page basis. If we were running a shop, for example, we might choose stories (and budgets) like this;

| Story Name                  | Detail                                                         | Budget |
| --------------------------- | -------------------------------------------------------------- | ------ |
| Not what I was looking for! | User saw the home page and realised it's not what they wanted  | 400kb  |
| Just browsing               | User comes to the site, looks at several products, then leaves | 5MB    |
| I know what I want          | User is looking for something specific, finds it, and buys it  | 4MB    |
| I want to talk to someone   | User wants to ask a question or make a complaint               | 2MB    |

As well as being a more realistic way to measure user experience, it also incentivises the creation of a set of core user stories for your application if you don't already have these. As a by product of optimising for these stories, you may find that you start to think more about how to make these stories take fewer steps or how to streamline them in other ways - all of which contributes to creating a great experience for you users.

## Other considerations

- The team developing the app should be the one to pick the budget, since they know the app intimately and are best-placed to pick a sensible or realistic budget. If your company makes multiple apps, don't mandate company-wide page weight budgets. The nature of apps means that some will generate more carbon than others. Don't pit your applications against each other, but of course there is a lot to be gained by ensuring that the channels of knowledge sharing are open between teams.
- Like many things, you can turn this into a game by giving teams incentive to shed page weight. Everyone enjoys a bit of code golf, right? Think of this as energy golf - but be cautious when adopting this kind of gamification because it can easily become a perverse incentive: ask your developers to shed 1% of their data usage a month, and you may be inadvertedly incentivising them to hold back the big optimisations to ensure they meet can their monthly targets.

## Relevant Links

- [MDN article about page weight](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Author_fast-loading_HTML_pages)
- [Web.dev Performance Budgets 101](https://web.dev/performance-budgets-101/)
- [HTTPArchive Web Almanac chapter on page weights](https://almanac.httparchive.org/en/2020/page-weight#page-weight)
- [HTTPArchive page weight report tool](https://httparchive.org/reports/page-weight) - use this to compare your page weights to the internet average
