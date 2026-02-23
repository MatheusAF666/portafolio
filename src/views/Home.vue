<template>
  <div class="portfolio">
    <!-- Navigation -->
    <nav class="navbar">
      <div class="nav-container">
        <a href="#" class="nav-logo">{{ portfolioData.profile.name.split(' ')[0] }}</a>
        <ul class="nav-menu">
          <li><a href="#about" class="nav-link">Sobre Mí</a></li>
          <li><a href="#skills" class="nav-link">Habilidades</a></li>
          <li><a href="#projects" class="nav-link">Proyectos</a></li>
          <li><a href="#education" class="nav-link">Formación</a></li>
          <li><a href="#contact" class="nav-link">Contacto</a></li>
        </ul>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-container">
        <div class="hero-content">
          <div class="hero-avatar">
            <img :src="portfolioData.profile.avatar" :alt="portfolioData.profile.name" />
          </div>
          <div class="hero-text">
            <h1 class="hero-title">{{ portfolioData.profile.name }}</h1>
            <p class="hero-role">{{ portfolioData.profile.role }}</p>
            <p class="hero-tagline">{{ portfolioData.profile.tagline }}</p>
            <div class="hero-ctas">
              <a href="#projects" class="btn btn-primary">Ver Proyectos</a>
              <a href="#contact" class="btn btn-secondary">Contacto</a>
            </div>
            <div class="hero-stats">
              <div v-for="stat in portfolioData.stats" :key="stat.label" class="stat">
                <div class="stat-number">{{ stat.number }}</div>
                <div class="stat-label">{{ stat.label }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about">
      <div class="section-container">
        <h2 class="section-title">Sobre Mí</h2>
        <div class="about-content">
          <div class="about-text">
            <h3 class="about-subtitle">{{ portfolioData.profile.tagline }}</h3>
            <p>{{ portfolioData.profile.bio }}</p>
            <p>{{ portfolioData.profile.bio2 }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section skills">
      <div class="section-container">
        <h2 class="section-title">Habilidades Técnicas</h2>
        <div class="skills-grid">
          <div v-for="skill in portfolioData.skills" :key="skill.name" class="skill-item">
            <div class="skill-icon"><i :class="skill.iconClass"></i></div>
            <div class="skill-info">
              <h4 class="skill-name">{{ skill.name }}</h4>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section projects">
      <div class="section-container">
        <h2 class="section-title">Proyectos Destacados</h2>
        <div class="projects-list">
          <article
            v-for="project in portfolioData.projects"
            :key="project.id"
            class="project-card"
            :style="{ backgroundImage: 'linear-gradient(135deg, rgba(255, 255, 255, 0.6) 0%, rgba(249, 250, 251, 0.55) 100%), url(' + project.image + ')' }"
          >
            <div class="project-content">
              <div class="project-header">
                <div class="project-title-row">
                  <h3>{{ project.title }}</h3>
                  <span v-if="project.badge" class="project-badge">{{ project.badge }}</span>
                </div>
                <span class="project-role">{{ project.role }}</span>
              </div>
              <p class="project-description">{{ project.description }}</p>
              
              <div class="project-tech">
                <span v-for="tech in project.technologies" :key="tech" class="tech-tag">
                  {{ tech }}
                </span>
              </div>

              <div class="project-metric">
                <strong>{{ project.metrics.label }}:</strong>
                {{ project.metrics.value }}
              </div>

              <div class="project-learning">
                <strong>Aprendizajes clave:</strong> {{ project.learnings }}
              </div>
              <div class="project-actions">
                <a v-if="project.demoUrl" :href="project.demoUrl" class="project-btn" target="_blank">Ver Demo</a>
                <a v-if="project.repoUrl" :href="project.repoUrl" class="project-btn" target="_blank">GitHub</a>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="section education">
      <div class="section-container">
        <h2 class="section-title">Formación</h2>
        <div class="education-content">
          <div v-for="edu in portfolioData.education" :key="edu.title" class="education-card">
            <div class="edu-logo-container">
              <div class="edu-logo-text">ILERNA</div>
            </div>
            <h3 class="edu-title">{{ edu.title }}</h3>
            <p class="edu-institution">{{ edu.institution }}</p>
            <span class="edu-year">{{ edu.year }}</span>
            <a v-if="edu.certificateUrl" :href="edu.certificateUrl" class="cert-link" target="_blank">
              Ver Certificado →
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section contact">
      <div class="section-container">
        <h2 class="section-title">Contacto</h2>
        <p class="contact-subtitle">Contáctame por teléfono, email o GitHub.</p>
        
        <div class="contact-content">
          <div class="contact-methods">
            <a :href="`mailto:${portfolioData.contact.email}`" class="contact-link">
              <span class="contact-icon">✉</span>
              <span>{{ portfolioData.contact.email }}</span>
            </a>
            <a :href="`tel:${portfolioData.contact.phone}`" class="contact-link">
              <span class="contact-icon phone-icon">📞</span>
              <span>{{ portfolioData.contact.phone }}</span>
            </a>
            <a :href="portfolioData.contact.github" target="_blank" class="contact-link">
              <i class="devicon-github-original contact-icon" aria-hidden="true"></i>
              <span>GitHub</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2024 {{ portfolioData.profile.name }}. Desarrollado con Vue.js.</p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import portfolio from '../data/portfolio.json'

const portfolioData = ref(portfolio)
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --primary: #0f172a;
  --secondary: #64748b;
  --accent: #0ea5e9;
  --accent-light: #e0f2fe;
  --background: #f8fafc;
  --border: #e2e8f0;
  --text: #1e293b;
  --text-light: #64748b;
  --white: #ffffff;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  color: var(--text);
  background: var(--white);
  line-height: 1.6;
}

.portfolio {
  overflow-x: hidden;
  position: relative;
  background: linear-gradient(135deg, #0b1220 0%, #0f172a 55%, #101c2e 100%);
}

.portfolio::before {
  content: '';
  position: fixed;
  inset: 0;
  background:
    radial-gradient(700px 260px at 20% 5%, rgba(14, 165, 233, 0.22) 0%, transparent 60%),
    radial-gradient(520px 240px at 85% 15%, rgba(56, 189, 248, 0.16) 0%, transparent 60%),
    linear-gradient(180deg, rgba(255, 255, 255, 0.04) 0%, rgba(255, 255, 255, 0) 60%);
  pointer-events: none;
  z-index: 0;
}

/* Navigation */
.navbar {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--border);
  padding: 1rem 0;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-logo {
  font-size: 1.3rem;
  font-weight: 800;
  color: #0f172a;
  text-decoration: none;
  transition: all 0.3s ease;
}

.nav-logo:hover {
  color: #0ea5e9;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 0;
}

.nav-menu li {
  position: relative;
}

.nav-link {
  display: block;
  padding: 0.75rem 1.25rem;
  text-decoration: none;
  color: #1e293b;
  font-weight: 500;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  position: relative;
  background: transparent;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0.5rem;
  left: 1.25rem;
  right: 1.25rem;
  height: 2px;
  background: #0ea5e9;
  transform: scaleX(0);
  transform-origin: right;
  transition: transform 0.3s ease;
}

.nav-link:hover {
  color: #0ea5e9;
}

.nav-link:hover::after {
  transform: scaleX(1);
  transform-origin: left;
}

/* Hero Section */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 2rem;
  background: transparent;
}

.hero-container {
  max-width: 1200px;
  width: 100%;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-avatar {
  display: flex;
  justify-content: center;
}

.hero-avatar img {
  width: 320px;
  height: 320px;
  border-radius: 50%;
  border: 4px solid var(--white);
  box-shadow: 0 14px 32px rgba(14, 165, 233, 0.2);
  object-fit: cover;
}

.hero-text h1 {
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 0.5rem;
  color: var(--white);
}

.hero-role {
  font-size: 1.5rem;
  color: #38bdf8;
  font-weight: 600;
  margin-bottom: 1rem;
}

.hero-tagline {
  font-size: 1.2rem;
  color: rgba(255, 255, 255, 0.8);
  margin-bottom: 2rem;
  max-width: 600px;
  line-height: 1.6;
}

.hero-ctas {
  display: flex;
  gap: 1.5rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.btn {
  padding: 0.8rem 1.6rem;
  border-radius: 0.75rem;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.95rem;
  cursor: pointer;
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  display: inline-block;
  text-align: center;
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #0ea5e9 0%, #0b63a5 100%);
  color: var(--white);
  box-shadow: 0 6px 16px rgba(14, 165, 233, 0.28);
}

.btn-primary {
  background: linear-gradient(135deg, #0ea5e9 0%, #0b63a5 100%);
  color: var(--white);
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 6px 16px rgba(14, 165, 233, 0.28);
}

.btn-primary:hover {
  box-shadow: 0 8px 20px rgba(14, 165, 233, 0.35);
  transform: translateY(-2px);
}

.btn-secondary {
  background: linear-gradient(135deg, #0ea5e9 0%, #0b63a5 100%);
  color: var(--white);
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 6px 16px rgba(14, 165, 233, 0.28);
}

.btn-secondary:hover {
  box-shadow: 0 8px 20px rgba(14, 165, 233, 0.35);
  transform: translateY(-2px);
}

.hero-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.stat {
  text-align: left;
}

.stat-number {
  font-size: 2rem;
  font-weight: 800;
  color: #38bdf8;
  display: block;
}

.stat-label {
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.7);
  margin-top: 0.5rem;
}

/* Sections */
.section {
  padding: 6rem 2rem;
}

.section-container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 1;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 800;
  margin-bottom: 3rem;
  text-align: center;
  color: var(--primary);
  position: relative;
  padding-bottom: 1rem;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 4px;
  background: var(--accent);
  border-radius: 2px;
}

/* About Section */
.about {
  background: transparent;
}

.about .section-title {
  color: var(--white);
}

.about .section-title::after {
  background: var(--accent);
}

.about-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  align-items: start;
  max-width: 900px;
  margin: 0 auto;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.98) 0%, #f8fafc 100%);
  border-radius: 1rem;
  border: 1px solid rgba(226, 232, 240, 0.85);
  padding: 2.5rem;
}

.about-text p {
  font-size: 1.1rem;
  line-height: 1.8;
  margin-bottom: 1.5rem;
  color: #0f172a;
}

.about-subtitle {
  font-size: 1.3rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.about-values h3 {
  font-size: 1.3rem;
  margin-bottom: 1.5rem;
  color: #0f172a;
}

.values-list {
  list-style: none;
}

.values-list li {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
  font-size: 1.05rem;
  color: #475569;
  transition: all 0.3s ease;
}

.values-list li:hover {
  transform: translateX(8px);
  color: #0f172a;
}

.checkmark {
  color: var(--accent);
  font-weight: 800;
  font-size: 1.2rem;
}

/* Skills Section */
.skills {
  background: transparent;
}

.skills .section-title {
  color: var(--white);
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem;
  padding: 1.5rem 1.25rem;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.98) 0%, #f8fafc 100%);
  border-radius: 1rem;
  border: 1px solid rgba(226, 232, 240, 0.85);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  text-align: center;
  position: relative;
  overflow: hidden;
  color: #0f172a;
}

.skill-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--accent), #06b6d4);
}

