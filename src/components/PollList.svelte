<script>
  import PollStore from "../stores/PollStore";
  import PollDetails from "./PollDetails.svelte";
</script>

<div class="poll-list">
  <!-- $PollStore below subscribes and unsubscribes us from the store -->
  {#each $PollStore as poll (poll.id)}
    <div><PollDetails {poll} /></div>
  {/each}
</div>

<style>
  .poll-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
</style>
