<script setup lang="ts">
useHead({
  title: 'Home',
  meta: [
    {
      name: 'description',
      content: 'A student information website demonstrating reusable Vue components and props.'
    }
  ]
})

const features = [
  {
    id: 1,
    number: '01',
    title: 'Student Information',
    description:
      'View student records organized into reusable cards containing names, programs, year levels, and student references. Browse student profiles and find basic academic information in one place.'
  },
  {
    id: 2,
    number: '02',
    title: 'Reusable Components',
    description:
      'Build consistent user interfaces using shared Vue components instead of repeating the same HTML code.'
  }
]
</script>

<template>
  <div>
    <!-- Hero Section -->
    <section
      class="mx-auto max-w-6xl px-6 pt-10 pb-10 sm:pt-12 sm:pb-12 lg:px-8"
    >
      <div class="max-w-3xl">
        <div
          class="mb-7 inline-flex items-center gap-3 rounded-full border border-emerald-500/30 bg-emerald-500/10 px-4 py-2 text-xs font-semibold tracking-widest text-emerald-700 dark:text-emerald-400"
        >
          <span
            class="h-2 w-2 rounded-full bg-emerald-500"
          ></span>

          ITE 18 / ACTIVITY 02
        </div>

        <p
          class="mb-4 font-mono text-sm font-medium text-emerald-600 dark:text-emerald-400"
        >
          01 / INTRODUCTION
        </p>

        <h1
          class="mb-6 text-4xl font-black leading-tight tracking-tight sm:text-6xl"
        >
          Student Information
          <span
            class="block text-emerald-600 dark:text-emerald-400"
          >
            Made Simple.
          </span>
        </h1>

        <p
          class="mb-5 max-w-2xl text-lg font-medium text-slate-700 dark:text-slate-200"
        >
          Student Directory with Reusable Components.<br><br>This website is built using Nuxt.js and Tailwind CSS, showcasing a clean and responsive design for displaying student information. In compliance with the Activity 2 requirements for ITE 18.
        </p>

        <!-- Reusable Buttons -->
        <div class="mt-9 flex flex-wrap gap-3">
          <AppButton
            label="Explore Students →"
            color="emerald"
            to="/students"
          />

          <AppButton
            label="View Components"
            color="blue"
            to="/#components"
          />
        </div>
      </div>
    </section>

    <!-- Information Cards -->
    <section
      id="components"
      class="scroll-mt-16 border-t border-slate-200 bg-white/50 py-10 dark:border-white/10 dark:bg-white/[0.02]"
    >
      <div class="mx-auto max-w-6xl px-6 lg:px-8">
        <div class="mb-10">
          <p
            class="mb-4 font-mono text-sm text-emerald-600 dark:text-emerald-400"
          >
            02 / COMPONENT DEVELOPMENT
          </p>

          <h2
            class="mb-4 text-3xl font-black tracking-tight sm:text-4xl"
          >
            Built for
            <span
              class="text-emerald-600 dark:text-emerald-400"
            >
              Reusability.
            </span>
          </h2>

        </div>

        <div class="grid gap-5 md:grid-cols-3">
          <InfoCard
            v-for="feature in features"
            :key="feature.id"
            :number="feature.number"
            :title="feature.title"
            :description="feature.description"
          />
        </div>

        <div class="mt-10 flex justify-center">
          <AppButton
            label="Go to Student Directory"
            color="gray"
            to="/students"
          />
        </div>
      </div>
    </section>
  </div>
</template>
