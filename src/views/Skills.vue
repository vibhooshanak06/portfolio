<template>
  <div class="skills">
    <div class="container">
      <!-- Hero Section -->
      <section class="skills-hero section">
        <div class="hero-content fade-in-up">
          <h1 class="page-title">Skills & Technologies</h1>
          <p class="page-subtitle">
            The tools and technologies I use to bring ideas to life
          </p>
        </div>
      </section>

      <!-- Technical Skills -->
      <section class="technical-skills section">
        <h2 class="section-title fade-in-up">Technical Skills</h2>
        <div class="skills-categories">
          <div class="skill-category fade-in-up" v-for="category in skillCategories" :key="category.id">
            <div class="category-header">
              <div class="category-icon">
                <i :class="category.icon"></i>
              </div>
              <h3 class="category-title">{{ category.title }}</h3>
            </div>
            <div class="skills-grid">
              <div class="skill-item" v-for="skill in category.skills" :key="skill.name">
                <div class="skill-icon">
                  <i :class="skill.icon"></i>
                </div>
                <div class="skill-info">
                  <span class="skill-name">{{ skill.name }}</span>
                  <div class="skill-level">
                    <div class="level-bar">
                      <div class="level-fill" :style="{ width: skill.level + '%' }"></div>
                    </div>
                    <span class="level-text">{{ skill.level }}%</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Tools & Software -->
      <section class="tools-section section">
        <h2 class="section-title fade-in-up">Tools & Software</h2>
        <div class="tools-grid">
          <div class="tool-card fade-in-up" v-for="tool in tools" :key="tool.id">
            <div class="tool-icon">
              <i :class="tool.icon"></i>
            </div>
            <h3 class="tool-name">{{ tool.name }}</h3>
            <p class="tool-description">{{ tool.description }}</p>
            <div class="proficiency-badge" :class="tool.proficiency.toLowerCase()">
              {{ tool.proficiency }}
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      skillCategories: [
        {
          id: 1,
          title: 'Frontend Development',
          icon: 'fas fa-palette',
          skills: [
            { name: 'Vue.js', icon: 'fab fa-vuejs', level: 95 },
            { name: 'React', icon: 'fab fa-react', level: 85 },
            { name: 'JavaScript', icon: 'fab fa-js-square', level: 90 },
            { name: 'TypeScript', icon: 'fas fa-code', level: 80 },
            { name: 'HTML5', icon: 'fab fa-html5', level: 95 },
            { name: 'CSS3/SCSS', icon: 'fab fa-css3-alt', level: 90 }
          ]
        },
        {
          id: 2,
          title: 'Backend Development',
          icon: 'fas fa-server',
          skills: [
            { name: 'Node.js', icon: 'fab fa-node-js', level: 85 },
            { name: 'Express.js', icon: 'fas fa-code', level: 80 },
            { name: 'Python', icon: 'fab fa-python', level: 75 },
            { name: 'PHP', icon: 'fab fa-php', level: 70 },
            { name: 'REST APIs', icon: 'fas fa-exchange-alt', level: 90 },
            { name: 'GraphQL', icon: 'fas fa-project-diagram', level: 65 }
          ]
        },
        {
          id: 3,
          title: 'Database & Cloud',
          icon: 'fas fa-database',
          skills: [
            { name: 'MongoDB', icon: 'fas fa-leaf', level: 85 },
            { name: 'PostgreSQL', icon: 'fas fa-database', level: 80 },
            { name: 'MySQL', icon: 'fas fa-database', level: 75 },
            { name: 'AWS', icon: 'fab fa-aws', level: 70 },
            { name: 'Docker', icon: 'fab fa-docker', level: 65 },
            { name: 'Firebase', icon: 'fas fa-fire', level: 75 }
          ]
        }
      ],
      tools: [
        {
          id: 1,
          name: 'VS Code',
          icon: 'fas fa-code',
          description: 'Primary code editor with extensive customization',
          proficiency: 'Expert'
        },
        {
          id: 2,
          name: 'Git & GitHub',
          icon: 'fab fa-git-alt',
          description: 'Version control and collaborative development',
          proficiency: 'Expert'
        },
        {
          id: 3,
          name: 'Figma',
          icon: 'fab fa-figma',
          description: 'UI/UX design and prototyping',
          proficiency: 'Advanced'
        },
        {
          id: 4,
          name: 'Postman',
          icon: 'fas fa-paper-plane',
          description: 'API testing and development',
          proficiency: 'Advanced'
        }
      ]
    }
  }
}
</script>
<style scoped lang="scss">
.skills {
  padding-top: 80px;
}

