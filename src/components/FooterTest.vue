<!-- src/components/FooterTest.vue -->
<template>
  <footer class="footer">
    <div class="footer-waves">
      <div class="wave wave-1"></div>
      <div class="wave wave-2"></div>
      <div class="wave wave-3"></div>
    </div>
    
    <div class="container">

      
      <div class="footer-bottom">
        <div class="footer-line"></div>
        <div class="copyright">
          <p>&copy; 2025 Jhenifer Meneses</p>
          <div class="heart-beat">
            <span>Feito com</span>
            <i class="fas fa-heart"></i>
            <span>e muito código</span>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterTest'
}
</script>

<style scoped>
.footer {
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 50%, #0a0a0a 100%);
  position: relative;
  overflow: hidden;
  padding: 1.5rem 2rem 1rem;
  color: white;
}

.footer-waves {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100px;
  overflow: hidden;
}

.wave {
  position: absolute;
  top: 0;
  left: 0;
  width: 200%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(233, 30, 99, 0.1), transparent);
  animation: wave 6s linear infinite;
}

.wave-1 {
  animation-delay: 0s;
  opacity: 0.3;
}

.wave-2 {
  animation-delay: 2s;
  opacity: 0.2;
}

.wave-3 {
  animation-delay: 4s;
  opacity: 0.1;
}

@keyframes wave {
  0% { transform: translateX(-50%); }
  100% { transform: translateX(50%); }
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
}

.footer-content {
  display: flex;
  justify-content: center;
  margin-bottom: 1.5rem;
}

.footer-section {
  text-align: center;
}

.logo-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.logo-circle {
  width: 45px;
  height: 45px;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 8px 25px rgba(233, 30, 99, 0.3);
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

.logo-text {
  font-size: 1.1rem;
  font-weight: 800;
  color: white;
}

.footer-title {
  font-size: 1.1rem;
  font-weight: 700;
  margin: 0;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.footer-subtitle {
  color: #ccc;
  font-size: 0.9rem;
  margin: 0;
}

.section-title {
  font-size: 1rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: var(--primary);
}

.social-links {
  display: flex;
  flex-direction: row;
  gap: 1rem;
  align-items: center;
  justify-content: center;
}

.social-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
  border-radius: 15px;
  text-decoration: none;
  color: white;
  font-weight: 500;
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
  min-width: 100px;
  justify-content: center;
  font-size: 0.8rem;
}

.social-link:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
  border-color: var(--accent);
}

.social-link i {
  font-size: 1.2rem;
}

.github:hover {
  background: linear-gradient(135deg, #333, #555);
}

.linkedin:hover {
  background: linear-gradient(135deg, #0077b5, #00a0dc);
}

.email:hover {
  background: linear-gradient(135deg, #ea4335, #fbbc05);
}

.skills-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
}

.skill-tag {
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: all 0.3s ease;
  animation: float 3s ease-in-out infinite;
}

.skill-tag:nth-child(2) { animation-delay: 0.5s; }
.skill-tag:nth-child(3) { animation-delay: 1s; }
.skill-tag:nth-child(4) { animation-delay: 1.5s; }
.skill-tag:nth-child(5) { animation-delay: 2s; }

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-5px); }
}

.skill-tag:hover {
  transform: scale(1.1) translateY(-3px);
  box-shadow: 0 5px 15px rgba(233, 30, 99, 0.4);
}

.footer-bottom {
  text-align: center;
  padding-top: 1rem;
}

.footer-line {
  height: 2px;
  background: linear-gradient(90deg, transparent, var(--accent), transparent);
  margin-bottom: 1rem;
  border-radius: 1px;
}

.copyright {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.copyright p {
  color: #ccc;
  margin: 0;
  font-size: 0.9rem;
}

.heart-beat {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #ccc;
  font-size: 0.9rem;
}

.heart-beat i {
  color: #e91e63;
  animation: heartbeat 1.5s ease-in-out infinite;
}

@keyframes heartbeat {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.2); }
}

/* Responsividade */
@media (max-width: 768px) {
  .footer {
    padding: 3rem 1rem 1.5rem;
  }
  
  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .social-links {
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
  }
  
  .social-link {
    min-width: 120px;
  }
  
  .skills-tags {
    justify-content: center;
  }
}
</style>
