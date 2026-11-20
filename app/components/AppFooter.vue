<script setup lang="ts">
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer
    class="border-t border-slate-200 px-6 py-7 dark:border-white/10"
  >
    <div
      class="mx-auto flex max-w-6xl flex-col items-center justify-between gap-3 text-center text-sm text-slate-500 sm:flex-row dark:text-slate-400"
    >
      <p>
        © {{ currentYear }} Khizha Rhizhane Duquesa. All rights reserved.
      </p>

      <p>
        ITE 18 · Activity 2 · Nuxt.js + Tailwind CSS
      </p>
    </div>
  </footer>
</template>
