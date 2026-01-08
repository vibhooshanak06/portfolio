<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-background">
        <div class="floating-shapes">
          <div class="shape shape-1"></div>
          <div class="shape shape-2"></div>
          <div class="shape shape-3"></div>
        </div>
      </div>
      
      <div class="container">
        <div class="hero-content">
          <div class="hero-text fade-in-left">
            <h1 class="hero-title">
              Hi, I'm <span class="gradient-text">John Doe</span>
            </h1>
            <h2 class="hero-subtitle">Full Stack Developer</h2>
            <p class="hero-description">
              I create beautiful, responsive web applications with modern technologies.
              Passionate about clean code, user experience, and innovative solutions.
            </p>
            <div class="hero-buttons">
              <router-link to="/projects" class="btn btn-primary">
                View My Work
              </router-link>
              <router-link to="/contact" class="btn btn-outline">
                Get In Touch
              </router-link>
            </div>
          </div>
          
          <div class="hero-image fade-in-right">
            <div class="image-container">
              <div class="profile-image">
                <i class="fas fa-user"></i>
              </div>
              <div class="image-decoration"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Quick Stats -->
    <section class="stats section">
      <div class="container">
        <div class="stats-grid">
          <div class="stat-item fade-in-up">
            <div class="stat-number">50+</div>
            <div class="stat-label">Projects Completed</div>
          </div>
          <div class="stat-item fade-in-up">
            <div class="stat-number">3+</div>
            <div class="stat-label">Years Experience</div>
          </div>
          <div class="stat-item fade-in-up">
            <div class="stat-number">100+</div>
            <div class="stat-label">Happy Clients</div>
          </div>
          <div class="stat-item fade-in-up">
            <div class="stat-number">15+</div>
            <div class="stat-label">Technologies</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Featured Projects -->
    <section class="featured-projects section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title fade-in-up">Featured Projects</h2>
          <p class="section-subtitle fade-in-up">Some of my recent work</p>
        </div>
        
        <div class="projects-grid">
          <div class="project-card fade-in-up" v-for="project in featuredProjects" :key="project.id">
            <div class="project-image">
              <i :class="project.icon"></i>
            </div>
            <div class="project-content">
              <h3 class="project-title">{{ project.title }}</h3>
              <p class="project-description">{{ project.description }}</p>
              <div class="project-tech">
                <span v-for="tech in project.technologies" :key="tech" class="tech-tag">
                  {{ tech }}
                </span>
              </div>
            </div>
          </div>
        </div>
        
        <div class="section-footer fade-in-up">
          <router-link to="/projects" class="btn btn-primary">
            View All Projects
          </router-link>
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
      featuredProjects: [
        {
          id: 1,
          title: 'E-Commerce Platform',
          description: 'A full-stack e-commerce solution with modern UI/UX and secure payment integration.',
          technologies: ['Vue.js', 'Node.js', 'MongoDB'],
          icon: 'fas fa-shopping-cart'
        },
        {
          id: 2,
          title: 'Task Management App',
          description: 'Collaborative task management tool with real-time updates and team collaboration features.',
          technologies: ['React', 'Firebase', 'Material-UI'],
          icon: 'fas fa-tasks'
        },
        {
          id: 3,
          title: 'Weather Dashboard',
          description: 'Beautiful weather application with detailed forecasts and interactive maps.',
          technologies: ['JavaScript', 'API Integration', 'CSS3'],
          icon: 'fas fa-cloud-sun'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: 80px;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, var(--light-purple) 0%, var(--bg-primary) 100%);
  
  .dark-theme & {
    background: linear-gradient(135deg, rgba(139, 92, 246, 0.1) 0%, var(--bg-primary) 100%);
  }
}

.floating-shapes {
  position: absolute;
  width: 100%;
  height: 100%;
  
  .shape {
    position: absolute;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
    opacity: 0.1;
    
    &.shape-1 {
      width: 200px;
      height: 200px;
      top: 20%;
      left: 10%;
      animation: float 6s ease-in-out infinite;
    }
    
    &.shape-2 {
      width: 150px;
      height: 150px;
      top: 60%;
      right: 15%;
      animation: float 8s ease-in-out infinite reverse;
    }
    
    &.shape-3 {
      width: 100px;
      height: 100px;
      bottom: 20%;
      left: 60%;
      animation: float 7s ease-in-out infinite;
    }
  }
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
  position: relative;
  z-index: 2;
}

.hero-text {
  .hero-title {
    font-size: 3.5rem;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 16px;
    color: var(--text-primary);
    
    .gradient-text {
      background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
  }
  
  .hero-subtitle {
    font-size: 1.5rem;
    font-weight: 500;
    color: var(--text-secondary);
    margin-bottom: 24px;
  }
  
  .hero-description {
    font-size: 1.1rem;
    line-height: 1.6;
    color: var(--text-secondary);
    margin-bottom: 32px;
  }
  
  .hero-buttons {
    display: flex;
    gap: 16px;
  }
}

.hero-image {
  display: flex;
  justify-content: center;
  
  .image-container {
    position: relative;
    
    .profile-image {
      width: 300px;
      height: 300px;
      background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 120px;
      color: white;
      position: relative;
      z-index: 2;
      animation: pulse 3s infinite;
    }
    
    .image-decoration {
      position: absolute;
      top: -20px;
      left: -20px;
      right: -20px;
      bottom: -20px;
      border: 3px solid var(--accent-purple);
      border-radius: 50%;
      opacity: 0.5;
      animation: pulse 3s infinite reverse;
    }
  }
}

.stats {
  background: var(--bg-secondary);
  
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 40px;
    
    .stat-item {
      text-align: center;
      
      .stat-number {
        font-size: 3rem;
        font-weight: 700;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        margin-bottom: 8px;
      }
      
      .stat-label {
        color: var(--text-secondary);
        font-weight: 500;
      }
    }
  }
}

.featured-projects {
  .section-header {
    text-align: center;
    margin-bottom: 60px;
    
    .section-title {
      font-size: 2.5rem;
      font-weight: 700;
      color: var(--text-primary);
      margin-bottom: 16px;
    }
    
    .section-subtitle {
      font-size: 1.2rem;
      color: var(--text-secondary);
    }
  }
  
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 32px;
    margin-bottom: 60px;
    
    .project-card {
      background: var(--bg-card);
      border-radius: 16px;
      padding: 32px;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-8px);
        box-shadow: var(--shadow-lg);
      }
      
      .project-image {
        width: 80px;
        height: 80px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        border-radius: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 32px;
        color: white;
        margin-bottom: 24px;
      }
      
      .project-title {
        font-size: 1.5rem;
        font-weight: 600;
        color: var(--text-primary);
        margin-bottom: 12px;
      }
      
      .project-description {
        color: var(--text-secondary);
        line-height: 1.6;
        margin-bottom: 20px;
      }
      
      .project-tech {
        display: flex;
        flex-wrap: wrap;
        gap: 8px;
        
        .tech-tag {
          background: var(--light-purple);
          color: var(--dark-purple);
          padding: 4px 12px;
          border-radius: 20px;
          font-size: 0.875rem;
          font-weight: 500;
          
          .dark-theme & {
            background: rgba(139, 92, 246, 0.2);
            color: var(--accent-purple);
          }
        }
      }
    }
  }
  
  .section-footer {
    text-align: center;
  }
}

@media (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }
  
  .hero-text .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-image .image-container .profile-image {
    width: 250px;
    height: 250px;
    font-size: 100px;
  }
  
  .stats .stats-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
}
</style>