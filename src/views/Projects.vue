<template>
  <div class="projects">
    <div class="container">

      <!-- Compact Hero -->
      <section class="projects-hero">
        <div class="hero-inner">
          <h1 class="page-title">Things I've Built</h1>
        </div>
      </section>

      <!-- Carousel -->
      <section class="carousel-section">
        <div class="carousel-header">
          <span class="counter">{{ currentIndex + 1 }} – {{ currentIndex + 2 > projects.length ? projects.length : currentIndex + 2 }} of {{ projects.length }}</span>
          <div class="carousel-controls">
            <button class="ctrl-btn" @click="prev" :disabled="currentIndex === 0">
              <i class="fas fa-chevron-left"></i>
            </button>
            <button class="ctrl-btn" @click="next" :disabled="currentIndex + 2 >= projects.length">
              <i class="fas fa-chevron-right"></i>
            </button>
          </div>
        </div>

        <div class="carousel-track-wrap">
          <div class="carousel-track" :style="trackStyle">
            <div
              class="project-card"
              v-for="project in projects"
              :key="project.id"
            >
              <!-- Card top -->
              <div class="card-top">
                <div class="card-icon">
                  <i :class="project.icon"></i>
                </div>
                <div class="card-meta">
                  <h3 class="project-title">{{ project.title }}</h3>
                  <div class="project-links">
                    <a v-if="project.github" :href="project.github" target="_blank" class="link-btn github-btn">
                      <i class="fab fa-github"></i> GitHub
                    </a>
                    <a v-if="project.live && project.live !== 'coming-soon'" :href="project.live" target="_blank" class="link-btn live-btn">
                      <i class="fas fa-external-link-alt"></i> Live
                    </a>
                    <span v-if="project.live === 'coming-soon'" class="link-btn soon-btn">
                      <i class="fas fa-clock"></i> Coming Soon
                    </span>
                  </div>
                </div>
              </div>

              <!-- Bullets -->
              <ul class="project-bullets">
                <li v-for="(point, i) in project.bullets" :key="i">{{ point }}</li>
              </ul>

              <!-- Tech stack -->
              <div class="project-tech">
                <span v-for="tech in project.technologies" :key="tech" class="tech-chip">{{ tech }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Dot indicators -->
        <div class="dots">
          <button
            v-for="(_, i) in dotCount"
            :key="i"
            class="dot"
            :class="{ active: dotActive(i) }"
            @click="goToDot(i)"
          ></button>
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
      currentIndex: 0,
      projects: [
        {
          id: 1,
          title: 'Fraud Lens',
          icon: 'fas fa-search',
          github: 'https://github.com/vibhooshanak06/fraudlens',
          live: 'https://fraudlens-pi.vercel.app/login',
          technologies: ['React', 'Node.js', 'Express', 'Python', 'FastAPI', 'MySQL', 'MongoDB', 'FAISS'],
          bullets: [
            'Architected and shipped a 3-tier research paper integrity platform with independent services, dual databases, automating end-to-end analysis through 10 AI-powered features including plagiarism detection, fraud analysis, semantic search, AI-generated summaries, research Q&A and citation graph visualization.',
            'Engineered a document analysis pipeline that processes each uploaded PDF through 5 AI modules, generating comprehensive integrity reports and enabling a RAG-based chatbot with semantic retrieval for context-aware responses, significantly reducing manual review effort.'
          ]
        },
        {
          id: 2,
          title: 'Livi Shield',
          icon: 'fas fa-shield-alt',
          github: 'https://github.com/vibhooshanak06/livishield',
          live: 'coming-soon',
          technologies: ['MongoDB', 'MySQL','Express.js', 'React.js', 'Node.js'],
          bullets: [
            'Developed a full-stack health insurance platform supporting 13 insurance plans across 5 categories, delivering an end-to-end digital experience for policy purchase, document submission, premium payment and policy issuance.',
            'Built a workflow-driven underwriting system that orchestrates proposal approvals, document review, payment verification and policy lifecycle transitions with notifications, streamlining insurance operations.'
          ]
        }
      ]
    }
  },
  computed: {
    trackStyle() {
      // On mobile (single card), we advance by full card width (100% + gap)
      // On desktop (two cards), each step is half the track (50% + half-gap)
      return {
        transform: `translateX(calc(-${this.currentIndex} * (50% + 12px)))`
      }
    },
    dotCount() {
      return Math.ceil(this.projects.length / 2)
    }
  },
  methods: {
    prev() {
      if (this.currentIndex > 0) this.currentIndex -= 2
    },
    next() {
      if (this.currentIndex + 2 < this.projects.length) this.currentIndex += 2
    },
    goToDot(i) {
      this.currentIndex = i * 2
    },
    dotActive(i) {
      return Math.floor(this.currentIndex / 2) === i
    }
  }
}
</script>

<style scoped lang="scss">
/* ── Wrapper ── */
.projects {
  padding-top: 16px;
  padding-bottom: 48px;
}

/* ── Hero ── */
.projects-hero {
  padding: 28px 0 22px;
  text-align: center;
}

