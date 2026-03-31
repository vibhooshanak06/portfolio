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
              backed by hands-on experience from internships and real-world projects. I've built
              applications, worked on practical problems, and understood how to turn ideas into
              functional solutions.
            </p>
            <p class="page-description">
              Through my projects and experience, I've developed a strong interest in full-stack
              development and enjoy working across both frontend and backend. I focus on writing
              clean code, building user-friendly interfaces, and creating efficient systems.
            </p>
          </div>
          <div class="hero-right fade-in-right">
            <div class="experience-visual">
              <i class="fas fa-briefcase"></i>
            </div>
          </div>
        </div>
      </section>

      <!-- Work Experience Timeline -->
      <section class="work-experience section">
        <h2 class="section-title fade-in-up">Work Experience</h2>
        <div class="timeline">
          <div class="timeline-line"></div>
          <div class="timeline-item fade-in-up" v-for="(job, index) in workExperiences" :key="index">
            <div class="timeline-dot">
              <i :class="job.icon"></i>
            </div>
            <div class="timeline-card">
              <div class="card-header">
                <div class="card-logo">
                  <i :class="job.icon"></i>
                </div>
                <div class="card-title-group">
                  <h3 class="job-title">{{ job.title }}</h3>
                  <h4 class="company-name">
                    <i class="fas fa-building"></i> {{ job.company }}
                  </h4>
                  <span class="job-type-badge">{{ job.type }}</span>
                  <span class="location-chip"><i class="fas fa-map-marker-alt"></i> {{ job.location }}</span>
                </div>
                <div class="timeline-date">
                  <i class="fas fa-calendar-alt"></i> {{ job.period }}
                </div>
              </div>
              <ul class="responsibilities">
                <li v-for="item in job.responsibilities" :key="item">
                  <span class="bullet"><i class="fas fa-chevron-right"></i></span>{{ item }}
                </li>
              </ul>
              <div class="tech-stack">
                <span v-for="tech in job.technologies" :key="tech" class="tech-tag">{{ tech }}</span>
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
            <div class="education-icon"><i :class="edu.icon"></i></div>
            <div class="education-content">
              <h3 class="degree-title">{{ edu.degree }}</h3>
              <h4 class="institution-name">{{ edu.institution }}</h4>
              <div class="edu-chips">
                <span class="edu-period-chip"><i class="fas fa-clock"></i> {{ edu.period }}</span>
                <span class="location-chip"><i class="fas fa-map-marker-alt"></i> {{ edu.location }}</span>
              </div>
              <p class="education-description">{{ edu.description }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- Achievements -->
      <section class="certifications section">
        <h2 class="section-title fade-in-up">Achievements</h2>
        <div class="certifications-grid">
          <div class="certification-card fade-in-up" v-for="cert in certifications" :key="cert.id">
            <div class="cert-glow"></div>
            <div class="cert-icon"><i :class="cert.icon"></i></div>
            <div class="cert-content">
              <div class="cert-top-row">
                <h3 class="cert-title">{{ cert.title }}</h3>
                <div class="cert-badge"><i class="fas fa-certificate"></i></div>
              </div>
              <p class="cert-issuer"><i class="fas fa-building"></i> {{ cert.issuer }}</p>
              <div class="cert-footer">
                <span class="cert-date-chip"><i class="fas fa-calendar-alt"></i> {{ cert.date }}</span>
                <span class="cert-verified"><i class="fas fa-check-circle"></i> Verified</span>
              </div>
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
      workExperiences: [
        {
          title: "Software Development Engineer Intern",
          company: "Yuma Energy",
          location: "Bengaluru, Karnataka",
          period: "June 2025 - Dec 2025",
          type: "Internship",
          icon: "fas fa-laptop-code",
          responsibilities: [
            "Developed and improved features for web applications",
            "Worked on frontend and backend integration",
            "Collaborated with team members to deliver project tasks",
            "Gained hands-on experience in real-world development workflows"
          ],
          technologies: ["React", "Vue", "MySQL", "Node.js", "NestJs", "MongoDB"]
        },
        {
          title: "Director of Club Service",
          company: "Rotaract Club of Coimbatore Institute of Technology",
          location: "Coimbatore, Tamilnadu",
          period: "Jan 2024 - June 2025",
          type: "Director",
          icon: "fas fa-users",
          responsibilities: [
            "Organized events and initiatives to strengthen connections within the club",
            "Fostered community engagement and encouraged active member participation",
            "Led service projects that created a positive impact on the local community",
            "Coordinated with team leads to ensure smooth execution of club activities"
          ],
          technologies: ["Adobe Photoshop", "Teamwork", "Adaptability", "Organization Skills", "Communication"]
        }
      ],
      education: [
        {
          id: 1,
          degree: 'M.Sc Software Systems (Integrated)',
          institution: 'Coimbatore Institute of Technology',
          location: 'Coimbatore, Tamilnadu',
          period: '2022 - Present',
          icon: 'fas fa-graduation-cap',
          description: 'Focused on software development, problem-solving, and building real-world applications.'
        },
        {
          id: 2,
          degree: 'Higher Secondary Education',
          institution: 'Little Flower Convent Matriculation Higher Secondary School',
          location: 'Tirupur, Tamilnadu',
          period: 'Completed',
          icon: 'fas fa-school',
          description: 'Built a strong academic foundation and developed interest in technology.'
        }
      ],
      certifications: [
        { id: 1, title: 'Code Forge Series Winner', issuer: 'SDC CIT', date: '2025', icon: 'fas fa-trophy' },
        { id: 2, title: 'CODEVORTEX Hackathon Recognition', issuer: 'CIT Computing Association', date: '2025', icon: 'fas fa-medal' }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.experience { padding-top: 80px; }

/* ── Hero ── */
.experience-hero {
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

.experience-visual {
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

/* ── Section Title ── */
.section-title {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--text-primary);
  text-align: center;
  margin-bottom: 44px;
  position: relative;

  &::after {
    content: '';
    display: block;
    width: 50px;
    height: 3px;
    background: var(--gradient-primary);
    border-radius: 2px;
    margin: 10px auto 0;
  }
}

/* ── Timeline ── */
.timeline {
  position: relative;
  max-width: 640px;
  margin: 0 auto;
  padding-bottom: 16px;
}

.timeline-line {
  position: absolute;
  left: 50%;
  top: 0;
  bottom: 0;
  width: 2px;
  transform: translateX(-50%);
  background: linear-gradient(to bottom, transparent, var(--primary) 8%, #8B5CF6 50%, var(--accent) 92%, transparent);
  border-radius: 2px;

  &::after {
    content: '';
    position: absolute;
    inset: 0;
    background: inherit;
    filter: blur(5px);
    opacity: 0.45;
  }
}

.timeline-item {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 14px;
}

.timeline-dot {
  position: relative;
  z-index: 2;
  width: 38px;
  height: 38px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  color: white;
  margin-bottom: 8px;
  animation: pulse-glow 2.5s ease-in-out infinite;
}

@keyframes pulse-glow {
  0%, 100% { box-shadow: 0 0 0 4px rgba(99, 102, 241, 0.18), 0 0 14px rgba(99, 102, 241, 0.4); }
  50%       { box-shadow: 0 0 0 6px rgba(99, 102, 241, 0.12), 0 0 24px rgba(99, 102, 241, 0.55); }
}

.timeline-date {
  margin-left: auto;
  display: inline-flex;
  align-items: center;
  gap: 5px;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.25);
  color: var(--primary-light);
  font-size: 0.7rem;
  font-weight: 600;
  padding: 4px 10px;
  border-radius: 20px;
  white-space: nowrap;
  flex-shrink: 0;
  align-self: flex-start;
}

.timeline-card {
  width: 100%;
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 14px;
  padding: 16px 18px;
  position: relative;
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;

  &::before {
    content: '';
    position: absolute;
    top: -8px;
    left: 50%;
    transform: translateX(-50%);
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    border-bottom: 8px solid var(--border-color);
  }

  &::after {
    content: '';
    position: absolute;
    top: -6px;
    left: 50%;
    transform: translateX(-50%);
    border-left: 7px solid transparent;
    border-right: 7px solid transparent;
    border-bottom: 7px solid var(--bg-card);
  }

  &:hover {
    transform: translateY(-4px);
    border-color: rgba(99, 102, 241, 0.35);
    box-shadow: 0 12px 32px rgba(99, 102, 241, 0.15);
  }
}

.card-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 12px;
}

.card-logo {
  width: 40px;
  height: 40px;
  border-radius: 10px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  color: white;
  flex-shrink: 0;
  box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
}

.card-title-group { flex: 1; }

.job-title {
  font-size: 0.95rem;
  font-weight: 700;
  color: var(--text-primary);
  margin-bottom: 3px;
  line-height: 1.3;
}

.company-name {
  font-size: 0.82rem;
  color: var(--primary-light);
  font-weight: 500;
  margin-bottom: 5px;
  display: flex;
  align-items: center;
  gap: 5px;
}

.job-type-badge {
  display: inline-block;
  background: rgba(16, 185, 129, 0.1);
  border: 1px solid rgba(16, 185, 129, 0.25);
  color: var(--accent-light);
  font-size: 0.65rem;
  font-weight: 600;
  padding: 2px 8px;
  border-radius: 20px;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  margin-right: 6px;
}

.location-chip {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  background: rgba(239, 68, 68, 0.1);
  border: 1px solid rgba(239, 68, 68, 0.3);
  color: #F87171;
  font-size: 0.65rem;
  font-weight: 600;
  padding: 2px 8px;
  border-radius: 20px;
}

.responsibilities {
  list-style: none;
  margin-bottom: 10px;

  li {
    display: flex;
    align-items: flex-start;
    gap: 7px;
    color: var(--text-secondary);
    font-size: 0.8rem;
    line-height: 1.5;
    margin-bottom: 4px;
    padding: 5px 8px;
    border-radius: 7px;
    transition: background 0.2s;

    &:hover { background: rgba(99, 102, 241, 0.05); }
  }
}

.bullet {
  color: var(--primary-light);
  font-size: 0.6rem;
  margin-top: 4px;
  flex-shrink: 0;
}

.tech-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
}

.tech-tag {
  background: rgba(99, 102, 241, 0.08);
  border: 1px solid rgba(99, 102, 241, 0.2);
  color: var(--primary-light);
  padding: 3px 10px;
  border-radius: 20px;
  font-size: 0.72rem;
  font-weight: 500;
  transition: background 0.2s;

  &:hover { background: rgba(99, 102, 241, 0.18); }
}

/* ── Education ── */
.education {
  background: var(--bg-secondary);
  border-radius: 16px;
  padding: 40px 32px;
}

.education-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.education-card {
  background: var(--bg-card);
  border-radius: 16px;
  padding: 20px 22px;
  border: 1px solid var(--border-color);
  display: flex;
  align-items: flex-start;
  gap: 16px;
  position: relative;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;

  &::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--primary), #8B5CF6, var(--accent));
    border-radius: 16px 16px 0 0;
  }

  &::after {
    content: '';
    position: absolute;
    top: -30px; right: -30px;
    width: 120px; height: 120px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.12), transparent 70%);
    border-radius: 50%;
    opacity: 0;
    transition: opacity 0.4s ease;
    pointer-events: none;
  }

  &:hover {
    transform: translateY(-5px);
    border-color: rgba(99, 102, 241, 0.4);
    box-shadow: 0 16px 40px rgba(99, 102, 241, 0.18);

    &::after { opacity: 1; }
    .education-icon { transform: scale(1.08); }
  }
}

