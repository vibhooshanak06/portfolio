<template>
  <nav class="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <div class="nav-content">
        <router-link to="/" class="logo">
          <span class="logo-text">VK</span>
        </router-link>
        
        <div class="nav-links" :class="{ 'active': mobileMenuOpen }">
          <router-link to="/" @click="closeMobileMenu">Home</router-link>
          <router-link to="/about" @click="closeMobileMenu">About</router-link>
          <router-link to="/experience" @click="closeMobileMenu">Experience</router-link>
          <router-link to="/skills" @click="closeMobileMenu">Skills</router-link>
          <router-link to="/interests" @click="closeMobileMenu">Interests</router-link>
          <router-link to="/projects" @click="closeMobileMenu">Projects</router-link>
          <router-link to="/contact" @click="closeMobileMenu">Contact</router-link>
        </div>
        
        <div class="nav-actions">
          <button class="theme-toggle" @click="$emit('toggle-theme')">
            <i :class="isDarkMode ? 'fas fa-sun' : 'fas fa-moon'"></i>
          </button>
          
          <button class="mobile-menu-toggle" @click="toggleMobileMenu">
            <i :class="mobileMenuOpen ? 'fas fa-times' : 'fas fa-bars'"></i>
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    isDarkMode: Boolean
  },
  data() {
    return {
      isScrolled: false,
      mobileMenuOpen: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50
    },
    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen
    },
    closeMobileMenu() {
      this.mobileMenuOpen = false
    }
  }
}
</script>

<style scoped lang="scss">
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--border-color);
  transition: all 0.3s ease;
  
  .dark-theme & {
    background: rgba(15, 23, 42, 0.95);
  }
  
  &.scrolled {
    box-shadow: var(--shadow-lg);
  }
}

.nav-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 0;
}

.logo {
  text-decoration: none;
  
  .logo-text {
    font-size: 24px;
    font-weight: 700;
    background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
}

.nav-links {
  display: flex;
  gap: 32px;
  
  a {
    text-decoration: none;
    color: var(--text-secondary);
    font-weight: 500;
    transition: all 0.3s ease;
    position: relative;
    
    &:hover {
      color: var(--primary-purple);
    }
    
    &.router-link-active {
      color: var(--primary-purple);
      
      &::after {
        content: '';
        position: absolute;
        bottom: -4px;
        left: 0;
        right: 0;
        height: 2px;
        background: var(--primary-purple);
        border-radius: 1px;
      }
    }
  }
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: 16px;
}

.theme-toggle {
  background: none;
  border: none;
  color: var(--text-secondary);
  font-size: 18px;
  cursor: pointer;
  padding: 8px;
  border-radius: 8px;
  transition: all 0.3s ease;
  
  &:hover {
    color: var(--primary-purple);
    background: var(--bg-secondary);
  }
}

.mobile-menu-toggle {
  display: none;
  background: none;
  border: none;
  color: var(--text-secondary);
  font-size: 18px;
  cursor: pointer;
  padding: 8px;
  border-radius: 8px;
  transition: all 0.3s ease;
  
  &:hover {
    color: var(--primary-purple);
    background: var(--bg-secondary);
  }
}

@media (max-width: 768px) {
  .nav-links {
    position: fixed;
    top: 70px;
    left: 0;
    right: 0;
    background: var(--bg-primary);
    flex-direction: column;
    padding: 24px;
    border-bottom: 1px solid var(--border-color);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
    
    &.active {
      transform: translateY(0);
      opacity: 1;
      visibility: visible;
    }
    
    a {
      padding: 12px 0;
      border-bottom: 1px solid var(--border-color);
      
      &:last-child {
        border-bottom: none;
      }
    }
  }
  
  .mobile-menu-toggle {
    display: block;
  }
}
</style>