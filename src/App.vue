<template>
  <div>
    <form-helper :titleheader="headertitle">
      <div slot="form-header" >
        <h3>This is the title of the form</h3>
        <p>Information about the form</p>
      </div>
      <div slot="form-fields">
        <input type="text" placeholder="name" required>
        <input type="password" placeholder="password" required>
      </div>
      <div slot="form-controls">
        <button v-on:click="handleSubmit">Submit</button>
      </div>
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
      title: "I am a dynamic slot title",
      headertitle: "Netter header Titel"
    }
  },
  methods: {
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
    },
    handleSubmit: function(event) {
      event.preventDefault();
      console.log("SUBMITTED!");
    }
  }
}

</script>

<style>
h1 {
  color: blue;
}
</style>
