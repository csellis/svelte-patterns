---
title: Adding body classes on events
description: With this pattern you can stop the <body> from scrolling when a mobile menu is open
slug: body-classes-on-events
author: Chris Ellis
authorImage: https://avatars.githubusercontent.com/u/814405?v=4
date: 12/05/21
---

This one took me a little bit of time to find a solution. The problem I had was stopping scrolling when I had a mobile menu open.

The solution is to conditionally render a class with `<svelte:head>`
  
```
<svelte:head>
  {#if $mobileMenuOpen}
    <style>
      body {
        overflow: hidden;
      }
    </style>
  {/if}
</svelte:head>
```
  
There's alternative ideas floating out there how this should work. I couldn't get them to work in Svelte Kit.
This thread discusses it:
  [Change body class via <svelte:body />](https://github.com/sveltejs/svelte/issues/3105)
  
<svelte:body> only seems to work for actions, not classes.
