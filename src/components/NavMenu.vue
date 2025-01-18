<template>
    <nav class="flex justify-center w-full py-2 px-4 lg:py-5 lg:px-6 bg-white">
        <div class="flex flex-wrap justify-between lg:flex-nowrap items-center flex-row md:justify-start h-full max-w-[1536px] w-full">
            <div class="flex flex-wrap lg:flex-nowrap">
            <SfButton
                v-for="item in items"
                :key="item.label"
                variant="tertiary"
                :class="[
                'py-1 flex h-full w-full hover:text-primary-800 hover:bg-primary-100 active:text-primary-900 active:bg-primary-200',
                { 'text-primary-900 bg-primary-200': selectedItem === item.label },
                ]"
                @click="onClickHandler(item.label)"
            >
                {{ item.label }}
            </SfButton>
        </div>
        <SfButton variant="tertiary" class="ml-auto">Special Offer</SfButton>
        </div>
    </nav>
  </template>
  <script setup>
  import { ref } from 'vue';
  import { SfButton } from '@storefront-ui/vue';

  const items = [
    {
      label: 'Home',
    },
    {
      label: 'Products',
    },
    {
      label: 'Cart',
    },
    {
      label: 'Watchlist',
    },
    {
      label: 'Account',
    },
  ];
  const selectedItem = ref('');
  function onClickHandler(itemLabel) {
    selectedItem.value = itemLabel;
  }
  </script>  