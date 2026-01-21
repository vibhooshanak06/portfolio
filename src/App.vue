<template>
  <div id="app" :class="{ 'dark-theme': isDarkMode }">
    <Navbar @toggle-theme="toggleTheme" :isDarkMode="isDarkMode" />
    <main class="main-content">
      <!-- All sections on one page -->
      <section id="home" class="page-section">
        <Home />
      </section>
      
      <section id="about" class="page-section">
        <About />
      </section>
      
      <section id="experience" class="page-section">
        <Experience />
      </section>
      
      <section id="skills" class="page-section">
        <Skills />
      </section>
      
      <section id="interests" class="page-section">
        <Interests />
      </section>
      
      <section id="projects" class="page-section">
        <Projects />
      </section>
      
      <section id="contact" class="page-section">
        <Contact />
      </section>
    </main>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
import Home from './views/Home.vue'
import About from './views/About.vue'
import Experience from './views/Experience.vue'
import Skills from './views/Skills.vue'
import Interests from './views/Interests.vue'
import Projects from './views/Projects.vue'
import Contact from './views/Contact.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Footer,
    Home,
    About,
    Experience,
    Skills,
    Interests,
    Projects,
    Contact
  },
  data() {
    return {
      isDarkMode: true
    }
  },
  mounted() {
    const savedTheme = localStorage.getItem('theme')
    this.isDarkMode = savedTheme ? savedTheme === 'dark' : true
  },
  methods: {
    toggleTheme() {
      this.isDarkMode = !this.isDarkMode
      localStorage.setItem('theme', this.isDarkMode ? 'dark' : 'light')
    }
  }
}
</script>

<style lang="scss">
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.main-content {
  flex: 1;
  width: 100%;
  overflow-x: hidden;
}

.page-section {
  scroll-margin-top: 80px;
  
  // Reduce gaps between sections
  &:not(#home) {
    padding-top: 40px;
  }
  
  &#home {
    padding-bottom: 40px;
  }
}

// Simple smooth scrolling
html {
  scroll-behavior: smooth;
}

// Reduce section padding globally
:deep(.section) {
  padding: 50px 0;
  
  @media (max-width: 968px) {
    padding: 40px 0;
  }
  
  @media (max-width: 640px) {
    padding: 30px 0;
  }
}
</style>