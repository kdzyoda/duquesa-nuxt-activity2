
<script setup lang="ts">
withDefaults(
  defineProps<{
    title: string
    description: string
    number?: string
  }>(),
  {
    number: '01'
  }
)
</script>

<template>
  <article
    class="group relative overflow-hidden rounded-2xl border border-slate-200 bg-white p-7 shadow-sm
           transition-all duration-300 ease-out
           hover:-translate-y-1 hover:border-emerald-400/60
           hover:shadow-[0_12px_35px_rgba(16,185,129,0.12)]
           dark:border-white/10 dark:bg-[#111C30]
           dark:hover:border-emerald-400/50
           dark:hover:shadow-[0_12px_35px_rgba(16,185,129,0.10)]
           motion-reduce:transform-none motion-reduce:transition-none"
  >
    <!-- Animated top accent line -->
    <div
      aria-hidden="true"
      class="pointer-events-none absolute left-0 top-0 h-[2px] w-0
             bg-gradient-to-r from-emerald-500 via-teal-400 to-transparent
             transition-all duration-500 group-hover:w-full
             motion-reduce:transition-none"
    ></div>

    <!-- Subtle background illumination -->
    <div
      aria-hidden="true"
      class="pointer-events-none absolute -right-12 -top-12 h-32 w-32
             rounded-full bg-emerald-400/0 blur-3xl
             transition-colors duration-500
             group-hover:bg-emerald-400/10
             motion-reduce:transition-none"
    ></div>

    <!-- Card content -->
    <div class="relative z-10">
      <p
        class="mb-4 font-mono text-xs font-medium
               text-emerald-600 dark:text-emerald-400"
      >
        {{ number }} / INFORMATION
      </p>

      <h3
        class="mb-4 text-xl font-bold text-slate-900
               transition-colors duration-300
               group-hover:text-emerald-600
               dark:text-white dark:group-hover:text-emerald-400
               motion-reduce:transition-none"
      >
        {{ title }}
      </h3>

      <p
        class="text-sm leading-7 text-slate-600 dark:text-slate-400"
      >
        {{ description }}
      </p>
    </div>
  </article>
</template>
