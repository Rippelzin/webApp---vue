<template>
  <q-page>
    <div v-for="(item, index) in list" :key="index" class="card">
      <h1 class="nome">{{ item.name }}</h1>
      -
      <h2>{{ item.username }}</h2>
      <h1 class="email">{{ item.email }}</h1>
      <ul>
        <li>{{ item.address.street }}</li>
        <li>{{ item.address.suite }}</li>
        <li>{{ item.address.city }}</li>
      </ul>
      <h3>{{ item.phone }}</h3>
    </div>
  </q-page>
</template>

<script>
export default {
  props: {
    list: Object,
  },
};
</script>

<style>
.nome {
  background-color: lightblue;
}
.email {
  background-color: coral;
}
.card {
  background-color: lightgrey;
}
</style>
