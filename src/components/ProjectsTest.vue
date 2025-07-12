<template>
  <section id="projects" class="projects-section">
    <h2 class="section-title">Projetos</h2>
    
    <!-- Projetos Pessoais -->
    <div class="projects-category">
      <p class="category-description">Projetos desenvolvidos demonstrando criatividade e habilidades técnicas.</p>
      <div class="projects">
        <div class="project-card" v-for="project in personalProjects" :key="project.id">
          <div class="project-header">
            <h4>{{ project.name }}</h4>
            <span class="project-type">{{ project.type }}</span>
          </div>
          <p class="project-description">{{ project.description }}</p>
          <div class="tech-stack">
            <span class="tech-tag" v-for="tech in project.technologies" :key="tech">{{ tech }}</span>
          </div>
          <div class="project-links">
            <a :href="project.github" target="_blank" class="project-link">
              <i class="fab fa-github"></i> Ver no GitHub
            </a>
            <a v-if="project.live" :href="project.live" target="_blank" class="project-link live">
              <i class="fas fa-external-link-alt"></i> Ver ao vivo
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Projetos Profissionais -->
    <div class="projects-category">
      <p class="category-description">Projetos desenvolvidos em ambiente corporativo, focados em soluções empresariais e escalabilidade.</p>
      <div class="projects">
        <div class="project-card" v-for="project in professionalProjects" :key="project.id">
          <div class="project-header">
            <h4>{{ project.name }}</h4>
            <span class="project-type">{{ project.type }}</span>
          </div>
          <p class="project-description">{{ project.description }}</p>
          <div class="tech-stack">
            <span class="tech-tag" v-for="tech in project.technologies" :key="tech">{{ tech }}</span>
          </div>
          <div class="project-links" v-if="project.github || project.live">
            <a v-if="project.github" :href="project.github" target="_blank" class="project-link">
              <i class="fab fa-github"></i> Ver no GitHub
            </a>
            <a v-if="project.live" :href="project.live" target="_blank" class="project-link live">
              <i class="fas fa-external-link-alt"></i> Ver ao vivo
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      personalProjects: [
        {
          id: 1,
          name: 'Portfolio Pessoal',
          type: 'Projeto de Apresentação',
          description: 'Portfolio profissional desenvolvido com tecnologias modernas, apresentando projetos, habilidades e experiência de forma elegante e responsiva.',
          technologies: ['Vue.js', 'CSS3', 'JavaScript', 'Vite'],
          github: 'https://github.com/jheni/portfolio-jhenifer',
          live: null
        },
        {
          id: 2,
          name: 'Sistema de Gestão Escolar',
          type: 'Projeto Acadêmico',
          description: 'Solução completa para instituições educacionais, incluindo gestão de matrículas, controle de notas, frequência e comunicação integrada entre escola, alunos e responsáveis.',
          technologies: ['PHP', 'JavaScript', 'MySQL', 'CSS3'],
          github: 'https://github.com/jheni/sistema-escolar',
          live: null
        },
        {
          id: 3,
          name: 'Plataforma Educacional',
          type: 'Projeto Educacional',
          description: 'Plataforma educacional inovadora que conecta voluntários a estudantes, facilitando o acesso à educação tecnológica. Sistema completo com gestão de usuários, cursos e acompanhamento de progresso.',
          technologies: ['Vue.js', 'PHP', 'MySQL', 'Bootstrap'],
          github: 'https://github.com/jheni/programando-futuros',
          live: null
        }
      ],
      professionalProjects: [
        {
          id: 4,
          name: 'Módulo PDP - Sistema SGP',
          type: 'Sistema Corporativo',
          description: 'Desenvolvimento de módulo para o Sistema de Gestão de Pessoal (SGP), focado no planejamento de desenvolvimento pessoal. Implementação de funcionalidades para gestão de capacitações, treinamentos e evolução profissional dos colaboradores.',
          technologies: ['Laravel', 'Vue.js', 'MySQL', 'PHP'],
          github: null,
          live: null
        },
        {
          id: 5,
          name: 'Automação de Produtos Meteorológicos',
          type: 'Sistema de Monitoramento',
          description: 'Manutenção e suporte de sistema automatizado para coleta, processamento e apresentação de dados meteorológicos. Trabalho com dashboards interativos e monitoramento de dados climáticos em tempo real.',
          technologies: ['Python', 'Grafana', 'Zabbix', 'Linux'],
          github: null,
          live: null
        },
        {
          id: 6,
          name: 'Sistema de Formulários - Nebula',
          type: 'Sistema Corporativo',
          description: 'Participação em equipe no desenvolvimento de sistema de formulários para a DPDF. Trabalho colaborativo em solução para gestão de formulários de cadeia, contribuindo com desenvolvimento e manutenção do sistema.',
          technologies: ['Python', 'Linux', 'Grafana', 'Zabbix'],
          github: null,
          live: null
        }
      ]
    };
  }
};
</script>

<style scoped>
.projects-section {
  padding: 4rem 2rem;
  background: linear-gradient(135deg, var(--bg-light) 0%, var(--secondary) 50%, var(--bg-light) 100%);
}

.dark-mode .projects-section {
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 50%, #0a0a0a 100%);
}

.projects-category {
  margin-bottom: 4rem;
}

.projects-category:last-child {
  margin-bottom: 0;
}

.category-title {
  font-size: 2rem;
  font-weight: 700;
  color: var(--primary);
  text-align: center;
  margin-bottom: 1rem;
  position: relative;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.category-title::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 2px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  border-radius: 1px;
}

.category-description {
  text-align: center;
  color: var(--text-light);
  font-size: 1.1rem;
  margin-bottom: 2.5rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.6;
  opacity: 0.8;
}

.projects {
  display: grid;
  gap: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
  max-width: 1200px;
  margin: 0 auto;
}

.project-card {
  background: var(--card-bg-light);
  padding: 2rem;
  border-radius: 20px;
  transition: all 0.3s ease;
  border: 2px solid var(--border-light);
  box-shadow: 0 8px 25px var(--shadow-light);
  position: relative;
  overflow: hidden;
}

.project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 40px var(--shadow-light);
  border-color: var(--accent);
}

.project-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 1rem;
}

.project-card h4 {
  color: var(--primary);
  margin: 0;
  font-size: 1.4rem;
  font-weight: 700;
}

.project-type {
  background: linear-gradient(135deg, var(--secondary), var(--accent));
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.project-description {
  color: var(--text-light);
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 1rem;
}

.tech-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.tech-tag {
  background: linear-gradient(135deg, var(--secondary), var(--accent));
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.85rem;
  font-weight: 600;
}

.project-links {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  text-decoration: none;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px var(--shadow-light);
}

.project-link:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px var(--shadow-light);
}

.project-link.live {
  background: linear-gradient(135deg, #28a745, #20c997);
}

/* Responsividade */
@media (max-width: 768px) {
  .projects-section {
    padding: 3rem 1rem;
  }
  
  .category-title {
    font-size: 1.8rem;
  }
  
  .category-description {
    font-size: 1rem;
    margin-bottom: 2rem;
  }
  
  .projects {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .project-card {
    padding: 1.5rem;
  }
  
  .project-card h4 {
    font-size: 1.3rem;
  }
  
  .project-links {
    flex-direction: column;
  }
  
  .project-link {
    justify-content: center;
  }
}
</style>
