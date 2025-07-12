<template>
  <nav class="navbar">
    <div class="nav-left">
      <div class="logo">
        <span class="logo-text">Jhenifer Meneses</span>
      </div>
    </div>
    
    <ul class="nav-menu">
      <li><a href="#about">Sobre</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projetos</a></li>
      <li><a href="#contact">Contato</a></li>
    </ul>
    
    <div class="nav-right">
      <div class="social-links">
        <a href="https://github.com/jheni" target="_blank" class="social-link" title="GitHub">
          <i class="fab fa-github"></i>
        </a>
        <a href="https://www.linkedin.com/in/jhenifer-meneses" target="_blank" class="social-link" title="LinkedIn">
          <i class="fab fa-linkedin"></i>
        </a>
        <a href="https://instagram.com/jhenifer" target="_blank" class="social-link" title="Instagram">
          <i class="fab fa-instagram"></i>
        </a>
      </div>
      <button @click="$emit('toggle-theme')" class="theme-toggle">
        <span v-if="!isDark">🌙</span>
        <span v-else>☀️</span>
      </button>
    </div>
  </nav>
</template>

<script>
export default {
  props: {
    isDark: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: var(--card-bg-light);
  box-shadow: 0 2px 10px var(--shadow-light);
  position: sticky;
  top: 0;
  z-index: 1000;
  border-bottom: 2px solid var(--border-light);
}

.nav-left {
  display: flex;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--primary);
  background: linear-gradient(135deg, var(--primary), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.nav-menu a {
  text-decoration: none;
  color: var(--text-light);
  font-weight: 600;
  font-size: 1.1rem;
  transition: all 0.3s ease;
  position: relative;
}

.nav-menu a:hover {
  color: var(--primary);
  transform: translateY(-2px);
}

.nav-menu a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -5px;
  left: 0;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  transition: width 0.3s ease;
}

.nav-menu a:hover::after {
  width: 100%;
}

.nav-right {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.social-links {
  display: flex;
  gap: 0.5rem;
}

.social-link {
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  border: none;
  padding: 0.5rem;
  border-radius: 50%;
  cursor: pointer;
  font-size: 1.1rem;
  transition: all 0.3s ease;
  width: 35px;
  height: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
}

.social-link:hover {
  transform: translateY(-3px) scale(1.1);
  box-shadow: 0 6px 20px var(--shadow-light);
}

.theme-toggle {
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  border: none;
  padding: 0.75rem 1rem;
  border-radius: 25px;
  cursor: pointer;
  font-size: 1.1rem;
  font-weight: 600;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px var(--shadow-light);
}

.theme-toggle:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px var(--shadow-light);
}

/* Responsividade */
@media (max-width: 768px) {
  .navbar {
    padding: 1rem;
    flex-direction: column;
    gap: 1rem;
  }
  
  .nav-menu {
    gap: 1rem;
  }
  
  .nav-right {
    gap: 0.5rem;
  }
  
  .social-links {
    gap: 0.25rem;
  }
  
  .social-link {
    width: 30px;
    height: 30px;
    font-size: 1rem;
  }
}
</style>
