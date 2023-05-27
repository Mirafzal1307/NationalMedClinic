<template>
  <section id="services" class="w-full">
    <div class="max-w-7xl mx-auto px-4 md:px-16 py-14">
      <div class="flex flex-col space-y-8">
        <div class="w-full md:w-8/12 space-y-2">
          <div class="text-4xl md:text-5xl font-black">Бизнинг хизматлар</div>
          <div class="text-lg font-semibold text-dark-l-6">Биз сизга ўзимизнинг энг замонавий, қулай ва хамёнбоб хизматларимизни таклиф қиламиз</div>
        </div>
        <div class="flex flex-col sm:flex-row flex-wrap space-y-5 md:space-y-0">
          <div
            v-for="(feature,key) in features"
            :key="key"
            class="flex md:w-1/3 md:p-5"
          >
            <AppCard
              :icon="feature.icon"
              :services="feature.services"
              :color="feature.color"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Services',

  data: () => ({
    features: [
      { icon: '1', color: 'yellow-500', services: [{title:'- Окулист'},{title:'- Хирург'},{title:'- Лабаратория' }]},
      { icon: '2', color: 'pink-600', services: [{title:'- Дерматолог'},{title:'- Ортопед-травмотолог'},{title:'- Эндокринолог'} ,{title:'- Диагностика текширувлари       '}]},
      { icon: '3', color: 'purple-600', services: [{title:'- Терапевт'},{title:'- Кардиолог'},{title:'- Невролог'}]},
      { icon: '4', color: 'blue-600', services: [{title:'- Физиотерапия'},{title:'- Массаж'},{title:'-  Люкс палаталар'},{title:'-  24 соатлик шифокорлар назорати'}] },
      { icon: '5', color: 'green-600', services: [{title:'- МРТ'},{title:'- МСКТ'},{title:'- Рентген'},{title:'- Анализ'}] },
      { icon: '6', color: 'red-600', services: [{title:'- Диетолог назоратида таомлар'},{title:'- Хар бир палатада алохида ювиниш хоналари'},{title:'- Интернет ва бошка хизматлар'}]}
    ]
  })
}
</script>
