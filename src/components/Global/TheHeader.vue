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
  height: 80px;
}

.nav-button {
  font-weight: 500;
  border: none;
  color: #3d3d3d;
  margin: 0 1rem;
  cursor: pointer;
  font-size: 1.2rem;
  transition: color 0.3s ease, transform 0.2s ease;
}

.nav-button:hover {
  color: #00c44b;
  transform: scale(1.1);
}

.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 35px;
  height: 28px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.hamburger:hover {
  transform: rotate(5deg);
}

.hamburger-line {
  width: 100%;
  height: 4px;
  background-color: #00c44b;
  transition: background-color 0.3s ease;
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
  width: 200px;
}

.nav-mobile button {
  margin: 0.7rem 0;
  font-size: 1.2rem;
}

@media (max-width: 1024px) {
  .header {
    padding: 1rem 5vw;
  }
  .logo img {
    height: 70px;
  }
  .nav-button {
    font-size: 1rem;
    margin: 0 0.8rem;
  }
}

@media (max-width: 768px) {
  .nav-desktop {
    display: none;
  }
  .hamburger {
    display: flex;
  }
  .nav-mobile {
    width: 180px;
    right: 0.5rem;
  }
}

@media (max-width: 480px) {
  .header {
    padding: 0.8rem 3vw;
  }
  .logo img {
    height: 60px;
  }
  .nav-mobile {
    width: 160px;
    right: 0.5rem;
  }
  .hamburger {
    width: 30px;
    height: 24px;
  }
  .hamburger-line {
    height: 3px;
  }
}

</style>