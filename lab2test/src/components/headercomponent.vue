<template>
  <h4 class="w-100 text-center text-black p-4 bg-secondary-subtle">
    Welcome {{ data.name }}, Branch: {{ data.branch }} - Track:
    {{ data.track }} - Governorate:
    {{ data.gov }}
  </h4>
</template>

<script>
export default {
  data: () => ({}),
  // props: ["name", "branch", "track", "gov"],
  props: ["data"],
};
</script>

<style></style>
