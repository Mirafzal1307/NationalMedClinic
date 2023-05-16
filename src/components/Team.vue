<template>
  <section id="team" class="w-full">
    <div class="max-w-7xl mx-auto px-4 md:px-16 py-14">
      <div class="flex flex-col space-y-8">
        <div class="w-full md:w-8/12 space-y-2 mx-auto">
          <div class="text-4xl md:text-5xl font-black text-center">Meet the team</div>
          <div class="text-lg font-semibold text-dark-l-6 text-center">Morbi sit amet sollicitudin arcu condimentum, nisi vitae aliquam sagittis, lorem lorem.</div>
        </div>
        <div class="w-full md:w-8/12 mx-auto">
          <div class="flex flex-wrap flex-shrink justify-center gap-2 md:gap-5">
            <AppTabButton
              chip
              v-for="(department,key) in departments"
              :key="key"
              :active="activeDept===department.name"
              @click="activeDept = department.name===activeDept ? '' : department.name"
              :icon="department.icon"
            >
              {{department.name}}
            </AppTabButton>
          </div>
        </div>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-5 md:gap-16">
          <div
            v-for="character in characters"
            :key="character.id"
            :class="[character.id===activeId ? 'h-full row-span-2' : 'md:h-60 h-40']"
            @click="activeId = character.id===activeId ? null : character.id"
          >
            <AppImageCard
              :file="character.file"
              :name="character.name"
              :role="character.role"
              :active="character.id===activeId"
              :focus="activeDept===character.department"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Team',

  data: () => ({
    activeDept: '',
    departments: [
      { name: 'Head Doctor', icon: 'font' },
      { name: 'Assistant Doctor', icon: 'font' },
      { name: 'Head', icon: 'font' }
    ],
    activeId: null,
    characters: [
      { id: 1, name: 'Alex Sanders', department: 'Doctor D', role: 'Doctor D', file: 'alex.png' },
      { id: 2, name: 'Ian Dominguez', department: 'Doctor K', role: 'Doctor K', file: 'ian.png' },
      { id: 3, name: 'Eliza Howell', department: 'Doctor H', role: 'Doctor H', file: 'eliza.png' },
      { id: 4, name: 'Alison Cobb', department: 'Doctor N', role: 'Doctor N', file: 'alison.png' },
      { id: 5, name: 'Minnie Brown', department: 'Doctor B', role: 'Doctor B', file: 'minnie.png' },
      { id: 6, name: 'Gabby Hoffman', department: 'Doctor A', role: 'Doctor A', file: 'gabby.png' },
      { id: 7, name: 'Ryan Hernandez', department: 'Doctor C', role: 'Doctor C ', file: 'ryan.png' },
      { id: 8, name: 'Tiffany Chang', department: 'Doctor P', role: 'Doctor P ', file: 'tiffany.png' },

    ]
  })
}
</script>
