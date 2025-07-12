<template>
  <div :class="{ 'dark-mode': isDark }">
    <NavbarTest :is-dark="isDark" @toggle-theme="toggleTheme" />
    <HeroSectionTest />
    <AboutTest />
    <SkillsTest />
    <ExperienceTest />
    <ProjectsTest />
    <ContactTest />
    <FooterTest />
  </div>
</template>

<script>
import NavbarTest from './components/NavbarTest.vue'
import HeroSectionTest from './components/HeroSectionTest.vue'
import AboutTest from './components/AboutTest.vue'
import ExperienceTest from './components/ExperienceTest.vue'
import SkillsTest from './components/SkillsTest.vue'
import ProjectsTest from './components/ProjectsTest.vue'
import ContactTest from './components/ContactTest.vue'
import FooterTest from './components/FooterTest.vue'

export default {
  components: {
    NavbarTest,
    HeroSectionTest,
    AboutTest,
    ExperienceTest,
    SkillsTest,
    ProjectsTest,
    ContactTest,
    FooterTest
  },
  data() {
    return {
      isDark: false
    }
  },
  methods: {
    toggleTheme() {
      this.isDark = !this.isDark
      // Salvar preferência no localStorage
      localStorage.setItem('theme', this.isDark ? 'dark' : 'light')
    }
  },
  mounted() {
    // Carregar preferência salva
    const savedTheme = localStorage.getItem('theme')
    if (savedTheme) {
      this.isDark = savedTheme === 'dark'
    }
  }
}
</script>

<style>
@import './assets/style.css';
</style>
