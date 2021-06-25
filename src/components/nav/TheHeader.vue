<template>
  <header id="nav">
    <h3>Steam Calc</h3>
    <div v-if="clientWidth > 500">
      <router-link to="/">Home</router-link>
      <router-link to="/about">FAQs</router-link>
      <router-link to="/about">About</router-link>
      <button>Get Started</button>
    </div>
    <button v-else @click.prevent="toggleDropdown" style="border-radius: 0.3em">
      <font-awesome-icon icon="bars" style="font-size: 1.5em" />
    </button>
  </header>
  <transition name="dropdown" mode="out-in">
    <div class="dropdown" v-if="clientWidth <= 500 && showDropdown">
      <router-link to="/">Home</router-link>
      <hr />
      <router-link to="/about">FAQs</router-link>
      <hr />
      <router-link to="/about">About</router-link>
      <hr />
      <button>Get Started</button>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      clientWidth: null,
      showDropdown: false,
    };
  },
  methods: {
    handleResize() {
      this.clientWidth = window.innerWidth;
    },
    toggleDropdown() {
      this.showDropdown = !this.showDropdown;
    },
  },
  created() {
    window.addEventListener('resize', this.handleResize);
    this.handleResize();
  },
  unmounted() {
    window.removeEventListener('resize', this.handleResize);
  },
};
</script>

<style scoped>
/* HEADER */
header {
  padding: 1em 2em;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
h3 {
  margin: 0;
}
header a {
  font-weight: bold;
  color: #2c3e50;
  margin: 0 0.5em;
}
header a.router-link-exact-active {
  color: #42b983;
}
header a:hover,
header a:active {
  color: #7fd1ac;
}
/* BUTTON */
button {
  background-color: #42b983;
  color: #fff;
  padding: 0.5em 1em;
  border: 1px solid green;
  border-radius: 2em;
  margin: 0 1em;
  cursor: pointer;
}
button:hover,
button:active {
  background-color: #7fd1ac;
}
/* DROPDOWN */
.dropdown {
  box-shadow: 0 10px 11px rgba(0, 0, 0, 0.26);
  padding: 0 1rem 1rem;
  border-bottom-left-radius: 2em;
  border-bottom-right-radius: 2em;
}
.dropdown a {
  font-weight: bold;
  color: #2c3e50;
  margin: 0 0.5em;
  align-self: stretch;
}
.dropdown a.router-link-exact-active {
  color: #42b983;
}
.dropdown a:hover,
.dropdown a:active {
  color: #7fd1ac;
}

/* Dropdown Animation */
.dropdown-enter-active {
  animation: slide-scale 0.3s ease-out;
}
.dropdown-leave-active {
  animation: slide-scale 0.3s ease-in reverse;
}

@keyframes slide-scale {
  0% {
    transform: translateY(-5em) scale(0.5);
  }
  100% {
    transform: translateY(0px) scale(1);
  }
}
</style>
