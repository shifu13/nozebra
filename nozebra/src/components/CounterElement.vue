<script setup>
import { defineProps} from 'vue';

const props = defineProps({
    count: {
        type: Number,
        default: 5
    },
    textColor: {
        type: String,
        default: 'black'
    }
});

</script>
<template>
    <div :style="{ color: textColor }"> 
        <p>{{ count }}</p>
        <slot></slot>
    </div>
</template>