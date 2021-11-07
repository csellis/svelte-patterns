---
title: Passing the Midpoint of an Element around
description: Passing the midpoint of an element around can be tricky.
slug: midpoint
author: Chris Ellis
authorImage: https://avatars.githubusercontent.com/u/814405?v=4
date: 11/7/21
---

Recently I needed to pass the midpoint height of a modal element around. The content inside the modal was larger than the element and I wanted to absolutely position a button on the outside of it.

I made use of Stores, bind:clientWidth/Height, and the style tag in this one.

```
// stores.js
export const modalSize = writable({ w: 0, h: 0 })
```

As you see the store is pretty simple.

```
<!-- Modal.svelte -->
<script>
  import { modalSize } from '../../../lib/api/stores'

  let trackSize = false
  let w, h

  onMount(() => {
    if (trackSize) {
      modalSize.update(
        (n) =>
          (n = {
            w,
            h,
          })
      )
    }
  })
</script>

<div
  class="fixed z-50 inset-24 overflow-y-auto"
  aria-labelledby="modal-title"
  role="dialog"
  aria-modal="true"
  bind:clientWidth={w}
  bind:clientHeight={h}
>
  | Modal Content here
</div>
```

This update could probably be shifted to a method from the store but I'm being lazy.

```
<!-- PhotoPreviews.svelte -->
<script>
  import { modalSize } from '../../../lib/api/stores'

  $: midpointHeight = $modalSize.h / 2
</script>

{#if preview}
  <Portal>
    <Modal {closeModal} maxWidth="screen-md" fullSize={true} trackSize={true}>
      <div class="flex relative">
        <button
          style="top: {midpointHeight}px"
          class="absolute -left-12"
          on:click={() => previewPhoto(previewIndex - 1)}
          type="button"
        >
          Left
        </button>
        <Photo handle={preview} imgClass="object-scale-down" />
        <button
          style="top: {midpointHeight}px"
          class="absolute -right-12"
          on:click={() => previewPhoto(previewIndex + 1)}
          type="button"
        >
          Right
        </button>
      </div>
    </Modal>
  </Portal>
{/if}
```

Here's where the magic happens. Now I can link the buttons position to the Modal container. They're outside of the normal flow and if I were to position them based on the document they wouldn't be in the perceived middle.
