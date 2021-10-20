---
title: Svelte Keydown
description: Detecting and using keypress events is dead easy in Svelte. Make your app feel native with a few lines of code.
slug: keydown
author: Chris Ellis
authorImage: https://avatars.githubusercontent.com/u/814405?v=4
date: 10/8/21
---

Detecting keypress events is useful for creating webapps and websites that feel like native applications. The good news is Svelte makes it super easy to do this.

```js
<script>
  let keyPressed = ''
  function handleKeyUp(event) {
    keyPressed = event.key
  }
</script>

<svelte:window on:keyup={handleKeyUp} />

<h1>{keyPressed}</h1>
```
