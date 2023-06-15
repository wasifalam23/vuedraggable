<script setup></script>

<template>
  <button type="button" class="fancy-btn">
    <!-- slot outlet -->

    <slot>click</slot>
  </button>
</template>

<style>
.fancy-btn {
  padding: 0.5rem 1rem;
  border: none;
  font-size: 0.8rem;
  background-color: teal;
  color: #fff;
  font-family: system-ui;
  font-weight: 500;
  cursor: pointer;
}
</style>
