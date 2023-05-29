<template>
  <div
    :class="[
      'relative rounded-lg h-full w-full group cursor-pointer inline-block overflow-hidden',
      focus ? 'bg-red-500' : 'bg-blue-500'
    ]"
  >
    <img
      :src="require(`@/assets/images/${file}`)"
      alt=""
      :class="[
        'object-contain w-full h-full block mt-5 filter transform transition duration-500',
        active ? 'scale-150 grayscale-0' : 'scale-125 grayscale group-hover:grayscale-0 group-hover:scale-135'
      ]"
    >
    <div v-if="active" class="absolute bottom-0 w-full px-2 py-5">
      <div class="text-center">
        <div class="text-base md:text-xl text-light font-bold text-style">{{name}}</div>
        <div class="text-sm md:text-lg text-light font-semibold text-style">{{experience}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppImageCard',

  props: {
    file: { type: String, default: '' },
    name: { type: String, default: '' },
    role: { type: String, default: '' },
    active: { type: Boolean, default: false },
    focus: { type: Boolean, default: false },
    experience: { type: String, default:''}
  }
}
</script>
<style scoped>
.text-style{
  text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
}
</style>
