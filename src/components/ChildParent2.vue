<script>
export default {
    props:{
        nameParent: String
    },
    methods: {
        changeName (event) {
            this.$emit('changeTitle', event.target.value)
        }
    }
};
</script>

<template>
  <div class="child-box column">
    <h2>Child</h2>
    <h3>{{nameParent}}  <span style="color: magenta; fontSize: 16px;">" from props "</span></h3>
    <input style="margin-top: 10px" type="text" :placeholder="nameParent" @input="changeName" />
  </div>
</template>

<style>
.child-box {
    border: 2px solid rgb(202, 98, 0);
    margin: 10px;
    padding: 10px;
}

</style>
