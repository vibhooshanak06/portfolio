<template>
  <div class="skills">
    <div class="container">
      <!-- Hero Section with Two Columns -->
      <section class="skills-hero section">
        <div class="hero-grid">
          <!-- Left: Description -->
          <div class="hero-left">
            <h1 class="page-title">Skills & Technologies</h1>
            <p class="page-description">
              I'm a full-stack developer with expertise in modern web technologies. 
              My skill set spans across frontend frameworks, backend development, 
              databases, and cloud infrastructure.
            </p>
            <p class="page-description">
              I am deeply passionate about continuous learning and staying ahead of evolving
  industry trends. By blending strong technical expertise with creative
  problem-solving, I transform ideas into meaningful, high-quality digital
  experiences that are both efficient and engaging.
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
                  '--item-index': index
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

      <!-- Compact Tech Stack - Single View -->
      <section class="tech-stack-compact section">
        <div class="section-header">
          <h2 class="section-title">Tech Stack Overview</h2>
          <p class="section-subtitle">Technologies I work with daily</p>
        </div>
        
        <div class="tech-stack-grid">
          <div 
            class="tech-stack-item" 
            v-for="category in techStack" 
            :key="category.name"
          >
            <div class="tech-header">
              <div class="tech-icon">
                <i :class="category.icon"></i>
              </div>
              <h3 class="tech-category-name">{{ category.name }}</h3>
            </div>
            <div class="tech-list">
              <span 
                class="tech-tag" 
                v-for="tech in category.items" 
                :key="tech"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </section>

      <!-- Certifications -->
      <section class="certifications section">
        <div class="section-header">
          <h2 class="section-title">Certifications</h2>
        </div>
        
        <div class="cert-grid">
          <div 
            class="cert-card" 
            v-for="cert in certifications" 
            :key="cert.name"
          >
            <div class="cert-badge">
              <i :class="cert.icon"></i>
            </div>
            <h4 class="cert-name">{{ cert.name }}</h4>
            <p class="cert-issuer">{{ cert.issuer }}</p>
            <span class="cert-year">{{ cert.year }}</span>
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
      orbitalTools: [
        { name: 'Vue.js', icon: 'fab fa-vuejs' },
        { name: 'React', icon: 'fab fa-react' },
        { name: 'Node.js', icon: 'fab fa-node-js' },
        { name: 'Python', icon: 'fab fa-python' },
        { name: 'MongoDB', icon: 'fas fa-database' },
        { name: 'Docker', icon: 'fab fa-docker' },
        { name: 'AWS', icon: 'fab fa-aws' },
        { name: 'Git', icon: 'fab fa-git-alt' },
        { name: 'Figma', icon: 'fab fa-figma' },
        { name: 'TypeScript', icon: 'fas fa-code' },
        { name: 'PostgreSQL', icon: 'fas fa-database' },
        { name: 'JavaScript', icon: 'fab fa-js-square' }
      ],
      techStack: [
        {
          name: 'Frontend',
          icon: 'fas fa-laptop-code',
          items: ['HTML5', 'CSS3', 'SCSS', 'Tailwind', 'Bootstrap', 'Material-UI', 'Ant Design', 'Responsive Design']
        },
        {
          name: 'Backend',
          icon: 'fas fa-server',
          items: ['Express.js', 'Nest.js', 'GraphQL', 'REST API', 'WebSocket', 'Microservices', 'JWT', 'OAuth']
        },
        {
          name: 'Database',
          icon: 'fas fa-database',
          items: ['MySQL', 'Redis', 'Firebase', 'Supabase', 'Prisma', 'TypeORM', 'Mongoose', 'SQL']
        },
        {
          name: 'DevOps & Tools',
          icon: 'fas fa-cloud',
          items: ['CI/CD', 'Jenkins', 'Nginx', 'PM2', 'Vercel', 'Netlify', 'GitHub Actions', 'VS Code']
        }
      ],
      certifications: [
        { name: 'AWS Certified Developer', issuer: 'Amazon Web Services', year: '2024', icon: 'fab fa-aws' },
        { name: 'Vue.js Certification', issuer: 'Vue School', year: '2023', icon: 'fab fa-vuejs' },
        { name: 'Full Stack Development', issuer: 'freeCodeCamp', year: '2023', icon: 'fas fa-certificate' },
        { name: 'JavaScript Algorithms', issuer: 'Coursera', year: '2022', icon: 'fab fa-js-square' }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.skills {
  padding-top: 100px;
}

// Hero Section with Two Columns
.skills-hero {
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

// Left Side - Description
.hero-left {
  animation: fadeInLeft 0.8s ease-out;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 20px;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  border-radius: 24px;
  font-size: 14px;
  color: var(--text-secondary);
  margin-bottom: 24px;
  
  .badge-icon {
    font-size: 16px;
  }
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

.stats-mini {
  display: flex;
  gap: 32px;
  margin-top: 40px;
  padding-top: 32px;
  border-top: 1px solid var(--border-color);
}

.stat-mini {
  .stat-number {
    font-size: 2rem;
    font-weight: 700;
    background: var(--gradient-primary);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
    margin-bottom: 8px;
  }
  
  .stat-label {
    font-size: 0.875rem;
    color: var(--text-tertiary);
    font-weight: 500;
  }
}

// Right Side - Orbital Animation
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
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0 0 40px rgba(99, 102, 241, 0.4);
  z-index: 10;
  animation: float 3s ease-in-out infinite;
}

.center-icon {
  font-size: 40px;
  color: white;
  margin-bottom: 6px;
}

.center-text {
  font-size: 0.8125rem;
  font-weight: 600;
  color: white;
  text-transform: uppercase;
  letter-spacing: 0.05em;
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

.pulse-ring-2 {
  animation-delay: 1s;
}

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

// Compact Tech Stack - Single View
.tech-stack-compact {
  padding: 80px 0;
}

.section-header {
  text-align: center;
  margin-bottom: 48px;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--text-primary);
  margin-bottom: 12px;
  letter-spacing: -0.02em;
}

.section-subtitle {
  font-size: 1.0625rem;
  color: var(--text-tertiary);
}

.tech-stack-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
  max-width: 1000px;
  margin: 0 auto;
}

.tech-stack-item {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 16px;
  padding: 24px;
  transition: all 0.3s ease;
  
  &:hover {
    transform: translateY(-4px);
    border-color: var(--border-hover);
    box-shadow: 0 12px 32px rgba(0, 0, 0, 0.2);
    
    .tech-icon {
      transform: scale(1.1);
      background: var(--gradient-primary);
      
      i {
        color: white;
      }
    }
  }
}

.tech-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 16px;
  padding-bottom: 12px;
  border-bottom: 1px solid var(--border-color);
}

