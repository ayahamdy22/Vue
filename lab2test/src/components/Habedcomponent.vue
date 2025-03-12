<template>
  <div>
    <button
      class="btn btn-primary w-100 my-3 text-center"
      @click="isShow = true"
    >
      Add New Student
    </button>

    <!-- -------------- Start Habed ---------------------- -->
    <form v-if="isShow" @submit.prevent="addNewStudent">
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Name</label>
        <input
          v-model="newStd.name"
          type="text"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
        />
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">City</label>
        <input
          v-model="newStd.city"
          type="text"
          class="form-control"
          id="exampleInputPassword1"
        />
      </div>

      <button type="submit" class="btn btn-primary m-2">ADD</button>
      <button
        @click="isShow = false"
        type="button"
        class="btn btn-secondary m-2"
        data-bs-dismiss="modal"
      >
        Cancel
      </button>
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
export default {
  // hebd
  data: () => ({
    students: students,
    isShow: false,
    newStd: { name: "", city: "" },
  }),
  // hebd
  methods: {
    addNewStudent() {
      if (this.newStd.name != "" && this.newStd.city != "") {
        const newId = this.students[this.students.length - 1].id + 1;

        this.students.push({
          id: newId,
          name: this.newStd.name,
          city: this.newStd.city,
        });

        this.newStd.name = "";
        this.newStd.city = "";
        //   this.isShow = false;
      }
    },
  },
};
</script>

<style></style>
