<template>
<div id="ninjas">
  <p>Passed Props: Ninjasarray</p>
  <ul>
  <li v-bind:key="ninja.name" v-for="ninja in ninjabond"
      v-on:click="ninja.show =!ninja.show">
      <h2 :style="{display:'inline-block'}">{{ninja.name}}</h2> 
      <h3 :style="{display:'inline-block'}" v-show="ninja.show">
        ==> {{ninja.speciality}}</h3>
  </li>
</ul>
<button v-on:click="deleteNinja">Delete Ninja</button>

</div>
</template>

<script>
export default {
  props: {
    ninjabond: {
      type: Array,
      required: true,
    }
  },
  data () {
    return {
      
    }
  },
  methods: {
    deleteNinja: function() {
      this.ninjabond.pop();
    }
  }
}

</script>

<style scoped>
#ninjas {
  width: 100%;
  max-width: 1200px;
  margin: 40px auto;
  padding: 0 20px;
  box-sizing: border-box;
}
ul {
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  padding: 0;
}
li {
  flex-grow: 1;
  flex-basis: 300px;
  text-align: center;
  padding: 30px;
  border: 1px solid #222;
  margin: 10px
}
</style>
