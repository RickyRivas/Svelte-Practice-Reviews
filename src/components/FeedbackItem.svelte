<script>
  // to export custom events
  import { createEventDispatcher } from "svelte";
  // import card component
  import Card from "./ui/card.svelte";
  export let item;
  const dispatch = createEventDispatcher();

  const handleDelete = (itemId) => {
    // dispatch(func-name, data)
    dispatch("delete-feedback", itemId);
  };
</script>

<Card>
  <div class="num-display">
    {item.rating}
  </div>
  <button on:click={() => handleDelete(item.id)} class="close">X</button>
  <p class="text-display">
    {item.text}
  </p>
</Card>

<style>
  .num-display {
    position: absolute;
    top: -25px;
    left: -25px;
    width: 50px;
    height: 50px;
    background: #ff6a95;
    color: white;
    border: 1px #eee solid;
    border-radius: 50%;
    padding: 15px;
    text-align: center;
    font-size: 19px;
  }
  .close {
    position: absolute;
    right: 1rem;
    top: 1rem;
    background: none;
    border: 0;
  }
</style>
