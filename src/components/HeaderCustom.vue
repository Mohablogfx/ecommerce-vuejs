<template>
    <header class="flex justify-center w-full py-2 px-4 lg:py-5 lg:px-6 bg-white border-b border-neutral-200">
      <div
        class="flex flex-wrap justify-between lg:flex-nowrap items-center flex-row md:justify-start h-full max-w-[1536px] w-full lg:gap-32"
      >
        <SfButton variant="tertiary" square class="md:hidden" aria-label="Go back">
          <SfIconArrowBack />
        </SfButton>
        <a
          href="#"
          aria-label="SF Homepage"
          class="inline-block mr-4 focus-visible:outline focus-visible:outline-offset focus-visible:rounded-sm shrink-0"
        >
          <img
            src="https://storage.googleapis.com/sfui_docs_artifacts_bucket_public/production/vsf_logo.svg"
            alt="Sf Logo"
            class="w-[175px] md:h-6 md:w-[176px] lg:w-[12.5rem] lg:h-[1.75rem]"
          />
        </a>
        <SfButton variant="tertiary" class="md:hidden" square aria-label="Search">
          <SfIconSearch />
        </SfButton>
        <SfButton
          aria-label="Open categories"
          class="hidden md:block lg:hidden order-first lg:order-1 mr-4"
          square
          variant="tertiary"
        >
          <SfIconMenu />
        </SfButton>
        <form
          role="search"
          class="hidden md:flex flex-[100%] order-last lg:order-3 mt-2 lg:mt-0 pb-2 lg:pb-0"
          @submit.prevent="search"
        >
          <SfInput
            v-model="inputValue"
            type="search"
            class="[&::-webkit-search-cancel-button]:appearance-none"
            placeholder="Search"
            wrapper-class="flex-1 h-10 pr-0"
            size="base"
          >
            <template #suffix>
              <span class="flex items-center">
                <SfButton
                  variant="tertiary"
                  square
                  aria-label="search"
                  type="submit"
                  class="rounded-l-none hover:bg-transparent active:bg-transparent"
                >
                  <SfIconSearch />
                </SfButton>
              </span>
            </template>
          </SfInput>
        </form>
        <nav class="flex-1 hidden md:flex justify-end lg:order-last lg:ml-4">
          <div class="flex flex-row flex-nowrap">
            <SfButton
              v-for="actionItem in actionItems"
              :key="actionItem.ariaLabel"
              class="mr-2 -ml-0.5 rounded-md text-primary-700 hover:bg-primary-100 active:bg-primary-200 hover:text-primary-600 active:text-primary-700"
              :aria-label="actionItem.ariaLabel"
              variant="tertiary"
              square
            >
              <template #prefix>
                <Component :is="actionItem.icon" />
              </template>

              <div v-if="actionItem.role === 'phone'" class="hidden xl:inline-flex xl:flex-col whitespace-nowrap">
                <span class="text-gray-500 text-sm text-left">{{ actionItem.subLabel }}</span>
                <span class="text-neutral-900 text-xl">{{ actionItem.label }}</span>
              </div>
            </SfButton>
          </div>
        </nav>
      </div>
    </header>
  </template>
  <script setup>
  import { ref } from 'vue';
  import {
    SfButton,
    SfIconShoppingCart,
    SfIconFavorite,
    SfIconPerson,
    SfIconCall,
    SfInput,
    SfIconSearch,
    SfIconMenu,
    SfIconArrowBack,
  } from '@storefront-ui/vue';
  
  const actionItems = [
    {
      icon: SfIconCall,
      ariaLabel: 'Phone',
      role: 'phone',
      label: '+123 456 7890',
      subLabel: 'Call us now',
    },
    {
      icon: SfIconShoppingCart,
      ariaLabel: 'Cart',
      role: 'button',
      label: '',
    },
    {
      icon: SfIconFavorite,
      ariaLabel: 'Wishlist',
      role: 'button',
      label: '',
    },
    {
      label: 'Log in',
      icon: SfIconPerson,
      ariaLabel: 'Log in',
      role: 'login',
    },
  ];
  
  const inputValue = ref('');
  
  const search = () => {
    alert(`Successfully found 10 results for ${inputValue.value}`);
  };
  </script>  