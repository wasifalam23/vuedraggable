<template>
  <div class="container">
    <h2>Vue Draggable</h2>
    <ul class="list-holder">
      <li>
        <NuxtLink class="link" to="/simple">Simple</NuxtLink>
      </li>
      <li>
        <NuxtLink class="link" to="/table">Table</NuxtLink>
      </li>
      <li>
        <NuxtLink class="link" to="/slots">Slots</NuxtLink>
      </li>
    </ul>

    <FancyButton @Click="navigateTo({ path: '/exp' })"> Click Me </FancyButton>
  </div>
</template>

<style>
.container {
  margin-top: 5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.container h2 {
  font-size: 1.8rem;
  color: #444;
}

.list-holder {
  padding: 2rem 4rem;
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.link {
  font-size: 1.2rem;
  color: rgb(0, 150, 150);
  text-decoration: none;
}
</style>
