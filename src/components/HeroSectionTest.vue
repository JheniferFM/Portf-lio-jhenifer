<template>
  <section class="hero">
    <div class="hero-banner glass-card">
      <!-- Elementos decorativos modernos -->
      <div class="decorative-elements">
        <div class="gradient-orb orb-1"></div>
        <div class="gradient-orb orb-2"></div>
        <div class="gradient-orb orb-3"></div>
        <div class="gradient-orb orb-4"></div>
        <div class="decorative-line line-1"></div>
        <div class="decorative-line line-2"></div>
        <div class="decorative-line line-3"></div>
        <div class="wave-element wave-1"></div>
        <div class="wave-element wave-2"></div>
        <div class="wave-element wave-3"></div>
        <div class="floating-dots">
          <div class="dot dot-1"></div>
          <div class="dot dot-2"></div>
          <div class="dot dot-3"></div>
          <div class="dot dot-4"></div>
          <div class="dot dot-5"></div>
        </div>
        <div class="geometric-shapes">
          <div class="shape shape-1"></div>
          <div class="shape shape-2"></div>
          <div class="shape shape-3"></div>
        </div>
        <div class="sparkles">
          <div class="sparkle sparkle-1">•</div>
          <div class="sparkle sparkle-2">•</div>
          <div class="sparkle sparkle-3">•</div>
          <div class="sparkle sparkle-4">•</div>
          <div class="sparkle sparkle-5">•</div>
          <div class="sparkle sparkle-6">•</div>
          <div class="sparkle sparkle-7">•</div>
          <div class="sparkle sparkle-8">•</div>
          <div class="sparkle sparkle-9">•</div>
          <div class="sparkle sparkle-10">•</div>
          <div class="sparkle sparkle-11">•</div>
          <div class="sparkle sparkle-12">•</div>
          <div class="sparkle sparkle-13">•</div>
          <div class="sparkle sparkle-14">•</div>
          <div class="sparkle sparkle-15">•</div>
          <div class="sparkle sparkle-16">•</div>
          <div class="sparkle sparkle-17">•</div>
          <div class="sparkle sparkle-18">•</div>
          <div class="sparkle sparkle-19">•</div>
          <div class="sparkle sparkle-20">•</div>
        </div>
      </div>
      
      <div class="hero-content">
        <div class="hero-text">
          <h1><span class="ola">Olá,</span> eu sou <span class="gradient-name">Jhenifer Meneses</span></h1>
          <h2 class="title">Desenvolvedora Full Stack</h2>
          <div class="subtitle-typing">
            <span>{{ animatedSubtitle }}</span><span class="cursor">|</span>
          </div>
          <div class="hero-buttons">
            <button class="btn-cta" @click="scrollToSection('projects')">
              <i class="fas fa-folder-open"></i> Veja meus projetos
            </button>
            <button class="btn-secondary" @click="scrollToSection('contact')">
              <i class="fas fa-envelope"></i> Entre em contato
            </button>
          </div>
        </div>
        <div class="hero-image">
          <div class="profile-container" @mouseenter="showTooltip = true" @mouseleave="showTooltip = false">
            <div class="profile-shadow-animated"></div>
            <img src="/foto.jpeg" alt="Jhenifer Meneses" class="profile-photo" />
            <div v-if="showTooltip" class="profile-tooltip">Olá! Eu sou a Jhenifer 👋</div>
          </div>
        </div>
      </div>
      
      <!-- Separador ondulado -->
      <svg class="banner-wave" viewBox="0 0 1440 80" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M0,40 C360,80 1080,0 1440,40 L1440,80 L0,80 Z" fill="#fff5f7"/>
      </svg>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const showTooltip = ref(false)

const subtitles = [
  'Transformando ideias em código',
  'Apaixonada por tecnologia e design',
  'Experiência em Vue.js, Laravel, JS e mais',
  'Vamos criar algo incrível juntos?'
]
const animatedSubtitle = ref('')
let subtitleIndex = 0
let charIndex = 0
let typingInterval = null

function typeSubtitle() {
  if (charIndex < subtitles[subtitleIndex].length) {
    animatedSubtitle.value += subtitles[subtitleIndex][charIndex]
    charIndex++
    typingInterval = setTimeout(typeSubtitle, 60)
  } else {
    setTimeout(() => {
      eraseSubtitle()
    }, 1800)
  }
}
function eraseSubtitle() {
  if (charIndex > 0) {
    animatedSubtitle.value = animatedSubtitle.value.slice(0, -1)
    charIndex--
    typingInterval = setTimeout(eraseSubtitle, 30)
  } else {
    subtitleIndex = (subtitleIndex + 1) % subtitles.length
    setTimeout(typeSubtitle, 400)
  }
}
onMounted(() => {
  typeSubtitle()
})

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<style scoped>
.hero {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  padding: 0 2rem;
  background: linear-gradient(135deg, var(--bg-light) 0%, var(--secondary) 100%);
  margin-top: 0;
}

