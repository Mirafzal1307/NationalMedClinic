<template>
  <span
    :class="[
      'hover:text-red-500 cursor-pointer font-semibold',
      small ? 'text-sm' : 'text-lg',
      active ? 'text-red-500' : 'text-blue-500'
    ]"
    v-on="$listeners"
  >
    <slot></slot>
  </span>
</template>

<script>
export default {
  name: 'AppTextButton',
  props: {
    small: { type: Boolean, default: false },
    active: { type: Boolean, default: false }
  }
}
</script>