.hero-inner {
  max-width: 560px;
  margin: 0 auto;
}

.page-title {
  font-size: clamp(1.8rem, 3.5vw, 2.4rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  line-height: 1.1;
  margin-bottom: 10px;
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.page-subtitle {
  font-size: 0.9rem;
  line-height: 1.6;
  color: var(--text-secondary);
}

/* ── Carousel ── */
.carousel-section {
  padding: 0;
}

.carousel-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 14px;
}

.counter {
  font-size: 0.78rem;
  color: var(--text-tertiary);
  font-weight: 500;
}

.carousel-controls {
  display: flex;
  gap: 8px;
}

.ctrl-btn {
  width: 32px;
  height: 32px;
  border-radius: 8px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  color: var(--text-secondary);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.7rem;
  transition: all 0.2s;

  &:hover:not(:disabled) {
    background: rgba(99, 102, 241, 0.12);
    border-color: rgba(99, 102, 241, 0.35);
    color: var(--primary-light);
  }

  &:disabled {
    opacity: 0.3;
    cursor: not-allowed;
  }
}

/* Track */
.carousel-track-wrap {
  overflow: hidden;
  border-radius: 18px;
}

.carousel-track {
  display: flex;
  gap: 24px;
  transition: transform 0.45s cubic-bezier(0.4, 0, 0.2, 1);
}

/* ── Card ── */
.project-card {
  min-width: calc(50% - 12px);
  max-width: calc(50% - 12px);
  flex-shrink: 0;
  background: var(--bg-card);
  border-radius: 16px;
  border: 1px solid var(--border-color);
  padding: 22px 24px;
  position: relative;
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;

  &::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--primary), #8B5CF6, var(--accent));
    border-radius: 16px 16px 0 0;
  }

  &:hover {
    transform: translateY(-3px);
    border-color: rgba(99, 102, 241, 0.35);
    box-shadow: 0 12px 32px rgba(99, 102, 241, 0.12);
  }
}

/* Card top row */
.card-top {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 14px;
}

.card-icon {
  width: 40px;
  height: 40px;
  border-radius: 10px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 17px;
  color: white;
  flex-shrink: 0;
  box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
}

.card-meta {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 8px 12px;
  flex: 1;
  min-width: 0;
}

.project-title {
  font-size: 1.05rem;
  font-weight: 700;
  color: var(--text-primary);
  line-height: 1.2;
  white-space: nowrap;
}

.project-links {
  display: flex;
  gap: 6px;
}

.link-btn {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 3px 10px;
  border-radius: 16px;
  font-size: 0.72rem;
  font-weight: 600;
  text-decoration: none;
  transition: opacity 0.2s, transform 0.2s;

  &:hover { opacity: 0.82; transform: translateY(-1px); }
}

.github-btn {
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(255, 255, 255, 0.13);
  color: var(--text-secondary);
}

.live-btn {
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.28);
  color: var(--primary-light);
}

.soon-btn {
  background: rgba(245, 158, 11, 0.08);
  border: 1px solid rgba(245, 158, 11, 0.25);
  color: #F59E0B;
  cursor: default;
  opacity: 0.85;
}

/* Bullets */
.project-bullets {
  list-style: none;
  padding: 0;
  margin: 0 0 14px 0;
  display: flex;
  flex-direction: column;
  gap: 8px;

  li {
    position: relative;
    padding-left: 16px;
    font-size: 0.82rem;
    line-height: 1.6;
    color: var(--text-secondary);

    &::before {
      content: '▸';
      position: absolute;
      left: 0;
      color: var(--primary);
      font-size: 0.68rem;
      top: 3px;
    }
  }
}

/* Tech chips */
.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
}

.tech-chip {
  background: rgba(99, 102, 241, 0.07);
  border: 1px solid rgba(99, 102, 241, 0.2);
  color: var(--primary-light);
  padding: 3px 9px;
  border-radius: 16px;
  font-size: 0.68rem;
  font-weight: 500;
  transition: background 0.2s;

  &:hover { background: rgba(99, 102, 241, 0.18); }
}

/* Dots */
.dots {
  display: flex;
  justify-content: center;
  gap: 6px;
  margin-top: 16px;
}

.dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--border-hover);
  border: none;
  cursor: pointer;
  padding: 0;
  transition: all 0.25s;

  &.active {
    width: 20px;
    border-radius: 3px;
    background: var(--primary);
  }
}

/* ── Responsive ── */
@media (max-width: 640px) {
  .page-title { font-size: 1.6rem; }
  .projects-hero { padding: 20px 0 16px; }

  /* Stack cards vertically on mobile — no carousel sliding */
  .carousel-track-wrap { overflow: visible; }

  .carousel-track {
    flex-direction: column;
    transform: none !important;
    gap: 16px;
  }

  .project-card {
    min-width: 100%;
    max-width: 100%;
    padding: 18px;
  }

  .dots { display: none; }
  .carousel-controls { display: none; }
  .counter { display: none; }
}
</style>