.dark-mode .hero {
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
}

.glass-card {
  background: rgba(255,255,255,0.85);
  box-shadow: 0 4px 32px 0 rgba(30,30,60,0.08);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border-radius: 28px;
  border: 1.5px solid #f3e6ef;
  position: relative;
  overflow: hidden;
  margin-top: 0;
  padding: 2rem;
  width: 100%;
  max-width: none;
}

.dark-mode .glass-card {
  background: rgba(26,26,26,0.9);
  border: 1.5px solid #333333;
  box-shadow: 0 4px 32px 0 rgba(0,0,0,0.3);
}

.decorative-elements {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 0;
}

.gradient-orb {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(233, 30, 99, 0.1) 0%, rgba(142, 36, 170, 0.05) 50%, transparent 100%);
  animation: orbFloat 12s ease-in-out infinite;
}

.orb-1 {
  width: 120px;
  height: 120px;
  top: 10%;
  left: 5%;
  animation-delay: 0s;
}

.orb-2 {
  width: 80px;
  height: 80px;
  top: 60%;
  right: 10%;
  animation-delay: 4s;
}

.orb-3 {
  width: 100px;
  height: 100px;
  bottom: 20%;
  left: 15%;
  animation-delay: 8s;
}

.orb-4 {
  width: 60px;
  height: 60px;
  top: 80%;
  right: 20%;
  animation-delay: 6s;
}

.decorative-line {
  position: absolute;
  background: linear-gradient(90deg, transparent, rgba(233, 30, 99, 0.2), transparent);
  border-radius: 1px;
  animation: lineGlow 8s ease-in-out infinite;
}

.line-1 {
  width: 80px;
  height: 1px;
  top: 30%;
  left: 8%;
  animation-delay: 2s;
}

.line-2 {
  width: 60px;
  height: 1px;
  bottom: 40%;
  right: 15%;
  animation-delay: 6s;
}

.line-3 {
  width: 40px;
  height: 1px;
  top: 70%;
  left: 25%;
  animation-delay: 4s;
}

@keyframes orbFloat {
  0%, 100% { 
    transform: translateY(0px) scale(1); 
    opacity: 0.6;
  }
  50% { 
    transform: translateY(-30px) scale(1.1); 
    opacity: 0.8;
  }
}

@keyframes lineGlow {
  0%, 100% { 
    opacity: 0.3; 
    transform: scaleX(1);
  }
  50% { 
    opacity: 0.6; 
    transform: scaleX(1.2);
  }
}

/* Novos elementos decorativos */
.wave-element {
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(45deg, rgba(233, 30, 99, 0.1), rgba(142, 36, 170, 0.1));
  animation: waveFloat 8s ease-in-out infinite;
}

.wave-1 {
  width: 150px;
  height: 150px;
  top: 15%;
  right: 5%;
  animation-delay: 0s;
}

.wave-2 {
  width: 100px;
  height: 100px;
  bottom: 30%;
  left: 5%;
  animation-delay: 3s;
}

.wave-3 {
  width: 120px;
  height: 120px;
  top: 70%;
  right: 30%;
  animation-delay: 6s;
}

@keyframes waveFloat {
  0%, 100% { 
    transform: translateY(0px) rotate(0deg); 
    opacity: 0.4;
  }
  50% { 
    transform: translateY(-20px) rotate(180deg); 
    opacity: 0.7;
  }
}

.floating-dots {
  position: absolute;
  width: 100%;
  height: 100%;
}

.dot {
  position: absolute;
  width: 8px;
  height: 8px;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  border-radius: 50%;
  animation: dotFloat 6s ease-in-out infinite;
}

.dot-1 {
  top: 25%;
  left: 10%;
  animation-delay: 0s;
}

.dot-2 {
  top: 45%;
  right: 15%;
  animation-delay: 1s;
}

.dot-3 {
  bottom: 35%;
  left: 20%;
  animation-delay: 2s;
}

.dot-4 {
  top: 65%;
  right: 25%;
  animation-delay: 3s;
}

.dot-5 {
  bottom: 15%;
  right: 10%;
  animation-delay: 4s;
}

@keyframes dotFloat {
  0%, 100% { 
    transform: translateY(0px) scale(1); 
    opacity: 0.6;
  }
  50% { 
    transform: translateY(-15px) scale(1.2); 
    opacity: 1;
  }
}

.geometric-shapes {
  position: absolute;
  width: 100%;
  height: 100%;
}

.shape {
  position: absolute;
  background: linear-gradient(135deg, rgba(233, 30, 99, 0.15), rgba(142, 36, 170, 0.15));
  animation: shapeRotate 10s linear infinite;
}

