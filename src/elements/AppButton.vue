<template>
  <component
    :is="to ? 'router-link' : 'button'"
    :to="to"
    :type="type"
    :class="[
      'font-semibold px-2 rounded-md',
      `bg-${background}`,
      `text-${background==='light'
        ? color==='light'
          ? 'dark shadow-md'
          : `${color} shadow-md`
        : color
      }`,
      background==='light'
        ? `hover:bg-light-d-6`
        : background==='dark'
          ? `hover:bg-dark-l-10`
          : `hover:bg-${background}-d-2`,
      large ? '' : 'w-full md:min-w-32 text-base py-2.5',
      {
        'py-4 text-lg w-full md:min-w-40': large,
        'bg-opacity-30': transparent
      }
    ]"
    v-on="$listeners"
  >
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: 'AppButton',
  props: {
    to: { type: [String, Object], default: null },
    type: { type: String, default: 'button' },
    background: { type: String, default: 'primary' },
    color: { type: String, default: 'light' },
    large: { type: Boolean, default: false },
    transparent: { type: Boolean, default: false }
  },
  computed: {
  }
}
</script>