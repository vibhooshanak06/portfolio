<template>
  <div class="projects">
    <div class="container">
      <section class="projects-hero section">
        <div class="hero-grid">
          <div class="hero-left fade-in-left">
            <h1 class="page-title">My Projects</h1>
            <p class="page-description">
              A curated collection of academic and personal projects that showcase my 
              technical skills and problem-solving abilities.
            </p>
            <p class="page-description">
              Each project represents a unique challenge and learning opportunity, 
              demonstrating my commitment to building innovative solutions.
            </p>
          </div>
          <div class="hero-right fade-in-right">
            <div class="projects-visual">
              <i class="fas fa-rocket"></i>
            </div>
          </div>
        </div>
      </section>

      <section class="projects-grid-section section">
        <div class="projects-grid">
          <div class="project-card fade-in-up" v-for="project in projects" :key="project.id">
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
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'E-Learning Platform',
          description: 'A comprehensive online learning platform with video streaming, quizzes, and progress tracking.',
          technologies: ['Vue.js', 'Express.js', 'MongoDB', 'Socket.io'],
          icon: 'fas fa-graduation-cap'
        },
        {
          id: 2,
          title: 'Task Management App',
          description: 'Cross-platform mobile app for team collaboration and project management.',
          technologies: ['React Native', 'Firebase', 'Redux'],
          icon: 'fas fa-mobile-alt'
        },
        {
          id: 3,
          title: 'Weather Prediction ML',
          description: 'Machine learning model for weather prediction using historical data and neural networks.',
          technologies: ['Python', 'TensorFlow', 'Pandas', 'Scikit-learn'],
          icon: 'fas fa-cloud-sun'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.projects {
  padding-top: 80px;
}

.projects-hero {
  min-height: 90vh;
  display: flex;
  align-items: center;
  padding: 60px 0;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
}

.hero-left {
  animation: fadeInLeft 0.8s ease-out;
}

.page-title {
  font-size: clamp(2.5rem, 5vw, 3.5rem);
  font-weight: 700;
  letter-spacing: -0.03em;
  color: var(--text-primary);
  margin-bottom: 24px;
  line-height: 1.1;
  
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.page-description {
  font-size: 1.0625rem;
  line-height: 1.7;
  color: var(--text-tertiary);
  margin-bottom: 20px;
}

.hero-right {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeInRight 0.8s ease-out;
}

.projects-visual {
  width: 250px;
  height: 250px;
  background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 80px;
  color: white;
  animation: float 3s ease-in-out infinite;
}

.projects-grid-section {
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 32px;
    
    .project-card {
      background: var(--bg-card);
      border-radius: 20px;
      overflow: hidden;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-8px);
        box-shadow: var(--shadow-lg);
      }
      
      .project-image {
        height: 200px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 48px;
        color: white;
      }
      
      .project-content {
        padding: 24px;
        
        .project-title {
          font-size: 1.25rem;
          font-weight: 600;
          color: var(--text-primary);
          margin-bottom: 12px;
        }
        
        .project-description {
          color: var(--text-secondary);
          line-height: 1.6;
          margin-bottom: 16px;
        }
        
        .project-tech {
          display: flex;
          flex-wrap: wrap;
          gap: 8px;
          
          .tech-tag {
            background: var(--light-purple);
            color: var(--dark-purple);
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 0.75rem;
            font-weight: 500;
            
            .dark-theme & {
              background: rgba(139, 92, 246, 0.2);
              color: var(--accent-purple);
            }
          }
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .projects-hero {
    padding-top: 80px;
  }
  
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }
  
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>