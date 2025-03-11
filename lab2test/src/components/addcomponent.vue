<template>
  <button
    class="btn btn-primary w-100 my-3 text-center"
    @click="onAddNewStudent"
  >
    Add
  </button>
</template>

<script>
export default {
  methods: {
    onAddNewStudent() {
      let test = { name: "DoDo", city: "Turky" };
      // raise event use $emit ("eventname", data)
      this.$emit("addBtn", test);
    },
  },
};
</script>

<style></style>
