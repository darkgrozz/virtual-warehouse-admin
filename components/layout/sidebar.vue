<template>
  <div
    style="min-width: 300px; max-width: 300px"
    :class="
      windowWidth < 1140
        ? mobileOpened
          ? 'z-10 fixed top-0 h-full flex justify-start items-start flex-col w-full max-h-screen'
          : 'hidden'
        : 'z-0 sticky top-0 hidden justify-start items-start flex-col lg:flex w-full max-h-screen'
    "
  >
    <div class="flex flex-col max-h-full justify-center items-center w-full">
      <div class="flex w-full justify-center items-center flex-col mb-4 mt-6">
        <img
          class="h-fit"
          style="height: 25px; object-fit: cover"
          src="~/assets/images/xl-logo.svg"
          alt=""
        />
      </div>
      <hr class="bg-gray-100" style="width: 95%" />
      <div class="overflow-auto w-full max-h-full py-1">
        <div class="flex px-3 w-full justify-center items-center flex-col">
          <button
            v-for="item in sidebarData"
            :key="item.title"
            @click="$router.push(`${item.link}`)"
            :style="`${
              item.link === $route.path ? 'background-color: #28ae86' : ''
            }`"
            :class="`${
              item.link === $route.path
                ? 'w-full my-1 rounded-md text-white font-bold flex justify-start p-3 flex-row items-center'
                : 'w-full my-1 rounded-md text-gray-600 font-bold flex justify-start p-3 flex-row items-center'
            }`"
          >
            <b-icon :icon="item.icon"> </b-icon>
            <span class="ml-4">{{ item.title }}</span>
          </button>
        </div>
        <div class="flex px-5 mt-4 w-full justify-start items-center flex-row">
          <span class="text-lg">Admin</span>
        </div>
        <div class="flex px-3 mt-4 w-full justify-center items-center flex-col">
          <button
            v-for="item in sidebarAdminData"
            :key="item.title"
            @click="$router.push(`${item.link}`)"
            :style="`${
              item.link === $route.path ? 'background-color: #28ae86' : ''
            }`"
            :class="`${
              item.link === $route.path
                ? 'w-full my-1 rounded-md text-white font-bold flex justify-start p-3 flex-row items-center'
                : 'w-full my-1 rounded-md text-gray-600 font-bold flex justify-start p-3 flex-row items-center'
            }`"
          >
            <b-icon :icon="item.icon"> </b-icon>
            <span class="ml-4">{{ item.title }}</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";
import { Prop } from "vue-property-decorator";

@Component
export default class LayoutSidebar extends Vue {
  @Prop({ type: [Boolean], default: false })
  mobileOpened!: boolean;

  windowWidth = null as any;

  sidebarData = [
    {
      title: "Dashboard",
      icon: "speedometer",
      link: "/",
    },
    {
      title: "In Bound",
      icon: "package-down",
      link: "/in-bounds",
    },
    {
      title: "Out Bound",
      icon: "package-up",
      link: "/out-bounds",
    },
    {
      title: "Seller",
      icon: "account-supervisor-circle",
      link: "/sellers",
    },
  ];

  sidebarAdminData = [
    {
      title: "User Manajemen",
      icon: "account",
      link: "/user-management",
    },
    {
      title: "Warehouse Setting",
      icon: "warehouse",
      link: "/warehouse",
    },
  ];

  onResize() {
    this.windowWidth = window.innerWidth;
  }

  mounted() {
    this.$nextTick(() => {
      this.windowWidth = window.innerWidth;
      window.addEventListener("resize", this.onResize);
    });
  }
}
</script>
