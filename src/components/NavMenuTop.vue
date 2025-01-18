<template>
    <nav class="flex justify-center w-full py-2 px-4 lg:py-2 lg:px-6 bg-white border-b border-neutral-200">
        <div class="flex flex-wrap justify-between lg:flex-nowrap items-center flex-row md:justify-start h-full max-w-[1536px] w-full">
          <p class="mr-auto uppercase text-sm text-gray-600 font-bold">Free Returns. Standard Shipping Orders $99+</p>
            <div class="flex flex-wrap lg:flex-nowrap whitespace-nowrap">
            <SfButton
                v-for="item in items"
                :key="item.label"
                variant="tertiary"
                :class="[
                'py-1 flex h-full w-full text-gray-600 text-sm',
                ]"
            >
                {{ item.label }}
            </SfButton>
        </div>
        </div>
    </nav>
  </template>
  <script setup>
  import { SfButton } from '@storefront-ui/vue';

  const items = [
    {
      label: 'My Account',
    },
    {
      label: 'About US',
    },
    {
      label: 'Blog',
    },
    {
      label: 'My Watchlist',
    },
    {
      label: 'Cart',
    },
    {
      label: 'Log In',
    },
    {
      label: 'Eng',
    },
    {
      label: 'USD',
    },
  ];
  </script>  