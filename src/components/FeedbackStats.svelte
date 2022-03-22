<script>
  import { FeedbackStore } from "../stores/stores";

  $: count = $FeedbackStore.length;
  $: average =
    $FeedbackStore.reduce((a, { rating }) => a + rating, 0) /
    $FeedbackStore.length;
</script>

<div class="feedback-stats">
  <h4>{count} Reviews</h4>
  {#if average !== NaN}
    <h4>Rating Average: {average}</h4>
  {/if}
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
