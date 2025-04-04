<template>
  <div class="hero-section">
    <div class="content">
      <div class="logo-container" >
        <img class="logo" src="../../assets/img/logo-saquecredito-sf.png" alt="Logo" />
      </div>

      <h2>
        <span style="color: #2fb869;">Saque-aniversário:<br></span>
        A liberdade de usar seu FGTS como quiser!
      </h2>
      <h3>Liberamos seu FGTS sem complicação</h3>
      <div class="gif-container">
        <img class="img" src="../../assets/img/muie.png" alt="Logo" />
      </div>
      <h2>Clique no botão para sacar agora mesmo!</h2>
      <a href="https://saquecredito.com.br/"><button class="cta-button">SOLICITE SAQUE</button></a>
    </div>
  </div>
</template>

<script>
export default {
  name: "PromoCard",
};
</script>

<style scoped>
.hero-section {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 85vh;
  background-size: 400% 400%;
  animation: gradientAnimation 10s ease infinite;
  text-align: center;
  padding: 20px;
  opacity: 0;
  animation: fadeIn 1.5s ease-in-out forwards;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }

  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes gradientAnimation {
  0% {
    background-position: 0% 50%;
  }

  25% {
    background-position: 50% 100%;
  }

  50% {
    background-position: 100% 50%;
  }

  75% {
    background-position: 50% 0%;
  }

  100% {
    background-position: 0% 50%;
  }
}

.content {
  background: white;
  padding: 40px;
  border-radius: 20px;
  max-width: 90%;
  width: 500px;
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInContent 1.5s ease-in-out forwards 0.5s;
}

@keyframes fadeInContent {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }

  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.logo-container {
  display: flex;
  justify-content: center;
  margin-bottom: 25px;
  animation: bounceIn 1.2s ease-in-out;
}

@keyframes bounceIn {
  0% {
    transform: scale(0.8);
    opacity: 0;
  }

  50% {
    transform: scale(1.1);
    opacity: 1;
  }

  100% {
    transform: scale(1);
  }
}

.logo {
  width: 180px;
}

h2 {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 20px;
  opacity: 0;
  transform: translateY(10px);
  animation: fadeInText 1.5s ease-in-out forwards 1s;
}

h3 {
  font-size: 19px;
  font-weight: bold;
  color: #333;
  margin-bottom: 20px;
  opacity: 0;
  transform: translateY(10px);
  animation: fadeInText 1.5s ease-in-out forwards 1s;
}

@keyframes fadeInText {
  0% {
    opacity: 0;
    transform: translateY(10px);
  }

  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.gif-container {
  display: flex;
  justify-content: center;
  margin: 30px 0;
}

.highlight-gif {
  width: 100%;
  max-width: 400px;
  border-radius: 15px;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.2);
  opacity: 0;
  animation: fadeInGif 1.5s ease-in-out forwards 1.2s;
}

@keyframes fadeInGif {
  0% {
    opacity: 0;
    transform: scale(0.9);
  }

  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.cta-button {
  background: #05a552;
  color: white;
  border: none;
  padding: 18px 30px;
  font-size: 20px;
  font-weight: bold;
  border-radius: 8px;
  cursor: pointer;
  box-shadow: 0px 5px 15px rgba(255, 255, 255, 0.5);
  transition: all 0.3s;
  opacity: 0;
  animation: fadeInButton 1.5s ease-in-out forwards 1.5s, pulse 2s infinite ease-in-out 2s;
}

@keyframes fadeInButton {
  0% {
    opacity: 0;
    transform: scale(0.9);
  }

  100% {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.05);
  }

  100% {
    transform: scale(1);
  }
}

.cta-button:hover {
  background: #afafaf;
  color: black;
  transform: scale(1.05);
}

@media (max-width: 600px) {
  .content {
    padding: 30px;
  }

  h2 {
    font-size: 24px;
  }

  .cta-button {
    font-size: 18px;
    padding: 15px 25px;
  }
}

@media (max-width: 768px) {
  .content {
    padding: 40px 20px;
    width: 90%;
  }

  h2 {
    font-size: 28px;
  }

  .cta-button {
    font-size: 20px;
    padding: 18px 30px;
  }

  .logo {
    width: 160px;
  }

  .highlight-gif {
    max-width: 350px;
  }
}

@media (max-width: 480px) {
  .content {
    padding: 30px 15px;
    max-width: 100%;
  }

  h2 {
    font-size: 22px;
  }

  .cta-button {
    font-size: 18px;
    padding: 15px 20px;
  }

  .logo {
    width: 140px;
  }

  .highlight-gif {
    max-width: 300px;
  }
}

* {
  font-family: 'Poppins', sans-serif;
}
</style>