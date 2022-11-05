# Curate features responsibly

Deprecate features that users are not making use of, especially if they are resource intensive. Just because a feature is "cool" does not mean it is also necessary. By maintaining resource-heavy features that your customers are not using, you may be forcing them to download data un-necessarily. Even if the feature can't be deprecated, there may be other ways of achieving the same funcionality at a fraction of the cost.

## Example: Mapping functionality

A classic example of a feature that many sites include needlessly is an interactive map, with the de-facto solution being to use [Google Maps](https://www.google.com/maps).

Google Maps is an excellent resource and easily ranks the most fully featured mapping platform in the world... however, at time of writing it is much more data intensive than alternatives such as [Leaflet](https://leafletjs.com/). You can choose which tile set Leaflet uses under the hood but a common option is the [OpenStreetMap](https://www.openstreetmap.org/) which is a worldwide collaborative effort to map the world, similar in principle to a wiki.

You can confirm which solution is more data intensive from the network tab of your browser's developer tools - you should see as you interact with a google map that you have much more data being requested by Google Maps than by leaflet (which, at least when I tried this, requested nothing but the new tiles).

There will, of course, be times when you absolutely need to use Google Maps because either you need some of that library's functionality OR you need to do mapping in a part of the world where Google has better data... however, often developers will just default to Google Maps without considering alternatives.

In addition to considering alternative technologies, have you considered not having any mapping funcitonality at all? Maps look absolutely fantastic, but if all that funcitonality is doing is displaying an overhead view of your customer's shop, could you get away with just using a static image? If it's important that users are able to scroll around / interact with the map, how about providing a link to the mapping provider rather than hosting the mapping content yourself? That way, the data cost of displaying and running a map is only paid for by the customers who actually use that feature. If you are absoultely certain that you want a map to appear in-line on your app, consider hiding the feature behind an opt-in mechanism like a button or accordian and only serving the required resources and data to users that activate the feature.

## Measuring feature usage

If you are lucky enough to work on an application where you actually get to speak to your customers - ask them about older / resource intensive features. Often people will get very attached to features (especially cool ones!) and deprecating them reduce an application's energy footprint can be a difficult conversation, so you might want to go armed with some statistics demonstrating that a feature is or is not being used.

One way of figuring out usage is via analytics. There are a number of analytics platforms out there that can provide usage data, allowing you to see which features and pages are/aren't being used - popular choices include [Google Analytics](https://analytics.google.com/analytics/web) and [Matomo](https://matomo.org/). These platforms allow you to collect anonymous usage data to let you see how your users are interacting with the application. As well as broad statistics such as page visits and journeys, both of these platforms offer fine grained control over the metrics that are collected, allowing you to track custom interactions with individual buttons and controls.

Whilst extremely useful, developers should use these platforms with caution. Currently in the EU and the UK, there are certain [legalities around the use of analytics](https://ico.org.uk/for-organisations/guide-to-pecr/guidance-on-the-use-of-cookies-and-similar-technologies/) on websites which require you to inform your users when you are collecting these kinds of metrics and invite them to either opt out or leave the site (even if that collect is done anonymously!). In addition to the negative impact on user experience, **having these kinds of analytics platforms installed increases the energy footprint of your application** because it means you will be sending additional data over the internet. You should only use analytics platforms if you are making active and efficient use of the metrics that are being collecting.

## Relevant Links

- [Google Maps](https://www.google.com/maps) - A popular mapping platform
- [Leaflet](https://leafletjs.com/) - An open source equivalent to Google Maps.
- [Google Analytics](https://analytics.google.com/analytics/web) - A popular analytics platform for measuring user behavior.
- [Matomo](https://matomo.org/) - an open source equivalent to Google Analytics.
