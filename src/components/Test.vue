<template>
  <div class="row">
    <div class="col-8">
      <h3>Draggable table</h3>

      <table class="table table-striped">
        <thead class="thead-dark">
          <tr>
            <th scope="col">Id</th>
            <th scope="col">Name</th>
            <th scope="col">Sport</th>
          </tr>
        </thead>
        <draggable v-model="list" tag="tbody">
          <tr v-for="item in list" :key="item.name">
            <td scope="row">{{ item.id }}</td>
            <td>{{ item.name }}</td> 
            <td>{{ item.sport }}</td>
          </tr>
        </draggable>
        <ul class="list-group" v-sortable>
          <li class="list-group-item">Foo</li>
          <li class="list-group-item">Bar</li>
          <li class="list-group-item">Baz</li>
        </ul>
      </table>
    </div>

    <!-- <rawDisplayer class="col-3" :value="list" title="List" /> -->
  </div>
</template>

<script>
import Vue from 'vue'
import Sortable from 'vue-sortable'
import draggable from "vuedraggable";
Vue.use(Sortable);

export default {
  name: "Test",
  display: "Table",
  order: 8,
  components: {
    draggable
  },
  data() {
    return {
      list: [
        { id: 1, name: "Abby", sport: "basket" },
        { id: 2, name: "Brooke", sport: "foot" },
        { id: 3, name: "Courtenay", sport: "volley" },
        { id: 4, name: "David", sport: "rugby" }
      ],
      dragging: false
    };
  }
};
</script>
<style scoped>
.buttons {
  margin-top: 35px;
}
</style>