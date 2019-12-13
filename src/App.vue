<template>
  <div>
    <form-helper>
      <h2 slot="titleslot">{{title}}</h2>
      <p slot="paraslot">I am the paragraph text !</p>
    </form-helper>
    <app-header v-bind:title="title"
    v-on:changeTitle="updateTitle($event)"></app-header>
    <app-ninjas :ninjabond="ninjas"></app-ninjas>
    <app-footer :title="title"></app-footer>
  </div>
</template>

<script>
import Ninjas from './Ninjas.vue';
import Header from './header';
import Footer from './footer';
import formHelper from './formHelper';
export default {
  components: {
    'app-header': Header,
    'app-ninjas' : Ninjas,
    'app-footer': Footer,
    'form-helper': formHelper, 
  },
  data () {
    return {
      ninjas: [
        {name: 'Ryu', speciality: 'Vue Components', show: false},
        {name: 'Crystal', speciality: 'HTML Wizardry', show: false},
        {name: "Hitoshi", speciality: "Click Events", show: false},
        {name: "Becky", speciality: "Fall apart", show: false}
      ],
      title: "I am a dynamic slot title"
    }
  },
  methods: {
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
    }
  }
}

</script>

<style>
h1 {
  color: blue;
}
</style>
