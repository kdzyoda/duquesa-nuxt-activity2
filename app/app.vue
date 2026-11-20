<script setup lang="ts">
type Theme = 'light' | 'dark'

const themeCookie = useCookie<Theme>('activity2-theme-cookie', {
  default: () => 'dark',
  sameSite: 'lax',
  path: '/'
})

const theme = useState<Theme>('activity2-theme', () =>
  themeCookie.value === 'light' ? 'light' : 'dark'
)

useHead({
  htmlAttrs: {
    class: computed(() =>
      theme.value === 'dark' ? 'dark' : ''
    )
  },
  titleTemplate: (title) =>
    title
      ? `${title} | StudentHub`
      : 'StudentHub'
})
</script>

<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>
