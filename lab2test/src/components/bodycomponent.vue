<template>
  <div>
    <addcomponent @addBtn="addNewStudent" />

    <!-- -------------- Start Habed ---------------------- -->
    <form>
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Name</label>
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
        />
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">Password</label>
        <input
          type="password"
          class="form-control"
          id="exampleInputPassword1"
        />
      </div>
      <div class="mb-3 form-check">
        <input type="checkbox" class="form-check-input" id="exampleCheck1" />
        <label class="form-check-label" for="exampleCheck1">Check me out</label>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
    <!-- -------------- End Habed ---------------------- -->

    <table class="table table-striped text-center table-bordered">
      <thead>
        <tr>
          <th>Id</th>
          <th>Name</th>
          <th>City</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="students in students" :key="students.id">
          <td>{{ students.id }}</td>
          <td>{{ students.name }}</td>
          <td>{{ students.city }}</td>
        </tr>
      </tbody>

      <tfoot>
        <tr>
          <th colspan="3" class="fs-5 text-primary">
            Total: {{ students.length }}
          </th>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script>
import students from "../students";
import addcomponent from "./addcomponent.vue";
export default {
  // hebd
  data: () => ({
    isShow: false,
  }),
  // hebd
  components: { addcomponent },
  methods: {
    addNewStudent(_data) {
      _data.id = this.students[this.students.length - 1].id + 1;
      this.students.push(_data);
    },
  },
  data: () => ({
    students: students,
  }),
};
</script>

<style></style>
