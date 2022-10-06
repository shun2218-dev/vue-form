<script setup lang="ts">
import { ref, Ref } from "@vue/reactivity";
import Header from "./components/Header.vue";

const name = ref("");
const email = ref("");
const activate = ref(0);
const menus = ["Form", "List"];

const onSubmit = () => {
  console.log(name.value, email.value);
};
</script>

<template>
  <Header :menus="menus" :activate="activate" />
  <form action="" @submit.prevent="onSubmit" class="form">
    <input type="text" v-model="name" />
    <input type="email" v-model="email" />
    <button>submit</button>
  </form>
</template>

<style scoped lang="scss">
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}
</style>
