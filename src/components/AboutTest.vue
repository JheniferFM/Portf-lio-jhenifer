<template>
  <section id="about" class="about-section">
    <div class="container">
      <h2 class="section-title">Sobre Mim</h2>
      
      <div class="about-content">
        <div class="about-main">
          <div class="about-text">
            <h3>Jhenifer Meneses</h3>
            <p class="lead-text">
              Desenvolvedora Full Stack apaixonada por tecnologia e inovação, especializada em criar soluções digitais que fazem a diferença.
            </p>
            <p class="description">
              Com experiência sólida em desenvolvimento web, trabalho com as tecnologias mais modernas do mercado, 
              incluindo <strong>Vue.js</strong>, <strong>Laravel</strong>, <strong>JavaScript</strong> e <strong>Python</strong>. 
              Meu foco está em desenvolver aplicações robustas, escaláveis e com excelente experiência do usuário.
            </p>
            <p class="description">
              Além do desenvolvimento, tenho expertise em <strong>monitoramento e observabilidade</strong> com 
              <strong>Grafana</strong> e <strong>Zabbix</strong>, garantindo que as aplicações sejam não apenas 
              funcionais, mas também monitoradas e otimizadas para o melhor desempenho.
            </p>
            
            <div class="cv-buttons">
              <a href="/curriculo.pdf" target="_blank" class="cv-btn cv-view">
                <span class="cv-icon">👁️</span>
                <span>Visualizar CV</span>
              </a>
              <a href="/curriculo.pdf" download class="cv-btn cv-download">
                <span class="cv-icon">📥</span>
                <span>Baixar CV</span>
              </a>
            </div>
          </div>
          
          <div class="about-stats">
            <div class="stat-card">
              <div class="stat-icon">🚀</div>
              <div class="stat-number">2+</div>
              <div class="stat-label">Anos de Experiência</div>
            </div>
          </div>
        </div>
        
        <div class="about-skills">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 4rem 2rem;
  background: linear-gradient(135deg, var(--bg-light) 0%, var(--secondary) 100%);
  position: relative;
  overflow: hidden;
}

.about-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23e91e63' fill-opacity='0.03'%3E%3Ccircle cx='30' cy='30' r='4'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  pointer-events: none;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 1;
}

.about-content {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.about-main {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 3rem;
  align-items: start;
}

.about-text h3 {
  font-size: 2.5rem;
  font-weight: 800;
  color: var(--primary);
  margin-bottom: 1rem;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  position: relative;
}

.about-text h3::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  border-radius: 2px;
}

.lead-text {
  font-size: 1.3rem;
  color: var(--text-light);
  font-weight: 600;
  margin-bottom: 1.5rem;
  line-height: 1.6;
  position: relative;
  padding-left: 20px;
}

.lead-text::before {
  content: '✨';
  position: absolute;
  left: -10px;
  top: 0;
  font-size: 1.2rem;
}

.description {
  font-size: 1.1rem;
  color: var(--text-light);
  line-height: 1.7;
  margin-bottom: 1rem;
  position: relative;
  padding-left: 20px;
}

.description::before {
  content: '→';
  position: absolute;
  left: 0;
  top: 0;
  color: var(--primary);
  font-weight: bold;
}

.description strong {
  color: var(--primary);
  font-weight: 700;
  position: relative;
}

.description strong::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--secondary), transparent);
  border-radius: 1px;
}

.cv-buttons {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
  flex-wrap: wrap;
}

.cv-btn {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.8rem 1.5rem;
  border-radius: 25px;
  text-decoration: none;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  border: 2px solid transparent;
}

.cv-btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s ease;
}

.cv-btn:hover::before {
  left: 100%;
}

.cv-view {
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  box-shadow: 0 4px 15px var(--shadow-light);
}

.cv-view:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px var(--shadow-light);
}

.cv-download {
  background: transparent;
  color: var(--primary);
  border-color: var(--primary);
  box-shadow: 0 4px 15px rgba(233, 30, 99, 0.1);
}

.cv-download:hover {
  background: var(--primary);
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 8px 25px var(--shadow-light);
}

.cv-icon {
  font-size: 1.2rem;
}

.about-stats {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.stat-card {
  background: var(--card-bg-light);
  padding: 2rem;
  border-radius: 20px;
  text-align: center;
  border: 2px solid var(--border-light);
  box-shadow: 0 8px 30px var(--shadow-light);
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.stat-card::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(45deg, transparent, rgba(233, 30, 99, 0.1), transparent);
  transform: rotate(45deg);
  transition: all 0.6s ease;
  opacity: 0;
}

.stat-card:hover::before {
  opacity: 1;
  transform: rotate(45deg) translate(50%, 50%);
}

.stat-card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 15px 40px var(--shadow-light);
  border-color: var(--accent);
}

.stat-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-10px);
  }
  60% {
    transform: translateY(-5px);
  }
}

.stat-number {
  font-size: 3rem;
  font-weight: 900;
  color: var(--primary);
  margin-bottom: 0.5rem;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.stat-label {
  font-size: 1rem;
  color: var(--text-light);
  font-weight: 600;
}

.about-skills h4 {
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--primary);
  margin-bottom: 2rem;
  text-align: center;
  position: relative;
}

.about-skills h4::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 3px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  border-radius: 2px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.skill-category {
  background: var(--card-bg-light);
  padding: 2.5rem;
  border-radius: 20px;
  border: 2px solid var(--border-light);
  box-shadow: 0 8px 30px var(--shadow-light);
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.skill-category::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
}

.skill-category:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 40px var(--shadow-light);
  border-color: var(--accent);
}

.skill-category h5 {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--primary);
  margin-bottom: 2rem;
  text-align: center;
  position: relative;
}

.skill-category h5::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 2px;
  background: var(--accent);
  border-radius: 1px;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}

.skill-tag {
  background: linear-gradient(135deg, var(--secondary), var(--accent));
  color: white;
  padding: 0.6rem 1.2rem;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 600;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.skill-tag::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  transition: left 0.5s ease;
}

.skill-tag:hover::before {
  left: 100%;
}

.skill-tag:hover {
  transform: scale(1.05) translateY(-2px);
  box-shadow: 0 6px 20px var(--shadow-light);
}

/* Modo escuro */
.dark-mode .about-section {
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
}

.dark-mode .stat-card,
.dark-mode .skill-category {
  background: var(--card-bg-dark);
  border-color: var(--border-dark);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
}

.dark-mode .stat-card:hover,
.dark-mode .skill-category:hover {
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
}

.dark-mode .cv-download {
  border-color: var(--primary);
  color: var(--primary);
}

.dark-mode .cv-download:hover {
  background: var(--primary);
  color: white;
}

/* Responsividade */
@media (max-width: 768px) {
  .about-section {
    padding: 3rem 1rem;
  }
  
  .about-main {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .about-text h3 {
    font-size: 2rem;
  }
  
  .lead-text {
    font-size: 1.1rem;
  }
  
  .description {
    font-size: 1rem;
  }
  
  .cv-buttons {
    flex-direction: column;
    gap: 0.8rem;
  }
  
  .cv-btn {
    justify-content: center;
    padding: 1rem 1.5rem;
  }
  
  .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .stat-card,
  .skill-category {
    padding: 2rem;
  }
  
  .stat-icon {
    font-size: 2.5rem;
  }
  
  .stat-number {
    font-size: 2.5rem;
  }
}
</style>
