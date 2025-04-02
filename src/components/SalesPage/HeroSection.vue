<template>
  <section class="hero-section">
    <div class="container">
      <div class="grid">
        <!-- Texto e Call to Action -->
        <div class="text-content">
          <p class="tagline fade" ref="tagline">Conte com a Saque Crédito</p>
          <h1 class="fade" ref="title">Seu Crédito de Forma Rápida e Segura!</h1>
          <h4 class="fade" ref="subtitle">
            Oferecemos as melhores condições para você acessar seu crédito sem burocracia. Realize seus planos com segurança e confiança!
          </h4>

          <!-- Avaliações -->
          <div class="review">
            <span class="reviews-count">(+ de 10.000 clientes satisfeitos)</span>
          </div>

          <!-- Botão de Call to Action -->
          <a href="https://api.whatsapp.com/send/?phone=+552799242-5656&text=Olá,%20gostaria%20de%20simular%20meu%20crédito%20consignado!" target="_blank">
            <button class="cta-button">FALE CONOSCO</button>
          </a>
        </div>

        <!-- Imagem -->
        <div class="image-wrapper">
          <img class="hero-image fade" ref="heroImage" src="../../assets/img/mulher.png" alt="Imagem do Hero Section" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "HeroSection",
  mounted() {
    setTimeout(() => {
      this.$refs.tagline.classList.add("visible");
      this.$refs.title.classList.add("visible");
      this.$refs.subtitle.classList.add("visible");
      this.$refs.heroImage.classList.add("visible");
    }, 200);
  }
};
</script>

<style scoped>
.hero-section {
  background-color: #d1d1d1;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem 1rem;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

@media (min-width: 768px) {
  .hero-section {
    padding: 6rem 1rem;
  }
}

.container {
  max-width: 1500px;
  width: 100%;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.grid {
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  gap: 2rem;
}

@media (min-width: 768px) {
  .grid {
    flex-direction: row;
    justify-content: space-between;
  }
}

.text-content {
  text-align: center;
  color: #000;
  max-width: 600px;
  padding: 0.5rem;
}

@media (min-width: 768px) {
  .text-content {
    text-align: left;
  }
}

.tagline {
  font-size: 1rem;
  font-weight: 600;
  color: #00a508;
  text-transform: uppercase;
  letter-spacing: 1px;
}

h1 {
  font-size: 3rem;
  font-weight: 700;
  line-height: 1.2;
  color: #000;
}

h4 {
  font-size: 1.4rem;
  font-weight: 400;
  line-height: 1.5;
  color: #000;
}

@media (max-width: 1024px) {
  h1 {
    font-size: 2.5rem;
  }
  h4 {
    font-size: 1.2rem;
  }
}

@media (max-width: 768px) {
  h1 {
    font-size: 2.2rem;
  }
  h4 {
    font-size: 1.1rem;
  }
}

@media (max-width: 480px) {
  h1 {
    font-size: 1.8rem;
  }
  h4 {
    font-size: 1rem;
  }
}

.review {
  margin-bottom: 1.5rem;
}

.reviews-count {
  font-size: 1rem;
  font-weight: 500;
}

.cta-button {
  background-color: #007506;
  color: #fff;
  font-weight: 700;
  font-size: 1rem;
  padding: 12px 20px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s;
  width: 100%;
}

.cta-button:hover {
  background-color: #000;
  transform: scale(1.05);
}

@media (max-width: 480px) {
  .cta-button {
    font-size: 0.9rem;
    padding: 10px 18px;
  }
}

.hero-image {
  width: 100%;
  max-width: 800px;
  border-radius: 10px;
  transition: transform 0.3s;
}

@media (max-width: 768px) {
  .hero-image {
    max-width: 450px;
  }
}

@media (max-width: 480px) {
  .hero-image {
    max-width: 100%;
  }
}

.fade {
  opacity: 0;
  transition: opacity 1s ease-in-out;
}

.fade.visible {
  opacity: 1;
}
</style>