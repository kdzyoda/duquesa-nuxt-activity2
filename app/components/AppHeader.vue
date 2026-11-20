<script setup lang="ts">
import { Sun, Moon, GraduationCap } from 'lucide-vue-next'

type Theme = 'light' | 'dark'

const theme = useState<Theme>('activity2-theme', () => 'dark')

const themeCookie = useCookie<Theme>('activity2-theme-cookie', {
  default: () => 'dark',
  sameSite: 'lax',
  path: '/'
})

const isDark = computed(() => theme.value === 'dark')

function toggleTheme() {
  const nextTheme: Theme = isDark.value ? 'light' : 'dark'

  theme.value = nextTheme
  themeCookie.value = nextTheme
}
</script>

<template>
  <header
    class="sticky top-0 z-50 border-b border-slate-200 bg-white/90 backdrop-blur-xl dark:border-white/10 dark:bg-[#0B1120]/90"
  >
    <nav
      class="mx-auto flex max-w-6xl flex-wrap items-center justify-between gap-4 px-5 py-4 sm:px-8"
    >
      <!-- Branding -->
      <NuxtLink
        to="/"
        class="flex items-center gap-3 text-lg font-black tracking-tight"
      >
        <div
          class="flex h-10 w-10 items-center justify-center rounded-xl bg-emerald-500/10 text-emerald-600 dark:text-emerald-400"
        >
          <GraduationCap :size="22" />
        </div>

        <span>
          Student<span class="text-emerald-500">Hub.</span>
        </span>
      </NuxtLink>

      <!-- Navigation -->
      <div class="flex flex-wrap items-center gap-4 sm:gap-7">
        <NuxtLink
          to="/"
          class="text-sm font-medium text-slate-600 transition hover:text-emerald-600 dark:text-slate-300 dark:hover:text-emerald-400"
          active-class="!text-emerald-600 dark:!text-emerald-400"
        >
          Home
        </NuxtLink>

        <NuxtLink
          to="/students"
          class="text-sm font-medium text-slate-600 transition hover:text-emerald-600 dark:text-slate-300 dark:hover:text-emerald-400"
          active-class="!text-emerald-600 dark:!text-emerald-400"
        >
          Students
        </NuxtLink>

        <!-- Theme Toggle -->
        <button
          type="button"
          :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
          :aria-pressed="isDark"
          class="flex h-10 w-10 items-center justify-center rounded-xl border border-slate-200 bg-slate-100 text-slate-700 transition-all hover:border-emerald-500 dark:border-white/10 dark:bg-white/5 dark:text-white dark:hover:bg-white/10"
          @click="toggleTheme"
        >
          <Sun
            v-if="isDark"
            :size="19"
            :stroke-width="1.8"
          />

          <Moon
            v-else
            :size="19"
            :stroke-width="1.8"
          />
        </button>
      </div>
    </nav>
  </header>
</template>