.skill-item:hover {
  border-color: var(--accent);
  transform: translateY(-4px);
}

.skill-icon {
  font-size: 2.5rem;
  min-width: auto;
  text-align: center;
  color: var(--accent);
  transition: transform 0.3s ease;
}

.skill-item:hover .skill-icon {
  transform: scale(1.08);
}

.skill-info {
  flex: 1;
  width: 100%;
}

.skill-name {
  font-size: 1.1rem;
  font-weight: 700;
  color: #0f172a;
}

/* Projects Section */
.projects {
  background: transparent;
}

.projects .section-title {
  color: var(--white);
}

.projects-list {
  display: grid;
  gap: 4rem;
}

.project-card {
  display: grid;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  border: 1px solid rgba(255, 255, 255, 0.35);
  grid-template-columns: 1fr;
  box-shadow: 0 8px 22px rgba(239, 68, 68, 0.35);
  background: linear-gradient(135deg, var(--white) 0%, #f9fafb 100%);
  background-size: cover;
  background-position: center;
  box-shadow: 0 12px 30px rgba(245, 158, 11, 0.5);
  transform: translateY(-2px) scale(1.02);
  border-radius: 1.2rem;
  overflow: hidden;
  border: 1px solid #f0f1f3;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.project-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: rgba(15, 23, 42, 0.85);
  z-index: 0;
}


.project-btn {
  padding: 0.8rem 1.6rem;
  background: linear-gradient(135deg, #0ea5e9 0%, #0b63a5 100%);
  color: var(--white);
  text-decoration: none;
  border-radius: 0.75rem;
  font-weight: 600;
  font-size: 0.95rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: 0 6px 16px rgba(14, 165, 233, 0.28);
}

.project-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-top: 1.5rem;
}

.project-btn:hover {
  box-shadow: 0 8px 20px rgba(14, 165, 233, 0.35);
  transform: translateY(-2px);
}

.project-content {
  padding: 2.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;
  z-index: 1;
}

.project-header h3 {
  font-size: 1.6rem;
  font-weight: 700;
  color: var(--primary);
  margin-bottom: 0.75rem;
  transition: color 0.3s ease;
}

.project-title-row {
  display: flex;
  align-items: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.project-badge {
  display: inline-block;
  background: linear-gradient(135deg, #f97316 0%, #ea580c 100%);
  color: white;
  padding: 0.35rem 1rem;
  border-radius: 2rem;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  border: 1px solid #ea580c;
}

.project-card:hover .project-header h3 {
  color: var(--accent);
}

.project-role {
  display: inline-block;
  background: linear-gradient(135deg, var(--accent-light) 0%, #cffafe 100%);
  color: var(--accent);
  padding: 0.35rem 1rem;
  border-radius: 2rem;
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 1rem;
  border: 1px solid var(--accent);
}

.project-description {
  color: var(--text-light);
  margin-bottom: 1.5rem;
  line-height: 1.7;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-bottom: 1.5rem;
}

.tech-tag {
  background: linear-gradient(135deg, var(--primary) 0%, #1a254f 100%);
  color: var(--white);
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  font-size: 0.85rem;
  font-weight: 500;
  transition: all 0.3s ease;
}

.tech-tag:hover {
  box-shadow: 0 4px 12px rgba(15, 23, 42, 0.3);
  transform: translateY(-2px);
}

.project-metric {
  padding: 1.25rem;
  background: linear-gradient(135deg, var(--accent-light) 0%, #cffafe 100%);
  border-left: 4px solid var(--accent);
  border-radius: 0.5rem;
  margin-bottom: 1rem;
  font-size: 0.95rem;
  color: var(--primary);
  font-weight: 500;
}

.project-learning {
  font-size: 0.95rem;
  color: var(--text-light);
  line-height: 1.6;
}

/* Education Section */
.education {
  background: transparent;
}

.education .section-title {
  color: var(--white);
}

.education .section-title::after {
  background: var(--accent);
}

.education-content {
  max-width: 900px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 2rem;
}

.education-card {
  padding: 2.5rem;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.98) 0%, #f8fafc 100%);
  border-radius: 1rem;
  border: 1px solid rgba(226, 232, 240, 0.85);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  text-align: center;
  position: relative;
  overflow: hidden;
  color: #0f172a;
}

.education-card > * {
  position: relative;
  z-index: 1;
}

.education-card::before {
  content: '';
  position: absolute;
  top: 1.25rem;
  bottom: 1.25rem;
  left: 1.25rem;
  width: 4px;
  border-radius: 999px;
  background: linear-gradient(180deg, var(--accent) 0%, #38bdf8 100%);
  opacity: 0.9;
}

.education-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background:
    radial-gradient(160px 120px at 20% 10%, rgba(14, 165, 233, 0.12) 0%, transparent 60%),
    radial-gradient(180px 140px at 85% 0%, rgba(15, 23, 42, 0.08) 0%, transparent 60%);
  pointer-events: none;
  z-index: 0;
}


.edu-logo-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
  position: relative;
  z-index: 1;
}

.edu-logo-text {
  width: 90px;
  height: 90px;
  background: linear-gradient(135deg, var(--accent) 0%, #0284c7 100%);
  border-radius: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--white);
  font-weight: 800;
  font-size: 0.95rem;
  text-align: center;
  transition: all 0.3s ease;
}


.edu-title {
  font-size: 1.4rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 0.75rem;
  line-height: 1.5;
}

.edu-institution {
  color: #475569;
  font-weight: 600;
  font-size: 1rem;
  margin-bottom: 0.75rem;
  display: block;
}

.edu-year {
  display: inline-block;
  background: #0ea5e9;
  color: var(--white);
  padding: 0.4rem 1rem;
  border-radius: 2rem;
  font-size: 0.9rem;
  font-weight: 600;
  margin-bottom: 1.25rem;
}

.cert-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: #0ea5e9;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  margin-top: 0.75rem;
  font-size: 0.95rem;
  padding: 0.6rem 1.2rem;
  border: 1px solid #0ea5e9;
  border-radius: 0.5rem;
}




/* Contact Section */
.contact {
  background: transparent;
  text-align: center;
}

.contact .section-title {
  color: var(--white);
}

.contact .section-title::after {
  background: linear-gradient(90deg, var(--accent), #06b6d4);
}

.contact-subtitle {
  font-size: 1.15rem;
  color: rgba(255, 255, 255, 0.85);
  margin-bottom: 3.5rem;
  text-align: center;
  font-weight: 500;
}

.contact-methods {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  max-width: 900px;
  margin: 0 auto;
  gap: 2rem;
}

.contact-link {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem 1.5rem;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.98) 0%, #f8fafc 100%);
  border: 1px solid rgba(226, 232, 240, 0.85);
  border-radius: 1rem;
  text-decoration: none;
  color: #0f172a;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.contact-link::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(14, 165, 233, 0.25), rgba(56, 189, 248, 0.25));
  opacity: 0;
  transition: opacity 0.3s ease;
  z-index: -1;
}

.contact-link:hover {
  border-color: var(--accent);
  transform: translateY(-4px);
}

.contact-link:hover::before {
  opacity: 0.35;
}

.contact-icon {
  font-size: 2rem;
  color: var(--accent);
  transition: transform 0.3s ease;
}

.phone-icon {
  color: #000000 !important;
  filter: saturate(0);
}

.contact-link:hover .contact-icon {
  transform: scale(1.2) rotate(10deg);
}

/* Footer */
.footer {
  background: var(--primary);
  color: var(--white);
  text-align: center;
  padding: 2rem;
  font-size: 0.9rem;
}

/* Responsive */
@media (max-width: 1024px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }

  .hero-text {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .hero-ctas {
    justify-content: center;
  }

  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .project-card {
    grid-template-columns: 1fr;
  }

  .project-card:nth-child(even) {
    grid-template-columns: 1fr;
  }


}

@media (max-width: 768px) {
  .nav-menu {
    display: none;
  }

  .hero-text h1 {
    font-size: 2.5rem;
  }

  .hero-role {
    font-size: 1.2rem;
  }

  .hero-ctas {
    flex-direction: column;
    width: 100%;
  }

  .btn {
    width: 100%;
  }

  .hero-stats {
    grid-template-columns: 1fr;
    gap: 1rem;
  }

  .section {
    padding: 4rem 1.5rem;
  }

  .section-title {
    font-size: 2rem;
  }

  .project-card {
    gap: 1.5rem;
  }

  .project-card {
    min-height: 300px;
  }
}

@media (max-width: 480px) {
  .hero-avatar img {
    width: 180px;
    height: 180px;
  }

  .hero-text h1 {
    font-size: 1.8rem;
  }

  .hero-role {
    font-size: 1rem;
  }

  .hero-ctas {
    flex-direction: column;
  }

  .btn {
    width: 100%;
  }

  .section {
    padding: 3rem 1rem;
  }

  .section-title {
    font-size: 1.5rem;
  }

  .skills-grid {
    grid-template-columns: 1fr;
  }

  .project-card {
    gap: 1rem;
  }

  .project-content {
    padding: 1.5rem;
  }

  .education-card {
    padding: 2rem;
  }

  .edu-logo-text {
    width: 80px;
    height: 80px;
    font-size: 0.9rem;
  }

  .contact-methods {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .contact-link {
    padding: 1.5rem 1rem;
  }
}
</style>
