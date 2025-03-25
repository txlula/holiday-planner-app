<script setup lang="ts">
import Button from 'primevue/button'
import Dialog from 'primevue/dialog'
import InputText from 'primevue/inputtext'
import { ref } from 'vue'

const eventList = ref([])

const addDialogVisible = ref(false)
const addEvent = function () {
  addDialogVisible.value = false
}
</script>

<template>
  <div class="box">
    <div class="events">
      <ul>
        <li class="event">Example 1</li>
        <li class="event">Example 2</li>
      </ul>
    </div>
    <div>
      <Button icon="pi pi-plus-circle" @click="addDialogVisible = true" />
      <Dialog
        modal
        v-model:visible="addDialogVisible"
        header="Add Event"
        :style="{
          borderRadius: '5px',
          width: '25rem',
          backgroundColor: '#374743',
          padding: '10px',
        }"
      >
        <div class="add-event-form">
          <label for="event-title">Title</label>
          <InputText class="add-event-text-input" id="event-title" />
        </div>
        <div class="add-event-form">
          <label for="event-description">Description</label>
          <InputText class="add-event-text-input" id="event-description" />
        </div>
        <div class="add-dialog-buttons">
          <Button class="add-button" label="Add" @click="addEvent()" />
          <Button class="cancel-button" label="Cancel" @click="addDialogVisible = false" />
        </div>
      </Dialog>
    </div>
  </div>
</template>

<style scoped>
.box {
  text-align: center;
}

.events {
  margin: 10px;
}

.event {
  border: 1px solid white;
  margin: 10px 0px 10px 0px;
}

.add-event-form {
  display: flex;
  justify-content: center;
  margin: 10px 0px 10px 0px;
}

.add-event-text-input {
  background-color: white;
  color: black;
  margin: 0px 5px 0px 5px;
  border-radius: 2px;
}

.add-dialog-buttons {
  display: flex;
  justify-content: end;
}

.cancel-button {
  border-radius: 5px;
  padding: 10px;
  margin: 0px 5px 0px 5px;
  background-color: #80c2af;
}

.add-button {
  border-radius: 5px;
  padding: 10px;
  margin: 0px 5px 0px 5px;
  background-color: #5c946e;
}
</style>
