<template>
  <div class="experience">
    <div class="container">
      <!-- Hero Section -->
      <section class="experience-hero section">
  <div class="hero-grid">
    
    <div class="hero-left fade-in-left">
      <h1 class="page-title">Professional Experience</h1>

     <p class="page-description">
  I'm a fresher actively seeking full-time opportunities in software development, 
  backed by hands-on experience from internships and real-world projects. I’ve built 
  applications, worked on practical problems, and understood how to turn ideas into 
  functional solutions.
</p>

<p class="page-description">
  Through my projects and experience, I’ve developed a strong interest in full-stack 
  development and enjoy working across both frontend and backend. I focus on writing 
  clean code, building user-friendly interfaces, and creating efficient systems.
</p>

<p class="page-description">
  I’m driven to learn, grow, and take on new challenges. I enjoy working in collaborative 
  environments and aim to contribute to meaningful projects while continuously improving 
  my skills as a developer.
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

  <div class="single-experience fade-in-up">
    <div class="experience-card">

      <div class="experience-header">
        <div class="company-info">
          <h3 class="job-title">{{ workExperience.title }}</h3>
          <h4 class="company-name">{{ workExperience.company }}</h4>
          <div class="job-period">{{ workExperience.period }}</div>
        </div>

        <div class="company-logo">
          <i :class="workExperience.icon"></i>
        </div>
      </div>

      <div class="job-description">
        <ul>
          <li v-for="item in workExperience.responsibilities" :key="item">
            {{ item }}
          </li>
        </ul>
      </div>

      <div class="job-technologies">
        <span v-for="tech in workExperience.technologies" :key="tech" class="tech-tag">
          {{ tech }}
        </span>
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
      /* ✅ SINGLE REAL EXPERIENCE */
      workExperience: {
        title: "Software Development Engineer Intern",
        company: "Yuma Energy",
        period: "June 2025 - December 2025",
        icon: "fas fa-building",
        responsibilities: [
          "Developed and improved features for web applications",
          "Worked on frontend and backend integration",
          "Collaborated with team members to deliver project tasks",
          "Gained hands-on experience in real-world development workflows"
        ],
        technologies: ["React","Vue","MySQL", "Node.js", "MongoDB"]
      },

      /* ✅ EDUCATION (keep yours or modify) */
      education: [
        {
          id: 1,
          degree: 'MSc Integrated Software Systems',
          institution: 'Coimbatore Institute of Technology',
          period: '2022 - Present',
          icon: 'fas fa-graduation-cap',
          description: 'Focused on software development, problem-solving, and building real-world applications.'
        },
        {
          id: 2,
          degree: 'Higher Secondary Education',
          institution: 'Little Flower Convent Matric Hr Sec School',
          period: 'Completed',
          icon: 'fas fa-school',
          description: 'Built a strong academic foundation and developed interest in technology.'
        }
      ],

      /* ✅ CERTIFICATIONS (edit if needed) */
      certifications: [
        {
          id: 1,
          title: 'Code Forge Series Winner',
          issuer: 'SDC CIT',
          date: '2025',
          icon: 'fas fa-trophy'
        },
        {
          id: 2,
          title: 'CODEVORTEX Hackathon Recognition',
          issuer: 'CIT Computing Association',
          date: '2025',
          icon: 'fas fa-medal'
        }
      ],

      /* ✅ SKILLS (realistic for fresher) */
      skillsProgress: [
        { name: 'JavaScript', level: 80 },
        { name: 'React.js', level: 75 },
        { name: 'Node.js', level: 70 },
        { name: 'MongoDB', level: 70 },
        { name: 'Problem Solving', level: 85 }
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
  min-height: 40vh;
  display: flex;
  align-items: flex-start;
  padding: 10px 0 0; /* remove bottom space */
}

/* GRID */
.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px; /* reduced from 80px → tighter */
  align-items: center;
}

/* LEFT */
.hero-left {
  animation: fadeInLeft 0.8s ease-out;
}

/* TITLE */
.page-title {
  font-size: clamp(2.2rem, 4vw, 3rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 12px;
  line-height: 1.1;

  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* DESCRIPTION */
.page-description {
  font-size: 1rem;
  line-height: 1.6;
  color: var(--text-secondary);
  margin-bottom: 14px; /* tighter */
}

/* RIGHT */
.hero-right {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeInRight 0.8s ease-out;
}

/* ICON (important polish) */
.experience-visual {
  font-size: 80px;
  color: rgba(139, 92, 246, 0.7);
  background: rgba(139, 92, 246, 0.08);
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 10px 25px rgba(139, 92, 246, 0.15);
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

@media (max-width: 968px) {
  .experience-hero {
    padding-top: 80px;
    min-height: auto;
  }
  
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }
  
  .page-title {
    font-size: 2.5rem;
  }
  
  .page-description {
    font-size: 1rem;
  }
  
  .experience-visual {
    width: 200px;
    height: 200px;
    font-size: 64px;
    margin: 0 auto;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .experience-timeline::before {
    left: 15px;
  }
  
  .experience-item {
    padding-left: 50px;
    margin-bottom: 40px;
    
    .experience-marker {
      left: 3px;
    }
  }
  
  .experience-card {
    padding: 24px;
    
    .experience-header {
      flex-direction: column;
      gap: 16px;
      align-items: flex-start;
    }
    
    .company-logo {
      width: 50px;
      height: 50px;
      font-size: 20px;
    }
  }
  
  .education-grid {
    grid-template-columns: 1fr;
    gap: 24px;
  }
  
  .education-card {
    flex-direction: column;
    text-align: center;
    padding: 24px;
  }
  
  .education-icon {
    width: 60px;
    height: 60px;
    font-size: 24px;
    margin: 0 auto;
  }
  
  .certifications-grid {
    grid-template-columns: 1fr;
  }
  
  .education,
  .skills-progress {
    padding: 40px 20px;
  }
}

@media (max-width: 640px) {
  .page-title {
    font-size: 2rem;
  }
  
  .experience-visual {
    width: 150px;
    height: 150px;
    font-size: 48px;
  }
  
  .section-title {
    font-size: 1.75rem;
  }
  
  .experience-card {
    padding: 20px;
  }
  
  .job-title {
    font-size: 1.25rem;
  }
  
  .job-description ul li {
    font-size: 0.9375rem;
  }
  
  .certification-card {
    padding: 20px;
  }
}
</style>