<script>
  // *Below line required for subscribe/unsub long way* //
  // import { onMount, onDestroy } from "svelte";

  import PollStore from "../stores/PollStore";
  import PollDetails from "./PollDetails.svelte";

  // *No longer need below if referencing store directly* //
  // export let polls = [];

  // *Subscribes to PollStore AND returns an unsubscribe function* //
  // const unsub = PollStore.subscribe((data) => {
  // updates local polls variable
  //   polls = data;
  // });

  // *LIFECYCLE HOOKS* //

  // // onMount(() => {
  // //   // maybe get data from a db
  // //   console.log("component mounted");
  // // });

  // onDestroy(() => {
  //   // unsub from store
  //   console.log("component destroyed");
  //   unsub();
  // });
</script>

<div class="poll-list">
  <!-- $PollStore below subscribes and unsubscribes us from the store -->
  {#each $PollStore as poll (poll.id)}
    <div><PollDetails {poll} on:vote /></div>
  {/each}
</div>

<style>
  .poll-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
</style>
