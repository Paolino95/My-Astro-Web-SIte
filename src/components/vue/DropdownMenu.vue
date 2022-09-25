<template>
    <button class="block md:hidden" aria-label="menu" @click="toggleInput = !toggleInput">
        <i
            class="buttons-transition fa-solid fa-bars text-2xl hover:text-zinc-600 dark:hover:text-slate-400"
        ></i>
    </button>
    <transition>
        <div
            v-if="toggleInput === true"
            class="block md:hidden absolute top-12 right-1 p-1 w-56 rounded-md"
        >
            <div
                class="flex flex-col overflow-auto text-sm z-10 bg-orange-50 border-[1px] border-zinc-900 dark:border-zinc-100 dark:bg-zinc-900 rounded-xl"
            >
                <h1 class="text-zinc-900 dark:text-zinc-100 p-2 font-semibold uppercase">Pagine</h1>

                <a
                    v-for="item in items"
                    :href="item.href"
                    class="text-zinc-900 hover:bg-orange-300 italic dark:text-zinc-100 p-2 hover:dark:bg-zinc-400"
                    >{{ item.name }}</a
                >
            </div>
        </div>
    </transition>
</template>

<script setup>
    import { ref } from 'vue';

    const items = [
        { name: 'Posts', href: './posts' },
        { name: `What I've use`, href: './wiu' },
    ];

    let toggleInput = ref(false);
</script>

<style scoped>
    .v-enter-active,
    .v-leave-active {
        transition: opacity 0.5s ease;
    }

    .v-enter-from,
    .v-leave-to {
        opacity: 0;
    }
</style>
