<template>
  <div class="flex flex-col border hover:border-transparent px-5 py-12 rounded-xl space-y-2 hover:bg-blue-400 group hover:text-light w-full">
    <div class="flex">
      <div
        :class="[`
          bg-${color}
          flex items-center justify-center flex-shrink rounded-md h-10 w-10 font-bold text-2xl text-white
        `]"
      >
        {{icon}}
      </div>
    </div>
    <div class="text-2xl font-bold">{{  }}</div>
    <div class="text-lg font-semibold text-dark-l-6 group-hover:text-light  " v-for="service in services" :key="service.title">{{ service.title }}</div>
  </div>
</template>

<script>
export default {
  name: 'AppCard',

  props: {
    icon: { type: String, default: '' },
    color: { type: String, default: 'neutral' },
    services: {
      type: Array,
      default() {
        return []
      }
    },

  }
}
</script>
