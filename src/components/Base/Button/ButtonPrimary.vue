<template>
    <div :class="['flex items-center h-10 px-10 rounded-full cursor-pointer', active ? 'bg-blue-600 text-white' : ' bg-gray-100 text-black', ' hover:bg-blue-600 hover:text-white']">
        <slot />
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    props: {
        active: {
            type: Boolean,
            required: false,
            default: false
        }
    }
})
</script>