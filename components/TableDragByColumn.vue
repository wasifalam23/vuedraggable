<script setup>
import draggable from 'vuedraggable';

const headers = ref(['name', 'age', 'city']);
const list = ref([
  {
    name: 'John Doe',
    age: 25,
    city: 'New York',
  },
  {
    name: 'Jane Smith',
    age: 30,
    city: 'London',
  },
  {
    name: 'Michael Johnson',
    age: 40,
    city: 'Tokyo',
  },
  {
    name: 'Sarah Davis',
    age: 35,
    city: 'Sydney',
  },
]);

const dragging = ref(false);
</script>

<template>
  <table class="border-collapse">
    <thead>
      <draggable v-model="headers" tag="tr" :item-key="(key) => key">
        <template #item="{ element: headers }">
          <th
            class="border-collapse border border-gray-500 text-start cursor-pointer"
            scope="col"
          >
            {{ headers }}
          </th>
        </template>
      </draggable>
    </thead>

    <draggable v-model="list" tag="tbody" :item-key="(key) => key.name">
      <template #item="{ element: item }">
        <tr :key="item.name">
          <td
            class="border-collapse border border-gray-500"
            v-for="header in headers"
            :key="header"
          >
            {{ item[header] }}
          </td>
        </tr>
      </template>
    </draggable>
  </table>
</template>
