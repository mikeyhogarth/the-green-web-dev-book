# Use semantic markup

Where possible, always try to use native browser elements for your web content. Reaching straight for widgets and plugins will lead to an increased bundle size and possibly an [Excessive DOM](/prompts/no-excessive-dom). This will mean [your browser has to work harder](https://web.dev/dom-size/) on queries whilst also increasing the amount of data you are sending over the wire - both of which contribute to an increased energy usage and battery drain.

## Semantic Markup

Today, the web platform provides a [wide range of HTML elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) for you to use when creating content for the web. Having a healthy working knowledge of these tags is undeniably useful, but even the most experienced web developers can still encounter tags and features that they've never used before or didn't know existed.

Did you know, for example, that there is a [`date` input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date) that is natively supported accross [all major browsers](https://caniuse.com/input-datetime)? And that it can be styled to suit your application?

<div className="text-center p-4 border-2 border-grey-300 mb-2">
  <label htmlFor="my-date">Pick a Date:</label>
  <input type="date" id="my-date" name="my-date" defaultValue="2021-09-30" />
</div>

```
<label for="my-date">Pick a Date:</label>
<input type="date" id="my-date" name="my-date" value="2021-09-30" />
```

Whilst using semantic markup [does not always mean you are safe](https://www.hassellinclusion.com/blog/input-type-date-ready-for-use/) from an accessibility perspective, using semantic markup will normally get you most if not all of the way towards being inclusive and is strongly encouraged. Any shortcomings in screen reader browser support are likely to become better over time, meaning that using semantic markup is also an effective way of future-proofing your site.

## Widgets, Components and Plugins

If you do reach a point where you have exhausted all native browser options, you may find that it's time to reach out to the open source community to find an appropriate plugin/component. Javascript has a huge ecosystem and there is [a lot of choice](https://github.com/sorrycc/awesome-javascript) - here are some things to look out for;

- **Evaluate the popular ones first**. It's not all about github stars and npm downloads, but as a general rule the components with the most stars/downloads are normally the better ones, so start with those but don't just default to them.
- Check that the component you choose is **accessible** - they will normally state this in their documentation.
- **Don't use a sledgehammer to crack a nut** - if a plugin provides 100 features and you only need one of them, you are probably going to be downloading (and serving to your users) a lot more code than they are actually using, contributing negatively to your page weight.
- Just because a component _looks_ good doesn't mean it _is_ good. Take a look at the markup the component generates before making a decision. Are there problems that could be fixed? Would this component be perfect if it just had one more feature? Consider getting involved with that component's development and submimtting a pull request to the creator. Just because a component doesn't do quite what you want it to does not mean that you need to always choose second best.

There is an online convention known as [awesome lists](https://github.com/sindresorhus/awesome) which you can use to browse your options. If you find (or create) a great component that is not on one of these lists, consider submitting a change request to get it added.

## Relevant Links

- [MDN list of HTML5 tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- [Awesome Javascript](https://github.com/sorrycc/awesome-javascript) - A curated list of browser-side Javascript libraries and components.
- [Awesome React Components](https://github.com/brillout/awesome-react-components) - a curated list of React components.
- [Awesome Vue Components](https://github.com/vuejs/awesome-vue#components--libraries) - a curated list of Vue components.
- [Awesome Angular Components](https://github.com/brillout/awesome-angular-components) - a curated list of Angular components.
- [Awesome Svelte Components](https://github.com/TheComputerM/awesome-svelte) - a curated list of Svelte components.
