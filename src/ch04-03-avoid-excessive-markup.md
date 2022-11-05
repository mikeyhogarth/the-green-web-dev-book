# Avoid excessive markup

Always try to avoid superflous markup, in particular you should avoid adding DOM elements to achieve a particular look or style when there are CSS-based alternatives. Having an overly-busy DOM will affect [runtime performance and page speed](https://web.dev/dom-size/), as well as contributing to more data being sent to clients. In addition to this, your browser will have to work harder when querying and manipulating a busy DOM, leading to additional battery drain, whilst at the same time harming SEO and accessibility.

## An example

Consider a form label, which will default to being an `inline` element. This means that when rendered, the label will appear to the left of any subsequent input element;

<div className="text-center p-4 border-2 border-grey-300 mb-2">
  <label htmlFor="my-input">Enter some text:</label>
  <input type="text" id="my-input" name="my-input" />
</div>

```
<label for="my-input">Enter some text:</label>
<input type="text" id="my-input" name="my-input" />
```

Now lets say you wanted that label to instead appear _above_ the form element. Inexperienced web developers may default to trying to achieve this with markup, such as the line break tag (`br`) or by adding `div` elements;

```
<!-- using a line break -->
<label for="my-input">Enter some text:</label>
<br />
<input type="text" id="my-input" name="my-input" />

<!-- using div elements -->
<div>
  <label for="my-input">Enter some text:</label>
</div>
<div>
  <input type="text" id="my-input" name="my-input" />
</div>
```

Whilst both of these approaches would achieve the desired _look_, they both involve adding elements to the DOM which do not need to be there. The same style can be achieved using CSS alone, for example by making the label a `block` level element and adjusting its alignment.

<div className="text-center p-4 border-2 border-grey-300 mb-2">
  <label id="syled-label" htmlFor="my-input" style={{ display: "block" }}>
    Enter some text:
  </label>
  <input id="styled-input" type="text" name="my-input" />
</div>

```
<label style="display:block" id="syled-label" for="styled-input">Enter some text:</label>
<input id="styled-input" type="text" name="styled-input" />
```

HTML can be minified only by removing whitespace, whereas you will achieve better compression on css because classes and selectors can be programatically obfuscated and optimised - this means that if you default to css, you'll probably end up sending less data to the user.

## So you're saying NEVER add markup just to achieve a style?

Definitely not - there will be some cases where, in order to achieve a particular style, you _will_ need to add some additional markup. [Material UI](https://mui.com/), for example, adds an extra `span` element to achieve the famous [ripple effect](https://mui.com/components/buttons/) on elements such as buttons.

There may even be rare cases where the amount of CSS required to achieve a particular style is massive, and you'd end up spending _more_ data than you would if you just added a new element. The trick is just to be pragmatic and make your choices with your eyes open to the cost of your decisions.
