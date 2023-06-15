<script setup>
import draggable from 'vuedraggable';

const list = ref([
  { id: 1, name: 'Abby', sport: 'basket' },
  { id: 2, name: 'Brooke', sport: 'foot' },
  { id: 3, name: 'Courtenay', sport: 'volley' },
  { id: 4, name: 'David', sport: 'rugby' },
]);

const dragging = ref(false);
</script>

<template>
  <table class="border-collapse border border-gray-500">
    <thead>
      <tr>
        <th
          class="border-collapse border border-gray-500 text-start"
          scope="col"
        >
          Id
        </th>
        <th
          class="border-collapse border border-gray-500 text-start"
          scope="col"
        >
          Name
        </th>
        <th
          class="border-collapse border border-gray-500 text-start"
          scope="col"
        >
          Sport
        </th>
      </tr>
    </thead>

    <draggable v-model="list" tag="tbody" item-key="table-example">
      <template #item="{ element }">
        <tr>
          <td class="border-collapse border border-gray-500" scope="row">
            {{ element.id }}
          </td>
          <td class="border-collapse border border-gray-500">
            {{ element.name }}
          </td>
          <td class="border-collapse border border-gray-500">
            {{ element.sport }}
          </td>
        </tr>
      </template>
    </draggable>
  </table>
</template>

<style>
.table-container {
  padding: 4rem;
}

.table-container h3 {
  margin-bottom: 1.5rem;
}

td {
  cursor: pointer;
}

thead > tr > th,
tbody > tr > td {
  padding: 0.8rem 2rem;
}
</style>
