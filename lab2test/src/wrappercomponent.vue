<template>
  <div class="container my-2 border border-2 border-secondary p-1">
    <!-- header -->
    <div class="row my-1">
      <div class="col-12">
        <!--when send object  we must use binding :  -->
        <headercomponent
          :data="{
            name: 'Yoya',
            branch: 'ITI Menofia',
            track: 'OS',
            gov: 'Menofia',
          }"
        />

        <!-- when send premitive data not require binding (:) -->
        <!-- <headercomponent name="Ahmed" branch="menofia" /> -->
      </div>
    </div>

    <!------------------------ body------------------- -->
    <div class="row m-2">
      <div class="col-3">
        <linkscomponent />
      </div>
      <div class="col-8 offset-1">
        <!-- <bodycomponent /> -->
        <Habedcomponent />
      </div>
    </div>

    <!------------- footer -------------------------->
    <div class="row my-1">
      <div class="col-12">
        <footercomponent />
      </div>
    </div>
  </div>
</template>

<script>
// 1-- import target component
import headercomponent from "./components/headercomponent.vue";
import footercomponent from "./components/footercomponent.vue";
import linkscomponent from "./components/linkscomponent.vue";
import bodycomponent from "./components/bodycomponent.vue";
import Habedcomponent from "./components/Habedcomponent.vue";
export default {
  data: () => ({}),
  methods: {},

  // 2-- register import component
  components: {
    headercomponent,
    linkscomponent,
    bodycomponent,
    footercomponent,
    Habedcomponent,
  },
};
</script>

<style></style>
