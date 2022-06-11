<template>
  <layout-container nav-title="Dashboard" no-back>
    <div class="flex justify-center flex-col items-start p-2">
      <span class="text-lg">@2022 Virtual Warehouse Repository</span>
      <div class="flex justify-center mt-2 items-start flex-row">
        <span>Set-Up By : </span>
        <a target="blank" href="https://gitlab.com/fighantalenta_"
          >@figantalenta</a
        >
      </div>
    </div>
  </layout-container>
  
</template>
<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";

@Component
export default class Index extends Vue {
  mounted() {}
}
</script>
