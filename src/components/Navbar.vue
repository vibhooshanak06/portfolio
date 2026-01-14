<template>
  <nav class="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <div class="nav-content">
        <router-link to="/" class="logo">
          <div class="logo-icon">
            <span>VK</span>
          </div>
        </router-link>
        
        <div class="nav-links" :class="{ 'active': mobileMenuOpen }">
          <router-link to="/" @click="closeMobileMenu">Home</router-link>
          <router-link to="/about" @click="closeMobileMenu">About</router-link>
          <router-link to="/experience" @click="closeMobileMenu">Experience</router-link>
          <router-link to="/skills" @click="closeMobileMenu">Skills</router-link>
          <router-link to="/projects" @click="closeMobileMenu">Projects</router-link>
          <router-link to="/contact" @click="closeMobileMenu">Contact</router-link>
        </div>
        
        <div class="nav-actions">
          <button class="theme-toggle" @click="$emit('toggle-theme')" title="Toggle theme">
            <i :class="isDarkMode ? 'fas fa-sun' : 'fas fa-moon'"></i>
          </button>
          
          <button class="mobile-menu-toggle" @click="toggleMobileMenu">
            <span class="hamburger-line"></span>
            <span class="hamburger-line"></span>
            <span class="hamburger-line"></span>
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
  background: rgba(10, 10, 15, 0.8);
  backdrop-filter: blur(20px) saturate(180%);
  border-bottom: 1px solid var(--border-color);
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  
  &.scrolled {
    background: rgba(10, 10, 15, 0.95);
    box-shadow: 0 4px 24px rgba(0, 0, 0, 0.4);
  }
}

.nav-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 0;
}

.logo {
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 12px;
  transition: all 0.3s ease;
  
  &:hover {
    transform: translateX(2px);
  }
  
  .logo-icon {
    width: 36px;
    height: 36px;
    background: var(--gradient-primary);
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 18px;
    color: white;
    box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
  }
  
  .logo-text {
    font-size: 18px;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.02em;
  }
}

.nav-links {
  display: flex;
  gap: 8px;
  
  a {
    text-decoration: none;
    color: var(--text-secondary);
    font-weight: 500;
    font-size: 14px;
    padding: 8px 16px;
    border-radius: 8px;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    
    &:hover {
      color: var(--text-primary);
      background: var(--bg-hover);
    }
    
    &.router-link-active {
      color: var(--text-primary);
      background: var(--bg-tertiary);
      
      &::before {
        content: '';
        position: absolute;
        bottom: 6px;
        left: 50%;
        transform: translateX(-50%);
        width: 4px;
        height: 4px;
        background: var(--primary);
        border-radius: 50%;
      }
    }
  }
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: 12px;
}

.theme-toggle {
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  color: var(--text-secondary);
  font-size: 16px;
  cursor: pointer;
  padding: 10px;
  width: 40px;
  height: 40px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  
  &:hover {
    color: var(--primary-light);
    background: var(--bg-hover);
    border-color: var(--border-hover);
    transform: rotate(15deg);
  }
}

.mobile-menu-toggle {
  display: none;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  cursor: pointer;
  padding: 10px;
  width: 40px;
  height: 40px;
  border-radius: 10px;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 4px;
  transition: all 0.3s ease;
  
  .hamburger-line {
    width: 18px;
    height: 2px;
    background: var(--text-secondary);
    border-radius: 2px;
    transition: all 0.3s ease;
  }
  
  &:hover {
    background: var(--bg-hover);
    border-color: var(--border-hover);
    
    .hamburger-line {
      background: var(--primary-light);
    }
  }
}

@media (max-width: 968px) {
  .nav-links {
    position: fixed;
    top: 76px;
    left: 0;
    right: 0;
    background: rgba(10, 10, 15, 0.98);
    backdrop-filter: blur(20px);
    flex-direction: column;
    padding: 24px;
    border-bottom: 1px solid var(--border-color);
    transform: translateY(-120%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    gap: 4px;
    
    &.active {
      transform: translateY(0);
      opacity: 1;
      visibility: visible;
    }
    
    a {
      padding: 14px 16px;
      width: 100%;
      
      &.router-link-active::before {
        left: 16px;
        transform: none;
      }
    }
  }
  
  .mobile-menu-toggle {
    display: flex;
  }
  
  .logo-text {
    display: none;
  }
}
</style>