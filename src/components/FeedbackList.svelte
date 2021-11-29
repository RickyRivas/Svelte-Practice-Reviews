<script>
  import FeedbackItem from "./FeedbackItem.svelte";
  export let feedback = [];
</script>

{#each feedback as fb (fb.id)}
  <!-- event forwarding from feedback item to main app-->
  <FeedbackItem item={fb} on:delete-feedback />
{/each}
