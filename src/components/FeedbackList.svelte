<script>
  // import { onMount, onDestroy } from "svelte";
  import { FeedbackStore } from "../stores/stores";
  import { fade, scale } from "svelte/transition";
  import FeedbackItem from "./FeedbackItem.svelte";
  // let feedback = [];

  // const unsubscribe = FeedbackStore.subscribe((data) => (feedback = data));

  // onMount(() => {
  //   console.log("mounted");
  // });

  // onDestroy(() => {
  //   unsubscribe();
  // });
</script>

{#each $FeedbackStore as feed (feed.id)}
  <div in:scale out:fade={{ duration: 500 }}>
    <FeedbackItem {feed} />
  </div>
{/each}
