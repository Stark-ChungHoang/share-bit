<template>
    <div>
      <div class="tab">
        <button v-for="(tab, index) in tabs" :key="index" @click="currentTab = tab">
          {{ tab.name }}
        </button>
      </div>
      <div class="tab-content">
        <div v-for="(tab, index) in tabs" :key="index" v-show="currentTab === tab">
          {{ tab.content }}
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        tabs: [
          { name: 'Tab 1', content: 'Tab 1 content' },
          { name: 'Tab 2', content: 'Tab 2 content' },
          { name: 'Tab 3', content: 'Tab 3 content' }
        ],
        currentTab: null
      };
    },
    mounted() {
      this.currentTab = this.tabs[0]; // Set the initial tab
    }
  };
  </script>
  
  <style>
  .tab {
    display: flex;
  }
  
  .tab button {
    border: none;
    background-color: transparent;
    cursor: pointer;
    padding: 10px;
  }
  
  .tab-content div {
    display: none;
    padding: 10px;
  }
  
  .tab-content div.show {
    display: block;
  }
  </style>
  