.shape-1 {
  width: 40px;
  height: 40px;
  top: 20%;
  right: 10%;
  clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
  animation-delay: 0s;
}

.shape-2 {
  width: 30px;
  height: 30px;
  bottom: 25%;
  left: 10%;
  clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
  animation-delay: 3s;
}

.shape-3 {
  width: 35px;
  height: 35px;
  top: 60%;
  right: 20%;
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
  animation-delay: 6s;
}

@keyframes shapeRotate {
  0% { 
    transform: rotate(0deg) scale(1); 
    opacity: 0.5;
  }
  50% { 
    transform: rotate(180deg) scale(1.1); 
    opacity: 0.8;
  }
  100% { 
    transform: rotate(360deg) scale(1); 
    opacity: 0.5;
  }
}

/* Partículas de brilho */
.sparkles {
  position: absolute;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.sparkle {
  position: absolute;
  font-size: 0.6rem;
  animation: sparkleTwinkle 5s ease-in-out infinite;
  opacity: 0.9;
  color: #6366f1;
  filter: drop-shadow(0 0 2px rgba(99, 102, 241, 0.8));
}

.dark-mode .sparkle {
  color: white;
  filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.8));
}

.sparkle-1 {
  top: 15%;
  left: 15%;
  animation-delay: 0s;
}

.sparkle-2 {
  top: 25%;
  right: 20%;
  animation-delay: 0.5s;
}

.sparkle-3 {
  top: 45%;
  left: 25%;
  animation-delay: 1s;
}

.sparkle-4 {
  top: 55%;
  right: 15%;
  animation-delay: 1.5s;
}

.sparkle-5 {
  bottom: 25%;
  left: 10%;
  animation-delay: 2s;
}

.sparkle-6 {
  bottom: 35%;
  right: 25%;
  animation-delay: 2.5s;
}

.sparkle-7 {
  top: 75%;
  left: 20%;
  animation-delay: 0.8s;
}

.sparkle-8 {
  bottom: 15%;
  right: 10%;
  animation-delay: 1.2s;
}

.sparkle-9 {
  top: 35%;
  left: 35%;
  animation-delay: 0.3s;
}

.sparkle-10 {
  top: 65%;
  right: 35%;
  animation-delay: 0.7s;
}

.sparkle-11 {
  bottom: 45%;
  left: 45%;
  animation-delay: 1.1s;
}

.sparkle-12 {
  top: 85%;
  right: 45%;
  animation-delay: 0.4s;
}

.sparkle-13 {
  top: 10%;
  left: 50%;
  animation-delay: 0.9s;
}

.sparkle-14 {
  top: 30%;
  right: 50%;
  animation-delay: 0.2s;
}

.sparkle-15 {
  bottom: 20%;
  left: 60%;
  animation-delay: 0.6s;
}

.sparkle-16 {
  top: 50%;
  right: 60%;
  animation-delay: 1.0s;
}

.sparkle-17 {
  bottom: 60%;
  left: 70%;
  animation-delay: 0.5s;
}

.sparkle-18 {
  top: 20%;
  right: 70%;
  animation-delay: 0.8s;
}

.sparkle-19 {
  bottom: 80%;
  left: 80%;
  animation-delay: 0.1s;
}

.sparkle-20 {
  top: 40%;
  right: 80%;
  animation-delay: 0.4s;
}

@keyframes sparkleTwinkle {
  0%, 100% { 
    transform: scale(1); 
    opacity: 0.6;
  }
  50% { 
    transform: scale(1.1); 
    opacity: 1;
  }
}

.dark-mode .sparkle {
  filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.6));
}

.dark-mode .sparkle:nth-child(odd) {
  filter: drop-shadow(0 0 4px rgba(255, 255, 255, 1));
}

