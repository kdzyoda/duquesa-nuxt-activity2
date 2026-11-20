<script setup lang="ts">
useHead({
  title: 'Student Directory'
})

interface Student {
  id: number
  name: string
  course: string
  yearLevel: string
  studentId: string
  initials: string
  department: string
  email: string
}

const students: Student[] = [
  {
    id: 1,
    name: 'Khizha Rhizhane C. Duquesa',
    course: 'BS Information Technology',
    yearLevel: '2nd Year',
    studentId: '241-02067',
    initials: 'KRD',
    department: 'CCIS Department',
    email: 'khizha.duquesa@carsu.edu.ph'
  },
  {
    id: 2,
    name: 'Rubie Jane Badayon',
    course: 'BS Information Technology',
    yearLevel: '3rd Year',
    studentId: '241-02944',
    initials: 'RJB',
    department: 'CCIS Department',
    email: 'rubie.badayon@carsu.edu.ph'
  },
  {
    id: 3,
    name: 'Ace Nathaniel Magbanua',
    course: 'BS Computer Science',
    yearLevel: '1st Year',
    studentId: '261-00945',
    initials: 'ANM',
    department: 'CCIS Department',
    email: 'ace.magbanua@carsu.edu.ph'
  },
  {
    id: 4,
    name: 'Aldis Valdehueza',
    course: 'BS Information Technology',
    yearLevel: '3rd Year',
    studentId: '241-02164',
    initials: 'AV',
    department: 'CCIS Department',
    email: 'aldis.valdehueza@carsu.edu.ph'
  },
  {
    id: 5,
    name: 'Sarah Geronimo',
    course: 'BS Information Sciences',
    yearLevel: '1st Year',
    studentId: '261-02671',
    initials: 'SG',
    department: 'CCIS Department',
    email: 'sarah.geronimo@carsu.edu.ph'
  },
  {
    id: 6,
    name: 'Trisha Mae Degamo',
    course: 'BS Information Sciences',
    yearLevel: '2nd Year',
    studentId: '251-02014',
    initials: 'TMD',
    department: 'CCIS Department',
    email: 'trisha.degamo@carsu.edu.ph'
  }
]

</script>

<template>
  <section
    class="mx-auto max-w-6xl px-6 py-16 lg:px-8"
  >
    <!-- Heading -->
    <div class="mb-12">
      <p
        class="mb-4 font-mono text-sm text-emerald-600 dark:text-emerald-400"
      >
        02 / STUDENT DIRECTORY
      </p>

      <h1
        class="mb-4 text-4xl font-black tracking-tight sm:text-5xl"
      >
        Student
        <span class="text-emerald-600 dark:text-emerald-400">
          Records.
        </span>
      </h1>

      <div
        class="mt-6 inline-flex items-center gap-2 rounded-lg border border-emerald-500/20 bg-emerald-500/10 px-4 py-2 text-sm font-medium text-emerald-700 dark:text-emerald-400"
      >
        <span
          class="h-2 w-2 rounded-full bg-emerald-500"
        ></span>

        {{ students.length }} Student Records
      </div>
    </div>

    <!-- Reusable Student Cards -->
    <div class="grid gap-5 md:grid-cols-2 lg:grid-cols-3">
      <StudentCard
        v-for="student in students"
        :key="student.id"
        :name="student.name"
        :course="student.course"
        :year-level="student.yearLevel"
        :student-id="student.studentId"
        :initials="student.initials"
        :department="student.department"
        :email="student.email"
      />
    </div>

    <!-- Component Explanation -->
    <div class="mt-12">
      <InfoCard
        number="03"
        title="About the Student Directory"
        description="This directory provides an organized overview of student profiles, including academic programs, year levels, and contact information."
      />
    </div>

    <!-- Different Button Props -->
    <div class="mt-8 flex flex-wrap gap-3">
      <AppButton
        label="← Back to Homepage"
        color="emerald"
        to="/"
      />

      <AppButton
        label="Explore StudentHub"
        color="blue"
        to="/#infomation"
      />
    </div>
  </section>
</template>
