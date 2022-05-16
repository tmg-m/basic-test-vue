<script>
import Vmodel from "../components/V-model.vue";
import Vbind from "../components/V-bind.vue";
import ChildParent from "../components/ChildParent.vue";
import ChildParent2 from "../components/ChildParent2.vue";
import ChildParent3 from "../components/ChildParent3.vue";
export default {
  setup() {
    let dbData = [
      { name: "Jon", city: "Barcelona" },
      { name: "Matt", city: "Berlin" },
      { name: "David", city: "Calefornia" },
      { name: "Martin", city: "London" },
      { name: "Phill", city: "Lisben" },
      { name: "Bill", city: "New york" },
    ];
    return { dbData };
  },
  data() {
    return {
      dbNames: this.dbData,
      parentName: "Brad",
      parent3: "Parent BIlly"
    };
  },
  components: {
    Vmodel,
    Vbind,
    ChildParent,
    ChildParent2,
    ChildParent3,
  },
  methods: {
    logChange (inputFromChild) {
      this.parentName = inputFromChild;
    },
    
    changeParentName (inputFromChild) {
      this.parent3 = inputFromChild;
    }
  },
};
</script>

<template>
  <section class="project">
    <h1 style="padding-bottom: 50px; color: white">Project Page</h1>

    <div class="space-div">
      <h2 style="color: lightGreen">For loop with " v-for "</h2>
      <hr />
      <h2 v-for="person in dbNames" :key="person">
        Name: {{ person.name }}, City: {{ person.city }}
      </h2>
    </div>

    <div class="space-div">
      <h2>v-model "1 way"</h2>
      <hr />
      <div>
        <Vmodel />
      </div>
    </div>

    <div class="space-div">
      <h2>v-bind "2 way"</h2>
      <hr />
      <div>
        <Vbind />
      </div>
    </div>

    <div class="space-div">
      <h2>Child to Parent with props "with $emit"</h2>
      <hr />
      <div>
        <h2>
          {{ parentName }}
          <span style="color: green; fontsize: 16px">" from parrent "</span>
        </h2>
        <ChildParent :nameParent="parentName" @changeTitle="logChange" />
      </div>
    </div>

    <div class="space-div">
      <h2>Child to Parent with props "with $emit with Method"</h2>
      <hr />
      <div>
        <h2>
          {{ parentName }}
          <span style="color: green; fontsize: 16px">" from parrent "</span>
        </h2>
        <ChildParent2 :nameParent="parentName" @changeTitle="logChange" />
      </div>
    </div>

    <div class="space-div">
      <h2>Child to Parent with props "with props and method 'v-model and input' "</h2>
      <hr />
      <div>
        <h2>
          {{ parent3 }}
          <span style="color: green; fontsize: 16px">" from parrent "</span>
        </h2>
        <ChildParent3 :nameParent="parent3" :changeParentName="changeParentName" />
      </div>
    </div>
  </section>
</template>

<style>
@media (min-width: 1024px) {
  .project {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .space-div {
    margin: 20px 0 20px;
    border: 2px solid white;
    padding: 20px;
  }
  .column {
    display: flex;
    flex-direction: column;
  }
}
</style>
