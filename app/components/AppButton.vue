<script setup lang="ts">
type ButtonColor = 'emerald' | 'blue' | 'gray'

withDefaults(
  defineProps<{
    label: string
    color?: ButtonColor
    to?: string
  }>(),
  {
    color: 'emerald'
  }
)

const emit = defineEmits<{
  click: []
}>()

const colorClasses: Record<ButtonColor, string> = {
  emerald: 'bg-emerald-500 text-slate-950 hover:bg-emerald-400',
  blue: 'bg-blue-600 text-white hover:bg-blue-500',
  gray: 'bg-slate-700 text-white hover:bg-slate-600'
}
</script>

<template>
  <NuxtLink
    v-if="to"
    :to="to"
    :class="colorClasses[color]"
    class="inline-flex items-center justify-center rounded-xl px-6 py-3 text-sm font-semibold transition-all duration-200"
  >
    {{ label }}
  </NuxtLink>

  <button
    v-else
    type="button"
    :class="colorClasses[color]"
    class="inline-flex items-center justify-center rounded-xl px-6 py-3 text-sm font-semibold transition-all duration-200"
    @click="emit('click')"
  >
    {{ label }}
  </button>
</template>
