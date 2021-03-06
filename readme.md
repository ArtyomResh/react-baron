**React-baron**

react component for baron scrollbar customization support. Now jQuery-free (you dont have to have jQuery anymore).

```
npm i react-baron --save
```

example:

```js
Baron = require('react-baron');

...
// All params are optional
render: function() {
    return (
        <Baron
            clipperCls="clipper"
            scrollerCls="scroller"
            trackCls="track"
            barCls="bar"
            barOnCls="baron">

            ...Scrollable content here...
        </Baron>
    );
}
```

```css
.clipper {
    overflow: hidden;
    height: 100%;
}
.scroller {
    overflow-y: scroll;
    height: 100%;
}

/* or, for flexbox */

.clipper {
    display: flex;
    overflow: hidden;
    height: 100%;
}
.scroller {
    display: flex;
    flex-direction: column;
    overflow-y: scroll;
    flex: 1 1 auto;
}

/* And scrollbar */

.track {
    display: none;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    width: 0;
}
.baron > .track {
    display: block;
}
.bar {
    position: absolute;
    right: 0;
    width: 6px;
    border-radius: 3px;
    background: #ccc;
}
/* hide default chrome scrollbar */
.scroller::-webkit-scrollbar {
    width: 0;
    height: 0;
}
```

**API**

Same as [baron.js](https://github.com/Diokuz/baron).

Plus

```js
// Scroll as far as possible
this.refs.baron.scrollToLast()
// You must set baron ref for Baron component

// Get DOM-node scroller
this.refs.baron.getScroller();

// Get DOM-node clipper
this.refs.baron.getClipper();

// onScroll handler
onScroll: PropTypes.func;
```

## Browsers support

React-baron is jQuery-free (it has tiny jQuery-like utility, about 400 bytes), and its uses HTMLElement classList.

| <img src="http://diokuz.github.io/pics/chrome.png" width="48px" height="48px" alt="Chrome logo"> | <img src="http://diokuz.github.io/pics/firefox.png" width="48px" height="48px" alt="Firefox logo"> | <img src="http://diokuz.github.io/pics/ie.png" width="48px" height="48px" alt="Internet Explorer logo"> | <img src="http://diokuz.github.io/pics/opera.png" width="48px" height="48px" alt="Opera logo"> | <img src="http://diokuz.github.io/pics/safari.png" width="48px" height="48px" alt="Safari logo"> | <img src="http://diokuz.github.io/pics/android.png" width="48px" height="48px" alt="Android browser logo"> |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 8+ ✔ | 3.6+ ✔ | 10+ ✔ | 11.5+ ✔ | 5.1+ ✔ | 4+ ✔ |

If you want to support IE9- (or Firefox 3.0, etc.), just set `$` prop to your `jQuery` instance.

```jsx
<Baron $={jQuery} ... />
```
