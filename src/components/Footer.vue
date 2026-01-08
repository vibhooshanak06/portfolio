<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <h3 class="footer-title">Portfolio</h3>
          <p class="footer-text">
            Crafting digital experiences with passion and precision.
          </p>
          <div class="social-links">
            <a href="#" class="social-link">
              <i class="fab fa-github"></i>
            </a>
            <a href="#" class="social-link">
              <i class="fab fa-linkedin"></i>
            </a>
            <a href="#" class="social-link">
              <i class="fab fa-twitter"></i>
            </a>
            <a href="#" class="social-link">
              <i class="fab fa-instagram"></i>
            </a>
          </div>
        </div>
        
        <div class="footer-section">
          <h4 class="section-title">Quick Links</h4>
          <div class="footer-links">
            <router-link to="/">Home</router-link>
            <router-link to="/about">About</router-link>
            <router-link to="/projects">Projects</router-link>
            <router-link to="/contact">Contact</router-link>
          </div>
        </div>
        
        <div class="footer-section">
          <h4 class="section-title">Contact Info</h4>
          <div class="contact-info">
            <p><i class="fas fa-envelope"></i> hello@portfolio.com</p>
            <p><i class="fas fa-phone"></i> +1 (555) 123-4567</p>
            <p><i class="fas fa-map-marker-alt"></i> New York, NY</p>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; 2024 Portfolio. All rights reserved.</p>
        <p>Made with <i class="fas fa-heart"></i> using Vue.js</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped lang="scss">
.footer {
  background: var(--bg-secondary);
  border-top: 1px solid var(--border-color);
  padding: 60px 0 20px;
  margin-top: 80px;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: 40px;
  margin-bottom: 40px;
}

.footer-section {
  .footer-title {
    font-size: 24px;
    font-weight: 700;
    background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 16px;
  }
  
  .section-title {
    font-size: 18px;
    font-weight: 600;
    color: var(--text-primary);
    margin-bottom: 16px;
  }
  
  .footer-text {
    color: var(--text-secondary);
    line-height: 1.6;
    margin-bottom: 24px;
  }
}

.social-links {
  display: flex;
  gap: 16px;
  
  .social-link {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    background: var(--primary-purple);
    color: white;
    border-radius: 50%;
    text-decoration: none;
    transition: all 0.3s ease;
    
    &:hover {
      background: var(--dark-purple);
      transform: translateY(-2px);
    }
  }
}

.footer-links {
  display: flex;
  flex-direction: column;
  gap: 12px;
  
  a {
    color: var(--text-secondary);
    text-decoration: none;
    transition: all 0.3s ease;
    
    &:hover {
      color: var(--primary-purple);
    }
  }
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 12px;
  
  p {
    color: var(--text-secondary);
    display: flex;
    align-items: center;
    gap: 8px;
    
    i {
      color: var(--primary-purple);
      width: 16px;
    }
  }
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 20px;
  border-top: 1px solid var(--border-color);
  
  p {
    color: var(--text-secondary);
    font-size: 14px;
    
    i {
      color: #e74c3c;
      margin: 0 4px;
    }
  }
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 32px;
  }
  
  .footer-bottom {
    flex-direction: column;
    gap: 8px;
    text-align: center;
  }
}
</style>