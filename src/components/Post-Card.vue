<template>
  <q-page>
    <div v-for="(item, index) in this.list" :key="index">
      <h1>{{ item.title }}</h1>
      <p>{{ item.body }}</p>
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
