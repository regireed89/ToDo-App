<template>
  <div class="px-4">
    <div class="row">
      <div class="input-group mb-3">
        <input
          id="taskname"
          type="text"
          class="form-control"
          placeholder="Task name"
          aria-label="Recipient's username"
          aria-describedby="basic-addon2"
          inputRef="{ref =>{this.myInput = ref;}}"
        />
        <div class="input-group-append">
          <button class="btn btn-secondary" type="button" @click="addtask">
            Add Task
          </button>
        </div>
      </div>
      <div class="col-4">
        <draggable
          id="first"
          data-source="juju"
          :list="list"
          class="list-group"
          draggable=".item"
          group="a"
        >
          <div
            class="list-group-item item"
            v-for="element in list"
            :key="element.name"
          >
            <p class="text-break">{{ element.name }}</p>
            <button
              type="button"
              class="close"
              aria-label="Close"
              v-on:click="close(1, element.id)"
            >
              <span aria-hidden="true">&times;</span>
            </button>
          </div>

          <div
            slot="header"
            class="btn-group list-group-item bg-success"
            role="group"
            aria-label="Basic example"
          >
            <h3>ToDo</h3>
          </div>
        </draggable>
      </div>

      <div class="col-4">
        <draggable :list="list2" class="list-group" draggable=".item" group="a">
          <div
            class="list-group-item item"
            v-for="element in list2"
            :key="element.name"
          >
            <p class="text-break">{{ element.name }}</p>
            <button
              type="button"
              class="close"
              aria-label="Close"
              v-on:click="close(2, element.id)"
            >
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div
            slot="header"
            class="btn-group list-group-item bg-warning"
            role="group"
            aria-label="Basic example"
          >
            <h3>In Progress</h3>
          </div>
        </draggable>
      </div>

      <div class="col-4">
        <draggable :list="list3" class="list-group" draggable=".item" group="a">
          <div
            class="list-group-item item"
            v-for="element in list3"
            :key="element.name"
          >
            <p class="text-break">{{ element.name }}</p>
            <button
              type="button"
              class="close"
              aria-label="Close"
              v-on:click="close(3, element.id)"
            >
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div
            slot="header"
            class="btn-group list-group-item bg-danger"
            role="group"
            aria-label="Basic example"
          >
            <h3>Done</h3>
          </div>
        </draggable>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { createWrapper } from '@vue/test-utils'
import draggable from 'vuedraggable'
interface todo {
  name: any
  id: number
}
export default {
  name: 'two-list-headerslots',
  components: {
    draggable,
  },
  data() {
    return {
      id: 0,
      list: [] as Array<todo>,
      list2: [] as Array<todo>,
      list3: [] as Array<todo>,
    }
  },
  methods: {
    addtask: function () {
      var input: string = (<HTMLInputElement>(
        document.getElementById('taskname')
      )).value
      this.list.push({ name: input, id: this.id++ })
      console.log('yeet')
    },
    close: function (value: any, id: number) {
      if (value === 1)
        this.list = this.list.filter((x: todo) => x.id != id) as Array<todo>
      else if (value === 2)
        this.list2 = this.list2.filter((x: todo) => x.id != id) as Array<todo>
      else
        this.list3 = this.list3.filter((x: todo) => x.id != id) as Array<todo>
      console.log('hi')
    },
  },
}
</script>

<style></style>
