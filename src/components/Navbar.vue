
<template>
    <nav>
        <div class="nav-logo">
            <h1>Vue.js</h1>
            <img class="react-icon" src="/images/vue.png" alt="React">
        </div>
        <div class="menu-icon" @click="handleClick">
            <img v-if="data.isClicked" src="/images/close.png" alt="close icon">
            <img v-else src="/images/menu.png" alt="menu icon">
        </div>
        <ul class="nav-menu" :class="data.isClicked ? 'active' : ''">
            <li v-for="item in data.items" :key="item.title">
                <a :class="item.cName" :href="item.url">{{ item.title }}</a>
            </li>
        </ul>
        <Button>
            Sign in
        </Button>
    </nav>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import MenuItems from '@/utils/menuItems';
import Button from './Button.vue';

const data = ref({
    isClicked: false,
    items: MenuItems
})

const handleClick = () => {
    data.value.isClicked = !data.value.isClicked
}

</script>