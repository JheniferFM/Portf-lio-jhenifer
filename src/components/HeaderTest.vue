<template>
  <header :class="['header', darkMode ? 'dark' : 'light']">
    <nav class="nav container">
      <a href="#" class="logo">Jhenifer Meneses</a>

      <ul :class="['nav-links', showMenu ? 'show' : '']">
        <li><a href="#home" @click="toggleMenu">Home</a></li>
        <li><a href="#about" @click="toggleMenu">Sobre</a></li>
        <li><a href="#skills" @click="toggleMenu">Skills</a></li>
        <li><a href="#projects" @click="toggleMenu">Projetos</a></li>
        <li><a href="#contact" @click="toggleMenu">Contato</a></li>
      </ul>

      <div class="actions">
        <button class="theme-toggle" @click="toggleDarkMode" :aria-label="darkMode ? 'Modo claro' : 'Modo escuro'">
          <span v-if="darkMode">🌞</span>
          <span v-else>🌙</span>
        </button>
        <button class="menu-toggle" @click="toggleMenu" aria-label="Abrir menu">
          <span :class="showMenu ? 'close' : 'hamburger'"></span>
        </button>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderTest',
  data() {
    return {
      darkMode: false,
      showMenu: false
    }
  },
  created() {
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme) {
      this.darkMode = savedTheme === 'dark';
      this.applyTheme();
    }
  },
  methods: {
    toggleDarkMode() {
      this.darkMode = !this.darkMode;
      localStorage.setItem('theme', this.darkMode ? 'dark' : 'light');
      this.applyTheme();
    },
    applyTheme() {
      document.documentElement.setAttribute('data-theme', this.darkMode ? 'dark' : 'light');
    },
    toggleMenu() {
      this.showMenu = !this.showMenu;
    }
  }
}
</script>

<style scoped>
.header {
  position: fixed;
  top: 0; left: 0; right: 0;
  background-color: var(--bg-header);
  box-shadow: var(--shadow);
  z-index: 1000;
  transition: background-color 0.3s ease;
}

.nav {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0.5rem 1rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-weight: 700;
  font-size: 1.5rem;
  color: var(--text-primary);
  text-decoration: none;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1.5rem;
}

.nav-links li a {
  color: var(--text-primary);
  font-weight: 600;
  text-decoration: none;
  transition: color 0.3s ease;
}

.nav-links li a:hover {
  color: var(--color-accent);
}

.actions {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.theme-toggle {
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  color: var(--text-primary);
  transition: color 0.3s ease;
}

.menu-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
}

.menu-toggle .hamburger,
.menu-toggle .close {
  display: block;
  width: 25px;
  height: 3px;
  background-color: var(--text-primary);
  position: relative;
  transition: all 0.3s ease;
}

.menu-toggle .hamburger::before,
.menu-toggle .hamburger::after {
  content: '';
  position: absolute;
  width: 25px;
  height: 3px;
  background-color: var(--text-primary);
  transition: all 0.3s ease;
}

.menu-toggle .hamburger::before {
  top: -8px;
}

.menu-toggle .hamburger::after {
  top: 8px;
}

.menu-toggle .close {
  background-color: transparent;
}

.menu-toggle .close::before {
  content: '';
  position: absolute;
  width: 25px;
  height: 3px;
  background-color: var(--text-primary);
  transform: rotate(45deg);
  top: 0;
}

.menu-toggle .close::after {
  content: '';
  position: absolute;
  width: 25px;
  height: 3px;
  background-color: var(--text-primary);
  transform: rotate(-45deg);
  top: 0;
}

/* Responsivo */
@media (max-width: 768px) {
  .nav-links {
    position: fixed;
    top: 60px;
    right: 0;
    background: var(--bg-header);
    height: calc(100vh - 60px);
    width: 200px;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
    padding-top: 2rem;
    transform: translateX(100%);
    transition: transform 0.3s ease;
  }

  .nav-links.show {
    transform: translateX(0);
  }

  .menu-toggle {
    display: block;
  }
}
</style>
