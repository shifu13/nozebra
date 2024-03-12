<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    items: {
        type: Array,
        default: () => []
    }
});
</script>

<template>
    <ul class="list">
        <li class="list__item" v-for="item in props.items" :key="item">{{ item }}</li>
        <slot></slot>
    </ul>
</template>