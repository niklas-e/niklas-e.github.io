---
layout:     post
title:      'Popovers are finally becoming a browser problem'
date:       2026-05-12 18:00:00
author:     Niklas Engblom
summary:    Popover API and CSS anchor positioning can finally move a big part of popover positioning logic into the browser.
categories: Code
thumbnail:  browser
tags:
 - web
 - development
---

I have implemented way too many popovers.

Tooltips, structured tooltips, dropdown menus, custom menus, little info cards, things that look like tooltips but are actually interactive, and things that started as simple dropdowns but slowly grew into tiny applications.

The annoying part is rarely opening a box. That part is easy. The annoying part is everything around the box.

Where should it appear? What if there is not enough space? What if the user resizes the window? What if the content inside the popover changes? What if the trigger is near the edge of the screen? What if the first preferred position does not fit, but the second one does?

At some point, almost every custom popover implementation becomes a positioning engine.

## The old shape of the problem

The usual solution is some variation of measuring the trigger, measuring the popover, measuring the viewport, picking a position, noticing that it does not fit, flipping it, listening to resize events, listening to content changes, and doing it all again.

There are good libraries for this. There are also many custom implementations that start small and then collect edge cases until nobody wants to touch them.

I have written some of those. I have used some of those. I have probably cursed at most of those.

So when I noticed that `position-try-fallbacks` was now Baseline, I wanted to test how far modern CSS could take this. The question was simple: how little custom positioning logic do we need now?

## Finally, less measuring

The interesting part is that browsers can now understand this relationship more directly. There is an anchor and a thing positioned relative to that anchor. There is a preferred position and fallback positions.

That sounds exactly like what I have wanted for years.

With the Popover API, the browser can already handle a lot of the popover behavior. Opening, closing, top layer behavior, and light dismiss are not things I particularly enjoy rebuilding for the tenth time. Then CSS anchor positioning can take over more of the geometry side.

A very small version of the idea looks something like this:

```html
<button id="menu-button">Menu</button>

<div id="menu" popover>
  <button>Profile</button>
  <button>Settings</button>
  <button>Log out</button>
</div>
```

```js
menuButton.addEventListener("click", () => {
  menu.showPopover({ source: menuButton });
});
```

Then the positioning can live mostly in CSS.

```css
#menu {
  position-area: bottom span-right;
  position-try: flip-block, flip-inline;
}
```

This is the kind of thing I wanted to try. Not because the exact snippet above is a full component. It is not. Real components still need care around focus, keyboard behavior, semantics, and interaction details. A structured tooltip is not the same thing as a dropdown menu.

But for the actual positioning problem, this is a big improvement.

## The browser should know this stuff

The browser is in a much better position to answer layout questions than my component code. It knows the viewport. It knows the layout. It knows whether something overflows. It can react to resizing and layout changes without me wiring together a tiny measurement framework.

That is the part that feels good. Instead of asking JavaScript to constantly measure and guess, CSS can describe the intent.

I want this thing below the trigger. If that does not work, try another position. If that does not work either, try something else.

That is exactly the kind of logic that should not have to live in every application separately.

## Not quite the dream API

The funny thing is that the mental model is simpler than the syntax.

In my head, I want to write something like this:

```css
.popover {
  /** Open popover to the top-left of anchor from popover's bottom-right */
  attach-to: source top left;
  position: bottom right;
  fallback: top center, right center;
}
```

That is not the API.

The real API is more CSS-like, which means it is powerful, but also a bit indirect. There are anchors, position areas, try options, fallback rules, and a few different ways to express the same idea.

It is not bad. It is just not as simple as saying: this is my popover, attach it here, prefer this position, and if it does not fit, try these.

Maybe that level of simplicity would hide too much. Maybe the current shape is what we need for the feature to be flexible enough. I am not sure yet.

What I do know is that this is much better, but not as simple as it could be.

## Good enough to use

The surprising part was that this did not feel like a toy experiment.

I scribbled together a reusable React component to see how it would feel in practice. To make it dynamic and reusable, there were quite a lot of CSS variables involved. Still, I think that is a much nicer problem than the old growing pile of positioning corner cases.

For the kind of structured tooltip or dropdown menu I was testing, this approach felt good enough for real use. Not as a copy paste solution for every possible popover, but as a serious foundation.

You will most likely still have component logic around it. A dropdown is interactive, but a tooltip might not be. Focus, closing and other things still matter.

But the part where I used to write or import a lot of positioning code can now be much smaller. That is a win.

## Less arcane positioning code, please

Popover positioning has always felt like one of those frontend problems that should be simple, but somehow never is.

Modern CSS does not magically make every popover easy. It does not remove the need to think. It does not turn dropdowns, tooltips, and menus into the same component.

But it moves a meaningful part of the problem into the browser.

Anyway, I think I will finish this with a single word: finally.