.tech-icon {
  width: 44px;
  height: 44px;
  background: var(--bg-tertiary);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  flex-shrink: 0;
  
  i {
    font-size: 20px;
    color: var(--primary);
    transition: color 0.3s ease;
  }
}

.tech-category-name {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--text-primary);
}

.tech-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tech-tag {
  padding: 6px 12px;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  border-radius: 6px;
  font-size: 0.8125rem;
  color: var(--text-secondary);
  font-weight: 500;
  transition: all 0.3s ease;
  
  &:hover {
    background: var(--primary);
    border-color: var(--primary);
    color: white;
    transform: translateY(-2px);
  }
}

// Certifications
.certifications {
  background: var(--bg-secondary);
  border-radius: 32px;
  padding: 60px 40px;
  margin-bottom: 60px;
}

.cert-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 24px;
}

.cert-card {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 16px;
  padding: 28px;
  text-align: center;
  transition: all 0.3s ease;
  
  &:hover {
    transform: translateY(-6px);
    border-color: var(--accent);
    box-shadow: 0 12px 32px rgba(16, 185, 129, 0.2);
    
    .cert-badge {
      transform: scale(1.1);
      background: var(--gradient-accent);
      
      i {
        color: white;
      }
    }
  }
}

.cert-badge {
  width: 64px;
  height: 64px;
  background: var(--bg-tertiary);
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 16px;
  transition: all 0.3s ease;
  
  i {
    font-size: 28px;
    color: var(--accent);
    transition: color 0.3s ease;
  }
}

