<template>
  <div
    class="flex min-h-screen flex-col bg-[#F3F6FA] text-slate-900 transition-colors duration-200 dark:bg-[#0B1120] dark:text-white"
  >
    <AppHeader />

    <main class="flex-1">
      <slot />
    </main>

    <AppFooter />
  </div>
</template>
