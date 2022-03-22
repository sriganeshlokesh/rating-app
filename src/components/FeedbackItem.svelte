<script>
  import { createEventDispatcher } from "svelte";
  import Card from "./UI/Card.svelte";
  export let feed = {};

  const dispatch = createEventDispatcher();

  const handleDelete = (feedId) => {
    dispatch("delete-feedback", feedId);
  };
</script>

<Card>
  <div class="num-display">
    {feed.rating}
  </div>
  <button class="close" on:click={() => handleDelete(feed.id)}>X</button>
  <p class="text-display">
    {feed.text}
  </p>
</Card>

<style>
  .num-display {
    position: absolute;
    top: -10px;
    left: -10px;
    width: 50px;
    height: 50px;
    background: #ff6a95;
    color: #fff;
    border: 1px #eee solid;
    border-radius: 50%;
    padding: 10px;
    text-align: center;
    font-size: 19px;
  }
  .close {
    position: absolute;
    top: 10px;
    right: 20px;
    cursor: pointer;
    background: none;
    border: none;
  }
</style>
