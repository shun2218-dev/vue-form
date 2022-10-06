<script setup lang="ts">
import { computed, Ref, ref } from "vue";

export type Props = {
  menus: string[];
  activate: Ref<number>;
};
const props = defineProps<Props>();
const isActive = (index: number, activate: number) => (activate = index);
</script>

<template>
  <header class="header">
    <nav>
      <ul class="menu">
        <li
          v-for="(menu, index) in menus"
          :key="menu"
          @click="isActive(index, activate.value)"
          class="menuItem"
          :class="{
            activate: activate.value === index,
          }"
        >
          {{ menu }}
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped lang="scss">
.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 3%;
  box-shadow: 2px 2px 2px 1px #323232;
}
.menu {
  display: flex;
  justify-content: center;
  width: 100%;
  gap: 10%;
}

.menuItem {
  cursor: pointer;
}
.activate {
  text-decoration-line: underline;
  font-weight: bold;
  font-size: 1.2rem;
}
</style>
