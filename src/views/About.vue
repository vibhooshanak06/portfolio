<template>
  <div class="about">
    <div class="container">
      <!-- Hero Section -->
      <section class="about-hero section">
        <div class="hero-grid">
          <div class="hero-left fade-in-left">
            <h1 class="page-title">About Me</h1>
            <p class="page-description">
              Passionate developer with a love for creating innovative digital solutions 
              that make a difference in people's lives.
            </p>
            <p class="page-description">
              I believe in continuous learning, collaboration, and building products 
              that combine technical excellence with exceptional user experiences.
            </p>
          </div>
          <div class="hero-right fade-in-right">
            <div class="about-image">
              <i class="fas fa-code"></i>
            </div>
          </div>
        </div>
      </section>

      <!-- Story Section -->
      <section class="story-section section">
        <div class="story-content">
          <div class="story-text fade-in-up">
            <h2 class="section-title">My Story</h2>
            <div class="story-paragraphs">
              <p>
                Hello! I'm Vibhooshana Kannan, aspiring full-stack developer based in Tamilnadu. 
                My journey into the world of programming began during my college years when 
                I discovered the power of code to bring ideas to life.
              </p>
              <p>
                With over 3 years of experience in web development, I've had the privilege 
                of working on diverse projects ranging from e-commerce platforms to complex 
                web applications. I believe in writing clean, efficient code and creating 
                user experiences that make a difference.
              </p>
              <p>
                When I'm not coding, you can find me exploring new technologies, contributing 
                to open-source projects, or enjoying a good book with a cup of coffee. 
                I'm always eager to learn and take on new challenges.
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- Values Section -->
      <section class="values-section section">
        <h2 class="section-title fade-in-up">What Drives Me</h2>
        <div class="values-grid">
          <div class="value-card fade-in-up" v-for="value in values" :key="value.id">
            <div class="value-icon">
              <i :class="value.icon"></i>
            </div>
            <h3 class="value-title">{{ value.title }}</h3>
            <p class="value-description">{{ value.description }}</p>
          </div>
        </div>
      </section>

      <!-- Timeline Section -->
      <section class="timeline-section section">
        <h2 class="section-title fade-in-up">My Journey</h2>
        <div class="timeline">
          <div class="timeline-item fade-in-left" v-for="(item, index) in timeline" :key="item.id">
            <div class="timeline-marker">
              <div class="timeline-dot"></div>
            </div>
            <div class="timeline-content">
              <div class="timeline-year">{{ item.year }}</div>
              <h3 class="timeline-title">{{ item.title }}</h3>
              <p class="timeline-description">{{ item.description }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- Fun Facts -->
      <section class="fun-facts section">
        <div class="fun-facts-content">
          <h2 class="section-title fade-in-up">Fun Facts About Me</h2>
          <div class="facts-grid">
            <div class="fact-item fade-in-up" v-for="fact in funFacts" :key="fact.id">
              <div class="fact-icon">
                <i :class="fact.icon"></i>
              </div>
              <div class="fact-text">{{ fact.text }}</div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      values: [
        {
          id: 1,
          icon: 'fas fa-lightbulb',
          title: 'Innovation',
          description: 'Always seeking creative solutions and staying updated with the latest technologies.'
        },
        {
          id: 2,
          icon: 'fas fa-users',
          title: 'Collaboration',
          description: 'Believing in the power of teamwork and open communication to achieve great results.'
        },
        {
          id: 3,
          icon: 'fas fa-heart',
          title: 'Passion',
          description: 'Genuinely loving what I do and putting my heart into every project I work on.'
        },
        {
          id: 4,
          icon: 'fas fa-graduation-cap',
          title: 'Learning',
          description: 'Continuously improving my skills and embracing new challenges as opportunities to grow.'
        }
      ],
      timeline: [
        {
          id: 1,
          year: '2021',
          title: 'Started My Journey',
          description: 'Began learning web development and fell in love with creating digital experiences.'
        },
        {
          id: 2,
          year: '2022',
          title: 'First Professional Role',
          description: 'Joined a startup as a junior developer and gained valuable real-world experience.'
        },
        {
          id: 3,
          year: '2023',
          title: 'Full-Stack Developer',
          description: 'Expanded my skills to become a full-stack developer, working with both frontend and backend technologies.'
        },
        {
          id: 4,
          year: '2024',
          title: 'Freelance Success',
          description: 'Started freelancing and successfully delivered multiple projects for various clients.'
        }
      ],
      funFacts: [
        {
          id: 1,
          icon: 'fas fa-coffee',
          text: 'I drink at least 4 cups of coffee per day'
        },
        {
          id: 2,
          icon: 'fas fa-music',
          text: 'I code better with lo-fi music playing'
        },
        {
          id: 3,
          icon: 'fas fa-gamepad',
          text: 'I love playing strategy games in my free time'
        },
        {
          id: 4,
          icon: 'fas fa-mountain',
          text: 'I enjoy hiking and outdoor photography'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.about {
  padding-top: 80px;
}

.about-hero {
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

.about-image {
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

.story-section {
  .story-text {
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
    
    .section-title {
      font-size: 2.5rem;
      font-weight: 700;
      color: var(--text-primary);
      margin-bottom: 40px;
    }
    
    .story-paragraphs {
      p {
        font-size: 1.1rem;
        line-height: 1.8;
        color: var(--text-secondary);
        margin-bottom: 24px;
        text-align: left;
        
        &:last-child {
          margin-bottom: 0;
        }
      }
    }
  }
}

.values-section {
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
  
  .values-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 32px;
    
    .value-card {
      background: var(--bg-card);
      padding: 32px;
      border-radius: 16px;
      text-align: center;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-5px);
        box-shadow: var(--shadow-lg);
      }
      
      .value-icon {
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
      
      .value-title {
        font-size: 1.5rem;
        font-weight: 600;
        color: var(--text-primary);
        margin-bottom: 16px;
      }
      
      .value-description {
        color: var(--text-secondary);
        line-height: 1.6;
      }
    }
  }
}

.timeline-section {
  .section-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--text-primary);
    text-align: center;
    margin-bottom: 60px;
  }
  
  .timeline {
    max-width: 600px;
    margin: 0 auto;
    position: relative;
    
    &::before {
      content: '';
      position: absolute;
      left: 30px;
      top: 0;
      bottom: 0;
      width: 2px;
      background: var(--primary-purple);
    }
    
    .timeline-item {
      position: relative;
      padding-left: 80px;
      margin-bottom: 40px;
      
      .timeline-marker {
        position: absolute;
        left: 20px;
        top: 0;
        
        .timeline-dot {
          width: 20px;
          height: 20px;
          background: var(--primary-purple);
          border-radius: 50%;
          border: 4px solid var(--bg-primary);
        }
      }
      
      .timeline-content {
        .timeline-year {
          font-size: 0.875rem;
          font-weight: 600;
          color: var(--primary-purple);
          margin-bottom: 8px;
        }
        
        .timeline-title {
          font-size: 1.5rem;
          font-weight: 600;
          color: var(--text-primary);
          margin-bottom: 12px;
        }
        
        .timeline-description {
          color: var(--text-secondary);
          line-height: 1.6;
        }
      }
    }
  }
}

.fun-facts {
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
  
  .facts-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 24px;
    
    .fact-item {
      background: var(--bg-card);
      padding: 24px;
      border-radius: 12px;
      display: flex;
      align-items: center;
      gap: 16px;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateX(5px);
      }
      
      .fact-icon {
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
      
      .fact-text {
        color: var(--text-secondary);
        font-weight: 500;
      }
    }
  }
}

@media (max-width: 968px) {
  .about-hero {
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
  
  .about-image {
    width: 200px;
    height: 200px;
    font-size: 64px;
    margin: 0 auto;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .values-section,
  .fun-facts {
    padding: 40px 20px;
  }
  
  .values-grid,
  .facts-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .timeline::before {
    left: 15px;
  }
  
  .timeline-item {
    padding-left: 50px;
    
    .timeline-marker {
      left: 5px;
    }
  }
}

@media (max-width: 640px) {
  .page-title {
    font-size: 2rem;
  }
  
  .about-image {
    width: 150px;
    height: 150px;
    font-size: 48px;
  }
  
  .section-title {
    font-size: 1.75rem;
  }
  
  .value-card,
  .activity-card {
    padding: 24px;
  }
  
  .value-icon {
    width: 60px;
    height: 60px;
    font-size: 24px;
  }
  
  .story-paragraphs p {
    font-size: 1rem;
  }
}
</style>