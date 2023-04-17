<script lang="ts">
  import Card from "../components/Card.svelte";
</script>

<section>
  <Card>
    <h1 slot="title">Card vazio</h1>
  </Card>

  <Card>
    <h1 slot="title">Card com conteúdo</h1>
    Conteúdo do card
  </Card>

  <Card hoverable>
    <h1 slot="title">Card com efeito hover</h1>
    Conteúdo do card
  </Card>

  <Card easterEgg>
    <h1 slot="title">Card com easter egg</h1>
    Conteúdo do card
  </Card>

  <Card expandable>
    <h1 slot="title">Card com efeito de expansão</h1>
    Conteúdo do card
  </Card>

  <Card hoverable easterEgg expandable>
    <h1 slot="title">Megazord</h1>
    Conteúdo do card
  </Card>
</section>

<style lang="scss">
  section {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: stretch;
    flex-wrap: wrap;
    gap: 16px;
  }
</style>