.education-icon {
  width: 52px;
  height: 52px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  color: white;
  flex-shrink: 0;
  box-shadow: 0 6px 16px rgba(99, 102, 241, 0.35);
  transition: transform 0.3s ease;
}

.degree-title { font-size: 1rem; font-weight: 600; color: var(--text-primary); margin-bottom: 4px; }
.institution-name { color: var(--primary-light); font-weight: 500; font-size: 0.875rem; margin-bottom: 8px; }

.edu-chips {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 10px;
}

.edu-period-chip {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  background: rgba(16, 185, 129, 0.1);
  border: 1px solid rgba(16, 185, 129, 0.25);
  color: var(--accent-light);
  font-size: 0.65rem;
  font-weight: 600;
  padding: 2px 8px;
  border-radius: 20px;
}

.education-description { color: var(--text-secondary); font-size: 0.85rem; line-height: 1.55; }

/* ── Achievements ── */
.certifications-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 20px;
}

.certification-card {
  background: var(--bg-card);
  border-radius: 16px;
  padding: 20px 22px;
  border: 1px solid var(--border-color);
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  gap: 16px;
  position: relative;
  overflow: hidden;
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

    .cert-glow { opacity: 1; }
    .cert-icon { transform: scale(1.08); }
  }
}

.cert-glow {
  position: absolute;
  top: -30px; right: -30px;
  width: 120px; height: 120px;
  background: radial-gradient(circle, rgba(99, 102, 241, 0.15), transparent 70%);
  border-radius: 50%;
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.cert-icon {
  width: 48px;
  height: 48px;
  background: linear-gradient(135deg, var(--primary), #8B5CF6);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  color: white;
  flex-shrink: 0;
  box-shadow: 0 6px 16px rgba(99, 102, 241, 0.35);
  transition: transform 0.3s ease;
}

.cert-badge {
  font-size: 22px;
  background: linear-gradient(135deg, #F59E0B, #FBBF24);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 6px rgba(245, 158, 11, 0.4));
}

.cert-content { flex: 1; }

.cert-top-row {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 8px;
  margin-bottom: 6px;
}

.cert-title {
  font-size: 0.95rem;
  font-weight: 700;
  color: var(--text-primary);
  line-height: 1.35;
}

.cert-issuer {
  color: var(--text-secondary);
  font-size: 0.8rem;
  display: flex;
  align-items: center;
  gap: 5px;
  margin-bottom: 10px;
}

.cert-footer {
  display: flex;
  align-items: center;
  gap: 8px;
}

.cert-date-chip {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.25);
  color: var(--primary-light);
  font-size: 0.68rem;
  font-weight: 600;
  padding: 3px 10px;
  border-radius: 20px;
}

.cert-verified {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  background: rgba(16, 185, 129, 0.1);
  border: 1px solid rgba(16, 185, 129, 0.25);
  color: var(--accent-light);
  font-size: 0.68rem;
  font-weight: 600;
  padding: 3px 10px;
  border-radius: 20px;
}

/* ── Responsive ── */
@media (max-width: 968px) {
  .hero-grid { grid-template-columns: 1fr; gap: 30px; text-align: center; }
  .experience-visual { width: 90px; height: 90px; font-size: 34px; margin: 0 auto; }
  .timeline-line { left: 20px; transform: none; }
  .timeline-item { align-items: flex-start; padding-left: 56px; }
  .timeline-dot { position: absolute; left: 0; top: 0; margin-bottom: 0; }
  .timeline-card { &::before, &::after { left: 20px; transform: none; } }
  .education-grid { grid-template-columns: 1fr; }
  .education-card { flex-direction: column; }
  .education-icon { margin: 0 auto; }
  .education { padding: 30px 18px; }
}

@media (max-width: 640px) {
  .page-title { font-size: 1.8rem; }
  .timeline-card { padding: 14px; }
  .card-header { gap: 10px; }
  .section-title { font-size: 1.5rem; }
}
</style>
