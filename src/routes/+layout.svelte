<script lang="ts">
  import "../app.css";

  let { children } = $props();
</script>

<svelte:head>
  <title>P6U</title>
</svelte:head>

<div class="font-sans">
  {@render children()}
</div>
