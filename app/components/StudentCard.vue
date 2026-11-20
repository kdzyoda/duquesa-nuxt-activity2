<script setup lang="ts">
withDefaults(
  defineProps<{
    name: string
    course: string
    yearLevel: string
    studentId: string
    initials: string
    department?: string
    email?: string
  }>(),
  {
    department: 'College of Computing and Information Sciences',
    email: 'ccis@carsu.edu.ph'
  }
)
</script>

<template>
  <article
    class="rounded-2xl border border-slate-200 bg-white p-6 shadow-sm transition-all duration-200 hover:-translate-y-1 hover:border-emerald-500/40 hover:shadow-lg dark:border-white/10 dark:bg-[#111C30]"
  >
    <div class="mb-6 flex items-center gap-4">
      <div
        class="flex h-16 w-16 shrink-0 items-center justify-center rounded-2xl border border-emerald-500/20 bg-emerald-500/10 text-xl font-bold text-emerald-600 dark:text-emerald-400"
      >
        {{ initials }}
      </div>

      <div class="min-w-0">
        <h2 class="text-base font-bold text-slate-900 dark:text-white">
          {{ name }}
        </h2 >

        <p class="mt-1 text-xs text-slate-500 dark:text-slate-400">
          {{ department }}
        </p>
      </div>
    </div>

    <div class="space-y-4 border-t border-slate-200 pt-5 dark:border-white/10">
      <div>
        <p class="mb-1 text-xs text-slate-500 dark:text-slate-400">
          Program
        </p>
        <p class="text-sm font-semibold">
          {{ course }}
        </p>
      </div>

      <div class="grid grid-cols-2 gap-4">
        <div>
          <p class="mb-1 text-xs text-slate-500 dark:text-slate-400">
            Year Level
          </p>
          <p class="text-sm font-medium">
            {{ yearLevel }}
          </p>
        </div>

        <div>
          <p class="mb-1 text-xs text-slate-500 dark:text-slate-400">
            Student No.
          </p>
          <p class="font-mono text-sm font-medium">
            {{ studentId }}
          </p>
        </div>
      </div>

      <div>
        <p class="mb-1 text-xs text-slate-500 dark:text-slate-400">
          Email
        </p>
        <p class="text-sm font-medium break-all">
          {{ email }}
        </p>
      </div>
    </div>
  </article>
</template>