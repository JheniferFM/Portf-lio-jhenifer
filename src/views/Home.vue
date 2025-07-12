<template>
  <div>
    <nav class="navbar">
      <ul>
        <li><a href="#about">Sobre</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projetos</a></li>
        <li><a href="#experience">Experiência</a></li>
        <li><a href="#certifications">Certificações</a></li>
      </ul>
      <ThemeToggle />
    </nav>

    <SocialButtons />

    <main>
      <AboutTest />
      <SkillsTest />
      <ProjectsTest />
      <ExperienceTest />
      <CertificationsTest />
    </main>

    <FooterTest />
  </div>
</template>

<script>
import AboutTest from './AboutTest.vue'
import SkillsTest from './SkillsTest.vue'
import ProjectsTest from './ProjectsTest.vue'
import ExperienceTest from './ExperienceTest.vue'
import CertificationsTest from './CertificationsTest.vue'
import ThemeToggle from './ThemeToggle.vue'
import SocialButtons from './SocialButtons.vue'
import FooterTest from './FooterTest.vue' // Corrigido aqui

export default {
  components: {
    AboutTest,
    SkillsTest,
    ProjectsTest,
    ExperienceTest,
    CertificationsTest,
    ThemeToggle,
    SocialButtons,
    FooterTest,
  },
}
</script>
