<template>
  <section class="skills-section">
    <div class="container">
      <h2 class="section-title">Tecnologias</h2>
      
      <div class="skills-grid">
        <div class="skill-item python">
          <div class="skill-logo">
            <i class="fab fa-python"></i>
          </div>
          <span>Python</span>
        </div>
        
        <div class="skill-item linux">
          <div class="skill-logo">
            <i class="fab fa-linux"></i>
          </div>
          <span>Linux</span>
        </div>
        
        <div class="skill-item grafana">
          <div class="skill-logo">
            <i class="fas fa-chart-line"></i>
          </div>
          <span>Grafana</span>
        </div>
        
        <div class="skill-item zabbix">
          <div class="skill-logo">
            <i class="fas fa-server"></i>
          </div>
          <span>Zabbix</span>
        </div>
        
        <div class="skill-item powerbi">
          <div class="skill-logo">
            <i class="fas fa-chart-bar"></i>
          </div>
          <span>Power BI</span>
        </div>
        
        <div class="skill-item kotlin">
          <div class="skill-logo">
            <i class="fab fa-android"></i>
          </div>
          <span>Kotlin Multiplatform</span>
        </div>
        
        <div class="skill-item php">
          <div class="skill-logo">
            <i class="fab fa-php"></i>
          </div>
          <span>PHP</span>
        </div>
        
        <div class="skill-item laravel">
          <div class="skill-logo">
            <i class="fab fa-laravel"></i>
          </div>
          <span>Laravel</span>
        </div>
        
        <div class="skill-item javascript">
          <div class="skill-logo">
            <i class="fab fa-js"></i>
          </div>
          <span>JavaScript</span>
        </div>
        
        <div class="skill-item mysql">
          <div class="skill-logo">
            <i class="fas fa-database"></i>
          </div>
          <span>MySQL</span>
        </div>
        
        <div class="skill-item vuejs">
          <div class="skill-logo">
            <i class="fab fa-vuejs"></i>
          </div>
          <span>Vue.js</span>
        </div>
        
        <div class="skill-item react">
          <div class="skill-logo">
            <i class="fab fa-react"></i>
          </div>
          <span>React</span>
        </div>
        
        <div class="skill-item jquery">
          <div class="skill-logo">
            <i class="fab fa-js"></i>
          </div>
          <span>jQuery</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SkillsTest'
}
</script>

<style scoped>
.skills-section {
  padding: 4rem 0;
  background: var(--bg-light);
  color: var(--text-light);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}



.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1.5rem;
  max-width: 1000px;
  margin: 0 auto;
}

.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.8rem;
  padding: 1.5rem 1rem;
  background: var(--card-bg-light);
  border-radius: 15px;
  border: 2px solid var(--border-light);
  box-shadow: 0 5px 15px var(--shadow-light);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.skill-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  transition: left 0.6s ease;
}

.skill-item:hover::before {
  left: 100%;
}

.skill-item:hover {
  transform: translateY(-8px) scale(1.05);
  box-shadow: 0 12px 30px var(--shadow-light);
  border-color: currentColor;
}

.skill-logo {
  width: 45px;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 12px;
  transition: all 0.4s ease;
  position: relative;
}

.skill-logo i {
  font-size: 1.8rem;
  transition: all 0.4s ease;
  z-index: 2;
}

.skill-item:hover .skill-logo {
  transform: rotate(360deg) scale(1.2);
}

.skill-item:hover .skill-logo i {
  animation: bounce 0.6s ease;
}

.skill-item span {
  font-size: 0.95rem;
  font-weight: 600;
  text-align: center;
  color: var(--text-light);
  transition: all 0.3s ease;
}

.skill-item:hover span {
  transform: scale(1.1);
  font-weight: 700;
}

/* Cores específicas para cada tecnologia */
.skill-item.python {
  color: #3776ab;
}

.skill-item.python .skill-logo {
  background: #3776ab;
}

.skill-item.python .skill-logo i {
  color: #ffde57;
}

.skill-item.linux {
  color: #000000;
}

.skill-item.linux .skill-logo {
  background: #000000;
}

.skill-item.linux .skill-logo i {
  color: #fcc624;
}

.skill-item.grafana {
  color: #f46800;
}

.skill-item.grafana .skill-logo {
  background: #f46800;
}

.skill-item.grafana .skill-logo i {
  color: #ffffff;
}

.skill-item.zabbix {
  color: #d40000;
}

.skill-item.zabbix .skill-logo {
  background: #d40000;
}

.skill-item.zabbix .skill-logo i {
  color: #ffffff;
}

.skill-item.powerbi {
  color: #f2c811;
}

.skill-item.powerbi .skill-logo {
  background: #f2c811;
}

.skill-item.powerbi .skill-logo i {
  color: #000000;
}

.skill-item.kotlin {
  color: #7f52ff;
}

.skill-item.kotlin .skill-logo {
  background: #7f52ff;
}

.skill-item.kotlin .skill-logo i {
  color: #ffffff;
}

.skill-item.php {
  color: #777bb4;
}

.skill-item.php .skill-logo {
  background: #777bb4;
}

.skill-item.php .skill-logo i {
  color: #ffffff;
}

.skill-item.laravel {
  color: #ff2d20;
}

.skill-item.laravel .skill-logo {
  background: #ff2d20;
}

.skill-item.laravel .skill-logo i {
  color: #ffffff;
}

.skill-item.javascript {
  color: #f7df1e;
}

.skill-item.javascript .skill-logo {
  background: #f7df1e;
}

.skill-item.javascript .skill-logo i {
  color: #000000;
}

.skill-item.mysql {
  color: #4479a1;
}

.skill-item.mysql .skill-logo {
  background: #4479a1;
}

.skill-item.mysql .skill-logo i {
  color: #ffffff;
}

.skill-item.vuejs {
  color: #4fc08d;
}

.skill-item.vuejs .skill-logo {
  background: #4fc08d;
}

.skill-item.vuejs .skill-logo i {
  color: #ffffff;
}

.skill-item.react {
  color: #61dafb;
}

.skill-item.react .skill-logo {
  background: #61dafb;
}

.skill-item.react .skill-logo i {
  color: #000000;
}

.skill-item.jquery {
  color: #0769ad;
}

.skill-item.jquery .skill-logo {
  background: #0769ad;
}

.skill-item.jquery .skill-logo i {
  color: #ffffff;
}

/* Animação de bounce */
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

/* Responsive */
@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 1rem;
  }
  
  .skill-item {
    padding: 1.2rem 0.8rem;
  }
  
  .skill-logo {
    width: 40px;
    height: 40px;
  }
  
  .skill-logo i {
    font-size: 1.5rem;
  }
  
  .skill-item span {
    font-size: 0.85rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
}

@media (max-width: 480px) {
  .skills-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
