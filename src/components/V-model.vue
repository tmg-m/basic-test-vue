<script>
export default {
  data() {
    return {
      demoName: "David",
    };
  },
};
</script>

<template>
  <div class="child-box column">
    <h3>{{ demoName }}</h3>
    <input
      style="margin-top: 10px"
      type="text"
      :placeholder="demoName"
      v-model="demoName"
    />
  </div>
</template>

<style>
.child-box {
  border: 2px solid rgb(202, 98, 0);
  margin: 10px;
  padding: 10px;
}
</style>
