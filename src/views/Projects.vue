<template>
  <div class="projects">
    <div class="container">

      <!-- Hero -->
      <section class="projects-hero section">
        <div class="hero-grid">
          <div class="hero-left fade-in-left">
            <h1 class="page-title">My Projects</h1>
            <p class="page-description">
              A curated collection of projects that showcase my technical skills
              and problem-solving abilities across full-stack development and AI.
            </p>
            <p class="page-description">
              Each project represents a unique challenge — from AI-powered fraud
              detection to full-scale insurance platforms.
            </p>
          </div>
          <div class="hero-right fade-in-right">
            <div class="projects-visual">
              <i class="fas fa-rocket"></i>
            </div>
          </div>
        </div>
      </section>

      <!-- Projects -->
      <section class="projects-grid-section section">
        <div class="projects-list">
          <div
            class="project-card fade-in-up"
            v-for="project in projects"
            :key="project.id"
          >
            <!-- Top bar -->
            <div class="card-top">
              <div class="card-icon">
                <i :class="project.icon"></i>
              </div>
              <div class="card-meta">
                <h3 class="project-title">{{ project.title }}</h3>
                <div class="project-links">
                  <a
                    v-if="project.github"
                    :href="project.github"
                    target="_blank"
                    class="link-btn github-btn"
                  >
                    <i class="fab fa-github"></i> GitHub
                  </a>
                  <a
                    v-if="project.live"
                    :href="project.live"
                    target="_blank"
                    class="link-btn live-btn"
                  >
                    <i class="fas fa-external-link-alt"></i> Live
                  </a>
                </div>
              </div>
            </div>

            <!-- Bullets -->
            <ul class="project-bullets">
              <li v-for="(point, i) in project.bullets" :key="i">{{ point }}</li>
            </ul>

            <!-- Tech stack -->
            <div class="project-tech">
              <span
                v-for="tech in project.technologies"
                :key="tech"
                class="tech-chip"
              >{{ tech }}</span>
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
          title: 'Fraud Lens',
          icon: 'fas fa-search',
          github: 'https://github.com/vibhooshana',
          live: '',
          technologies: ['React', 'Node.js', 'Express', 'Python', 'FastAPI', 'MySQL', 'MongoDB', 'FAISS', 'Docker'],
          bullets: [
            'Built a full-stack AI platform that detects plagiarism and research fraud via TF-IDF cosine similarity, sentence-transformers, and LLM-based summarization through OpenRouter API, delivering end-to-end document analysis with actionable integrity reports.',
            'Engineered a RAG-based conversational chatbot leveraging FAISS vector search to semantically retrieve relevant paper chunks and generate grounded, context-aware responses — containerized the full system using Docker for consistent cross-environment deployment.'
          ]
        },
        {
          id: 2,
          title: 'Livi Shield',
          icon: 'fas fa-shield-alt',
          github: 'https://github.com/vibhooshana',
          live: '',
          technologies: ['MongoDB', 'Express.js', 'React.js', 'Node.js'],
          bullets: [
            'Engineered a full-stack car and health insurance platform supporting 20+ policy types, enabling end-to-end digital policy management including purchase, renewal, and claims submission workflows.',
            'Designed and implemented a streamlined claims processing pipeline with real-time status tracking and policy dashboard, reducing claims handling complexity and improving user experience across the insurance lifecycle.'
          ]
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.projects { padding-top: 20px; }

/* ── Hero ── */
.projects-hero {
  min-height: 20vh;
  display: flex;
  align-items: center;
  padding: 20px 0 40px;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
  align-items: center;
}

.hero-left { animation: fadeInLeft 0.8s ease-out; }

.page-title {
  font-size: clamp(2.2rem, 4vw, 3rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 14px;
  line-height: 1.1;
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.page-description {
  font-size: 1rem;
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

/* ── Projects List ── */
.projects-list {
  display: flex;
  flex-direction: column;
  gap: 28px;
  padding-bottom: 80px;
}

/* ── Card ── */
.project-card {
  background: var(--bg-card);
  border-radius: 18px;
  border: 1px solid var(--border-color);
  padding: 28px 32px;
  position: relative;
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;

  &::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--primary), #8B5CF6, var(--accent));
    border-radius: 18px 18px 0 0;
  }

  &:hover {
    transform: translateY(-4px);
    border-color: rgba(99, 102, 241, 0.4);
    box-shadow: 0 16px 40px rgba(99, 102, 241, 0.15);
  }
}

/* Top row: icon + title + links */
.card-top {
  display: flex;
  align-items: flex-start;
  gap: 16px;
  margin-bottom: 20px;
}

.card-icon {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  color: white;
  flex-shrink: 0;
  box-shadow: 0 4px 14px rgba(99, 102, 241, 0.35);
}

.card-meta {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 10px 16px;
  flex: 1;
}

.project-title {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--text-primary);
  line-height: 1.2;
}

/* Link buttons */
.project-links {
  display: flex;
  gap: 8px;
}

.link-btn {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  padding: 4px 14px;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 600;
  text-decoration: none;
  transition: opacity 0.2s, transform 0.2s;

  &:hover { opacity: 0.85; transform: translateY(-1px); }
}

.github-btn {
  background: rgba(255, 255, 255, 0.07);
  border: 1px solid rgba(255, 255, 255, 0.15);
  color: var(--text-secondary);
}

.live-btn {
  background: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.3);
  color: var(--primary-light);
}

/* Bullet points */
.project-bullets {
  list-style: none;
  padding: 0;
  margin: 0 0 20px 0;
  display: flex;
  flex-direction: column;
  gap: 10px;

  li {
    position: relative;
    padding-left: 18px;
    font-size: 0.9rem;
    line-height: 1.65;
    color: var(--text-secondary);

    &::before {
      content: '▸';
      position: absolute;
      left: 0;
      color: var(--primary);
      font-size: 0.75rem;
      top: 3px;
    }
  }
}

/* Tech chips */
.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 7px;
}

.tech-chip {
  background: rgba(99, 102, 241, 0.08);
  border: 1px solid rgba(99, 102, 241, 0.22);
  color: var(--primary-light);
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 500;
  transition: background 0.2s;

  &:hover { background: rgba(99, 102, 241, 0.2); }
}

/* ── Animations ── */
@keyframes fadeInLeft {
  from { opacity: 0; transform: translateX(-40px); }
  to   { opacity: 1; transform: translateX(0); }
}
@keyframes fadeInRight {
  from { opacity: 0; transform: translateX(40px); }
  to   { opacity: 1; transform: translateX(0); }
}
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-10px); }
}

/* ── Responsive ── */
@media (max-width: 968px) {
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 30px;
    text-align: center;
  }
  .projects-visual {
    width: 90px;
    height: 90px;
    font-size: 34px;
    margin: 0 auto;
  }
}

@media (max-width: 640px) {
  .project-card { padding: 20px; }
  .page-title { font-size: 1.8rem; }
  .card-meta { flex-direction: column; gap: 8px; }
}
</style>
