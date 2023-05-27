<template>
  <router-link
    to="/"
    class="flex items-center"
  >
    <img
      src="@/assets/images/logo.png"
      alt="logo"
      class="object-contain h-7 mr-3"
    >
    <div
      :class="[
        'text-2xl font-bold tracking-tighter uppercase text-blue-500 text flex-col ',

      ]"
    >
      <span class="" > National

    </span> <span class="text-red-500" >Hospital

    </span>
    </div>



  </router-link>
</template>

<script>
export default {
  name: 'AppLogo',
  props: {
    dark: { type: Boolean, default: false }
  }
}
</script>
<style scoped >
.text{
  letter-spacing: -2px;
}
</style>
