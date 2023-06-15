<template>
  <div class="slot-container">
    <h4>Learing the slot concepts in order to understand vue-draggable</h4>
    <BaseLayout>
      <template #header> This is the header </template>
      <template #default>This is the main</template>
      <template #footer>This is the footer</template>
    </BaseLayout>
  </div>
</template>

<style>
.slot-container {
  padding: 2rem 4rem;
}

.slot-container h4 {
  margin-bottom: 1rem;
  font-size: 1.4rem;
}
</style>
