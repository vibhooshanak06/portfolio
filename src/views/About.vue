<template>
  <div class="about">
    <div class="container">

     <section class="about-hero section">
  <div class="hero-grid">
    
    <div class="hero-left fade-in-left">
      <h1 class="page-title">About Me</h1>

      <p class="page-description">
        I'm Vibhooshana, an enthusiastic MSc Software Systems student based in 
        Tirupur, Tamil Nadu, with a strong interest in full-stack development. 
        I genuinely enjoy solving problems and turning ideas into real, working applications.
      </p>

      <p class="page-description">
        With a solid foundation in programming and a curiosity to explore how things work, 
        I continuously learn and experiment with new technologies. I focus on building 
        practical, user-friendly solutions that are not just functional, but meaningful.
      </p>

      <p class="page-description">
        Along with technical skills, I bring adaptability, leadership experience, and a 
        collaborative mindset. Whether working independently or in a team, I aim to 
        contribute effectively and keep improving with every project I take on.
      </p>
    </div>

    <div class="hero-right fade-in-right">
      <div class="photo-container">
        <div class="orbit-ring">
          <div class="orbit-dot orbit-dot-1"></div>
          <div class="orbit-dot orbit-dot-2"></div>
          <div class="orbit-dot orbit-dot-3"></div>
        
        </div>
        <div class="about-image">
          <img src="@/assets/me.jpeg" alt="Vibhooshana Kannan" class="profile-photo">
        </div>
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
          icon: 'fas fa-code',
          title: 'Building with Purpose',
          description: 'I like creating projects that solve real problems instead of just coding for the sake of it.'
        },
        {
          id: 2,
          icon: 'fas fa-brain',
          title: 'Problem Solving',
          description: 'I enjoy breaking down complex problems into simple steps and finding practical solutions.'
        },
        {
          id: 3,
          icon: 'fas fa-users',
          title: 'Team & Leadership',
          description: 'Through events and teamwork, I’ve learned how to collaborate, lead, and get things done together.'
        },
        {
          id: 4,
          icon: 'fas fa-rocket',
          title: 'Continuous Growth',
          description: 'I’m always learning — whether it’s new tech, better coding practices, or improving myself.'
        }
      ],

      timeline: [
        {
          id: 1,
          year: '2022',
          title: 'Started Exploring Programming',
          description: 'Got introduced to programming in college and became curious about how things work behind the scenes.'
        },
        {
          id: 2,
          year: '2023',
          title: 'Built My First Projects',
          description: 'Started building small projects and slowly understood how to turn ideas into working applications.'
        },
        {
          id: 3,
          year: '2024',
          title: 'Real-World Project Development',
          description: 'Worked on projects like PARK-N-GO and LIVISHIELD, focusing on solving practical problems.'
        },
        {
          id: 4,
          year: '2025',
          title: 'Leadership & Hackathons',
          description: 'Organized events, participated in hackathons, and gained confidence in building under pressure.'
        }
      ],

      funFacts: [
        {
          id: 1,
          icon: 'fas fa-music',
          text: 'I love listening to music while coding — it keeps me focused.'
        },
        {
          id: 2,
          icon: 'fas fa-utensils',
          text: 'Cooking is something I genuinely enjoy when I take a break.'
        },
        {
          id: 3,
          icon: 'fas fa-lightbulb',
          text: 'I tend to overthink sometimes, but it actually helps me plan better solutions.'
        },
        {
  id: 4,
  icon: 'fas fa-book',
  text: 'I enjoy reading books and learning new things at my own pace.'
}
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.about {
  padding-top: 20px;
}

/* HERO */
.about-hero {
  min-height: 20vh;
  display: flex;
  align-items: center;
  padding: 20px 0;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
  align-items: center;
}

.page-title {
  font-size: clamp(2.2rem, 4vw, 3rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 16px;

  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.page-description {
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 14px;
  color: var(--text-secondary);
}

/* IMAGE */
.hero-right {
  display: flex;
  justify-content: center;
}

.about-image {
  width: 220px;
  height: 220px;
  border-radius: 50%;
  overflow: hidden;
  border: 2px solid rgba(139, 92, 246, 0.2);
  box-shadow: 0 10px 25px rgba(139, 92, 246, 0.15);

  .profile-photo {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.photo-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* ORBIT RING */
.orbit-ring {
  position: absolute;
  width: 260px;
  height: 260px;
  border-radius: 50%;
  border: 1.5px solid rgba(139, 92, 246, 0.25);
  animation: rotateOrbit 18s linear infinite;
}

/* ORBIT DOTS */
.orbit-dot {
  position: absolute;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
  box-shadow: 0 0 8px rgba(139, 92, 246, 0.6);
}

/* Positions */
.orbit-dot-1 {
  top: -4px;
  left: 50%;
  transform: translateX(-50%);
}

.orbit-dot-2 {
  right: -4px;
  top: 50%;
  transform: translateY(-50%);
}

.orbit-dot-3 {
  bottom: -4px;
  left: 50%;
  transform: translateX(-50%);
}

.photo-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* BRIGHT ORBIT RING */
.orbit-ring {
  position: absolute;
  width: 260px;
  height: 260px;
  border-radius: 50%;
  
  border: 2px solid rgba(139, 92, 246, 0.6);
  box-shadow: 
    0 0 25px rgba(139, 92, 246, 0.6),
    0 0 60px rgba(139, 92, 246, 0.3);

  animation: rotateOrbit 12s linear infinite;
}

/* DOTS */
.orbit-dot {
  position: absolute;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: linear-gradient(135deg, #8b5cf6, #a78bfa);
  box-shadow: 0 0 10px rgba(139, 92, 246, 0.9);
}

.orbit-dot-1 {
  top: -4px;
  left: 50%;
  transform: translateX(-50%);
}

.orbit-dot-2 {
  right: -4px;
  top: 50%;
  transform: translateY(-50%);
}

.orbit-dot-3 {
  bottom: -4px;
  left: 50%;
  transform: translateX(-50%);
}


/* PROFILE IMAGE (STATIC) */
.about-image {
  width: 220px;
  height: 220px;
  border-radius: 50%;
  overflow: hidden;
  position: relative;
  z-index: 2;

  border: 2px solid rgba(139, 92, 246, 0.4);
  box-shadow: 0 10px 30px rgba(139, 92, 246, 0.25);

  transition: transform 0.3s ease;

  &:hover {
    transform: scale(1.05);
  }

  .profile-photo {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

/* ORBIT ROTATION */
@keyframes rotateOrbit {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

/* VALUES */
.values-section {
  margin-top: 40px;
}

.section-title {
  font-size: 2rem;
  font-weight: 600;
  text-align: center;
  margin-bottom: 30px;

  /* Gradient text color */
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
}

.value-card {
  background: var(--bg-card);
  padding: 22px;
  border-radius: 12px;
  text-align: center;
  border: 1px solid var(--border-color);
  transition: 0.25s ease;

  &:hover {
    transform: translateY(-3px);
  }

  .value-icon {
    width: 55px;
    height: 55px;
    margin: 0 auto 14px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;

    background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
    color: white;
    font-size: 20px;
  }

  .value-title {
    font-size: 1.1rem;
    font-weight: 600;
    margin-bottom: 8px;
  }

  .value-description {
    font-size: 0.95rem;
    line-height: 1.5;
    color: var(--text-secondary);
  }
}

/* FUN FACTS */
.fun-facts {
  margin-top: 40px;
}

.facts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 16px;
}

.fact-item {
  background: var(--bg-card);
  padding: 16px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  gap: 12px;
  border: 1px solid var(--border-color);
  transition: 0.25s ease;

  &:hover {
    transform: translateX(3px);
  }

  .fact-icon {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;

    background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
    color: white;
    font-size: 16px;
  }

  .fact-text {
    font-size: 0.95rem;
    color: var(--text-secondary);
  }
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 30px;
    text-align: center;
  }

  .about-image {
    width: 180px;
    height: 180px;
    margin: 0 auto;
  }

  .section-title {
    font-size: 1.6rem;
  }
}
</style>