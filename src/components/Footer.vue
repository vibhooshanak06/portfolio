<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-brand">
          <div class="brand-logo">
            <div class="logo-icon">
              <span>V</span>
            </div>
            <span class="logo-text">Vibhooshana</span>
          </div>
          <p class="brand-description">
            Crafting exceptional digital experiences with modern technologies and creative design.
          </p>
        </div>
        
        <div class="social-links">
          <a href="#" class="social-link" aria-label="GitHub">
            <i class="fab fa-github"></i>
          </a>
          <a href="#" class="social-link" aria-label="LinkedIn">
            <i class="fab fa-linkedin"></i>
          </a>
          <a href="#" class="social-link" aria-label="Twitter">
            <i class="fab fa-twitter"></i>
          </a>
          <a href="#" class="social-link" aria-label="Dribbble">
            <i class="fab fa-dribbble"></i>
          </a>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p class="copyright">&copy; 2024 Vibhooshana. All rights reserved.</p>
        <div class="footer-meta">
          <span>Built with Vue.js</span>
          <span class="separator">•</span>
          <span>Designed with passion</span>
        </div>
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
  padding: 60px 0 32px;
  margin-top: 100px;
}

.footer-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 40px;
  gap: 40px;
}

.footer-brand {
  max-width: 400px;
}

.brand-logo {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 16px;
  
  .logo-icon {
    width: 40px;
    height: 40px;
    background: var(--gradient-primary);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 20px;
    color: white;
    box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
  }
  
  .logo-text {
    font-size: 20px;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.02em;
  }
}

.brand-description {
  font-size: 0.9375rem;
  line-height: 1.6;
  color: var(--text-tertiary);
}

.social-links {
  display: flex;
  gap: 12px;
  
  .social-link {
    width: 44px;
    height: 44px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--bg-tertiary);
    border: 1px solid var(--border-color);
    border-radius: 10px;
    color: var(--text-secondary);
    text-decoration: none;
    font-size: 18px;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    
    &:hover {
      background: var(--primary);
      border-color: var(--primary);
      color: white;
      transform: translateY(-2px);
    }
  }
}

.footer-bottom {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 32px;
  border-top: 1px solid var(--border-color);
}

.copyright {
  font-size: 0.875rem;
  color: var(--text-muted);
}

.footer-meta {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 0.875rem;
  color: var(--text-muted);
  
  .separator {
    color: var(--border-color);
  }
}

@media (max-width: 768px) {
  .footer {
    padding: 50px 0 24px;
    margin-top: 80px;
  }
  
  .footer-content {
    flex-direction: column;
    align-items: flex-start;
    gap: 32px;
  }
  
  .footer-brand {
    max-width: 100%;
  }
  
  .social-links {
    width: 100%;
    justify-content: flex-start;
  }
  
  .footer-bottom {
    flex-direction: column;
    gap: 12px;
    text-align: center;
  }
}
</style>