.skills-hero {
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

.technical-skills {
  .section-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--text-primary);
    text-align: center;
    margin-bottom: 60px;
  }
  
  .skills-categories {
    display: grid;
    gap: 40px;
    
    .skill-category {
      background: var(--bg-card);
      border-radius: 20px;
      padding: 40px;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      
      .category-header {
        display: flex;
        align-items: center;
        gap: 16px;
        margin-bottom: 32px;
        
        .category-icon {
          width: 60px;
          height: 60px;
          background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
          border-radius: 16px;
          display: flex;
          align-items: center;
          justify-content: center;
          font-size: 24px;
          color: white;
        }
        
        .category-title {
          font-size: 1.75rem;
          font-weight: 600;
          color: var(--text-primary);
        }
      }
      
      .skills-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 24px;
        
        .skill-item {
          display: flex;
          align-items: center;
          gap: 16px;
          padding: 16px;
          background: var(--bg-secondary);
          border-radius: 12px;
          transition: all 0.3s ease;
          
          &:hover {
            transform: translateX(5px);
          }
          
          .skill-icon {
            width: 40px;
            height: 40px;
            background: var(--primary-purple);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            color: white;
            flex-shrink: 0;
          }
          
          .skill-info {
            flex: 1;
            
            .skill-name {
              font-weight: 600;
              color: var(--text-primary);
              display: block;
              margin-bottom: 8px;
            }
            
            .skill-level {
              display: flex;
              align-items: center;
              gap: 12px;
              
              .level-bar {
                flex: 1;
                height: 6px;
                background: var(--border-color);
                border-radius: 3px;
                overflow: hidden;
                
                .level-fill {
                  height: 100%;
                  background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
                  border-radius: 3px;
                  transition: width 1s ease-in-out;
                }
              }
              
              .level-text {
                font-size: 0.875rem;
                font-weight: 600;
                color: var(--primary-purple);
                min-width: 35px;
              }
            }
          }
        }
      }
    }
  }
}

.tools-section {
  background: var(--bg-secondary);
  border-radius: 20px;
  padding: 60px 40px;
  
  .section-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--text-primary);
    text-align: center;
    margin-bottom: 60px;
  }
  
  .tools-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
    
    .tool-card {
      background: var(--bg-card);
      border-radius: 16px;
      padding: 32px;
      text-align: center;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      position: relative;
      
      &:hover {
        transform: translateY(-5px);
        box-shadow: var(--shadow-lg);
      }
      
      .tool-icon {
        width: 80px;
        height: 80px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 32px;
        color: white;
        margin: 0 auto 24px;
      }
      
      .tool-name {
        font-size: 1.25rem;
        font-weight: 600;
        color: var(--text-primary);
        margin-bottom: 12px;
      }
      
      .tool-description {
        color: var(--text-secondary);
        line-height: 1.6;
        margin-bottom: 20px;
      }
      
      .proficiency-badge {
        display: inline-block;
        padding: 6px 16px;
        border-radius: 20px;
        font-size: 0.875rem;
        font-weight: 600;
        
        &.expert {
          background: linear-gradient(135deg, #10B981, #059669);
          color: white;
        }
        
        &.advanced {
          background: linear-gradient(135deg, #3B82F6, #1D4ED8);
          color: white;
        }
        
        &.intermediate {
          background: linear-gradient(135deg, #F59E0B, #D97706);
          color: white;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .skills-categories .skill-category .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .tools-section {
    padding: 40px 20px;
  }
}
</style>