# Support browsers sustainably

Choose a browser support strategy that is sustainable. At the most basic level, this should include a commitment to **support the most modern versions** of each browser and a limit for when you **stop supporting older versions**. The specifics of your browser support strategy are up to you, the main point is to make sure you _have_ one.

There are a few sustainability angles to this;

- Older browsers don't support sustainable techniques.
- Some browsers are more memory-intensive / power hungry than others.

The following sections go into more detail on each of these points.

## Older browsers lack support for sustainable techniques

Many of the potential gains from sustainable web development depend on modern browser techniques, including:

- [Modern image format support](https://caniuse.com/webp).
- [Tags that serve images at appropriate sizes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture).
- [CSS media queries](https://caniuse.com/css-mediaqueries).

By supporting older browsers (Notably Internet Exporer 11, Opera Mini, and any browser version released prior to 2018), you risk perpetuating unsustainable web practices.

Perhaps you have commercial reasons for supporting these browsers; your marketing data may suggest a significant loss of custom if you cease support for older software. Also, since modern web applications are meant to be inclusive, you will probably need to accommodate people who find the prospect of upgrading or switching their browser software a daunting task.

Despite what you may think, you are not truly helping your customers by enabling their continued use of outdated browsers (In the case of Internet Explorer, Microsoft have officially [withdrawn support](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)). Use of older browsers represents a very real security risk for your customers.

You have a few options for such customers:

- Refuse to serve them until they upgrade.
- Continue to cater for them, but encourage them to upgrade their browser. There are [tools available](https://browser-update.org/) to help you do this.

## Don't force users to use a particular browser

Websites often advise people to install a particular browser for "the best experience". Sometimes this advice is well-intentioned, and encourages customers to upgrade and use any popular, modern browser. Tooling and algorithms continually strive to be more efficient, so embracing modern software typically results in longer battery life and a better user experience.

Conversely, developers might encourage people to use a specific browser because they don't intend to support the others. As a developer who does this, you must weigh any productivity gains from reduced support requirements against the impact of people being forced to use browsers that consume more resources (and hence more power) than others you don't want to support. Chrome, for example, is an otherwise excellent browser that is frequently [called out as being very memory hungry](https://www.makeuseof.com/tag/chrome-using-much-ram-fix-right-now/).

## Relevant Links

- [Can I use?](https://caniuse.com/) - a comprehensive reference of browsers and the web technologies they support.
