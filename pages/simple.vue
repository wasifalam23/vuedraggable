<template>
  <div class="row">
    <div class="col-2">
      <div class="form-group">
        <div
          class="btn-group-vertical buttons"
          role="group"
          aria-label="Basic example"
        >
          <button class="btn btn-secondary" @click="add">Add</button>
          <button class="btn btn-secondary" @click="replace">Replace</button>
        </div>

        <div class="form-check">
          <input
            id="disabled"
            type="checkbox"
            v-model="dragData.enabled"
            class="form-check-input"
          />
          <label class="form-check-label" for="disabled">DnD enabled</label>
        </div>
      </div>
    </div>

    <div class="col-6">
      <h3>Draggable {{ draggingInfo }}</h3>

      <draggable
        :list="dragData.list"
        :disabled="!dragData.enabled"
        item-key="name"
        class="list-group"
        ghost-class="ghost"
        :move="checkMove"
        @start="dragData.dragging = true"
        @end="dragData.dragging = false"
      >
        <template #item="{ element }">
          <div
            class="list-group-item"
            :class="{ 'not-draggable': !dragData.enabled }"
          >
            {{ element.name }}
          </div>
        </template>
      </draggable>
    </div>

    <!-- <rawDisplayer class="col-3" :value="list" title="List" /> -->
  </div>
</template>

<script setup>
import draggable from 'vuedraggable';
let id = 1;

const dragData = ref({
  enabled: true,
  list: [
    { name: 'Apple', id: 0 },
    { name: 'Mango', id: 1 },
    { name: 'Orange', id: 2 },
  ],
  dragging: false,
});

const draggingInfo = computed(() =>
  dragData.value.dragging ? 'under drag' : ''
);

const add = () => {
  dragData.value.list.push({ name: 'Juan ' + id, id: id++ });
};

const replace = () => {
  dragData.value.list = [{ name: 'Edgard', id: id++ }];
};

const checkMove = (e) => {
  window.console.log('Future index: ' + e.draggedContext.futureIndex);
};
</script>

<style scoped>
.buttons {
  margin-top: 35px;
}

.ghost {
  opacity: 0.5;
  background: #c8ebfb;
}

.not-draggable {
  cursor: no-drop;
}
</style>
