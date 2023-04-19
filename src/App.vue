<script setup>
import {ref} from "vue";

import LayoutHeader from '@/components/layout/Header.vue'
import LayoutSidebar from '@/components/layout/Sidebar.vue'

const isOpenMenu = ref(false)

const toggleMenu = () => {
    isOpenMenu.value = !isOpenMenu.value;
}

</script>

<template>
    <div class="container">
        <div class="sidebar-toggle" @click="toggleMenu">&#5125;</div>
        <layout-header/>
        <layout-sidebar :openSidebar="isOpenMenu"/>
        <div :class="['content', {content_full : !isOpenMenu}]">
            <router-view/>
        </div>
    </div>
</template>

<style lang="scss">
@import "./styles/global.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.content {
  max-width: 1400px;
  margin-left: 270px;
  transition: .2s;
  &_full {
    margin-left: 20px;
  }
}

.sidebar-toggle {
    position: fixed;
    left: 0;
    width: 15px;
    background: var(--pripary-color);
    height: 100%;
    top: 62px;
    z-index: 1;
    cursor: pointer;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
}


</style>
