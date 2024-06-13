<template>
  <header id="cabecalho">
    <hgroup>
      <h1>Google Glass</h1>
      <h2> A Revolução do Google está chegando</h2>
    </hgroup>
    <!-- Indicativo de que aqui será exibida uma imagem -->
    <p>Imagem do Google Glass aqui</p>
    <nav>
      <ul>
        <li>Home</li>
        <li>Especificações</li>
        <li>Fotos</li>
        <li>Multimídia</li>
        <li>Fale conosco</li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent'
}
</script>

<style scoped>
nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
nav li {
  display: inline;
  margin-right: 10px;
}
</style>
