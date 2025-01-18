<script setup>
import { SfIconCheckCircle, SfIconClose } from '@storefront-ui/vue';
</script>  

<template>
    <div
        role="alert"
        class="flex items-start md:items-center shadow-md bg-positive-100 pr-2 pl-4 ring-1 ring-positive-200 typography-text-sm md:typography-text-base py-1 rounded-md"
    >
        <p class="py-2 mr-2 w-full text-center">Get Up to <strong>40% OFF</strong> New-Season Styles <strong class="bg-primary-700 text-primary-50 py-1 px-2 text-sm">Men</strong> <strong class="bg-primary-700 text-primary-50 py-1 px-2 text-sm">Women</strong> <span class="text-slate-300">*Limited time only</span></p>
        <button
        type="button"
        class="p-1.5 md:p-2 ml-auto rounded-md text-positive-700 hover:bg-positive-200 active:bg-positive-300 hover:text-positive-800 active:text-positive-900 focus-visible:outline focus-visible:outline-offset"
        aria-label="Close positive alert"
        >
        <SfIconClose class="hidden md:block" />
        <SfIconClose size="sm" class="block md:hidden" />
        </button>
    </div>
</template>
