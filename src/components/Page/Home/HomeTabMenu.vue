<template>
    <home-tab-menu-wrapper>
        <home-tab-menu-item v-for="tab in tabs" :active="tab.active" :key="tab.label">
            {{ tab.label }}
        </home-tab-menu-item>
    </home-tab-menu-wrapper>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import HomeTabMenuWrapper from "./HomeTabMenuWrapper.vue";
import HomeTabMenuItem from "./HomeTabMenuItem.vue";

export default defineComponent({
    data() {
        return {
            tabs: [
                {
                    label: "Overview",
                    active: true
                },
                {
                    label: "Wallet",
                    active: false
                },
                {
                    label: "Vault",
                    active: false
                },
            ]
        }
    },
    components: {
        HomeTabMenuWrapper,
        HomeTabMenuItem
    }
})
</script>