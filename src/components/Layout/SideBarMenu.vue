<template>
    <div class="flex flex-col gap-14">
        <div class="flex items-center justify-center cursor-pointer" v-for="menu in menus" :key="menu.label">
            <i :class="[menu.icon, ' text-lg']" />
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    data() {
        return {
            menus: [
                {
                    label: 'Home',
                    url: '/home',
                    icon: 'fa-regular fa-home'
                },
                {
                    label: 'Pie Chart',
                    url: '/pie-chart',
                    icon: 'fa-regular fa-chart-pie-simple'
                },
                {
                    label: 'Line Chart',
                    url: '/line-chart',
                    icon: 'fa-regular fa-chart-line-up'
                },
                {
                    label: 'Book',
                    url: '/book',
                    icon: 'fa-regular fa-book-blank'
                },
                {
                    label: 'More',
                    url: '/more',
                    icon: 'fa-regular fa-ellipsis-vertical'
                }
            ]
        }
    }
})
</script>