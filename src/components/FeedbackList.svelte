<script>
  import FeedbackItem from "./FeedbackItem.svelte";
  export let feedback = [];
</script>

{#each feedback as feed (feed.id)}
  <FeedbackItem {feed} />
{/each}
