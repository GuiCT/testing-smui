<script lang="ts">
  export let hoverable = false;
  export let easterEgg = false;
  export let expandable = false;

  let flags = ["transFlag", "mlmFlag", "wlwFlag", "biFlag"];

  // Use random flag
  let flagIndex = Math.floor(Math.random() * flags.length);
</script>

<div
  id="card"
  class={easterEgg ? flags[flagIndex] : ""}
  class:hoverable
  class:expandable
  on:mouseenter={() => {
    flagIndex = Math.floor(Math.random() * flags.length);
  }}
>
  <header>
    <h1><slot name="title" /></h1>
  </header>
  <article>
    <slot />
  </article>
</div>

<style lang="scss">
  .transFlag:hover {
    background: rgb(91, 207, 251);
    background: linear-gradient(
      90deg,
      rgba(91, 207, 251, 0.5) 0%,
      rgba(246, 170, 185, 0.5) 25%,
      rgba(255, 255, 255, 0.5) 50%,
      rgba(246, 170, 185, 0.5) 75%,
      rgba(91, 207, 251, 0.5) 100%
    );
  }

  .mlmFlag:hover {
    background: rgb(7, 141, 112);
    background: linear-gradient(
      90deg,
      rgba(7, 141, 112, 0.5) 0%,
      rgba(152, 232, 193, 0.5) 25%,
      rgba(255, 255, 255, 0.5) 50%,
      rgba(123, 173, 226, 0.5) 75%,
      rgba(61, 26, 120, 0.5) 100%
    );
  }

  .wlwFlag:hover {
    background: rgb(213, 45, 0);
    background: linear-gradient(
      90deg,
      rgba(213, 45, 0, 0.5) 0%,
      rgba(239, 118, 39, 0.5) 16%,
      rgba(255, 154, 86, 0.5) 38%,
      rgba(255, 255, 255, 0.5) 50%,
      rgba(209, 98, 164, 0.5) 62%,
      rgba(181, 86, 144, 0.5) 84%,
      rgba(163, 2, 98, 0.5) 100%
    );
  }

  .biFlag:hover {
    background: rgb(214, 2, 112);
    background: linear-gradient(
      90deg,
      rgba(214, 2, 112, 1) 0%,
      rgba(155, 79, 150, 1) 45%,
      rgba(155, 79, 150, 1) 55%,
      rgba(0, 56, 168, 1) 100%
    );
  }

  .hoverable:hover {
    border-color: #063970;
  }

  .expandable:hover {
    transform: scale(1.05);
  }

  div {
    border: 1px solid white;
    border-radius: 8px;
    padding: 4px 16px;
  }

  header {
    display: flex;
    flex-direction: row;
    align-items: center;
    padding-top: 8px;
    padding-bottom: 8px;

    h1 {
      font-size: 24px;
      font-family: "Roboto", sans-serif;
      font-weight: bold;
    }
  }

  article {
    // Only if not empty
    &:not(:empty) {
      padding-top: 8px;
      padding-bottom: 8px;
      border-top: 1px solid white;
    }
  }
</style>
