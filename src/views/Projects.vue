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
          <div class="project-card fade-in-up" v-for="project in paginatedProjects" :key="project.id">
            <div class="project-content">
              <div class="project-header">
                <div class="project-icon">
                  <i :class="project.icon"></i>
                </div>
                <div class="project-title-group">
                  <h3 class="project-title">{{ project.title }}</h3>
                  <div class="project-links">
                    <a v-if="project.github" :href="project.github" target="_blank" class="link-btn github-btn" title="GitHub">
                      <i class="fab fa-github"></i> GitHub
                    </a>
                    <a v-if="project.live" :href="project.live" target="_blank" class="link-btn live-btn" title="Live Demo">
                      <i class="fas fa-external-link-alt"></i> Live
                    </a>
                  </div>
                </div>
              </div>
              <p class="project-description">{{ project.description }}</p>
              <div class="project-tech">
                <span v-for="tech in project.technologies" :key="tech" class="tech-chip">{{ tech }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Pagination -->
        <div class="pagination">
          <button class="page-btn" :disabled="currentPage === 1" @click="currentPage--">
            <i class="fas fa-chevron-left"></i>
          </button>
          <span class="page-info">{{ currentPage }} / {{ totalPages }}</span>
          <button class="page-btn" :disabled="currentPage === totalPages" @click="currentPage++">
            <i class="fas fa-chevron-right"></i>
          </button>
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
      currentPage: 1,
      perPage: 3,
      projects: [
        {
          id: 1,
          title: 'LiviShield',
          description: 'Description coming soon.',
          technologies: [],
          icon: 'fas fa-shield-alt',
          github: '',
          live: ''
        },
        {
          id: 2,
          title: 'FraudLens',
          description: 'Description coming soon.',
          technologies: [],
          icon: 'fas fa-search',
          github: '',
          live: ''
        },
        {
          id: 3,
          title: 'Med ParaSearch',
          description: 'Description coming soon.',
          technologies: [],
          icon: 'fas fa-heartbeat',
          github: '',
          live: ''
        },
        {
          id: 4,
          title: 'My Portfolio',
          description: 'Description coming soon.',
          technologies: [],
          icon: 'fas fa-user',
          github: '',
          live: ''
        }
      ]
    }
  },
  computed: {
    totalPages() {
      return Math.ceil(this.projects.length / this.perPage)
    },
    paginatedProjects() {
      const start = (this.currentPage - 1) * this.perPage
      return this.projects.slice(start, start + this.perPage)
    }
  }
}
</script>

<style scoped lang="scss">
.projects { padding-top: 80px; }

/* ── Hero ── */
.projects-hero {
  min-height: 35vh;
  display: flex;
  align-items: flex-start;
  padding: 10px 0 0;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
  align-items: center;
}

.hero-left { animation: fadeInLeft 0.8s ease-out; }

.page-title {
  font-size: clamp(2rem, 4vw, 2.8rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 14px;
  line-height: 1.1;
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.page-description {
  font-size: 0.95rem;
  line-height: 1.65;
  color: var(--text-secondary);
  margin-bottom: 12px;
}

.hero-right {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeInRight 0.8s ease-out;
}

.projects-visual {
  width: 110px;
  height: 110px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 42px;
  color: white;
  animation: float 3s ease-in-out infinite;
  box-shadow: 0 0 0 12px rgba(99, 102, 241, 0.1), 0 16px 40px rgba(99, 102, 241, 0.3);
}

/* ── Grid ── */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
}

/* ── Card ── */
.project-card {
  background: var(--bg-card);
  border-radius: 16px;
  border: 1px solid var(--border-color);
  overflow: hidden;
  position: relative;
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;

  &::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--primary), #8B5CF6, var(--accent));
    border-radius: 16px 16px 0 0;
  }

  &:hover {
    transform: translateY(-5px);
    border-color: rgba(99, 102, 241, 0.4);
    box-shadow: 0 16px 40px rgba(99, 102, 241, 0.18);

    .project-icon { transform: scale(1.08); }
  }
}

.project-content { padding: 20px; }

.project-header {
  display: flex;
  align-items: flex-start;
  gap: 14px;
  margin-bottom: 12px;
}

.project-icon {
  width: 46px;
  height: 46px;
  border-radius: 12px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  color: white;
  flex-shrink: 0;
  box-shadow: 0 4px 14px rgba(99, 102, 241, 0.35);
  transition: transform 0.3s ease;
}

.project-title-group { flex: 1; }

.project-title {
  font-size: 1rem;
  font-weight: 700;
  color: var(--text-primary);
  margin-bottom: 6px;
  line-height: 1.3;
}

/* Link buttons */
.project-links {
  display: flex;
  gap: 6px;
}

.link-btn {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 3px 10px;
  border-radius: 20px;
  font-size: 0.7rem;
  font-weight: 600;
  text-decoration: none;
  transition: opacity 0.2s, transform 0.2s;

  &:hover { opacity: 0.85; transform: translateY(-1px); }
}

.github-btn {
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.15);
  color: var(--text-secondary);
}

.live-btn {
  background: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.3);
  color: var(--primary-light);
}

.project-description {
  color: var(--text-secondary);
  font-size: 0.875rem;
  line-height: 1.6;
  margin-bottom: 16px;
}

/* Tech chips */
.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.tech-chip {
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.25);
  color: var(--primary-light);
  padding: 3px 10px;
  border-radius: 20px;
  font-size: 0.72rem;
  font-weight: 500;
  transition: background 0.2s;

  &:hover { background: rgba(99, 102, 241, 0.2); }
}

/* ── Pagination ── */
.pagination {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-top: 40px;
}

.page-btn {
  width: 38px;
  height: 38px;
  border-radius: 10px;
  border: 1px solid var(--border-color);
  background: var(--bg-card);
  color: var(--text-primary);
  font-size: 14px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.2s ease;

  &:hover:not(:disabled) {
    background: var(--primary);
    border-color: var(--primary);
    color: white;
    box-shadow: 0 4px 14px rgba(99, 102, 241, 0.4);
  }

  &:disabled {
    opacity: 0.3;
    cursor: not-allowed;
  }
}

.page-info {
  font-size: 0.9rem;
  font-weight: 600;
  color: var(--text-secondary);
  min-width: 40px;
  text-align: center;
}

/* ── Responsive ── */
@media (max-width: 968px) {
  .hero-grid { grid-template-columns: 1fr; gap: 30px; text-align: center; }
  .projects-visual { width: 90px; height: 90px; font-size: 34px; margin: 0 auto; }
  .projects-grid { grid-template-columns: 1fr; }
}

@media (max-width: 640px) {
  .page-title { font-size: 1.8rem; }
  .project-banner { height: 120px; font-size: 40px; }
}
</style>
