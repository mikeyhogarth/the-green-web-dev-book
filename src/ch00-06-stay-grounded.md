# Stay grounded

It's great that you've decided to educate yourself about sustainable web development - we're all going to need to make changes to the way we work over the coming years and this book can help you to get a decent handle on the factors that contribute towards the energy footprint of web applications. The intention is _not_, however, to make anyone feel guilty for creating digital experiences. There is a temptation, once you know what to look for, to obsess over every single byte of data your applications consume or to agonize over the minutiae of factors that would affect CPU efficiency. 

Please try to balance the ideas in this book with reasoned thought when applying them to any situation, and definitely avoid using the ideas as *weapons* to win arguments with your colleagues. By taking the advice contained herein too far, you risk damaging the user expericnce of your product and driving customers away.

Many of the ideas presented in this book have effects that would be invisible to your users but extremely valuable from a sustainability perspective. This is not always the case - some of these ideas **do** have a noticable impact on things like image quality, brand identity and user experience. This presents you with a tradeoff: How much optimisation is "enough"? For this, there is a golden rule...

> ### The Golden Rule
> Focus on reducing waste, not capability.

If you go into this all guns blazing, insisting that every single byte of data and every single CPU cycle must be preserved at all costs, you risk not only damaging your business but also of losing the hearts and minds of those you are aiming to convince. Make sure all decisions are accompanied by a large dollop of common sense because it can happen that in choosing the most sustainable option, you erode the experience for your developers and users so much that the productivity hit ends up actually _increasing_ the amount of energy consumed by your application.

Many of the more crunchy pain points are related to **design**, an aspect where many tradeoffs can be made and where "vitalness" to the application beocmes somewhat subjective. Being sustainable does _not_ necessarily mean that your application will be unattractive, but many common design trends tend to lean towards being quite energy-intensive whilst adding only non-functional features:

- Large, bold images
- Streaming videos or interactive widgets
- Transitions and animations

These are all things that *will* increase the energy footprint of your app, and *might* improve the user experience, so you can expect any discussions about dropping these kinds of features to become a bit feisty but bear in mind that it is possible to take things too far in *either* direction. You could, for example, abandon styles completely and leave it all to the browser defaults - this will have a noticable _positive_ impact on your website's energy footprint (yay) but will almost certainly have a _negative_ impact on user experience, possibly even causing your users to believe your site is unprofessional or even that it's broken! It won't, as they say in the business, "pop" any more and this could end up affecting customer engagement and ultimately conversions.

Try to focus on the things that cause the biggest impact from an energy perspective, but which have the least impact to your users. It's not about scrabbling to save every CPU cycle or every byte of data - it is about striking a sensible balance between your appliction's energy footprint and the value it offers to users.
