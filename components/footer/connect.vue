<script setup lang="ts">
import { useAppStore } from '~/stores/appStore.js'
import languages from '~/content/language.json'
import type { FooterData, SupportedLanguage } from '~/types/language'

const footerData: FooterData = languages.footer

const appStore = useAppStore()

const selectedlanguage = useCookie< string >('language', {
  default: () => 'bn',
  path: '/',
})
</script>

<template>
  <div>
    <p class=" dark:text-zinc-300   text-base font-semibold">
      {{ footerData.connect.contact[selectedlanguage ? selectedlanguage as SupportedLanguage : appStore.language as SupportedLanguage] }}
    </p>
    <p class="dark:text-zinc-300  ">
      <Icon name="fa:phone" size="1em" />
      +8801759139913
    </p>

    <p class="dark:text-zinc-300 item-center ">
      {{ footerData.connect.or[selectedlanguage ? selectedlanguage as SupportedLanguage : appStore.language as SupportedLanguage] }}
    </p>
    <a
      href="mailto: zubairahmedrafi37@gmail.com"
      class="block text-center w-full bg-sky-700 p-2 rounded-lg text-[#F1F2F4]  mt-3 text-sm"
    >
      {{ footerData.connect.mail[selectedlanguage ? selectedlanguage as SupportedLanguage : appStore.language as SupportedLanguage] }}
    </a>
  </div>
</template>
