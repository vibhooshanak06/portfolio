<template>
  <div id="app" :class="{ 'dark-theme': isDarkMode }">
    <Navbar @toggle-theme="toggleTheme" :isDarkMode="isDarkMode" />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Footer
  },
  data() {
    return {
      isDarkMode: false
    }
  },
  mounted() {
    const savedTheme = localStorage.getItem('theme')
    this.isDarkMode = savedTheme === 'dark'
  },
  methods: {
    toggleTheme() {
      this.isDarkMode = !this.isDarkMode
      localStorage.setItem('theme', this.isDarkMode ? 'dark' : 'light')
    }
  }
}
</script>