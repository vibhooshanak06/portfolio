<template>
  <div class="contact">
    <div class="container">
      <div class="contact-layout">

        <!-- Left: info -->
        <div class="contact-left fade-in-left">
          <h1 class="page-title">Get In Touch</h1>
        
          <p class="page-subtitle">
            Open to opportunities & Collaborations. Reach out anytime.
          </p>

          <div class="contact-methods">
            <a href="mailto:vibhooshanak06@gmail.com" class="method-row">
              <div class="method-icon"><i class="fas fa-envelope"></i></div>
              <div class="method-text">
                <span class="method-label">Email</span>
                <span class="method-value">vibhooshanak06@gmail.com</span>
              </div>
            </a>
            <div class="method-row">
              <div class="method-icon"><i class="fas fa-phone"></i></div>
              <div class="method-text">
                <span class="method-label">Phone</span>
                <span class="method-value">+91 86101 83139</span>
              </div>
            </div>
            <div class="method-row">
              <div class="method-icon"><i class="fas fa-map-marker-alt"></i></div>
              <div class="method-text">
                <span class="method-label">Location</span>
                <span class="method-value">Coimbatore, Tamil Nadu</span>
              </div>
            </div>
          </div>

          <div class="social-row">
            <a href="https://github.com/vibhooshanak06" target="_blank" class="social-btn" title="GitHub">
              <i class="fab fa-github"></i>
            </a>
            <a href="https://www.linkedin.com/in/vibhooshana/" target="_blank" class="social-btn" title="LinkedIn">
              <i class="fab fa-linkedin"></i>
            </a>
          </div>
        </div>

        <!-- Right: form -->
        <div class="contact-right fade-in-right">
          <h2 class="form-heading">Send a Message</h2>
          <form class="contact-form" @submit.prevent="submitForm">
            <div class="form-row">
              <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" v-model="form.name" required placeholder="Your name" />
              </div>
              <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" v-model="form.email" required placeholder="your@email.com" />
              </div>
            </div>
            <div class="form-group">
              <label for="subject">Subject</label>
              <input type="text" id="subject" v-model="form.subject" required placeholder="What's this about?" />
            </div>
            <div class="form-group">
              <label for="message">Message</label>
              <textarea id="message" v-model="form.message" required rows="5" placeholder="Tell me about your project or idea..."></textarea>
            </div>
            <button type="submit" class="btn btn-primary submit-btn" :disabled="sending">
              <i :class="sending ? 'fas fa-spinner fa-spin' : 'fas fa-paper-plane'"></i>
              {{ sending ? 'Sending...' : 'Send Message' }}
            </button>
            <p v-if="sent" class="form-feedback success"><i class="fas fa-check-circle"></i> Message sent! I'll get back to you soon.</p>
            <p v-if="error" class="form-feedback error-msg"><i class="fas fa-exclamation-circle"></i> Something went wrong. Try emailing me directly.</p>
          </form>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import emailjs from '@emailjs/browser'

export default {
  name: 'Contact',
  data() {
    return {
      form: { name: '', email: '', subject: '', message: '' },
      sending: false,
      sent: false,
      error: false
    }
  },
  methods: {
    async submitForm() {
      this.sending = true
      this.sent = false
      this.error = false

      try {
        await emailjs.send(
          'service_s4e9u1b',       // replace after setup
          'template_w0miecg',      // replace after setup
          {
            from_name:    this.form.name,
            from_email:   this.form.email,
            subject:      this.form.subject,
            message:      this.form.message,
            reply_to:     this.form.email
          },
          '1ZffK8rwX1rYb_9zs'        // replace after setup
        )
        this.sent = true
        this.form = { name: '', email: '', subject: '', message: '' }
      } catch (err) {
        console.error('EmailJS error:', err)
        this.error = true
      } finally {
        this.sending = false
      }
    }
  }
}
</script>

<style scoped lang="scss">
/* ── Page wrapper ── */
.contact {
  min-height: calc(100vh - 64px);
  display: flex;
  align-items: flex-start;
  padding-top: 70px;
  padding-bottom: 24px;
}

.container {
  width: 100%;
}

/* ── Two-column layout ── */
.contact-layout {
  display: grid;
  grid-template-columns: 1fr 1.25fr;
  gap: 48px;
  align-items: center;
}

