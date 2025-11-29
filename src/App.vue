<template>
  <div :style="mainStyles">
    <div class="main-content">
      <!-- Dark Mode Toggle -->
      <button @click="toggleDark" :style="toggleBtnStyles" class="dark-toggle">
        <svg v-if="!isDark" class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z" />
        </svg>
        <svg v-else class="icon" fill="none" stroke="white" viewBox="0 0 24 24">
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
          />
        </svg>
      </button>

      <!-- Hero Section -->
      <section class="hero-section">
        <!-- Animated Background -->
        <div class="floating-bg">
          <div v-for="i in 12" :key="i" :class="['floating-circle', isDark ? 'dark' : '']" :style="getFloatingStyle(i)"></div>
        </div>

        <div class="hero-content">
          <!-- Avatar -->
          <div class="avatar-wrapper">
            <div class="avatar">FF</div>
          </div>

          <h1 class="main-title">Foziljon Faxriddinov</h1>
          <p :style="subtitleStyles" class="subtitle">Fullstack Developer</p>
          <p :style="descriptionStyles" class="description">
            8+ oylik tajriba bilan Vue.js va Node.js texnologiyalarida ilovalar yarataman. PowerMonitoring desktop ilovasida frontend dasturlash bo'yicha tajribaga egaman.
          </p>

          <!-- Contact Links -->
          <div class="contact-grid">
            <a href="mailto:faxriddinov0620@gmail.com" class="contact-btn primary">
              <svg class="icon-sm" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
             
            </a>
            <a href="tel:+998881083039" :style="secondaryBtnStyles" class="contact-btn secondary">
              <svg class="icon-sm" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"
                />
              </svg>
              +998 88 108 30 39
            </a>
            <a href="https://github.com/faxriddinov" target="_blank" :style="secondaryBtnStyles" class="contact-btn secondary">
              <svg class="icon-sm" fill="currentColor" viewBox="0 0 24 24">
                <path
                  d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"
                />
              </svg>
            </a>
            <a href="/src/resume.pdf" :style="secondaryBtnStyles" class="contact-btn secondary">
              <svg class="icon-sm" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
              </svg>
              Resume
            </a>
          </div>

          <!-- Scroll Indicator -->
          <div class="scroll-indicator">
            <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
            </svg>
          </div>
        </div>
      </section>

      <!-- Skills Section -->
      <section :style="skillsSectionStyles" class="skills-section">
        <div class="container">
          <h2 class="section-title">Ko'nikmalar</h2>

          <div class="skills-grid">
            <!-- Frontend -->
            <div :style="skillCardStyles" class="skill-card">
              <div class="skill-header">
                <div :style="indigoIconStyles" class="skill-icon">
                  <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
                  </svg>
                </div>
                <h3 class="skill-title">Frontend</h3>
              </div>
              <div class="skill-list">
                <div v-for="skill in frontendSkills" :key="skill" :style="skillItemStyles" class="skill-item indigo-hover">
                  {{ skill }}
                </div>
              </div>
            </div>

            <!-- Backend -->
            <div :style="skillCardStyles" class="skill-card">
              <div class="skill-header">
                <div :style="purpleIconStyles" class="skill-icon">
                  <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01"
                    />
                  </svg>
                </div>
                <h3 class="skill-title">Backend</h3>
              </div>
              <div class="skill-list">
                <div v-for="skill in backendSkills" :key="skill" :style="skillItemStyles" class="skill-item purple-hover">
                  {{ skill }}
                </div>
              </div>
            </div>

            <!-- Tools -->
            <div :style="skillCardStyles" class="skill-card full-width">
              <div class="skill-header">
                <div :style="greenIconStyles" class="skill-icon">
                  <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"
                    />
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                  </svg>
                </div>
                <h3 class="skill-title">Vositalar</h3>
              </div>
              <div class="tools-list">
                <div v-for="tool in tools" :key="tool" :style="skillItemStyles" class="skill-item green-hover">
                  {{ tool }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Footer -->
      <footer :style="footerStyles" class="footer">
        <p>© 2024 Foziljon Faxriddinov. Barcha huquqlar himoyalangan.</p>
      </footer>
    </div>
  </div>
</template>

<script setup>
  import { ref, computed, onMounted } from "vue";

  const isDark = ref(false);

  const frontendSkills = ["Vue.js", "Vue Router", "Vuex", "Pinia", "JavaScript (ES6+)", "HTML5", "CSS3", "TailwindCSS", "Vuetify", "Element-UI", "Electron.js"];

  const backendSkills = ["Node.js", "Express.js", "NestJS", "REST API", "MongoDB", "PostgreSQL", "TypeORM", "Sequelize", "Mongoose"];

  const tools = ["Git", "GitHub", "GitLab", "Postman"];

  // Computed styles based on dark mode
  const mainStyles = computed(() => ({
    minHeight: "100vh",
    background: isDark.value ? "rgb(15, 23, 42)" : "white",
    color: isDark.value ? "white" : "rgb(15, 23, 42)",
    transition: "all 0.3s ease",
  }));

  const toggleBtnStyles = computed(() => ({
    background: isDark.value ? "rgb(30, 41, 59)" : "rgb(226, 232, 240)",
  }));

  const subtitleStyles = computed(() => ({
    color: isDark.value ? "rgb(129, 140, 248)" : "rgb(99, 102, 241)",
  }));

  const descriptionStyles = computed(() => ({
    color: isDark.value ? "rgb(148, 163, 184)" : "rgb(71, 85, 105)",
  }));

  const secondaryBtnStyles = computed(() => ({
    background: isDark.value ? "rgb(30, 41, 59)" : "rgb(226, 232, 240)",
    color: isDark.value ? "white" : "rgb(15, 23, 42)",
  }));

  const skillsSectionStyles = computed(() => ({
    background: isDark.value ? "rgb(30, 41, 59)" : "rgb(248, 250, 252)",
  }));

  const skillCardStyles = computed(() => ({
    background: isDark.value ? "rgb(15, 23, 42)" : "white",
  }));

  const skillItemStyles = computed(() => ({
    background: isDark.value ? "rgb(30, 41, 59)" : "rgb(248, 250, 252)",
  }));

  const indigoIconStyles = computed(() => ({
    background: isDark.value ? "rgb(49, 46, 129)" : "rgb(224, 231, 255)",
    color: isDark.value ? "rgb(129, 140, 248)" : "rgb(79, 70, 229)",
  }));

  const purpleIconStyles = computed(() => ({
    background: isDark.value ? "rgb(88, 28, 135)" : "rgb(243, 232, 255)",
    color: isDark.value ? "rgb(192, 132, 252)" : "rgb(126, 34, 206)",
  }));

  const greenIconStyles = computed(() => ({
    background: isDark.value ? "rgb(20, 83, 45)" : "rgb(220, 252, 231)",
    color: isDark.value ? "rgb(134, 239, 172)" : "rgb(22, 163, 74)",
  }));

  const footerStyles = computed(() => ({
    background: isDark.value ? "rgb(30, 41, 59)" : "rgb(248, 250, 252)",
    color: isDark.value ? "rgb(148, 163, 184)" : "rgb(71, 85, 105)",
  }));

  const toggleDark = () => {
    isDark.value = !isDark.value;
    localStorage.setItem("darkMode", isDark.value);
  };

  const getFloatingStyle = (i) => {
    const size = Math.random() * 100 + 50;
    const left = Math.random() * 100;
    const top = Math.random() * 100;
    const delay = Math.random() * 5;
    const duration = Math.random() * 10 + 10;

    return {
      width: `${size}px`,
      height: `${size}px`,
      left: `${left}%`,
      top: `${top}%`,
      animation: `float ${duration}s ease-in-out ${delay}s infinite`,
    };
  };

  onMounted(() => {
    const saved = localStorage.getItem("darkMode");
    if (saved !== null) {
      isDark.value = saved === "true";
    }
  });
</script>

<style>
  *::-webkit-scrollbar {
    display: none !important;
  }

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .main-content {
    min-height: 100vh;
  }

  /* Dark Mode Toggle */
  .dark-toggle {
    position: fixed;
    top: 1.5rem;
    right: 1.5rem;
    z-index: 50;
    padding: 0.75rem;
    border-radius: 9999px;
    border: none;
    cursor: pointer;
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
  }

  .dark-toggle:hover {
    transform: scale(1.1);
  }

  .icon {
    width: 1.5rem;
    height: 1.5rem;
    display: block;
  }

  .icon-sm {
    width: 1.25rem;
    height: 1.25rem;
  }

  /* Hero Section */
  .hero-section {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1.5rem;
    position: relative;
    overflow: hidden;
  }

  .floating-bg {
    position: absolute;
    inset: 0;

    overflow: hidden;
    opacity: 0.3;
  }

  .floating-circle {
    position: absolute;
    border-radius: 9999px;
    background: rgb(99, 102, 241);
  }

  .floating-circle.dark {
    background: rgb(129, 140, 248);
  }

  .hero-content {
    max-width: 56rem;
    margin: 0 auto;
    text-align: center;
    position: relative;
    z-index: 10;
  }

  .avatar-wrapper {
    margin-bottom: 2rem;
    display: inline-block;
  }

  .avatar {
    width: 8rem;
    height: 8rem;
    border-radius: 9999px;
    background: linear-gradient(to bottom right, rgb(99, 102, 241), rgb(139, 92, 246));
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
    font-weight: bold;
    color: white;
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
    animation: bounce-slow 3s ease-in-out infinite;
  }

  .main-title {
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 1rem;
    animation: fadeIn 1s ease-out;
  }

  .subtitle {
    font-size: 1.5rem;
    margin-bottom: 1.5rem;
    animation: fadeIn 1s ease-out 0.3s backwards;
  }

  .description {
    font-size: 1.125rem;
    max-width: 42rem;
    margin: 0 auto 2rem;
    line-height: 1.75;
    animation: fadeIn 1s ease-out 0.6s backwards;
  }

  .contact-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
    margin-bottom: 2rem;
    animation: fadeIn 1s ease-out 0.9s backwards;
  }

  @media (min-width: 768px) {
    .main-title {
      font-size: 4.5rem;
    }

    .subtitle {
      font-size: 1.875rem;
    }

    .contact-grid {
      grid-template-columns: repeat(4, 1fr);
    }
  }

  .contact-btn {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.75rem 1rem;
    border-radius: 0.5rem;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.3s ease;
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    justify-content: center;
  }

  .contact-btn.primary {
    background: rgb(79, 70, 229);
    color: white;
  }

  .contact-btn.primary:hover {
    background: rgb(67, 56, 202);
    transform: scale(1.05);
  }

  .contact-btn.secondary:hover {
    transform: scale(1.05);
    opacity: 0.9;
  }

  @media (max-width: 768px) {
    .contact-btn {
      font-size: 0.875rem;
      padding: 0.5rem;
    }
  }

  .scroll-indicator {
    animation: bounce 2s infinite;
  }

  /* Skills Section */
  .skills-section {
    padding: 5rem 1.5rem;
  }

  .container {
    max-width: 72rem;
    margin: 0 auto;
  }

  .section-title {
    font-size: 2.25rem;
    font-weight: bold;
    text-align: center;
    margin-bottom: 4rem;
    background: linear-gradient(to right, rgb(79, 70, 229), rgb(139, 92, 246));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .skills-grid {
    display: grid;
    gap: 2rem;
  }

  @media (min-width: 768px) {
    .skills-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  .skill-card {
    padding: 2rem;
    border-radius: 1rem;
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
    transition: all 0.3s ease;
  }

  .skill-card:hover {
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.4);
    transform: translateY(-0.5rem);
  }

  .full-width {
    grid-column: 1 / -1;
  }

  .skill-header {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 1.5rem;
  }

  .skill-icon {
    width: 3rem;
    height: 3rem;
    border-radius: 0.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .skill-title {
    font-size: 1.5rem;
    font-weight: bold;
  }

  .skill-list,
  .tools-list {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .tools-list {
    flex-direction: row;
    flex-wrap: wrap;
  }

  .skill-item {
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    transition: all 0.3s ease;
    cursor: pointer;
  }

  .skill-item.indigo-hover:hover {
    background: rgb(224, 231, 255) !important;
  }

  .skill-item.purple-hover:hover {
    background: rgb(243, 232, 255) !important;
  }

  .skill-item.green-hover:hover {
    background: rgb(220, 252, 231) !important;
  }

  /* Footer */
  .footer {
    padding: 3rem 1.5rem;
    text-align: center;
  }

  /* Animations */
  @keyframes float {
    0%,
    100% {
      transform: translateY(0) translateX(0);
    }
    25% {
      transform: translateY(-20px) translateX(10px);
    }
    50% {
      transform: translateY(-10px) translateX(-10px);
    }
    75% {
      transform: translateY(-30px) translateX(5px);
    }
  }

  @keyframes bounce-slow {
    0%,
    100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-10px);
    }
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes bounce {
    0%,
    100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-10px);
    }
  }
</style>
