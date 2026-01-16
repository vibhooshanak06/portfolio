<template>
  <div class="experience">
    <div class="container">
      <!-- Hero Section -->
      <section class="experience-hero section">
        <div class="hero-grid">
          <div class="hero-left fade-in-left">
            <h1 class="page-title">Professional Experience</h1>
            <p class="page-description">
              My professional journey spans across diverse projects and technologies, 
              from startups to established companies.
            </p>
            <p class="page-description">
              Each role has shaped my expertise in full-stack development, team collaboration, 
              and delivering high-quality solutions that exceed expectations.
            </p>
          </div>
          <div class="hero-right fade-in-right">
            <div class="experience-visual">
              <i class="fas fa-briefcase"></i>
            </div>
          </div>
        </div>
      </section>

      <!-- Work Experience -->
      <section class="work-experience section">
        <h2 class="section-title fade-in-up">Work Experience</h2>
        <div class="experience-timeline">
          <div class="experience-item fade-in-left" v-for="job in workExperience" :key="job.id">
            <div class="experience-marker">
              <div class="experience-dot"></div>
            </div>
            <div class="experience-card">
              <div class="experience-header">
                <div class="company-info">
                  <h3 class="job-title">{{ job.title }}</h3>
                  <h4 class="company-name">{{ job.company }}</h4>
                  <div class="job-period">{{ job.period }}</div>
                </div>
                <div class="company-logo">
                  <i :class="job.icon"></i>
                </div>
              </div>
              <div class="job-description">
                <ul>
                  <li v-for="responsibility in job.responsibilities" :key="responsibility">
                    {{ responsibility }}
                  </li>
                </ul>
              </div>
              <div class="job-technologies">
                <span v-for="tech in job.technologies" :key="tech" class="tech-tag">
                  {{ tech }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Education -->
      <section class="education section">
        <h2 class="section-title fade-in-up">Education</h2>
        <div class="education-grid">
          <div class="education-card fade-in-up" v-for="edu in education" :key="edu.id">
            <div class="education-icon">
              <i :class="edu.icon"></i>
            </div>
            <div class="education-content">
              <h3 class="degree-title">{{ edu.degree }}</h3>
              <h4 class="institution-name">{{ edu.institution }}</h4>
              <div class="education-period">{{ edu.period }}</div>
              <p class="education-description">{{ edu.description }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- Certifications -->
      <section class="certifications section">
        <h2 class="section-title fade-in-up">Certifications & Achievements</h2>
        <div class="certifications-grid">
          <div class="certification-card fade-in-up" v-for="cert in certifications" :key="cert.id">
            <div class="cert-icon">
              <i :class="cert.icon"></i>
            </div>
            <div class="cert-content">
              <h3 class="cert-title">{{ cert.title }}</h3>
              <p class="cert-issuer">{{ cert.issuer }}</p>
              <div class="cert-date">{{ cert.date }}</div>
            </div>
            <div class="cert-badge">
              <i class="fas fa-certificate"></i>
            </div>
          </div>
        </div>
      </section>

      <!-- Skills Progress -->
      <section class="skills-progress section">
        <h2 class="section-title fade-in-up">Professional Growth</h2>
        <div class="skills-chart">
          <div class="skill-item fade-in-right" v-for="skill in skillsProgress" :key="skill.name">
            <div class="skill-info">
              <span class="skill-name">{{ skill.name }}</span>
              <span class="skill-percentage">{{ skill.level }}%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Experience',
  data() {
    return {
      workExperience: [
        {
          id: 1,
          title: 'Senior Full Stack Developer',
          company: 'TechCorp Solutions',
          period: 'Jan 2023 - Present',
          icon: 'fas fa-building',
          responsibilities: [
            'Led development of scalable web applications using Vue.js and Node.js',
            'Mentored junior developers and conducted code reviews',
            'Implemented CI/CD pipelines and improved deployment processes',
            'Collaborated with cross-functional teams to deliver high-quality products'
          ],
          technologies: ['Vue.js', 'Node.js', 'MongoDB', 'AWS', 'Docker']
        },
        {
          id: 2,
          title: 'Full Stack Developer',
          company: 'StartupXYZ',
          period: 'Jun 2022 - Dec 2022',
          icon: 'fas fa-rocket',
          responsibilities: [
            'Developed and maintained multiple client projects simultaneously',
            'Built responsive web applications with modern JavaScript frameworks',
            'Integrated third-party APIs and payment gateways',
            'Optimized application performance and user experience'
          ],
          technologies: ['React', 'Express.js', 'PostgreSQL', 'Stripe API']
        },
        {
          id: 3,
          title: 'Junior Web Developer',
          company: 'Digital Agency Pro',
          period: 'Mar 2021 - May 2022',
          icon: 'fas fa-laptop-code',
          responsibilities: [
            'Assisted in developing client websites and web applications',
            'Learned and applied best practices in web development',
            'Participated in agile development processes',
            'Contributed to team projects and gained valuable experience'
          ],
          technologies: ['HTML', 'CSS', 'JavaScript', 'PHP', 'MySQL']
        }
      ],
      education: [
        {
          id: 1,
          degree: 'Bachelor of Science in Computer Science',
          institution: 'University of Technology',
          period: '2017 - 2021',
          icon: 'fas fa-graduation-cap',
          description: 'Focused on software engineering, algorithms, and web technologies. Graduated with honors.'
        },
        {
          id: 2,
          degree: 'Full Stack Web Development Bootcamp',
          institution: 'CodeAcademy Pro',
          period: '2020',
          icon: 'fas fa-code',
          description: 'Intensive 6-month program covering modern web development technologies and best practices.'
        }
      ],
      certifications: [
        {
          id: 1,
          title: 'AWS Certified Developer',
          issuer: 'Amazon Web Services',
          date: '2023',
          icon: 'fab fa-aws'
        },
        {
          id: 2,
          title: 'Vue.js Certified Developer',
          issuer: 'Vue School',
          date: '2022',
          icon: 'fab fa-vuejs'
        },
        {
          id: 3,
          title: 'MongoDB Certified Developer',
          issuer: 'MongoDB University',
          date: '2022',
          icon: 'fas fa-database'
        },
        {
          id: 4,
          title: 'Google Analytics Certified',
          issuer: 'Google',
          date: '2021',
          icon: 'fab fa-google'
        }
      ],
      skillsProgress: [
        { name: 'JavaScript/TypeScript', level: 95 },
        { name: 'Vue.js/React', level: 90 },
        { name: 'Node.js/Express', level: 85 },
        { name: 'Database Design', level: 80 },
        { name: 'Cloud Services (AWS)', level: 75 },
        { name: 'DevOps/CI-CD', level: 70 }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.experience {
  padding-top: 80px;
}

.experience-hero {
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

.experience-visual {
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

.work-experience {
  .section-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--text-primary);
    text-align: center;
    margin-bottom: 60px;
  }
  
  .experience-timeline {
    max-width: 800px;
    margin: 0 auto;
    position: relative;
    
    &::before {
      content: '';
      position: absolute;
      left: 30px;
      top: 0;
      bottom: 0;
      width: 3px;
      background: linear-gradient(to bottom, var(--primary-purple), var(--secondary-purple));
    }
    
    .experience-item {
      position: relative;
      padding-left: 80px;
      margin-bottom: 50px;
      
      .experience-marker {
        position: absolute;
        left: 18px;
        top: 20px;
        
        .experience-dot {
          width: 24px;
          height: 24px;
          background: var(--primary-purple);
          border-radius: 50%;
          border: 4px solid var(--bg-primary);
          box-shadow: 0 0 0 4px var(--primary-purple);
        }
      }
      
      .experience-card {
        background: var(--bg-card);
        border-radius: 16px;
        padding: 32px;
        box-shadow: var(--shadow);
        border: 1px solid var(--border-color);
        transition: all 0.3s ease;
        
        &:hover {
          transform: translateY(-5px);
          box-shadow: var(--shadow-lg);
        }
        
        .experience-header {
          display: flex;
          justify-content: space-between;
          align-items: flex-start;
          margin-bottom: 24px;
          
          .company-info {
            .job-title {
              font-size: 1.5rem;
              font-weight: 600;
              color: var(--text-primary);
              margin-bottom: 8px;
            }
            
            .company-name {
              font-size: 1.1rem;
              color: var(--primary-purple);
              font-weight: 500;
              margin-bottom: 8px;
            }
            
            .job-period {
              color: var(--text-secondary);
              font-size: 0.9rem;
              font-weight: 500;
            }
          }
          
          .company-logo {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
          }
        }
        
        .job-description {
          margin-bottom: 24px;
          
          ul {
            list-style: none;
            
            li {
              color: var(--text-secondary);
              line-height: 1.6;
              margin-bottom: 8px;
              position: relative;
              padding-left: 20px;
              
              &::before {
                content: '▸';
                position: absolute;
                left: 0;
                color: var(--primary-purple);
                font-weight: bold;
              }
            }
          }
        }
        
        .job-technologies {
          display: flex;
          flex-wrap: wrap;
          gap: 8px;
          
          .tech-tag {
            background: var(--light-purple);
            color: var(--dark-purple);
            padding: 6px 12px;
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
  }
}

.education {
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
  
  .education-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    gap: 32px;
    
    .education-card {
      background: var(--bg-card);
      border-radius: 16px;
      padding: 32px;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      display: flex;
      gap: 24px;
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-5px);
        box-shadow: var(--shadow-lg);
      }
      
      .education-icon {
        width: 80px;
        height: 80px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        border-radius: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 32px;
        color: white;
        flex-shrink: 0;
      }
      
      .education-content {
        .degree-title {
          font-size: 1.25rem;
          font-weight: 600;
          color: var(--text-primary);
          margin-bottom: 8px;
        }
        
        .institution-name {
          color: var(--primary-purple);
          font-weight: 500;
          margin-bottom: 8px;
        }
        
        .education-period {
          color: var(--text-secondary);
          font-size: 0.9rem;
          margin-bottom: 12px;
        }
        
        .education-description {
          color: var(--text-secondary);
          line-height: 1.6;
        }
      }
    }
  }
}

.certifications {
  .section-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--text-primary);
    text-align: center;
    margin-bottom: 60px;
  }
  
  .certifications-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 24px;
    
    .certification-card {
      background: var(--bg-card);
      border-radius: 12px;
      padding: 24px;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      display: flex;
      align-items: center;
      gap: 20px;
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateX(5px);
        box-shadow: var(--shadow-lg);
      }
      
      .cert-icon {
        width: 50px;
        height: 50px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 20px;
        color: white;
        flex-shrink: 0;
      }
      
      .cert-content {
        flex: 1;
        
        .cert-title {
          font-size: 1.1rem;
          font-weight: 600;
          color: var(--text-primary);
          margin-bottom: 4px;
        }
        
        .cert-issuer {
          color: var(--text-secondary);
          font-size: 0.9rem;
          margin-bottom: 4px;
        }
        
        .cert-date {
          color: var(--primary-purple);
          font-size: 0.875rem;
          font-weight: 500;
        }
      }
      
      .cert-badge {
        color: var(--primary-purple);
        font-size: 24px;
      }
    }
  }
}

.skills-progress {
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
  
  .skills-chart {
    max-width: 600px;
    margin: 0 auto;
    
    .skill-item {
      margin-bottom: 32px;
      
      .skill-info {
        display: flex;
        justify-content: space-between;
        margin-bottom: 8px;
        
        .skill-name {
          font-weight: 600;
          color: var(--text-primary);
        }
        
        .skill-percentage {
          color: var(--primary-purple);
          font-weight: 600;
        }
      }
      
      .skill-bar {
        height: 8px;
        background: var(--border-color);
        border-radius: 4px;
        overflow: hidden;
        
        .skill-progress {
          height: 100%;
          background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
          border-radius: 4px;
          transition: width 1s ease-in-out;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .experience-hero {
    padding-top: 80px;
  }
  
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }
  
  .experience-timeline::before {
    left: 15px;
  }
  
  .experience-item {
    padding-left: 50px;
    
    .experience-marker {
      left: 3px;
    }
  }
  
  .experience-card .experience-header {
    flex-direction: column;
    gap: 16px;
  }
  
  .education-grid .education-card {
    flex-direction: column;
    text-align: center;
  }
  
  .education,
  .skills-progress {
    padding: 40px 20px;
  }
}
</style>