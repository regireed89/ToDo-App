<template>
  <div>
    <h1 class="title">ToDo App</h1>
    <div class="container-fluid">
      <div class="row">
        <div class="col-sm border border-success bg-dark text-white">ToDo</div>
        <div class="col-sm border border-success bg-dark text-white">
          In Progress
        </div>
        <div class="col-sm border border-success bg-dark text-white">Done</div>
      </div>
      <div class="row">
        <div class="col-sm border border-success bg-dark text-white">
          <div class="d-flex flex-column">
            <td class="p-2 align-middle">
              Task 1
              <div class="d-flex flex-row">
                <div class="input-group">
                  <input
                    type="text"
                    class="form-control"
                    placeholder="Task Name"
                    aria-label="Task Name"
                    aria-describedby="basic-addon2"
                  />
                  <div class="input-group-append">
                    <a class="btn btn-outline-light" type="button"> ToDo </a>
                    <button class="btn btn-outline-light" type="button">
                      In Progress
                    </button>
                    <button class="btn btn-outline-light" type="button">
                      Done
                    </button>
                  </div>
                </div>
              </div>
            </td>
            <div class="p-2">
              Task 2
              <div class="d-flex flex-row">
                <div class="input-group">
                  <input
                    type="text"
                    class="form-control"
                    placeholder="Task Name"
                    aria-label="Task Name"
                    aria-describedby="basic-addon2"
                  />
                  <div class="input-group-append">
                    <button class="btn btn-outline-light" type="button">
                      ToDo
                    </button>
                    <button class="btn btn-outline-light" type="button">
                      In Progress
                    </button>
                    <button class="btn btn-outline-light" type="button">
                      Done
                    </button>
                  </div>
                </div>
              </div>
            </div>

            <div class="p-2">
              Task 3
              <div class="d-flex flex-row">
                <div class="input-group">
                  <input
                    type="text"
                    class="form-control"
                    placeholder="Task Name"
                    aria-label="Task Name"
                    aria-describedby="basic-addon2"
                  />
                  <div class="input-group-append">
                    <button
                      class="btn btn-outline-light"
                      id="ToDo"
                      type="button"
                    >
                      ToDo
                    </button>
                    <button class="btn btn-outline-light" type="button">
                      In Progress
                    </button>
                    <button class="btn btn-outline-light" type="button">
                      Done
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-sm border border-success bg-dark text-white"></div>
        <div class="col-sm border border-success bg-dark text-white"></div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import draggable from 'vuedraggable'

export default Vue.extend({
  components: {
    draggable,
  },
})
</script>

<style></style>
