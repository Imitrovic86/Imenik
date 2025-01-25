<script>
import Header from "./components/Header.vue";
import Body from "./components/Body.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    'app-header': Header,
    'app-body': Body,
    'app-footer': Footer
  },
  data() {
    return {
      clickedTab: -1,
      currentRoute: window.location.pathname
    }
  },
  methods: {
    tabChange(tab) {
      this.clickedTab = tab;
    },
    addHandler(content) {
      alert("add" + content);
    },
    deleteHandler(content) {
      alert("delete" + content);
    }
  },

  computed: {
    activeTab() {
      let tab;

      if (this.clickedTab > -1) {
        return this.clickedTab;
      }
      switch (window.location.pathname) {
        case "add-name":
          tab = 1
          break;
        case "add-number":
          tab = 2
          break;
      }
      return tab;
    }
  }
}
</script>

<template>
  <div id="app-container">
    <app-header v-on:tab-change="tabChange" v-bind="activeTab"></app-header>
    <app-body v-bind:tab="activeTab"></app-body>
    <app-footer v-on:add="addHandler" v-on:delete="deleteHandler"></app-footer>
  </div>

  <div id="app-container">
    <app-header v-on:tab-change="tabChange" v-bind="activeTab"></app-header>
    <app-body v-bind:tab="activeTab"></app-body>
    <app-footer v-on:delete="delete"></app-footer>
  </div>
</template>

<style scoped>
#app-container {
  max-width: 490px;
  width: 100%;
  margin: 0 auto;
  height: 95vh;
  background: white;
  border-radius: 10px;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16),
    0 3px 6px rgba(0, 0, 0, 0.23);
  transform: translate(0, 2.5%);
  top: 50%;
  position: relative;
  display: flex;
  flex-direction: column;
}
</style>
