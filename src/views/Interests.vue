<template>
  <div class="interests">
    <div class="container">
      <section class="interests-hero section">
        <div class="hero-content fade-in-up">
          <h1 class="page-title">Interests & Hobbies</h1>
          <p class="page-subtitle">Beyond coding, here's what keeps me inspired and motivated</p>
        </div>
      </section>

      <section class="main-interests section">
        <div class="interests-grid">
          <div class="interest-card fade-in-up" v-for="interest in interests" :key="interest.id">
            <div class="interest-image">
              <i :class="interest.icon"></i>
            </div>
            <div class="interest-content">
              <h3 class="interest-title">{{ interest.title }}</h3>
              <p class="interest-description">{{ interest.description }}</p>
              <div class="interest-tags">
                <span v-for="tag in interest.tags" :key="tag" class="interest-tag">
                  {{ tag }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="fun-activities section">
        <h2 class="section-title fade-in-up">Fun Activities</h2>
        <div class="activities-grid">
          <div class="activity-card fade-in-up" v-for="activity in activities" :key="activity.id">
            <div class="activity-icon">
              <i :class="activity.icon"></i>
            </div>
            <h3 class="activity-name">{{ activity.name }}</h3>
            <p class="activity-description">{{ activity.description }}</p>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Interests',
  data() {
    return {
      interests: [
        {
          id: 1,
          title: 'Photography',
          icon: 'fas fa-camera',
          description: 'Capturing moments and exploring the world through different perspectives.',
          tags: ['Landscape', 'Street', 'Digital', 'Nature']
        },
        {
          id: 2,
          title: 'Music Production',
          icon: 'fas fa-music',
          description: 'Creating electronic music and experimenting with different sounds.',
          tags: ['Electronic', 'Ambient', 'Lo-fi', 'Experimental']
        },
        {
          id: 3,
          title: 'Gaming',
          icon: 'fas fa-gamepad',
          description: 'Strategy games and indie titles that challenge problem-solving skills.',
          tags: ['Strategy', 'Indie', 'Puzzle', 'RPG']
        },
        {
          id: 4,
          title: 'Hiking & Nature',
          icon: 'fas fa-mountain',
          description: 'Exploring trails and connecting with nature for inspiration.',
          tags: ['Trails', 'Mountains', 'Camping', 'Wildlife']
        }
      ],
      activities: [
        {
          id: 1,
          name: 'Coffee Brewing',
          icon: 'fas fa-coffee',
          description: 'Perfecting the art of pour-over and espresso making'
        },
        {
          id: 2,
          name: 'Board Games',
          icon: 'fas fa-dice',
          description: 'Strategy games with friends and family'
        },
        {
          id: 3,
          name: 'Podcasts',
          icon: 'fas fa-podcast',
          description: 'Tech talks, design stories, and entrepreneurship'
        },
        {
          id: 4,
          name: 'Reading',
          icon: 'fas fa-book',
          description: 'Technical books and creative fiction'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.interests {
  padding-top: 80px;
}

.interests-hero {
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

.main-interests {
  .interests-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 32px;
    
    .interest-card {
      background: var(--bg-card);
      border-radius: 20px;
      padding: 32px;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-8px);
        box-shadow: var(--shadow-lg);
      }
      
      .interest-image {
        width: 80px;
        height: 80px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        border-radius: 20px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 32px;
        color: white;
        margin-bottom: 24px;
        animation: float 3s ease-in-out infinite;
      }
      
      .interest-content {
        .interest-title {
          font-size: 1.5rem;
          font-weight: 600;
          color: var(--text-primary);
          margin-bottom: 16px;
        }
        
        .interest-description {
          color: var(--text-secondary);
          line-height: 1.6;
          margin-bottom: 20px;
        }
        
        .interest-tags {
          display: flex;
          flex-wrap: wrap;
          gap: 8px;
          
          .interest-tag {
            background: var(--light-purple);
            color: var(--dark-purple);
            padding: 4px 12px;
            border-radius: 16px;
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

.fun-activities {
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
  
  .activities-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 24px;
    
    .activity-card {
      background: var(--bg-card);
      border-radius: 16px;
      padding: 32px;
      text-align: center;
      box-shadow: var(--shadow);
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-5px);
        box-shadow: var(--shadow-lg);
      }
      
      .activity-icon {
        width: 70px;
        height: 70px;
        background: linear-gradient(135deg, var(--primary-purple), var(--secondary-purple));
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 28px;
        color: white;
        margin: 0 auto 24px;
      }
      
      .activity-name {
        font-size: 1.25rem;
        font-weight: 600;
        color: var(--text-primary);
        margin-bottom: 12px;
      }
      
      .activity-description {
        color: var(--text-secondary);
        line-height: 1.6;
      }
    }
  }
}

@media (max-width: 768px) {
  .fun-activities {
    padding: 40px 20px;
  }
}
</style>