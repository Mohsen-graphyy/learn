<template>
  <div
    class="relative min-h-screen flex bg-white px-4 md:px-6 lg:px-8 max-xl:max-w-screen-xl"
  >
    <side-bar></side-bar>
    <div class="basis-2/3 p-4 md:p-6 lg:p-8">
      <NuxtPage></NuxtPage>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  mounted() {
    this.getCourses();
  },
  methods: {
    async getCourses() {
      try {
        const response = await this.$api.general.getCourses();
        console.log(response);
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>
