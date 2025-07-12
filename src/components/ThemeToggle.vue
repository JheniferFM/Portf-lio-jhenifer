<template>
  <button @click="toggleTheme" :aria-label="theme === 'dark' ? 'Ativar modo claro' : 'Ativar modo escuro'">
    {{ theme === 'dark' ? '☀️ Claro' : '🌙 Escuro' }}
  </button>
</template>

<script>
export default {
  name: "ThemeToggle",
  data() {
    return {
      theme: localStorage.getItem('theme') || 'light',
    };
  },
  mounted() {
    document.documentElement.setAttribute('data-theme', this.theme);
  },
  methods: {
    toggleTheme() {
      this.theme = this.theme === 'dark' ? 'light' : 'dark';
      document.documentElement.setAttribute('data-theme', this.theme);
      localStorage.setItem('theme', this.theme);
    },
  },
};
</script>

<style scoped>
button {
  cursor: pointer;
  padding: 0.5rem 1rem;
  font-size: 1rem;
  background: var(--btn-bg);
  border: none;
  color: var(--btn-text);
  border-radius: 5px;
  transition: background-color 0.3s;
}
button:hover {
  background: var(--btn-hover);
}
</style>
