<script>
export default {
    props:{
        nameParent: String,
        changeParentName: Function,
    },
    data () {
      return {
        nameFromChild : this.nameParent,
      }
    },
    methods : {
      modifyName () {
        this.changeParentName(this.nameFromChild )
      }
    }
};
</script>

<template>
  <div class="child-box column">
    <h2>Child</h2>
    <h3>
      {{ nameParent }}
      <span style="color: magenta; fontsize: 16px">" from props "</span>
    </h3>
    <h3>
      {{ nameFromChild }}
      <span style="color: magenta; fontsize: 16px"
        >" from child Component "</span
      >
    </h3>
    <input
      style="margin-top: 10px"
      type="text"
      :placeholder="nameFromChild"
      v-model="nameFromChild"
      @input="modifyName"
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
