<script setup lang="ts">
import { makeFirstCharUpper } from '@/utils/helper'

const route = useRoute()

// take category from route params & make first char upper
const category = computed(() => {
  const name = route.params.category || ''
  let strName = ''

  if (Array.isArray(name))
    strName = name.at(0) || ''
  else strName = name
  return makeFirstCharUpper(strName)
})
</script>

<template>
  <div class="w-full mt-10">
    <div class="p-6 my-4 rounded-md bg-gray-200 dark:bg-slate-900 mx-auto max-w-6xl">
      <h1 class="dark:text-white font-semibold leading-tight text-xl md:text-2xl">
        #{{ category }}
      </h1>
    </div>
  </div>
</template>

