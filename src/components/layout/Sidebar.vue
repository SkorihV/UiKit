<script setup>
import {ref} from "vue";

const props = defineProps({
  openSidebar: {
    type: Boolean,
    required: true
  }
})

const links = ref([
  {name: 'Типография', href:'/typography'},
  {name: 'Кнопка', href:'/button'},
])

</script>

<template>
  <div :class="['sidebar', {'sidebar_isopen' : openSidebar}]">
      <router-link class="sidebar__link" v-for="link in links" :key="link.name" :to="link.href">{{link.name}}</router-link>
  </div>
</template>


<style lang="scss" scoped>
.sidebar {
  left: 0;
  top:62px;
  height: 100%;
  position: fixed;
  background: #fff;
  width: 250px;
  padding: 20px;
  transition: .2s;
  box-shadow: 0 0 10px rgb(0,0,0,0.07);
  transform: translateX(-270px);
  &_isopen {
    transform: translateX(0);
  }
  &__link {
    display: block;
    border-radius: 12px;
    padding: 10px;
    border: 2px solid #fff;
    transition: .2s;
    font-weight: bold;
    margin-bottom: 10px;
    &:hover {
      border-color: var(--primary-color-hover);
    }
  }
}
</style>
