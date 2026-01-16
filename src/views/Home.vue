<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-bg-gradient"></div>
      
      <div class="container">
        <div class="hero-content">
          <h1 class="page-title hero-title">
            Hi, I'm <span class="gradient-text">Vibhooshana</span>
          </h1>
          
          <h2 class="hero-subtitle">
            Full Stack Developer
          </h2>
          
          <p class="hero-description">
            I craft exceptional digital experiences that combine beautiful design 
            with powerful functionality. Specializing in modern web technologies 
            and user-centric solutions.
          </p>
          
          <p class="hero-description">
            With a passion for clean code and innovative problem-solving, I transform 
            ideas into scalable applications that make a real impact.
          </p>
          
          <div class="hero-actions">
            <a href="#projects" @click="scrollToSection('projects')" class="btn btn-primary">
              <span>View My Work</span>
              <i class="fas fa-arrow-right"></i>
            </a>
            <a href="#contact" @click="scrollToSection('contact')" class="btn btn-outline">
              <span>Get In Touch</span>
            </a>
          </div>
        </div>
      </div>
      
    </section>

    <!-- Skills Overview -->
    <section class="skills-overview section">
      <div class="container">
        <div class="skills-content">
          <div class="skills-text">
            <div class="section-label">Expertise</div>
            <h2 class="section-title">What I Do Best</h2>
            <p class="section-description">
              I specialize in building modern web applications with cutting-edge 
              technologies, focusing on performance, scalability, and user experience.
            </p>
            <a href="#skills" @click="scrollToSection('skills')" class="btn btn-outline">
              <span>Explore Skills</span>
              <i class="fas fa-arrow-right"></i>
            </a>
          </div>
          
          <div class="skills-grid">
            <div class="skill-card" v-for="skill in topSkills" :key="skill.name">
              <div class="skill-icon">
                <i :class="skill.icon"></i>
              </div>
              <h4 class="skill-name">{{ skill.name }}</h4>
              <p class="skill-description">{{ skill.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      topSkills: [
        {
          name: 'Frontend Development',
          description: 'Building responsive UIs with Vue, React, and modern CSS',
          icon: 'fas fa-code'
        },
        {
          name: 'Backend Development',
          description: 'Creating scalable APIs with Node.js and databases',
          icon: 'fas fa-server'
        },
        {
          name: 'UI/UX Design',
          description: 'Designing intuitive interfaces with Figma',
          icon: 'fas fa-palette'
        },
        {
          name: 'DevOps',
          description: 'Deploying and managing cloud infrastructure',
          icon: 'fas fa-cloud'
        }
      ]
    }
  },
  methods: {
    scrollToSection(sectionId) {
      const element = document.getElementById(sectionId)
      if (element) {
        const offset = 80
        const elementPosition = element.getBoundingClientRect().top
        const offsetPosition = elementPosition + window.pageYOffset - offset
        
        window.scrollTo({
          top: offsetPosition,
          behavior: 'smooth'
        })
      }
    }
  }
}
</script>

<style scoped lang="scss">
// Hero Section
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  padding: 120px 0 80px;
}

.hero-bg-gradient {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100%;
  max-width: 1400px;
  height: 600px;
  background: radial-gradient(circle at 50% 0%, rgba(99, 102, 241, 0.15) 0%, transparent 70%);
  pointer-events: none;
}

.hero-content {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 16px;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  border-radius: 24px;
  font-size: 13px;
  color: var(--text-secondary);
  margin-bottom: 32px;
  animation: fadeInUp 0.6s ease-out;
  
  .badge-dot {
    width: 8px;
    height: 8px;
    background: var(--accent);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }
}

.hero-title {
  font-size: clamp(2.5rem, 6vw, 4.5rem);
  font-weight: 700;
  line-height: 1.1;
  letter-spacing: -0.03em;
  color: var(--text-primary);
  margin-bottom: 24px;
  animation: fadeInUp 0.6s ease-out 0.1s backwards;
  
  .gradient-text {
    background: var(--gradient-primary);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    position: relative;
    display: inline-block;
  }
}

.hero-subtitle {
  font-size: clamp(1.25rem, 3vw, 1.75rem);
  font-weight: 500;
  color: var(--text-secondary);
  margin-bottom: 24px;
  animation: fadeInUp 0.6s ease-out 0.2s backwards;
}

