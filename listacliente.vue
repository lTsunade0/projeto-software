<template>
  <div class="client-list">
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="client in clients" :key="client.id" :style="{ color: client.color }">
        {{ client.name }}
      </li>
    </ul>
    <form @submit.prevent="addClient">
      <input v-model="newClientName" type="text" placeholder="Nome do cliente" required>
      <select v-model="newClientColor" required>
        <option value="" disabled>Escolha uma cor</option>
        <option value="red">Vermelho</option>
        <option value="green">Verde</option>
        <option value="blue">Azul</option>
      </select>
      <button type="submit">Adicionar Cliente</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'ClientList',
  props: {
    title: {
      type: String,
      default: 'Lista de Clientes'
    },
    clients: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      newClientName: '',
      newClientColor: ''
    }
  },
  methods: {
    addClient() {
      if (this.newClientName.trim() !== '' && this.newClientColor !== '') {
        this.$emit('add-client', { name: this.newClientName, color: this.newClientColor });
        this.newClientName = '';
        this.newClientColor = '';
      }
    }
  }
}
</script>

<style scoped>
.client-list {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 10px 0;
  font-size: 18px;
}
form {
  margin-top: 20px;
}
input, select {
  padding: 8px;
  font-size: 16px;
  margin-right: 10px;
}
button {
  padding: 8px 16px;
  font-size: 16px;
  background-color: #42b983;
  color: white;
  border: none;
  cursor: pointer;
}
button:hover {
  background-color: #339966;
}
</style>
