<template>
  <section id="home" class="relative h-screen w-full">
    <!-- Background -->
    <div class="wrapper absolute h-5/6 w-full">
      <img src="@/assets/images/office.jpg" alt="banner" class="image h-full  w-full object-cover">
    </div>
    <!-- Banner content -->
    <div class="max-w-7xl mx-auto px-4 md:px-5 h-full absolute left-0 right-0 w-full -top-5">
      <div class="flex flex-wrap content-center h-full">
        <!-- Banner copy -->
        <div class="w-full md:w-8/12 mx-auto">
          <div class="flex flex-col space-y-5">
            <div class=""> <span
                class="text-primary-l-3"></span> </div>
            <vue-typed-js class=" text-gray-200 text-5xl md:text-6xl font-black "  :typeSpeed="100" :strings="['Соғлигингиз ишончи қўлларда!']" :loop="true" :backSpeed="50"
  :cursorChar="''" >
              <h1 class="typing text-center "></h1>

            </vue-typed-js>

            <div class="text-lg font-semibold text-center text-gray-200">
              Бугунги кунда клиникамиз юкори малакали тиббиёт ходимлари ва энг янги жихозларга эга хамда замонавий диагностика ва стационар марказнинг барча талабларига жавоб берадиган юкори даражадаги клиника.
            </div>
            <div class="flex flex-col md:flex-row md:mx-auto gap-y-3 md:gap-x-3">
              <!-- <AppButton large background="light" color="primary">Learn more</AppButton>
              <AppButton large transparent background="primary">Try it now</AppButton> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { VueTypedJs } from "vue-typed-js";

export default {
  components: {
    VueTypedJs,
  },
  name: 'Banner'
}
</script>

<style scoped>
.wrapper {
  clip-path: polygon(0 0, 100% 0, 100% 100%, 0 92%);
}

.image {
  filter:sepia(5%) hue-rotate(740deg) saturate(2) brightness(60%);
}

.typed-cursor{
  color: white !important;
  font-size: 20px !important;
  font-weight: 700 !important;
}

</style>
