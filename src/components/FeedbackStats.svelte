<script>
  // brings in these vars
  export let count;
  export let average;
</script>

<div class="feedback-stats">
  <h4>{count}</h4>
  <h4>Ratings Average: {average}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
