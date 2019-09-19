<template>
  <div id="app">
    <img src="./assets/logo.svg" class="logo" alt="Aetna logo">
    <div class="container">
      <h1>Lorem ipsum dolor amet</h1>
      <aetna-accordion :items="accordionData" />
      <p>BKINNEY Aetna Test 2019-09-19</p>
    </div>
  </div>
</template>

<script>
import AetnaAccordion from './components/AetnaAccordion';

export default {
  name: 'app',
  components: { AetnaAccordion },
  data() {
    return {
      accordionData: [
        {
          title: 'Title 1',
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          link: 'http://www.google.com',
          expanded: true
        },
        {
          title: 'Title 2',
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          link: 'http://www.aetna.com',
          expanded: false
        },
        {
          title: 'Title 3',
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          link: 'http://www.yahoo.com',
          expanded: false
        }
      ]
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Open+Sans:400,700&display=swap');
@import url('https://fonts.googleapis.com/css?family=Playfair+Display:400,900&display=swap');

html, body {
  margin:0; padding:0; font-size:100%; line-height:1;
}

#app {
  font-family: 'Open Sans', sans-serif;
  color: #414141;
  background-color: #f5f5f5;

  h1 {
    font-family: 'Playfair Display', serif;
    color: #414141;
    font-weight: 900;
    margin: 100px 0 40px 50px;
  }

  .logo {
    width: 250px;
    margin: 50px 0 0 50px;
  }
}

.container {
  padding: 0 25px;
}

// I would rely on bootstrap's grid (or variant), but this is to make a quick "responsive" layout to support mobile

@media only screen and (max-width: 1440px) {
  .container {
    width: 80%;
  }
}

@media only screen and (max-width: 768px) {
  .container {
    width: 70%;
  }
}

@media only screen and (max-width: 640px) {
  .container {
    width: initial;
  }
}

@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.fadeIn {
  -webkit-animation-name: fadeIn;
  animation-name: fadeIn;
  -webkit-animation-duration: 0.75s;
  animation-duration: 0.75s;
}
</style>
