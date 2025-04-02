<template>
  <header class="header">
    <!-- Logo -->
    <div class="logo">
      <a href="https://saquecredito.com.br/">
        <img src="@/assets/img/logo-saquecredito-sf.png" alt="Logo" />
      </a>
    </div>

    <!-- Botões (visíveis em telas maiores) -->
    <nav class="nav-desktop" v-if="!isMobile">
      <button class="nav-button" @click="goToHome">Home</button>
      <button class="nav-button" @click="goToPartners">Seja Parceiro</button>
      <button class="nav-button" @click="goToFaq">Perguntas Frequentes</button>
    </nav>

    <!-- Menu Hambúrguer (visível em telas menores) -->
    <div class="hamburger" v-if="isMobile" @click="toggleMenu">
      <div class="hamburger-line"></div>
      <div class="hamburger-line"></div>
      <div class="hamburger-line"></div>
    </div>

    <!-- Menu Mobile (aparece ao clicar no hambúrguer) -->
    <nav class="nav-mobile" v-if="isMobile" :style="{ maxHeight: isMenuOpen ? '200px' : '0' }">
      <button class="nav-button" @click="goToHome">Home</button>
      <button class="nav-button" @click="goToPartners">Seja Parceiro</button>
      <button class="nav-button" @click="goToFaq">Perguntas Frequentes</button>
    </nav>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      isMobile: window.innerWidth <= 768,
      isMenuOpen: false,
    };
  },
  methods: {
    goToHome() {
      window.location.href = "https://saquecredito.com.br/";
    },
    goToPartners() {
      window.location.href = "https://saquecredito.com.br/seja-parceiro/";
    },
    goToFaq() {
      window.location.href = "https://saquecredito.com.br/#duvidas";
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    checkScreenSize() {
      this.isMobile = window.innerWidth <= 768;
    }
  },
  mounted() {
    this.checkScreenSize();
    window.addEventListener("resize", this.checkScreenSize);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.checkScreenSize);
  }
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 10vw;
  background-color: #ffffff;
}

.logo img {
  height: 90px;
}

.nav-button {
  font-weight: 500;
  border: none;
  color: #3d3d3d;
  margin: 0 1rem;
  cursor: pointer;
  font-size: 1.5rem;
}

.nav-button:hover {
  color: #00c44b;
}

.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 30px;
  height: 24px;
  cursor: pointer;
}

.hamburger-line {
  width: 100%;
  height: 3px;
  background-color: #00c44b;
}

.nav-mobile {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 60px;
  right: 1rem;
  background-color: #ffffff;
  padding: 0 1rem;
  border-radius: 5px;
  box-shadow: 0 4px 8px rgba(0, 139, 53, 0.1);
  transition: max-height 0.3s ease, padding 0.3s ease;
  max-height: 0;
  overflow: hidden;
}

.nav-mobile button {
  margin: 0.5rem 0;
}

@media (max-width: 768px) {
  .nav-desktop {
    display: none;
  }
}

@media (min-width: 769px) {
  .hamburger,
  .nav-mobile {
    display: none;
  }
}
</style>