<template>
  <section id="team" class="w-full">
    <div class="max-w-7xl mx-auto px-4 md:px-16 py-14">
      <div class="flex flex-col space-y-8">
        <div class="w-full md:w-8/12 space-y-2 mx-auto">
          <div class="text-4xl md:text-5xl font-black text-center">Жамоамиз билан танишинг</div>
          <div class="text-lg font-semibold text-dark-l-6 text-center">Бизнинг аҳил жамоамиз сизнинг саломатлигингизни барча нарсадан устун қўйишади.</div>
        </div>
        <div class="w-full md:w-8/12 mx-auto">
          <div class="flex flex-wrap flex-shrink justify-center gap-2 md:gap-5">
            <AppTabButton
              chip
              v-for="(department,key) in departments"
              :key="key"
              :active="activeDept===department.name"
              @click="activeDept = department.name===activeDept ? '' : department.name"

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
              :experience="character.experience"
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
      { name: 'Врач дерматолог' },
      { name: 'Врач офтальмолог' },
      { name: 'Врач терапевт, УЗИ'},
      { name: 'Акушер-гинеколог, УЗИ'},

    ],
    activeId: null,
    characters: [
      { id: 1, name: 'Шоматов Сирожиддин Холмуродович', department: 'Врач дерматолог', role: 'Врач дерматолог', experience: '30 йиллик стаж',  file: 'cholDoc.png' },
      { id: 2, name: 'Яқубджанов Алишер Сабиржанович', department: 'Врач офтальмолог', role: 'Врач офтальмолог', experience: '30 йиллик стаж',  file: 'kokDoc.png' },
      { id: 3, name: 'Каракулов Мутали Сапаралиевич', department: 'Врач терапевт, УЗИ', role: 'Врач терапевт, УЗИ', experience: '20 йиллик стаж',  file: 'oqDoc.png' },
      { id: 4, name: 'Эрматова Адолат Абдужалиловна', department: 'Акушер-гинеколог, УЗИ', role: 'Акушер-гинеколог, УЗИ', experience: '10 йиллик стаж',  file: 'ayol.png' },
    ]
  })
}
</script>
