<script lang="ts">
  import Button from "@smui/button";
</script>

<nav>
  <h1>Título da página</h1>
  <li>
    <Button variant="raised">Opção 1</Button>
    <Button variant="raised">Opção 2</Button>
  </li>
</nav>

<main>
  <slot />
</main>

<style lang="scss">
  nav {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    list-style: none;
    padding: 16px;
    backdrop-filter: brightness(0.666);

    h1 {
      font-size: 24px;
      font-family: "Roboto", sans-serif;
    }
  }

  main {
    padding: 24px;
  }
</style>
