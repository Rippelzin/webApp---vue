<template>
  <q-page class="flex flex-center">
    <!--<TodoCard :list="listCards" :teste="teste" />-->
    <!-- <PostCard :list="listPosts" />-->
    <UserCard :list="listusers" />
  </q-page>
</template>

<script>
/* eslint-disable */
import { defineComponent } from "vue";
import axios from "axios";
import TodoCard from "src/components/Todo-Card.vue";
import PostCard from "src/components/Post-Card.vue";
import UserCard from "src/components/User-Card.vue";

export default defineComponent({
  name: "IndexPage",

  data() {
    return {
      listCards: [],
      listPosts: [],
      listusers: [],
    };
  },
  components: {
    TodoCard,
    PostCard,
    UserCard,
  },
  mounted() {
    this.fetchDataTodos();
    this.fetchDataPosts();
    this.fetchDataUsers();
  },
  methods: {
    fetchDataTodos() {
      axios
        .get("https://jsonplaceholder.typicode.com/todos")
        .then((response) => (this.list = response.data));
    },

    fetchDataPosts() {
      axios
        .get("https://jsonplaceholder.typicode.com/posts")
        .then((response) => (this.listPosts = response.data));
    },
    fetchDataUsers() {
      axios
        .get("https://jsonplaceholder.typicode.com/users")
        .then((response) => (this.listusers = response.data));
    },
  },
});
</script>
