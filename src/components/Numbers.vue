<template>
  <section class="w-full relative h-96 flex items-center">
    <!-- Background -->
    <div class="wrapper absolute h-full w-full">
      <img src="@/assets/images/work.jpg" alt="work" class="image h-full w-full object-cover">
    </div>
    <div class="h-48 absolute w-full bg-gray-500 top-0 -z-1"></div>
    <div class="h-48 absolute w-full bg-light bottom-0 -z-1"></div>
    <!-- Numbers content -->
    <div class="max-w-7xl mx-auto px-4 md:px-5 md:h-full absolute left-0 right-0 w-full">
      <div class="grid md:grid-cols-4 grid-cols-2 gap-0 md:gap-5 md:h-full items-center mx-0">
        <div
          v-for="(value,key) in values"
          :key="key"
          class="p-5 flex flex-wrap align-center justify-center mx-auto group cursor-default"
        >
          <div class="my-auto space-y-1">
            <div class="text-4xl text-center font-black text-light group-hover:text-transparent bg-clip-text bg-gradient-to-r from-primary-l-5 to-primary">{{value.text}}</div>
            <div class="text-center font-bold text-light group-hover:text-transparent bg-clip-text bg-gradient-to-r from-primary-l-5 to-primary">{{value.caption}}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Nuumbers',

  data: () => ({
    values: [
      { text: '100K+', caption: 'Йиллик мижозлар' },
      { text: '30+', caption: 'Мутахассислар сони' },
      { text: '100+', caption: 'Буюртмачи ташкилотлар' },
      { text: '10+', caption: 'Замонавий жиҳозлар' }
    ]
  })
}
</script>

<style scoped>
  .wrapper {
    clip-path: polygon(0 15%, 100% 0%, 100% 85%, 0 100%);
  }

  .image {
    filter:sepia(5%) hue-rotate(740deg) saturate(2) brightness(60%);
  }
</style>
