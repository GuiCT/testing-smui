<script lang="ts">
  import Button from "@smui/button";
  const variants = [
    "text",
    "raised",
    "unelevated",
    "outlined",
  ] as ("text" | "raised" | "unelevated" | "outlined")[];
  const colors = [
    "primary",
    "secondary",
  ] as ("primary" | "secondary")[];
</script>

<h1>Buttons</h1>
{#each colors as color}
  <h2>Color: {color}
    {#each variants as variant}
      <Button variant={variant} color={color}>
        {variant} {color}
      </Button>
    {/each}
  </h2>
{/each}