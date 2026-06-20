<template>
  <div class="skills">
    <div class="container">

      <!-- Hero Section -->
      <section class="skills-hero section">
        <div class="hero-grid">

          <!-- Left: Description -->
          <div class="hero-left">
            <h1 class="page-title">Skills & Technologies</h1>
            <p class="page-description">
              I'm a full-stack developer with hands-on experience in modern web
              technologies — from crafting responsive UIs to building scalable
              backend services and managing databases.
            </p>
            <p class="page-description">
              I'm passionate about continuous learning and staying current with
              evolving industry trends, blending strong technical skills with
              creative problem-solving to deliver meaningful digital experiences.
            </p>
          </div>

          <!-- Right: Orbital Animation -->
          <div class="hero-right">
            <div class="orbital-container">
              <div class="orbital-center">
                <div class="center-icon">
                  <i class="fas fa-code"></i>
                </div>
                <div class="pulse-ring"></div>
                <div class="pulse-ring pulse-ring-2"></div>
              </div>

              <div
                class="orbital-item"
                v-for="(tool, index) in orbitalTools"
                :key="tool.name"
                :style="{
                  '--orbit-angle': `${(-180 / orbitalTools.length) * index}deg`,
                  '--item-index': index,
                }"
              >
                <div class="orbital-icon">
                  <i :class="tool.icon"></i>
                </div>
                <div class="orbital-tooltip">{{ tool.name }}</div>
              </div>
            </div>
          </div>

        </div>
      </section>

      <!-- Tech Stack — flat tag list -->
      <section class="tech-stack section">
        <div class="section-header">
          <h2 class="section-title">Tech Stack</h2>
          <p class="section-subtitle">Technologies I work with</p>
        </div>

        <div class="stack-groups">
          <div class="stack-group" v-for="group in techStack" :key="group.label">
            <span class="group-label">{{ group.label }}</span>
            <div class="tag-list">
              <span class="tech-tag" v-for="item in group.items" :key="item">
                {{ item }}
              </span>
            </div>
          </div>
        </div>
      </section>

    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      orbitalTools: [
        { name: "Vue.js",      icon: "fab fa-vuejs" },
        { name: "React",       icon: "fab fa-react" },
        { name: "Node.js",     icon: "fab fa-node-js" },
        { name: "Python",      icon: "fab fa-python" },
        { name: "MongoDB",     icon: "fas fa-database" },
        { name: "Docker",      icon: "fab fa-docker" },
        { name: "Git",         icon: "fab fa-git-alt" },
        { name: "JavaScript",  icon: "fab fa-js-square" },
        { name: "C++",         icon: "fas fa-code" },
        { name: "MySQL",       icon: "fas fa-database" },
        { name: "Postman",     icon: "fas fa-paper-plane" },
        { name: "Jenkins",     icon: "fas fa-cogs" },
      ],
      techStack: [
        {
          label: "Programming Languages",
          items: ["C++", "Python", "JavaScript"],
        },
        {
          label: "Frameworks",
          items: ["React.js", "Vue.js", "Node.js", "Express.js", "NestJS", "FastAPI"],
        },
        {
          label: "Databases",
          items: ["MySQL", "MongoDB"],
        },
        {
          label: "Tools",
          items: ["Git & Github", "Docker", "Jenkins", "Postman", "VS Code","Kiro - AI AGENT"],
        },
        {
          label: "Soft Skills",
          items: ["Leadership", "Team Collaboration", "Adaptability",],
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
.skills {
  padding-top: 20px;
}

/* ── Hero ── */
.skills-hero {
  min-height: 20vh;
  display: flex;
  align-items: center;
  padding: 20px 0 40px;
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
  font-size: clamp(2.2rem, 4vw, 3rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 20px;
  line-height: 1.15;
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.page-description {
  font-size: 1rem;
  line-height: 1.65;
  color: var(--text-secondary);
  margin-bottom: 14px;
}

/* ── Orbital ── */
.hero-right {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeInRight 0.8s ease-out;
}

.orbital-container {
  position: relative;
  width: 500px;
  height: 500px;
}

.orbital-center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120px;
  height: 120px;
  background: var(--gradient-primary);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 0 40px rgba(99, 102, 241, 0.4);
  z-index: 10;
  animation: float 3s ease-in-out infinite;
}

.center-icon {
  font-size: 40px;
  color: white;
}

.pulse-ring {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120px;
  height: 120px;
  border: 2px solid var(--primary);
  border-radius: 50%;
  animation: pulse 2s ease-out infinite;
  opacity: 0;
}
.pulse-ring-2 { animation-delay: 1s; }

.orbital-item {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 70px;
  height: 70px;
  margin: -35px 0 0 -35px;
  transform-origin: 35px 35px;
  animation: orbit 20s linear infinite;
  animation-delay: calc(var(--item-index) * -1.67s);
}

.orbital-icon {
  width: 70px;
  height: 70px;
  background: var(--bg-card);
  border: 2px solid var(--border-color);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
  color: var(--primary);
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  animation: counterRotate 20s linear infinite;
  animation-delay: calc(var(--item-index) * -1.67s);

  &:hover {
    background: var(--gradient-primary);
    border-color: var(--primary);
    color: white;
    transform: scale(1.2);
    box-shadow: 0 8px 24px rgba(99, 102, 241, 0.4);

    & + .orbital-tooltip {
      opacity: 1;
      visibility: visible;
      transform: translateX(-50%) translateY(-10px);
    }
  }
}

.orbital-tooltip {
  position: absolute;
  bottom: -40px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  padding: 6px 14px;
  border-radius: 8px;
  font-size: 0.8125rem;
  font-weight: 500;
  color: var(--text-primary);
  white-space: nowrap;
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
  pointer-events: none;
  z-index: 100;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

/* ── Tech Stack ── */
.tech-stack {
  padding: 60px 0 80px;
}

.section-header {
  text-align: center;
  margin-bottom: 44px;
}

.section-title {
  font-size: 2rem;
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 8px;
  background: var(--gradient-primary);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-subtitle {
  font-size: 1rem;
  color: var(--text-tertiary);
}

.stack-groups {
  display: flex;
  flex-direction: column;
  gap: 28px;
  max-width: 860px;
  margin: 0 auto;
}

.stack-group {
  display: flex;
  align-items: flex-start;
  gap: 20px;
}

.group-label {
  min-width: 190px;
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--text-tertiary);
  text-transform: uppercase;
  letter-spacing: 0.06em;
  padding-top: 7px;
  flex-shrink: 0;
}

.tag-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.tech-tag {
  padding: 6px 16px;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 20px;
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-secondary);
  transition: all 0.25s ease;
  cursor: default;

  &:hover {
    background: var(--primary);
    border-color: var(--primary);
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
  }
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
  0%, 100% { transform: translate(-50%, -50%) translateY(0); }
  50%       { transform: translate(-50%, -50%) translateY(-10px); }
}
@keyframes pulse {
  0%   { transform: translate(-50%, -50%) scale(1);   opacity: 0.8; }
  100% { transform: translate(-50%, -50%) scale(1.5); opacity: 0; }
}
@keyframes orbit {
  from { transform: rotate(0deg)   translateX(215px); }
  to   { transform: rotate(360deg) translateX(215px); }
}
@keyframes counterRotate {
  from { transform: rotate(0deg); }
  to   { transform: rotate(-360deg); }
}

/* ── Responsive ── */
@media (max-width: 1024px) {
  .hero-grid { gap: 50px; }
  .orbital-container { width: 420px; height: 420px; }

  @keyframes orbit {
    from { transform: rotate(0deg)   translateX(180px); }
    to   { transform: rotate(360deg) translateX(180px); }
  }
}

@media (max-width: 768px) {
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }

  .stack-group {
    flex-direction: column;
    gap: 10px;
  }

  .group-label {
    min-width: unset;
    padding-top: 0;
  }
}

@media (max-width: 640px) {
  .orbital-container {
    width: 100%;
    max-width: 320px;
    height: 320px;
  }
  .orbital-center { width: 90px; height: 90px; }
  .center-icon { font-size: 32px; }
  .orbital-item { width: 56px; height: 56px; margin: -28px 0 0 -28px; }
  .orbital-icon { width: 56px; height: 56px; font-size: 20px; }

  @keyframes orbit {
    from { transform: rotate(0deg)   translateX(130px); }
    to   { transform: rotate(360deg) translateX(130px); }
  }
}
</style>
