<template>
    <UseDark v-slot="{ isDark, toggleDark }">
        <div>
            <input
                type="checkbox"
                class="absolute opacity-0"
                id="checkbox"
                :checked="isDark"
                @click="toggleDark()"
            />
            <label
                for="checkbox"
                class="cursor-pointer flex items-center justify-between relative border-2 rounded-3xl border-solid border-zinc-800 dark:border-zinc-100"
            >
                <i class="fas fa-sun p-1 pr-2 text-sm"></i>
                <i class="fas fa-moon p-1 text-sm"></i>

                <div
                    class="ball opacity-4 w-6 h-6 bg-zinc-800 dark:bg-zinc-100 text-md absolute rounded-full transition duration-300 ease-linear items-center"
                />
            </label>
        </div>
    </UseDark>
</template>

<script setup>
    import { UseDark } from '@vueuse/components';
</script>

<style scoped>
    #checkbox:checked + label .ball {
        transform: translateX(21px);
    }
</style>
