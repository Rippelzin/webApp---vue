<template>
  <q-page>
    <div v-for="item in list" :key="item.id">
      <p :class="{ feito: item.completed }">{{ item.id }} - {{ item.title }}</p>
    </div>
  </q-page>
</template>
<script>
import axios from "axios";
import { list } from "postcss";
export default {
  props: {
    list: Object,
  },
};
</script>

<style>
.feito {
  background-color: green;
}
</style>