.cert-name {
  font-size: 1.0625rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 8px;
}

.cert-issuer {
  font-size: 0.875rem;
  color: var(--text-tertiary);
  margin-bottom: 12px;
}

.cert-year {
  display: inline-block;
  padding: 4px 12px;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  border-radius: 6px;
  font-size: 0.8125rem;
  color: var(--accent);
  font-weight: 600;
}

// Animations
@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-40px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(40px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes float {
  0%, 100% {
    transform: translate(-50%, -50%) translateY(0);
  }
  50% {
    transform: translate(-50%, -50%) translateY(-10px);
  }
}

@keyframes pulse {
  0% {
    transform: translate(-50%, -50%) scale(1);
    opacity: 0.8;
  }
  100% {
    transform: translate(-50%, -50%) scale(1.5);
    opacity: 0;
  }
}

@keyframes orbit {
  from {
    transform: rotate(0deg) translateX(215px);
  }
  to {
    transform: rotate(360deg) translateX(215px);
  }
}

@keyframes counterRotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(-360deg);
  }
}

// Responsive
@media (max-width: 1024px) {
  .hero-grid {
    gap: 60px;
  }
  
  .orbital-container {
    width: 450px;
    height: 450px;
  }
  
  @keyframes orbit {
    from {
      transform: rotate(0deg) translateX(190px);
    }
    to {
      transform: rotate(360deg) translateX(190px);
    }
  }
}

@media (max-width: 968px) {
  .skills {
    padding-top: 80px;
  }
  
  .skills-hero {
    min-height: auto;
  }
  
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 60px;
  }
  
  .hero-left {
    text-align: center;
  }
  
  .page-title {
    font-size: 2.5rem;
  }
  
  .page-description {
    font-size: 1rem;
  }
  
  .stats-mini {
    justify-content: center;
  }
  
  .orbital-container {
    width: 400px;
    height: 400px;
  }
  
  .tech-stack-grid {
    grid-template-columns: 1fr;
  }
  
  .certifications {
    padding: 40px 20px;
  }
  
  @keyframes orbit {
    from {
      transform: rotate(0deg) translateX(165px);
    }
    to {
      transform: rotate(360deg) translateX(165px);
    }
  }
}

@media (max-width: 640px) {
  .page-title {
    font-size: 2rem;
  }
  
  .page-description {
    font-size: 0.9375rem;
  }
  
  .orbital-container {
    width: 100%;
    max-width: 350px;
    height: 350px;
  }
  
  .orbital-center {
    width: 90px;
    height: 90px;
  }
  
  .center-icon {
    font-size: 32px;
  }
  
  .center-text {
    font-size: 0.75rem;
  }
  
  .orbital-item {
    width: 56px;
    height: 56px;
    margin: -28px 0 0 -28px;
  }
  
  .orbital-icon {
    width: 56px;
    height: 56px;
    font-size: 22px;
  }
  
  .stats-mini {
    flex-direction: column;
    gap: 20px;
  }
  
  .section-title {
    font-size: 1.75rem;
  }
  
  .tech-stack-item {
    padding: 20px;
  }
  
  .tech-category-name {
    font-size: 1rem;
  }
  
  .tech-tag {
    font-size: 0.75rem;
    padding: 5px 10px;
  }
  
  .cert-grid {
    grid-template-columns: 1fr;
  }
  
  .cert-card {
    padding: 24px;
  }
  
  @keyframes orbit {
    from {
      transform: rotate(0deg) translateX(147px);
    }
    to {
      transform: rotate(360deg) translateX(147px);
    }
  }
}
</style>
