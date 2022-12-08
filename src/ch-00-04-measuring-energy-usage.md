# Measuring energy usage

How exactly do you equate a energy footprint to your website or application?

The bad news is that you basically can't. Between the background noise of the measurement itself, unseen factors such as user device behaviors and the inherent opaqueness of hosting providers, getting an exact figure is essentially impossible. The best you can hope for is to get a decent _estimate_ that you are comfortable basing targets around. 

The _good news_ is that the factors that cause energy consumption to increase are fairly well understood, so we know what we need to optimise for even if we can't get an exact measurement of the associated energy cost. We can use this information to build a rough model for linking our application metrics to energy usage, and indeed several such models already exist in the wild.

A French think tank called [The Shift project](https://theshiftproject.org/en/home/) created a report a few years ago entitled [LEAN ICT: TOWARDS DIGITAL SOBRIETY](https://theshiftproject.org/en/article/lean-ict-our-new-report/). In this report, they proposed a model for estimating the carbon emissions of web based applications called the **1-byte model**. This model has become fairly prominent in the sustainable IT space and is often cited in the media. Essentially, the one-byte model applies coefficients to several metrics;

- Where is it hosted?
- What device is it running on?
- How much data is it using, both at rest and over the network?

From these, the 1-byte model proposes that you can get an energy estimate for your application. Colleting the metrics associated with these elements is broadly possible using a combination of client and server-side analytics software, but this highlights the earlier point about how "rough" this estimate is going to be. How can you be sure, for example, which device each of your users are using, or how much data usage is attributable to each device? This is made even more difficult by the fact that users are somewhat empowered to hide this information from you! The one-byte model itself often comes under criticism for this very reason, with statements being made about its accuracy and therefore the validity of any measurements derived from it... but is getting a precise measurement for energy consumption really the most important thing here? Of course, most organisations will need to adopt *some* form of measurement in order to track progress, but optimising is the real goal here and you never hear anyone arguing that the factors this model considers are not the right ones. 

There are well established ways of measuring things like CPU cycles and Data Usage - with industry leaders such as ElasticSearch allowing for metric collection to have become "business as usual" for anyone who owns kit either on premises or in a data centre - generally you need to know these statistics in order to keep your systems healthy and to diagnose issues - in some cases, you may even have access to your organisation's electricity bill and be able to *see* how much energy your servers are consuming. This becomes a lot more difficult if you are hosting within the cloud though as suddenly the energy usage is abstracted away and just becomes a monetary figure. Attempts have been made to create a model for calculating energy usage in the cloud, notably [Etsy Cloud Jewels](https://codeascraft.com/2020/04/23/cloud-jewels-estimating-kwh-in-the-cloud/) which provides a model for estimating Google Cloud energy usage.

Whilst it may be that we can never see the true carbon impact of our applications, the main messaging around this issue is very clear:

- Try to **use less data** and not be wasteful.
- Try to **build efficient, fast applications** to optimise for CPU cycles.

The ideas within this book mainly focus on these two aspects - minimise these, and you minimise the electricity consumption of your application. In most cases you will also enocunter side-benefits and will find that by doing this you are inadvertedly optimising for cost and user experience at the same time.

Several organisations and groups have dedicated lot of time into the science behind calculating energy estimates. In particular, the Green Web Foundation have produced some extremely thorough [articles](https://www.thegreenwebfoundation.org/news/) on the subject which you should read if you want to dig deeper.
