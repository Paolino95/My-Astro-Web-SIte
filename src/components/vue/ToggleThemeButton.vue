<template>
    <div class="ml-2">
        <input
            type="checkbox"
            class="absolute opacity-0"
            id="checkbox"
            :checked="isDark"
            @click="toggleDark()"
        />
        <label
            for="checkbox"
            class="cursor-pointer flex items-center justify-between relative border-2 bg-orange-200 dark:bg-zinc-900 rounded-3xl border-solid border-zinc-800 dark:border-zinc-100"
        >
            <i
                class="fas fa-sun w-6 h-6 md:w-8 md:h-8 p-1 mr-1 rounded-full text-sm bg-slate-50 dark:bg-transparent flex items-center justify-center"
            ></i>
            <i
                class="fas fa-moon p-1 w-6 h-6 md:w-8 md:h-8 rounded-full text-sm bg-transparent dark:bg-zinc-100 dark:text-zinc-900 flex items-center justify-center"
            ></i>
        </label>
    </div>
</template>

<script setup>
    import { useDark, useToggle } from '@vueuse/core';

    const isDark = useDark();
    const toggleDark = useToggle(isDark);
</script>
