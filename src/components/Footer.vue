<template>
  <section class="w-full bg-dark">
    <div class="max-w-7xl mx-auto px-4 md:px-0 py-14">
      <div class="flex justify-between md:flex-row flex-col space-y-5 md:space-y-0">
        <!-- First -->
        <div class="md:w-1/3 md:space-y-2 space-y-0 align-center flex flex-col md:justify-end justify-center">
          <div class="md:mx-0 mx-auto">
            <AppLogo dark />
          </div>
          <div class="text-center md:text-left">
            <div class="text-sm font-semibold text-dark-l-5 hidden md:block">© UMM 2023. Created by <a href="https://www.linkedin.com/in/mirafzal-usmonjonov-752138227/" target="_blank" class="text-light">Yusufxon</a></div>
          </div>
        </div>
        <!-- Second -->
        <div class="md:w-1/3 order-last md:order-none flex justify-center flex-col md:flex-row space-y-5 md:space-y-0">
          <div class="flex-grow md:flex-grow-0">
<!--            <AppButton large>Try it now</AppButton>-->
          </div>
          <div class="text-center md:hidden">
            <div class="text-sm font-semibold text-dark-l-5">© UMM 2023. Created by<a href="https://www.linkedin.com/in/mirafzal-usmonjonov-752138227/" target="_blank" class="text-light"> Yusufxon</a></div>
          </div>
        </div>
        <!-- Third -->
        <div class="md:w-1/2 md:space-y-2 space-y-5 align-center flex flex-col md:justify-end justify-center">
          <div class="flex gap-5 justify-end mx-auto md:mx-0">
            <a
              v-for="(media,key) in medias"
              :key="key"
              :href="media.to"
              target="_blank"
              class="flex items-center"
            >
              <AppIcon
                large
                :name="media.icon"
                :type="media.type"
                color="blue-500"
                class="hover:text-primary-d-2"
              />
            </a>
          </div>
          <ul class="flex gap-5 md:justify-end ml-4 justify-center ">
            <li
              v-for="(route,key) in routes"
              :key="key"
            >
              <AppTextButton small @click="scrollTo(route.to)">{{route.name}}</AppTextButton>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Footer',
  data: () => ({
    medias: [
      { name: 'Facebook', icon: 'facebook-f', type: 'fab', to: '' },
      { name: 'Twitter', icon: 'twitter', type: 'fab', to: '' },
      { name: 'Instagram', icon: 'instagram', type: 'fab', to: '' },
      { name: 'Youtube', icon: 'youtube', type: 'fab', to: '' },
      // { name: 'LinkedIn', icon: 'linkedin', type: 'fab', to: '' }
    ],
    routes: [
      { name: 'Бош саҳифа', to: 'home' },
      { name: 'Ҳизматлар', to: 'services' },
      { name: 'Жамоа', to: 'team' },
    ]
  }),
  methods: {
    scrollTo(id) {
      const element = document.getElementById(id)
      element.scrollIntoView({behavior: "smooth"})
    }
  }
}
</script>