/* ── Left panel ── */
.contact-left {
  animation: fadeInLeft 0.7s ease-out;
}

.page-title {
  font-size: clamp(1.8rem, 3vw, 2.4rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  line-height: 1.1;
  margin-bottom: 10px;
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.page-tagline {
  font-size: 0.95rem;
  font-weight: 600;
  font-style: italic;
  color: var(--primary-light);
  margin-bottom: 10px;
  letter-spacing: 0.01em;
  opacity: 0.9;
}

.page-subtitle {
  line-height: 1.6;
  color: var(--text-secondary);
  margin-bottom: 28px;
  max-width: 320px;
}

/* Contact method rows */
.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 24px;
}

.method-row {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 14px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  text-decoration: none;
  transition: border-color 0.2s, transform 0.2s;

  &:hover {
    border-color: rgba(99, 102, 241, 0.3);
    transform: translateX(3px);
  }
}

.method-icon {
  width: 34px;
  height: 34px;
  border-radius: 8px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  color: white;
  flex-shrink: 0;
}

.method-text {
  display: flex;
  flex-direction: column;
  gap: 1px;
}

.method-label {
  font-size: 0.68rem;
  color: var(--text-tertiary);
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.method-value {
  font-size: 0.82rem;
  color: var(--text-primary);
  font-weight: 500;
  overflow-wrap: break-word;
  word-break: break-all;
}

/* Social icons */
.social-row {
  display: flex;
  gap: 10px;
}

.social-btn {
  width: 36px;
  height: 36px;
  border-radius: 9px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  color: var(--text-secondary);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 15px;
  text-decoration: none;
  transition: all 0.2s;

  &:hover {
    background: rgba(99, 102, 241, 0.12);
    border-color: rgba(99, 102, 241, 0.35);
    color: var(--primary-light);
    transform: translateY(-2px);
  }
}

/* ── Right: Form ── */
.contact-right {
  animation: fadeInRight 0.7s ease-out;
}

.form-heading {
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--text-primary);
  margin-bottom: 16px;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 5px;

  label {
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--text-secondary);
    letter-spacing: 0.03em;
    text-transform: uppercase;
  }

  input,
  textarea {
    width: 100%;
    padding: 10px 13px;
    background: var(--bg-card);
    border: 1px solid var(--border-color);
    border-radius: 10px;
    color: var(--text-primary);
    font-size: 0.85rem;
    font-family: inherit;
    transition: border-color 0.2s, box-shadow 0.2s;

    &:focus {
      outline: none;
      border-color: rgba(99, 102, 241, 0.5);
      box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.08);
    }

    &::placeholder {
      color: var(--text-muted);
    }
  }

  textarea {
    resize: none;
    line-height: 1.55;
  }
}

.submit-btn {
  align-self: flex-start;
  padding: 10px 28px;
  font-size: 0.85rem;
  font-weight: 600;
  border-radius: 10px;
  gap: 7px;

  i { font-size: 0.8rem; }

  &:disabled {
    opacity: 0.65;
    cursor: not-allowed;
    transform: none !important;
  }
}

.form-feedback {
  font-size: 0.82rem;
  font-weight: 500;
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 8px 12px;
  border-radius: 8px;
  margin-top: 4px;

  &.success {
    background: rgba(16, 185, 129, 0.1);
    border: 1px solid rgba(16, 185, 129, 0.25);
    color: var(--accent-light);
  }

  &.error-msg {
    background: rgba(239, 68, 68, 0.08);
    border: 1px solid rgba(239, 68, 68, 0.25);
    color: #FCA5A5;
  }
}

/* ── Responsive ── */
@media (max-width: 968px) {
  .contact {
    align-items: flex-start;
    padding: 32px 0 48px;
  }

  .contact-layout {
    grid-template-columns: 1fr;
    gap: 32px;
  }

  .page-subtitle { max-width: 100%; }

  .submit-btn { width: 100%; justify-content: center; }
}

@media (max-width: 480px) {
  .form-row { grid-template-columns: 1fr; }
  .contact { padding-top: 24px; }
}

@keyframes fadeInLeft {
  from { opacity: 0; transform: translateX(-24px); }
  to   { opacity: 1; transform: translateX(0); }
}
@keyframes fadeInRight {
  from { opacity: 0; transform: translateX(24px); }
  to   { opacity: 1; transform: translateX(0); }
}
</style>
