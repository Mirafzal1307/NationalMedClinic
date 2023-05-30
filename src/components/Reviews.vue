<template>
  <section id="reviews" class="w-full bg-gray-500">
    <div class="max-w-7xl mx-auto px-4 md:px-16 py-14">
      <div class="flex flex-col space-y-8 items-center">
        <div class="w-full">
          <div class="md:w-8/12 space-y-2">
            <div class="text-4xl text-light md:text-5xl font-black">Бизнинг мижозларимиз</div>
            <div class="text-lg font-semibold text-primary-l-2">Ҳар бир мижознинг фикри биз учун жуда муҳим</div>
          </div>
        </div>
        <!-- Carousel -->
        <div class="max-w-10xl flex py-12 w-screen">
          <!-- Previous card -->
          <div class="hidden flex-grow md:flex w-1/3 items-center relative">
            <div class="absolute -left-5 mr-10">
              <AppMessageCard
                v-if="carousel[0]"
                :name="carousel[0].name"
                :designation="carousel[0].designation"
                :company="carousel[0].company"
                :message="carousel[0].message"
                :avatar="carousel[0].avatar"
              />
            </div>
          </div>
          <!-- Active card -->
          <div class="w-full lg:w-1/3 px-4 md:px-0 relative">
            <AppMessageCard
              v-if="carousel[1]"
              active
              :name="carousel[1].name"
              :designation="carousel[1].designation"
              :company="carousel[1].company"
              :message="carousel[1].message"
              :avatar="carousel[1].avatar"
            />
            <!-- Navigation -->
            <div class="absolute h-full items-center flex top-0 left-0 md:-left-24 z-20">
              <button
                class="rounded-full h-14 md:h-16 w-14 md:w-16 bg-light md:bg-dark bg-opacity-50 hover:bg-dark-l-10"
                @click="prevCard"
              >
                <AppIcon x-large name="chevron-left" />
              </button>
            </div>
            <div class="absolute h-full items-center flex top-0 right-0 md:-right-24 z-20">
              <button
                class="rounded-full h-14 md:h-16 w-14 md:w-16 bg-light md:bg-dark bg-opacity-50 hover:bg-dark-l-10"
                @click="nextCard"
              >
                <AppIcon x-large name="chevron-right"  />
              </button>
            </div>
            <!-- Pagination -->
            <div class="absolute -bottom-8 flex flex-wrap gap-3 justify-center mx-auto w-full">
              <button
                v-for="review in reviews"
                :key="review.id"
                :class="[
                  'h-3 w-3 rounded-full',
                  activeId===review.id ? 'bg-dark' : 'bg-primary-l-3'
                ]"
                @click="activeId=review.id"
              ></button>
            </div>
          </div>
          <!-- Next card -->
          <div class="hidden flex-grow md:flex w-1/3 items-center relative">
            <div class="absolute -right-5 ml-10">
              <AppMessageCard
                v-if="carousel[2]"
                :name="carousel[2].name"
                :designation="carousel[2].designation"
                :company="carousel[2].company"
                :message="carousel[2].message"
                :avatar="carousel[2].avatar"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Reviews',

  data: () => ({
    activeId: null,
    carousel: [],
    reviews: [
      {id: 1, name: 'Тошпўлатов A.A.',  message: 'Ажойиб тиббиёт маркази! Касбий ходимлар, мазмунли атмосфера ва  юқори даражадаги тиббий ёрдам. Хаммага тавсия қиламан!', avatar: '4www.webp'},
      {id: 2, name: 'Исмаилова G.M.',  message: ' Ушбу клиника хизматидан жуда мамнунман. Докторлар эътибор ва тезкорлик билан хизмат килдилар, даволаш жараёнининг барча муолажалани тушунтирдилар. Бу ерда ҳақиқий профессионал докторлар ишлайди!', avatar: '3www.jpeg'},
      {id: 3, name: 'Зебо Назарова',  message: 'Жудаям тоза жой, тартиб, хушмуомала персонал билан жамланган тиббиёт маркази. Яхши жиҳозлар, тезкор ва сифатли ёрдам. Проффесионаллик учун рахмат!', avatar: '5www.jpg'},
      {id: 4, name: 'Муҳаммад Али',  message: 'Ушбу клиникани ташриф буюрдим ва ҳурсанд бўлдим. Тартиб, хушмуомала персонал. Муаммога бўлган профессионаллик, тажрибали докторлар назорати ва ғамхўрлик учун рахмат. Барчага тавсия қиламан.', avatar: '2www.webp'},
      {id: 5, name: 'Михаэл A.I.',  message: 'Это лучший медицинский центр, в котором мне доводилось бывать. Полный спектр услуг, высококвалифицированный медперсонал и индивидуальный подход к каждому пациенту. Я рекомендую!', avatar: '1www.jpg'}
    ]
  }),
  watch: {
    activeId(id) {
      let activeKey = this.reviews.findIndex(review => review.id === id);
      if (activeKey === 0) {
        this.carousel = [
          this.reviews[this.reviews.length-1],
          this.reviews[0],
          this.reviews[1]
        ]
      }
      else if (activeKey === this.reviews.length-1) {
        this.carousel = [
          this.reviews[(this.reviews.length-1)-1],
          this.reviews[this.reviews.length-1],
          this.reviews[0]
        ]
      }
      else {
        this.carousel = [
          this.reviews[activeKey-1],
          this.reviews[activeKey],
          this.reviews[activeKey+1]
        ]
      }
    }
  },
  methods: {
    prevCard() {
      let activeKey = this.reviews.findIndex(review => review.id === this.activeId);
      if (activeKey === 0)
        this.activeId = this.reviews[this.reviews.length-1].id
      else if (activeKey === this.reviews.length-1)
        this.activeId = this.reviews[(this.reviews.length-1)-1].id
      else
        this.activeId = this.reviews[activeKey-1].id
    },
    nextCard() {
      let activeKey = this.reviews.findIndex(review => review.id === this.activeId);
      if (activeKey === 0)
        this.activeId = this.reviews[1].id
      else if (activeKey === this.reviews.length-1)
        this.activeId = this.reviews[0].id
      else
        this.activeId = this.reviews[activeKey+1].id
    }
  },
  mounted() {
    this.activeId = this.reviews[0].id
  }
}
</script>
