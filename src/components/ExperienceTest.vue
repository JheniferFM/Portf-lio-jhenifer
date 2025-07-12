<template>
  <section id="experience" class="experience-section">
    <div class="container">
      <h2 class="section-title">Experiência</h2>
      
      <div class="timeline-compact">
        <div 
          v-for="(experience, index) in experiences" 
          :key="index"
          class="timeline-item"
          :class="{ 'active': activeExperience === index }"
          @click="toggleExperience(index)"
        >
          <div class="timeline-marker">
            <div class="marker-dot">
              <div class="marker-icon">{{ experience.icon }}</div>
            </div>
          </div>
          
          <div class="timeline-content">
            <div class="experience-header">
              <div class="experience-info">
                <h3 class="experience-title">{{ experience.title }}</h3>
                <div class="experience-meta">
                  <span class="company">{{ experience.company }}</span>
                  <span class="period">{{ experience.period }}</span>
                </div>
              </div>
              <div class="expand-icon" :class="{ 'expanded': activeExperience === index }">
                <span>+</span>
              </div>
            </div>
            
            <div class="experience-summary">
              <p>{{ experience.summary }}</p>
            </div>
            
            <div class="experience-details" v-show="activeExperience === index">
              <div class="details-grid">
                <div class="achievements-section">
                  <h4>Principais Conquistas</h4>
                  <ul class="achievements-list">
                    <li v-for="achievement in experience.achievements" :key="achievement" v-html="achievement">
                    </li>
                  </ul>
                </div>
                
                <div class="tech-section">
                  <h4>Tecnologias</h4>
                  <div class="tech-tags">
                    <span 
                      v-for="tech in experience.technologies" 
                      :key="tech" 
                      class="tech-tag"
                    >
                      {{ tech }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const activeExperience = ref(null)

const experiences = ref([
  {
    icon: '💻',
    title: 'Desenvolvedora Júnior Full-Stack',
    company: 'Hospital das Forças Armadas (HFA) - Empresa Produtiva',
    period: 'Junho 2025 - Presente',
    summary: 'Desenvolvimento e manutenção de sistemas internos hospitalares terceirizados pela Empresa Produtiva, com foco em performance e escalabilidade.',
    achievements: [
      'Desenvolvimento de funcionalidades críticas para sistemas internos',
      'Implementação de melhorias de performance que reduziram o tempo de carregamento em 40%',
      'Correção de bugs e otimização de código legado',
      'Colaboração com equipe multidisciplinar em projetos ágeis'
    ],
    technologies: ['PHP', 'Laravel', 'JavaScript', 'Vue.js', 'MySQL', 'Git', 'Docker']
  },
  {
    icon: '📱',
    title: 'Estágio Full-Stack',
    company: 'Defensoria Pública do Distrito Federal (DPDF)',
    period: 'Janeiro 2025 - Junho 2025',
    summary: 'Desenvolvimento de aplicações multiplataforma com foco em inovação e qualidade para a Defensoria.',
    achievements: [
      'Desenvolvimento de aplicações multiplataforma utilizando Kotlin',
      'Implementação de funcionalidades de geolocalização e mapeamento',
      'Integração com APIs externas e serviços de terceiros',
      'Otimização de processos de deploy com Docker'
    ],
    technologies: ['Kotlin', 'Android', 'Git', 'Docker', 'REST APIs', 'SQLite']
  },
  {
    icon: '��️',
    title: 'Estágio em Desenvolvimento',
    company: 'Organização do Tratado de Cooperação Amazônica (OTCA) - 8 Países',
    period: 'Novembro 2024 - Janeiro 2025',
    summary: 'Manutenção de automações para produtos meteorológicos e análise de dados climáticos para 8 países da região amazônica: 🇧🇴 🇧🇷 🇨🇴 🇪🇨 🇬🇾 🇵🇪 🇸🇷 🇻🇪',
    achievements: [
      'Manutenção de scripts de automação para processamento de dados meteorológicos',
      'Suporte e manutenção de ferramentas de análise espacial com QGIS',
      'Manutenção de algoritmos para análise de padrões climáticos',
      'Manutenção de dashboards para visualização de dados',
      '<span class="flags-section">Trabalho com 8 países: <span class="flag">🇧🇴</span> <span class="flag">🇧🇷</span> <span class="flag">🇨🇴</span> <span class="flag">🇪🇨</span> <span class="flag">🇬🇾</span> <span class="flag">🇵🇪</span> <span class="flag">🇸🇷</span> <span class="flag">🇻🇪</span></span>'
    ],
    technologies: ['Python', 'QGIS', 'PostgreSQL', 'Pandas', 'NumPy', 'Matplotlib']
  },
  {
    icon: '📊',
    title: 'Estágio em Monitoramento',
    company: 'IGUT',
    period: 'Setembro 2024 - Novembro 2024',
    summary: 'Implementação de soluções de monitoramento e observabilidade para sistemas críticos.',
    achievements: [
      'Configuração e manutenção de dashboards de monitoramento com Grafana',
      'Implementação de alertas e notificações com Zabbix',
      'Monitoramento de performance e disponibilidade de sistemas',
      'Criação de relatórios de SLA e métricas de infraestrutura'
    ],
    technologies: ['Grafana', 'Zabbix', 'Linux', 'Shell Script', 'SQL', 'Docker']
  }
])

function toggleExperience(index) {
  if (activeExperience.value === index) {
    activeExperience.value = null
  } else {
    activeExperience.value = index
  }
}

onMounted(() => {
  activeExperience.value = null
})
</script>

<style scoped>
.experience-section {
  padding: 3rem 2rem;
  background: linear-gradient(135deg, var(--bg-light) 0%, var(--secondary) 100%);
  position: relative;
}

.container {
  max-width: 900px;
  margin: 0 auto;
  position: relative;
  z-index: 1;
}



.timeline-compact {
  position: relative;
  padding-left: 3rem;
}

.timeline-compact::before {
  content: '';
  position: absolute;
  left: 1.5rem;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(180deg, var(--primary), var(--accent));
  border-radius: 1px;
}

.timeline-item {
  position: relative;
  margin-bottom: 1.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.timeline-item:hover {
  transform: translateX(5px);
}

.timeline-marker {
  position: absolute;
  left: -3rem;
  top: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.marker-dot {
  width: 40px;
  height: 40px;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  border-radius: 50%;
  border: 3px solid var(--bg-light);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  box-shadow: 0 2px 10px rgba(233, 30, 99, 0.2);
}

.timeline-item.active .marker-dot {
  transform: scale(1.1);
  box-shadow: 0 4px 15px rgba(233, 30, 99, 0.4);
}

.marker-icon {
  font-size: 1.2rem;
  color: white;
}

.timeline-content {
  background: var(--card-bg-light);
  border-radius: 12px;
  padding: 1.5rem;
  border: 1px solid var(--border-light);
  box-shadow: 0 4px 15px var(--shadow-light);
  transition: all 0.3s ease;
}

.timeline-item:hover .timeline-content {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px var(--shadow-light);
  border-color: var(--accent);
}

.experience-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 1rem;
}

.experience-info {
  flex: 1;
}

.experience-title {
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--primary);
  margin-bottom: 0.3rem;
}

.experience-meta {
  display: flex;
  gap: 1rem;
  align-items: center;
}

.company {
  font-size: 1rem;
  font-weight: 600;
  color: var(--accent);
}

.period {
  font-size: 0.9rem;
  color: white;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  padding: 0.2rem 0.6rem;
  border-radius: 12px;
  font-weight: 600;
  box-shadow: 0 2px 8px rgba(233, 30, 99, 0.3);
}

.expand-icon {
  width: 24px;
  height: 24px;
  background: var(--secondary);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  font-weight: bold;
  color: var(--accent);
  transition: all 0.3s ease;
  cursor: pointer;
}

.expand-icon.expanded {
  transform: rotate(45deg);
  background: var(--accent);
  color: white;
}

.experience-summary {
  margin-bottom: 1rem;
}

.experience-summary p {
  color: var(--text-light);
  line-height: 1.5;
  font-size: 1rem;
  margin: 0;
}

.experience-details {
  margin-top: 1rem;
  padding-top: 1rem;
  border-top: 1px solid var(--border-light);
  animation: slideDown 0.3s ease;
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.details-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
}

.achievements-section h4,
.tech-section h4 {
  font-size: 1rem;
  font-weight: 600;
  color: var(--primary);
  margin-bottom: 0.8rem;
}

.achievements-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.achievements-list li {
  position: relative;
  padding-left: 1rem;
  margin-bottom: 0.5rem;
  color: var(--text-light);
  line-height: 1.4;
  font-size: 0.9rem;
}

.achievements-list li::before {
  content: '•';
  position: absolute;
  left: 0;
  color: var(--accent);
  font-weight: bold;
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
}

.tech-tag {
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  padding: 0.3rem 0.6rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 500;
  transition: all 0.3s ease;
}

.tech-tag:hover {
  transform: translateY(-1px);
  box-shadow: 0 2px 8px rgba(233, 30, 99, 0.3);
}

.flags-section {
  display: inline-block;
  margin-top: 0.5rem;
}

.flag {
  display: inline-block;
  font-size: 1.5rem;
  margin: 0 0.2rem;
  padding: 0.3rem;
  border-radius: 8px;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s ease;
  animation: flagWave 2s ease-in-out infinite;
}

.flag:hover {
  transform: scale(1.2) rotate(5deg);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

@keyframes flagWave {
  0%, 100% { transform: rotate(0deg); }
  50% { transform: rotate(2deg); }
}

/* Modo escuro */
.dark-mode .experience-section {
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
}

.dark-mode .timeline-content {
  background: var(--card-bg-dark);
  border-color: var(--border-dark);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
}

.dark-mode .timeline-item:hover .timeline-content {
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.4);
}

.dark-mode .marker-dot {
  border-color: var(--bg-dark);
}

/* Responsividade */
@media (max-width: 768px) {
  .experience-section {
    padding: 2rem 1rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .timeline-compact {
    padding-left: 2rem;
  }
  
  .timeline-compact::before {
    left: 1rem;
  }
  
  .timeline-marker {
    left: -2rem;
  }
  
  .timeline-content {
    padding: 1rem;
  }
  
  .experience-title {
    font-size: 1.1rem;
  }
  
  .experience-meta {
    flex-direction: column;
    gap: 0.3rem;
    align-items: flex-start;
  }
  
  .details-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .tech-tags {
    gap: 0.3rem;
  }
  
  .tech-tag {
    font-size: 0.75rem;
    padding: 0.25rem 0.5rem;
  }
}
</style> 