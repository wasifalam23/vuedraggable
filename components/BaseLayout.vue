<template>
  <div class="base-layout__container">
    <header class="base-layout__header">
      <slot name="header"></slot>
    </header>
    <main class="base-layout__main">
      <slot></slot>
    </main>
    <footer class="base-layout__footer">
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<style>
.base-layout__header {
  background-color: aqua;
}

.base-layout__main {
  background-color: lightgreen;
}

.base-layout__footer {
  background-color: lightyellow;
}
</style>