.hero-description {
  font-size: 1.125rem;
  line-height: 1.7;
  color: var(--text-tertiary);
  max-width: 600px;
  margin: 0 auto 40px;
  animation: fadeInUp 0.6s ease-out 0.3s backwards;
}

.hero-actions {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
  animation: fadeInUp 0.6s ease-out 0.4s backwards;
}

.section {
  padding: 100px 0;
}

.section-header {
  text-align: center;
  max-width: 700px;
  margin: 0 auto 80px;
}

.section-label {
  display: inline-block;
  padding: 6px 14px;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  border-radius: 20px;
  font-size: 13px;
  font-weight: 600;
  color: var(--primary-light);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 20px;
}

.section-title {
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  color: var(--text-primary);
  margin-bottom: 16px;
}

.section-description {
  font-size: 1.125rem;
  line-height: 1.7;
  color: var(--text-tertiary);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 32px;
  margin-bottom: 60px;
}

.project-card {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 20px;
  overflow: hidden;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  cursor: pointer;
  
  &:hover {
    transform: translateY(-8px);
    border-color: var(--border-hover);
    box-shadow: var(--shadow-lg);
    
    .project-overlay {
      opacity: 1;
    }
    
    .project-icon {
      transform: scale(1.1);
    }
  }
}

.project-image {
  position: relative;
  height: 240px;
  background: linear-gradient(135deg, var(--bg-tertiary) 0%, var(--bg-secondary) 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  
  .project-icon {
    font-size: 64px;
    color: var(--primary);
    transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: 2;
  }
  
  .project-overlay {
    position: absolute;
    inset: 0;
    background: rgba(99, 102, 241, 0.9);
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: opacity 0.4s ease;
    
    .view-project {
      color: white;
      font-weight: 600;
      font-size: 1.125rem;
    }
  }
}

.project-info {
  padding: 28px;
}

.project-meta {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 16px;
  
  .project-category {
    font-size: 0.875rem;
    font-weight: 600;
    color: var(--primary-light);
  }
  
  .project-year {
    font-size: 0.875rem;
    color: var(--text-muted);
  }
}

.project-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 12px;
  letter-spacing: -0.01em;
}

.project-description {
  font-size: 0.9375rem;
  line-height: 1.6;
  color: var(--text-tertiary);
  margin-bottom: 20px;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  
  .tech-badge {
    padding: 6px 12px;
    background: var(--bg-tertiary);
    border: 1px solid var(--border-color);
    border-radius: 8px;
    font-size: 0.8125rem;
    font-weight: 500;
    color: var(--text-secondary);
  }
}

// Skills Overview Section
.skills-overview {
  background: var(--bg-primary);
}

.skills-content {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 80px;
  align-items: start;
}

.skills-text {
  position: sticky;
  top: 120px;
  
  .section-title {
    text-align: left;
    margin-bottom: 20px;
  }
  
  .section-description {
    text-align: left;
    margin-bottom: 32px;
  }
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

.skill-card {
  padding: 28px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 16px;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  
  &:hover {
    transform: translateY(-4px);
    border-color: var(--border-hover);
    box-shadow: var(--shadow);
    
    .skill-icon {
      transform: scale(1.1);
      color: var(--primary-light);
    }
  }
}

.skill-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--bg-tertiary);
  border-radius: 12px;
  font-size: 24px;
  color: var(--primary);
  margin-bottom: 20px;
  transition: all 0.3s ease;
}

.skill-name {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 8px;
}

.skill-description {
  font-size: 0.9375rem;
  line-height: 1.6;
  color: var(--text-tertiary);
}

// Animations
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

// Responsive
@media (max-width: 968px) {
  .hero {
    padding: 100px 0 60px;
  }
  
  .section {
    padding: 80px 0;
  }
  
  .skills-content {
    grid-template-columns: 1fr;
    gap: 60px;
  }
  
  .skills-text {
    position: static;
  }
  
  .skills-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 640px) {
  .hero-actions {
    flex-direction: column;
    width: 100%;
    
    .btn {
      width: 100%;
    }
  }
}
</style>