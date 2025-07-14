<template>
  <section id="contact" class="contact-section">
    <div class="container">
      <div class="contact-header">
        <h2 class="section-title">Vamos Conversar?</h2>
        <p class="contact-subtitle">
          Estou sempre aberta a novas oportunidades e colaborações. 
          Entre em contato e vamos criar algo incrível juntos! 🚀
        </p>
      </div>
      
      <div class="contact-grid">
        <div class="contact-card email-card">
          <div class="card-header">
            <div class="icon-wrapper">
              <i class="fas fa-envelope"></i>
            </div>
            <h3>Email</h3>
          </div>
          <div class="card-content">
            <p class="contact-value">jhenifer.meneses@email.com</p>
            <p class="contact-description">Envie um email direto para mim</p>
          </div>
          <a href="mailto:jhenifer.meneses@email.com" class="contact-action">
            <i class="fas fa-paper-plane"></i>
            Enviar Email
          </a>
        </div>

        <div class="contact-card whatsapp-card">
          <div class="card-header">
            <div class="icon-wrapper">
              <i class="fab fa-whatsapp"></i>
            </div>
            <h3>WhatsApp</h3>
          </div>
          <div class="card-content">
            <p class="contact-value">+55 (11) 99999-9999</p>
            <p class="contact-description">Conversa rápida e direta</p>
          </div>
          <a href="https://wa.me/5511999999999" target="_blank" class="contact-action">
            <i class="fab fa-whatsapp"></i>
            Enviar Mensagem
          </a>
        </div>

        <div class="contact-card linkedin-card">
          <div class="card-header">
            <div class="icon-wrapper">
              <i class="fab fa-linkedin"></i>
            </div>
            <h3>LinkedIn</h3>
          </div>
          <div class="card-content">
            <p class="contact-value">jhenifer-meneses</p>
            <p class="contact-description">Conecte-se profissionalmente</p>
          </div>
                      <a href="https://linkedin.com/in/jhenifer-meneses-98293b300/" target="_blank" class="contact-action">
            <i class="fab fa-linkedin"></i>
            Ver Perfil
          </a>
        </div>

        <div class="contact-card github-card">
          <div class="card-header">
            <div class="icon-wrapper">
              <i class="fab fa-github"></i>
            </div>
            <h3>GitHub</h3>
          </div>
          <div class="card-content">
            <p class="contact-value">JheniferFM</p>
            <p class="contact-description">Veja meus projetos e contribuições</p>
          </div>
          <a href="https://github.com/JheniferFM" target="_blank" class="contact-action">
            <i class="fab fa-github"></i>
            Ver Repositórios
          </a>
        </div>
      </div>

      <div class="contact-footer">
        <div class="availability-badge">
          <i class="fas fa-circle"></i>
          <span>Disponível para novos projetos</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Componente de contato moderno e interativo
</script>

<style scoped>
.contact-section {
  padding: 5rem 2rem;
  background: linear-gradient(135deg, var(--bg-light) 0%, var(--secondary) 100%);
  position: relative;
  overflow: hidden;
}

.contact-section::before {
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

.contact-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 3.2rem;
  font-weight: 800;
  color: var(--primary);
  margin-bottom: 1.5rem;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  border-radius: 2px;
}

.contact-subtitle {
  font-size: 1.3rem;
  color: var(--text-light);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.7;
  opacity: 0.9;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
  margin-bottom: 3rem;
}

.contact-card {
  background: var(--card-bg-light);
  border-radius: 20px;
  padding: 2rem;
  border: 2px solid var(--border-light);
  box-shadow: 0 8px 32px var(--shadow-light);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.contact-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.contact-card:hover::before {
  transform: scaleX(1);
}

.contact-card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 16px 48px var(--shadow-light);
  border-color: var(--accent);
}

.card-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.icon-wrapper {
  width: 60px;
  height: 60px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.8rem;
  color: white;
  transition: all 0.3s ease;
}

.email-card .icon-wrapper {
  background: linear-gradient(135deg, #ea4335, #d93025);
}

.whatsapp-card .icon-wrapper {
  background: linear-gradient(135deg, #25d366, #128c7e);
}

.linkedin-card .icon-wrapper {
  background: linear-gradient(135deg, #0077b5, #005885);
}

.github-card .icon-wrapper {
  background: linear-gradient(135deg, #333, #24292e);
}

.contact-card:hover .icon-wrapper {
  transform: rotate(360deg) scale(1.1);
}

.card-header h3 {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--primary);
  margin: 0;
}

.card-content {
  flex: 1;
  margin-bottom: 1.5rem;
}

.contact-value {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--text-light);
  margin-bottom: 0.5rem;
  word-break: break-all;
}

.contact-description {
  font-size: 0.95rem;
  color: var(--text-light);
  opacity: 0.8;
  line-height: 1.5;
}

.contact-action {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  text-decoration: none;
  padding: 0.8rem 1.5rem;
  border-radius: 12px;
  font-weight: 600;
  font-size: 0.95rem;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px var(--shadow-light);
  margin-top: auto;
}

.contact-action:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px var(--shadow-light);
  color: white;
}

.contact-footer {
  text-align: center;
  margin-top: 3rem;
}

.availability-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: linear-gradient(135deg, #28a745, #20c997);
  color: white;
  padding: 0.8rem 1.5rem;
  border-radius: 25px;
  font-weight: 600;
  font-size: 1rem;
  box-shadow: 0 4px 15px rgba(40, 167, 69, 0.3);
}

.availability-badge i {
  font-size: 0.8rem;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}

/* Modo escuro */
.dark-mode .contact-section {
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
}

.dark-mode .contact-card {
  background: var(--card-bg-dark);
  border-color: var(--border-dark);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
}

.dark-mode .contact-card:hover {
  box-shadow: 0 16px 48px rgba(0, 0, 0, 0.4);
}

/* Responsividade */
@media (max-width: 1200px) {
  .contact-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
}

@media (max-width: 768px) {
  .contact-section {
    padding: 3rem 1rem;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .contact-subtitle {
    font-size: 1.1rem;
  }
  
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .contact-card {
    padding: 1.5rem;
  }
  
  .icon-wrapper {
    width: 50px;
    height: 50px;
    font-size: 1.5rem;
  }
  
  .card-header h3 {
    font-size: 1.2rem;
  }
  
  .contact-value {
    font-size: 1rem;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: 2rem;
  }
  
  .contact-subtitle {
    font-size: 1rem;
  }
  
  .contact-card {
    padding: 1.2rem;
  }
  
  .card-header {
    flex-direction: column;
    text-align: center;
    gap: 0.8rem;
  }
  
  .contact-action {
    padding: 0.7rem 1.2rem;
    font-size: 0.9rem;
  }
}
</style>
