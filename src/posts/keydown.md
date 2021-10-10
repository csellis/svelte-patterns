---
title: Svelte Keydown
description: Detecting and using keypress events is dead easy in Svelte. Make your app feel native with a few lines of code.
slug: keydown
author: Chris Ellis
authorImage: https://avatars.githubusercontent.com/u/814405?v=4
date: 10/8/21
---

Detecting keypress events is useful for creating webapps and websites that feel like native applications. The good news is Svelte makes it super easy to do this.

```
<script>
  let keyPressed = ''
  function handleKeyUp(event) {
    keyPressed = event.key
  }
</script>

<svelte:window on:keyup={handleKeyUp} />

<h1>{keyPressed}</h1>
```

#h
#k
sdfjslkjdf

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean vitae est nibh. Praesent quis rhoncus nisl, ac condimentum sapien. Mauris venenatis vestibulum tempus. Vivamus tristique placerat bibendum. Nulla et consectetur tortor. In porta dui sollicitudin libero commodo mollis. Aliquam at aliquam orci.

Proin eget finibus metus. Donec at gravida nibh, sit amet aliquet nunc. Proin sollicitudin elementum sollicitudin. Integer nec lectus ac quam condimentum interdum. Etiam tincidunt ligula at dapibus tincidunt. Morbi nec lobortis neque. Pellentesque at sodales quam, iaculis iaculis lectus. Praesent cursus arcu eu cursus efficitur. Ut varius accumsan fermentum.

Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Etiam erat ex, varius et suscipit nec, fringilla id erat. Phasellus a diam hendrerit, semper mi a, iaculis nisl. Maecenas dolor ex, aliquet eu rhoncus in, feugiat in nisl. Vivamus a blandit risus. Curabitur aliquam mauris lectus, in lobortis dolor eleifend nec. Phasellus eleifend nisi luctus ligula rutrum, a euismod eros cursus. Fusce tincidunt ex purus, ac elementum felis viverra vel. Duis fermentum pharetra leo in tincidunt. Nunc tincidunt faucibus enim ut dignissim. Maecenas ac tincidunt dui. Vivamus placerat, nibh et molestie elementum, lorem leo fringilla justo, eu fringilla purus elit et mauris. Proin tincidunt quam nec nunc consequat, sollicitudin elementum magna efficitur. Integer ornare magna vitae maximus suscipit.

Ut luctus, libero at consequat molestie, nulla nisi vestibulum nisl, quis viverra metus metus eget mi. Donec orci turpis, convallis ut aliquam at, facilisis sed neque. Fusce eget augue velit. In hac habitasse platea dictumst. Curabitur sagittis, dolor nec pretium consequat, orci lectus eleifend nisi, congue condimentum ipsum elit vel ante. Etiam pellentesque erat tortor, sit amet efficitur augue suscipit in. Suspendisse in sagittis velit, ut volutpat sem. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

Vivamus ac tincidunt ipsum, et lobortis leo. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Integer tempus turpis tempor nisl tincidunt, et porttitor mi eleifend. Maecenas elit risus, sollicitudin ac sollicitudin et, molestie in arcu. Praesent luctus nisl turpis, eget facilisis justo interdum in. Curabitur ornare ex ac dui accumsan, vitae scelerisque ipsum dapibus. Cras vehicula faucibus lacus, in venenatis diam finibus eu. Maecenas sit amet tortor ac dui maximus elementum eu vitae purus. Curabitur eleifend, erat in vulputate commodo, lorem nibh mollis nibh, sed tincidunt nisi risus in velit. Morbi id iaculis odio, nec lacinia metus. Proin sagittis, ante lacinia venenatis porta, augue augue ullamcorper augue, at convallis mauris velit eu tellus. Sed eu sodales nisi, sit amet placerat ipsum. Quisque dictum augue et aliquam imperdiet.
