<template>
  <button
    type="button"
    class="
      px-4
      py-3
      bg-blue-600
      rounded-md
      text-white
      outline-none
      focus:ring-4
      shadow-lg
      transform
      active:scale-x-75
      transition-transform
      mx-5
      flex
    "
  >
    <span>
      <slot></slot>
    </span>
  </button>
</template>

<script>
export default {};
</script>

<style></style>
