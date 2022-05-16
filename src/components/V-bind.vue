<script>
export default {
  data() {
    return {
      demoName: "David",
    };
  },
  methods: {
    changeDemoName (event) {
      this.demoName = event.target.value
    }
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
      v-bind:value="demoName"
      @input="changeDemoName($event)"
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
