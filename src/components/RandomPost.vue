<template>
    <div class="pop-up" v-if="isOpen" v-on:click="closePopup()">
      <div class="popup-content">
        <h2>{{ randomContent }}</h2>
        <button v-on:click.stop="generateNewContent()">Move Next </button>
        <button v-on:click.stop="closePopup()">Close Pop-up</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isOpen: false,
        randomContent: ''
      };
    },
    methods: {
      openPopup() {
        this.isOpen = true;
        this.generateNewContent();
      },
      closePopup() {
        this.isOpen = false;
      },
      generateNewContent() {
        const contents = [
          'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
          'Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
          'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
          'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
        ];
        const randomIndex = Math.floor(Math.random() * contents.length);
        this.randomContent = contents[randomIndex];
      }
    }
  };
  </script>
  
  <style scoped>
  .pop-up {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    padding: 20px;
    border: 1px solid black;
  }
  
  .popup-content {
    text-align: center;
  }
  
  button {
    margin-top: 10px;
  }
  </style>
  
  