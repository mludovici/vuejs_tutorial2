<template>
<header>
    <h1 v-on:click="changeTitle">{{title}}</h1>
</header>
</template>

<script>
import {bus} from './main';

export default {
  props: {
    title: {
      type: String,
    }
  },
  data () {
    return {
      testtitle: "Hello from Header!"
    }
  },
  methods: {
    changeTitle: function() {
      //this.$emit('changeTitle', "New vue title");
    bus.$emit('titleChanged','New Bus Vue Wizard')
    
    }
    
  }
}

</script>


<style scoped>
header {
    background: lightgreen;
    padding: 10px;
}
h1 {
    color: #222;
    text-align: center;
}
</style>
