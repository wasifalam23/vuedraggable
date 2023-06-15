<script setup>
import draggable from 'vuedraggable';

const data = ref([
  {
    id: 1,
    name: 'Box-1',
    color: 'bg-red-300',
  },
  {
    id: 2,
    name: 'Box-2',
    color: 'bg-green-300',
  },
  {
    id: 3,
    name: 'Box-3',
    color: 'bg-orange-300',
  },
  {
    id: 4,
    name: 'Box-4',
    color: 'bg-teal-300',
  },
  {
    id: 5,
    name: 'Box-5',
    color: 'bg-blue-300',
  },
  {
    id: 6,
    name: 'Box-6',
    color: 'bg-yellow-300',
  },
]);

const dragging = ref(false);
</script>

<template>
  <div class="w-fit mx-auto mt-24">
    <div>
      <h2 class="text-gray-800 font-medium text-2xl">
        Playing with vuedraggable
      </h2>

      <p class="text-sm" v-if="dragging">Dragging happening</p>
    </div>

    <draggable
      :list="data"
      item-key="exp-simple"
      class="mt-10 grid grid-cols-3 gap-4"
      @start="dragging = true"
      @end="dragging = false"
      tag="div"
    >
      <template #item="{ element }">
        <div
          :class="`${element.color} w-24 h-24 cursor-pointer flex items-center justify-center`"
        >
          <span>
            {{ element.name }}
          </span>
        </div>
      </template>
    </draggable>
  </div>
</template>

<style></style>
