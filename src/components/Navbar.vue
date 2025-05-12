<template>
  <div class="navbar bg-base-300 shadow-sm">
    <div class="navbar-start">
      <a class="btn btn-ghost text-xl">daisyUI</a>
    </div>
    <div class="navbar-center hidden lg:flex">
      <!-- name of each tab group should be unique -->
      <div class="tabs tabs-box">
        <input type="radio" name="my_tabs_1" class="tab" aria-label="Apresentação" checked="checked" />
        <input type="radio" name="my_tabs_1" class="tab" aria-label="Experiências" />
        <input type="radio" name="my_tabs_1" class="tab" aria-label="Contratar" />
      </div>
    </div>
    <div class="navbar-end">
      <a class="btn">Button</a>
    </div>
  </div>
</template>


<script setup>

</script>
