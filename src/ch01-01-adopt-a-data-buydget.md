# Adopt a data budget

Choose a data budget for your application and stick to it. Research such as the [lean ITC report](https://theshiftproject.org/wp-content/uploads/2019/03/Lean-ICT-Report_The-Shift-Project_2019.pdf) by [Shift Project](https://theshiftproject.org/en/home/) indicates that there is a direct correlation between the amount of data an application uses and the amount of carbon it generates. As developers we seldom pay attention to the data we use until it starts to affect our application's performance. This is largely because we live in an age where storage is cheap, and we have no incentive to reduce the volume of data we transmit.

As explained elsewhere on this site, the energy footprint of our applications is directly proportional to visitor numbers, so one smart decision by us can result in massive carbon savings for our application, with the added benefits of faster and cheaper overall performance. Most of the other prompts on this site are contingent on using less data: **do this correctly, and the rest looks after itself!**

We're using the term **data budget** here to describe any situation for which you can limit the volume of data used. The most common scenario for this metric involves what is often called the "page weight", meaning the number of KB downloaded when a page is rendered. However, any part of your application that transmits data—such as any back-end processes that the user never sees—may benefit from the introduction of a data budget.

There are many tools that can show the exact energy footprint of your application resulting from data usage:

- [The Carbonalyser browser extension](https://theshiftproject.org/en/carbonalyser-browser-extension/)
- [CodeCarbon](https://github.com/mlco2/codecarbon) - track emissions from compute
- [CO2.js](https://github.com/thegreenwebfoundation/co2.js) - a Javascript library for calculating bytes-to-carbon
- [Various tools by the Green Web Foundation](https://github.com/thegreenwebfoundation)
- [NPM Size Limit](https://github.com/ai/size-limit/) - a tool to monitor NPM bundle size limits

These let you choose a data budget strategy and then **enforce it through automation**. Doing this needn't be a massive overhead for your team ; simply install the tooling, check what your current page weight or bundle size is, add 10%, and that's your initial budget. You can then work towards reducing that budget over time, and—more importantly—making sure you never exceed it without **making the conscious decision to do so**.

## Setting a page weight

You can see what the internet average page weight is using the [page weight report tool](https://httparchive.org/reports/page-weight) from _httparchive_. This lets you break down page weights by type and by date. For example, in 2021 the average web page for the top 100,000 sites on the internet measured approximately 1700KB, of which 540KB were images and 570KB was JavaScript (these are typically the biggest areas for improvement). **You can be as granular as you want to be** with your own page weight budgets, either setting a weight limit for the whole page, or setting individual budgets for different aspects of the page (such as an image data budget, a CSS data budget, etc.)

## Alternative: Set a "story weight"

Sometimes it won't make sense to use a page weight, so you might instead want to adopt a 'story weight' for your application by calculating the overall weight of a complete user journey, rather than doing it on a page-by-page basis. If we were running a shop, for example, we might choose stories (and budgets) like this;

| Story Name                  | Detail                                                         | Budget |
| --------------------------- | -------------------------------------------------------------- | ------ |
| Not what I was looking for! | User saw the home page and realised it's not what they wanted  | 400kb  |
| Just browsing               | User comes to the site, looks at several products, then leaves | 5MB    |
| I know what I want          | User is looking for something specific, finds it, and buys it  | 4MB    |
| I want to talk to someone   | User wants to ask a question or make a complaint               | 2MB    |

This gives development teams incentive to consider user stories if they don't already, and to make your users' journeys through the application as efficient as possible. Having a user get lost within an app—downloading hundreds of bytes worth of images they don't need in the process—is not only bad for the environment, it's also a bad user experience.

## Other considerations

- If your company makes multiple apps, don't mandate company-wide page weight budgets. The nature of apps means that some will generate more carbon than others, so don't pit them against each other!
- Like many things, you can turn this into a game by giving teams incentive to shed page weight. Everyone enjoys a bit of code golf, right? Think of this as carbon golf!
- The team developing the app should be the one to pick the budget, since they know the app intimately and are best-placed to pick a sensible or realistic budget.

## Relevant Links

- [MDN article about page weight](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Author_fast-loading_HTML_pages)
- [Web.dev Performance Budgets 101](https://web.dev/performance-budgets-101/)
- [HTTPArchive Web Almanac chapter on page weights](https://almanac.httparchive.org/en/2020/page-weight#page-weight)
- [HTTPArchive page weight report tool](https://httparchive.org/reports/page-weight) - use this to compare your page weights to the internet average
