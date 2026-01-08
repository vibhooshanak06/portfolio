<template>
  <div class="contact">
    <div class="container">
      <section class="contact-hero section">
        <div class="hero-content fade-in-up">
          <h1 class="page-title">Get In Touch</h1>
          <p class="page-subtitle">Let's discuss your next project or just say hello!</p>
        </div>
      </section>

      <section class="contact-content section">
        <div class="contact-grid">
          <div class="contact-form-section fade-in-left">
            <h2 class="form-title">Send Me a Message</h2>
            <form class="contact-form" @submit.prevent="submitForm">
              <div class="form-group">
                <label for="name">Full Name</label>
                <input type="text" id="name" v-model="form.name" required placeholder="Your full name">
              </div>
              
              <div class="form-group">
                <label for="email">Email Address</label>
                <input type="email" id="email" v-model="form.email" required placeholder="your.email@example.com">
              </div>
              
              <div class="form-group">
                <label for="subject">Subject</label>
                <input type="text" id="subject" v-model="form.subject" required placeholder="What's this about?">
              </div>
              
              <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" v-model="form.message" required rows="6" placeholder="Tell me about your project!"></textarea>
              </div>
              
              <button type="submit" class="btn btn-primary submit-btn">
                <i class="fas fa-paper-plane"></i>
                Send Message
              </button>
            </form>
          </div>

          <div class="contact-info-section fade-in-right">
            <h2 class="info-title">Let's Connect</h2>
            <p class="info-description">
              I'm always open to discussing new opportunities and creative projects.
            </p>
            
            <div class="contact-methods">
              <div class="contact-method">
                <div class="method-icon">
                  <i class="fas fa-envelope"></i>
                </div>
                <div class="method-info">
                  <h3>Email</h3>
                  <p>hello@johndoe.dev</p>
                </div>
              </div>
              
              <div class="contact-method">
                <div class="method-icon">
                  <i class="fas fa-phone"></i>
                </div>
                <div class="method-info">
                  <h3>Phone</h3>
                  <p>+1 (555) 123-4567</p>
                </div>
              </div>
              
              <div class="contact-method">
                <div class="method-icon">
                  <i class="fas fa-map-marker-alt"></i>
                </div>
                <div class="method-info">
                  <h3>Location</h3>
                  <p>New York, NY</p>
                </div>
              </div>
            </div>

            <div class="social-section">
              <h3 class="social-title">Follow Me</h3>
              <div class="social-links">
                <a href="#" class="social-link">
                  <i class="fab fa-github"></i>
                  <span>GitHub</span>
                </a>
                <a href="#" class="social-link">
                  <i class="fab fa-linkedin"></i>
                  <span>LinkedIn</span>
                </a>
                <a href="#" class="social-link">
                  <i class="fab fa-twitter"></i>
                  <span>Twitter</span>
                </a>
                <a href="#" class="social-link">
                  <i class="fab fa-instagram"></i>
                  <span>Instagram</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      form: {
        name: '',
        email: '',
        subject: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      alert('Thank you for your message! I\'ll get back to you soon.')
      this.resetForm()
    },
    
    resetForm() {
      this.form = {
        name: '',
        email: '',
        subject: '',
        message: ''
      }
    }
  }
}
</script>

<style scoped lang="scss">
.contact {
  padding-top: 80px;
}

.contact-hero {
  text-align: center;
  
  .page-title {
    font-size: 3rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 24px;
  }
  
  .page-subtitle {
    font-size: 1.25rem;
    color: var(--text-secondary);
    line-height: 1.6;
    max-width: 600px;
    margin: 0 auto;
  }
}

.contact-content {
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: flex-start;
  }
}

.contact-form-section {
  .form-title {
    font-size: 2rem;
    font-weight: 600;
    color: var(--text-primary);
    margin-bottom: 32px;
  }
  
  .contact-form {
    .form-group {
      margin-bottom: 24px;
      
      label {
        display: block;
        font-weight: 500;
        color: var(--text-primary);
        margin-bottom: 8px;
      }
      
      input,
      textarea {
        width: 100%;
        padding: 16px;
        border: 2px solid var(--border-color);
        border-radius: 12px;
        background: var(--bg-card);
        color: var(--text-primary);
        font-size: 16px;
        transition: all 0.3s ease;
        
        &:focus {
          outline: none;
          border-color: var(--primary-purple);
          box-shadow: 0 0 0 3px rgba(139, 92, 246, 0.1);
        }
        
        &::placeholder {
          color: var(--text-secondary);
        }
      }
      
      textarea {
        resize: vertical;
        min-height: 120px;
      }
    }
    
    .submit-btn {
      width: 100%;
      padding: 16px;
      font-size: 16px;
      font-weight: 600;
      
      i {
        margin-right: 8px;
      }
    }
  }
}

.contact-info-section {
  .info-title {
    font-size: 2rem;
    font-weight: 600;
    color: var(--text-primary);
    margin-bottom: 16px;
  }
  
  .info-description {
    color: var(--text-secondary);
    line-height: 1.6;
    margin-bottom: 40px;
  }
  
  .contact-methods {
    margin-bottom: 40px;
    
    .contact-method {
      display: flex;
      gap: 20px;
      margin-bottom: 32px;
      padding: 24px;
      background: var(--bg-card);
      border-radius: 16px;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-2px);
        box-shadow: var(--shadow-lg);
      }
      
      .method-icon {
        width: 60px;
        height: 60px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 24px;
        color: white;
        flex-shrink: 0;
      }
      
      .method-info {
        h3 {
          font-size: 1.25rem;
          font-weight: 600;
          color: var(--text-primary);
          margin-bottom: 8px;
        }
        
        p {
          color: var(--text-secondary);
        }
      }
    }
  }
  
  .social-section {
    .social-title {
      font-size: 1.25rem;
      font-weight: 600;
      color: var(--text-primary);
      margin-bottom: 20px;
    }
    
    .social-links {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
      
      .social-link {
        display: flex;
        align-items: center;
        gap: 12px;
        padding: 16px;
        background: var(--bg-card);
        border-radius: 12px;
        text-decoration: none;
        color: var(--text-primary);
        border: 1px solid var(--border-color);
        transition: all 0.3s ease;
        
        &:hover {
          background: var(--primary-purple);
          color: white;
          transform: translateY(-2px);
        }
        
        i {
          font-size: 20px;
        }
        
        span {
          font-weight: 500;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .social-links {
    grid-template-columns: 1fr;
  }
}
</style>