.hero-content {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

.gradient-name {
  background: linear-gradient(90deg, #e91e63, #8e24aa, #e91e63);
  background-size: 200% auto;
  color: #fff;
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: shine 3s linear infinite;
  font-weight: 900;
}


@keyframes shine {
  to { background-position: 200% center; }
}

.hero-text h1, .hero-text .title {
  color: #222;
  font-weight: 800;
  text-shadow: none;
}
.hero-text h1 .ola {
  color: var(--primary);
  font-weight: 800;
}



.subtitle-typing {
  font-size: 1.15rem;
  color: #6d2777;
  min-height: 2.2rem;
  margin-bottom: 1.5rem;
  font-family: 'Fira Mono', 'Courier New', monospace;
  font-weight: 600;
  letter-spacing: 1px;
  display: flex;
  align-items: center;
  gap: 0.2rem;
}



.cursor {
  color: var(--primary);
  font-weight: 900;
  animation: blink 1s steps(2, start) infinite;
}


@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn-cta {
  background: var(--primary);
  color: #fff;
  border: none;
  padding: 1rem 2rem;
  border-radius: 50px;
  font-weight: 700;
  font-size: 1.1rem;
  cursor: pointer;
  box-shadow: 0 2px 8px 0 rgba(233,30,99,0.10);
  transition: all 0.2s cubic-bezier(.4,1.4,.7,1.1);
  border: 2px solid var(--primary);
  position: relative;
  overflow: hidden;
}


.btn-cta::after {
  content: '';
  position: absolute;
  left: 0; top: 0; right: 0; bottom: 0;
  background: rgba(255,255,255,0.12);
  opacity: 0;
  transition: opacity 0.3s;
}
.btn-cta:hover {
  background: #fff;
  color: var(--primary);
  border: 2px solid var(--primary);
  box-shadow: 0 6px 24px 0 rgba(233,30,99,0.15);
  transform: translateY(-2px) scale(1.04);
}


.btn-cta:hover::after {
  opacity: 1;
}

.btn-secondary {
  background: #fff;
  border: 2px solid var(--primary);
  padding: 1rem 2rem;
  border-radius: 50px;
  font-weight: 700;
  color: var(--primary);
  cursor: pointer;
  transition: all 0.2s cubic-bezier(.4,1.4,.7,1.1);
  font-size: 1.1rem;
  box-shadow: 0 2px 8px 0 rgba(233,30,99,0.10);
  position: relative;
  overflow: hidden;
}


.btn-secondary::after {
  content: '';
  position: absolute;
  left: 0; top: 0; right: 0; bottom: 0;
  background: var(--primary);
  opacity: 0;
  transition: opacity 0.3s;
}
.btn-secondary:hover {
  background: var(--primary);
  color: #fff;
  border: 2px solid var(--primary);
  transform: translateY(-2px) scale(1.04);
}


.btn-secondary:hover::after {
  opacity: 0.08;
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.profile-container {
  position: relative;
  width: 280px;
  height: 280px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fff;
  border-radius: 50%;
  box-shadow: 0 4px 24px 0 rgba(30,30,60,0.08);
  margin: 0 auto;
  border: 4px solid #f3e6ef;
  overflow: visible;
}





.profile-shadow-animated {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 300px;
  height: 300px;
  background: conic-gradient(from 0deg, #e91e63, #8e24aa, #e91e63 100%);
  opacity: 0.18;
  border-radius: 50%;
  transform: translate(-50%, -50%) scale(1);
  z-index: 0;
  filter: blur(6px);
  animation: shadowPulse 3s ease-in-out infinite;
}


@keyframes shadowPulse {
  0%, 100% { opacity: 0.18; transform: translate(-50%, -50%) scale(1); }
  50% { opacity: 0.32; transform: translate(-50%, -50%) scale(1.07); }
}

.profile-photo {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  object-position: center 0%;
  border: none;
  background: #fff;
  transition: all 0.3s ease;
  position: relative;
  z-index: 1;
}

.profile-tooltip {
  position: absolute;
  bottom: -2.2rem;
  left: 50%;
  transform: translateX(-50%);
  background: #fff;
  color: #e91e63;
  font-weight: 700;
  font-size: 1rem;
  padding: 0.5rem 1.2rem;
  border-radius: 16px;
  box-shadow: 0 2px 12px 0 rgba(233,30,99,0.10);
  white-space: nowrap;
  opacity: 0.95;
  z-index: 10;
  pointer-events: none;
  animation: tooltipFade 0.4s;
}


@keyframes tooltipFade {
  from { opacity: 0; transform: translateX(-50%) translateY(10px); }
  to { opacity: 0.95; transform: translateX(-50%) translateY(0); }
}

.hero-buttons .btn-cta i,
.hero-buttons .btn-secondary i {
  margin-right: 0.6em;
  font-size: 1.1em;
  vertical-align: middle;
}

@media (max-width: 900px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }
  .hero-text {
    text-align: center;
  }
  .hero-text h1 {
    font-size: 2rem;
  }
  .title {
    font-size: 1.2rem;
  }
  .profile-container {
    width: 160px;
    height: 160px;
  }
  .profile-shadow-animated {
    width: 180px;
    height: 180px;
  }
}

/* Modo escuro */
.dark-mode .hero-text h1, 
.dark-mode .hero-text .title {
  color: #f8f9fa;
}

.dark-mode .subtitle-typing {
  color: #e1bee7;
}

.dark-mode .profile-container {
  background: #2d2d2d;
  border-color: #424242;
  box-shadow: 0 4px 24px 0 rgba(0, 0, 0, 0.3);
}



.dark-mode .profile-tooltip {
  background: #2d2d2d;
  color: #e91e63;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.3);
}

.dark-mode .banner-wave path {
  fill: #0a0a0a;
}
</style>
