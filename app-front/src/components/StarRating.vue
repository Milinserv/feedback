<template>
    <div class="flex">
        <button :value="rating" type="button" v-for="i in 5" :class="{ 'mr-1': i < 5 }"
                @click="$emit('update:modelValue', rating = i)"
                :disabled="isDisabled">
            <svg class="block h-8 w-8" :class="[ rating >= i ? 'text-amber-300': 'text-gray-300']"
                 fill="currentColor" xmlns="http://www.w3.org/2000/svg"
                 viewBox="0 0 20 20">
                <path d="M10 15l-5.878 3.09 1.123-6.545L.489 6.91l6.572-.955L10 0l2.939 5.955 6.572.955-4.756 4.635 1.123 6.545z"/>
            </svg>
        </button>
    </div>
</template>

<script setup>

const props = defineProps({
    rating: Number,
    isDisabled: {
        type: Boolean,
        default: false
    }
});
</script>
