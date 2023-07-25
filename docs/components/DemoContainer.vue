<script setup lang="ts">
import { Icon } from "@iconify/vue";

defineProps<{
    title?: string;
    overflow?: boolean;
}>();
</script>

<template>
    <div class="w-full" :class="{ 'overflow-x-auto': overflow }">
        <a v-if="title" class="capitalize md:text-lg font-semibold mb-2 ml-2 inline-flex items-center group"
            :href="`/components/${title?.replace(' ', '-')}.html`">{{ title }}
            <Icon icon="ic-round-arrow-forward" class="ml-2 group-focus:ml-3 group-hover:ml-3 transition-[margin]"></Icon>
        </a>
        <div class="bg-gradient-to-br from-teal9 to-green9 relative grid place-items-center p-4 md:p-10 min-h-[256px]"
            :class="[{ 'overflow-x-auto': overflow }, title ? 'rounded-xl lg:h-[400px]' : 'rounded-t-lg']">
            <slot />
        </div>
    </div>
</template>
