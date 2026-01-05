<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content fade-in-up">
        <h1>Inclusion Financière pour Tous</h1>
        <p class="hero-subtitle">Accès aux services financiers pour les populations défavorisées de la RDC</p>
        <div class="hero-buttons">
          <router-link to="/services" class="btn btn-primary">Nos Services</router-link>
          <router-link to="/contact" class="btn btn-secondary">Nous Contacter</router-link>
        </div>
      </div>
      <div class="hero-image">
        <div class="hero-shape"></div>
      </div>
    </section>

    <!-- Stats Section -->
    <section class="section stats-section">
      <div class="container">
        <div class="stats-grid">
          <div class="stat-card fade-in-up" style="animation-delay: 0.1s">
            <div class="stat-number">15+</div>
            <div class="stat-label">Années d'Expérience</div>
          </div>
          <div class="stat-card fade-in-up" style="animation-delay: 0.2s">
            <div class="stat-number">50K+</div>
            <div class="stat-label">Clients Satisfaits</div>
          </div>
          <div class="stat-card fade-in-up" style="animation-delay: 0.3s">
            <div class="stat-number">3</div>
            <div class="stat-label">Provinces Desservies</div>
          </div>
          <div class="stat-card fade-in-up" style="animation-delay: 0.4s">
            <div class="stat-number">100%</div>
            <div class="stat-label">Taux de Satisfaction</div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section class="section about-section">
      <div class="container">
        <div class="about-grid">
          <div class="about-content slide-in-left">
            <h2 class="section-title">À Propos de PAIDEKSA</h2>
            <p>PAIDEKSA se donne comme mission de contribuer au renforcement du tissu économique et à la redynamisation de l'économie populaire de la République Démocratique du Congo.</p>
            <p>Nous facilitons l'accès des populations défavorisées et exclues du système bancaire classique aux services financiers et non financiers.</p>
            <ul class="features-list">
              <li>✓ Services financiers accessibles</li>
              <li>✓ Suivi personnalisé des clients</li>
              <li>✓ Solutions adaptées aux besoins</li>
              <li>✓ Transparence et confiance</li>
            </ul>
            <router-link to="/mission" class="btn btn-primary">En Savoir Plus</router-link>
          </div>
          <div class="about-image slide-in-right">
            <div class="image-placeholder">
              <div class="placeholder-icon">💼</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Preview Section -->
    <section class="section services-preview">
      <div class="container">
        <h2 class="section-title">Nos Services</h2>
        <div class="services-grid">
          <div class="service-card fade-in-up" style="animation-delay: 0.1s">
            <div class="service-icon">💰</div>
            <h3>Microfinance</h3>
            <p>Solutions de financement adaptées aux petits entrepreneurs et aux économies populaires.</p>
          </div>
          <div class="service-card fade-in-up" style="animation-delay: 0.2s">
            <div class="service-icon">🏦</div>
            <h3>Épargne</h3>
            <p>Produits d'épargne sécurisés pour constituer votre patrimoine progressivement.</p>
          </div>
          <div class="service-card fade-in-up" style="animation-delay: 0.3s">
            <div class="service-icon">📱</div>
            <h3>Services Numériques</h3>
            <p>Accès mobile et digital pour gérer vos finances facilement et en toute sécurité.</p>
          </div>
          <div class="service-card fade-in-up" style="animation-delay: 0.4s">
            <div class="service-icon">📚</div>
            <h3>Formation</h3>
            <p>Programme d'éducation financière pour renforcer vos compétences de gestion.</p>
          </div>
        </div>
        <div class="services-cta">
          <router-link to="/services" class="btn btn-primary">Tous les Services</router-link>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="section cta-section">
      <div class="container">
        <div class="cta-content fade-in-up">
          <h2>Prêt à Commencer ?</h2>
          <p>Rejoignez des milliers de clients qui ont transformé leur vie financière</p>
          <router-link to="/contact" class="btn btn-secondary">Démarrez Maintenant</router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
</script>

<style scoped>
.home {
  width: 100%;
}

/* Hero Section */
.hero {
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: var(--spacing-3xl);
  padding: var(--spacing-4xl) 0;
  background: linear-gradient(135deg, rgba(0, 121, 107, 0.05) 0%, rgba(0, 121, 107, 0.1) 100%);
  position: relative;
  overflow: hidden;
}

.hero-content h1 {
  font-size: var(--text-5xl);
  line-height: var(--line-height-tight);
  color: var(--primary);
  margin-bottom: var(--spacing-lg);
}

.hero-subtitle {
  font-size: var(--text-lg);
  color: var(--text-light);
  margin-bottom: var(--spacing-xl);
  line-height: var(--line-height-relaxed);
}

.hero-buttons {
  display: flex;
  gap: var(--spacing-lg);
  flex-wrap: wrap;
}

.hero-image {
  position: relative;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-shape {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
  border-radius: var(--radius-xl);
  position: relative;
  box-shadow: 0 20px 60px rgba(0, 121, 107, 0.3);
  animation: float 3s ease-in-out infinite;
}

/* Stats Section */
.stats-section {
  background-color: var(--bg-light);
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: var(--spacing-lg);
}

.stat-card {
  background: white;
  padding: var(--spacing-2xl);
  border-radius: var(--radius-lg);
  text-align: center;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
}

.stat-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 30px rgba(0, 121, 107, 0.2);
}

.stat-number {
  font-size: var(--text-4xl);
  font-weight: var(--font-bold);
  color: var(--primary);
  margin-bottom: var(--spacing-md);
}

.stat-label {
  color: var(--text-light);
  font-size: var(--text-base);
  font-weight: var(--font-medium);
}

/* About Section */
.about-section {
  background-color: white;
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--spacing-3xl);
  align-items: center;
}

.about-content h2 {
  font-size: var(--text-4xl);
}

.about-content p {
  font-size: var(--text-lg);
  margin-bottom: var(--spacing-lg);
  color: var(--text-light);
  line-height: var(--line-height-relaxed);
}

.features-list {
  list-style: none;
  margin: var(--spacing-xl) 0;
  padding: 0;
}

.features-list li {
  padding: var(--spacing-md) 0;
  font-size: var(--text-lg);
  color: var(--text-dark);
  font-weight: var(--font-medium);
}

.image-placeholder {
  width: 100%;
  height: 400px;
  background: linear-gradient(135deg, var(--primary-lighter) 0%, var(--primary) 100%);
  border-radius: var(--radius-xl);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 20px 60px rgba(0, 121, 107, 0.2);
}

.placeholder-icon {
  font-size: 6rem;
  animation: pulse 2s ease-in-out infinite;
}

/* Services Preview */
.services-preview {
  background-color: var(--bg-light);
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-lg);
  margin-bottom: var(--spacing-2xl);
}

.service-card {
  background: white;
  padding: var(--spacing-2xl);
  border-radius: var(--radius-lg);
  text-align: center;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
  cursor: pointer;
}

.service-card:hover {
  transform: translateY(-15px);
  box-shadow: 0 15px 40px rgba(0, 121, 107, 0.2);
  border-top: 4px solid var(--secondary);
}

.service-icon {
  font-size: 3rem;
  margin-bottom: var(--spacing-lg);
  display: block;
  transition: transform var(--transition-base);
}

.service-card:hover .service-icon {
  transform: scale(1.2) rotate(5deg);
}

.service-card h3 {
  font-size: var(--text-xl);
  margin-bottom: var(--spacing-md);
  color: var(--primary);
}

.service-card p {
  color: var(--text-light);
  line-height: var(--line-height-normal);
}

.services-cta {
  text-align: center;
  margin-top: var(--spacing-2xl);
}

/* CTA Section */
.cta-section {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
  text-align: center;
}

.cta-content h2 {
  font-size: var(--text-4xl);
  margin-bottom: var(--spacing-lg);
  color: white;
}

.cta-content p {
  font-size: var(--text-lg);
  margin-bottom: var(--spacing-xl);
  opacity: 0.95;
}

.cta-section .section-title::after {
  display: none;
}

@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
    padding: var(--spacing-2xl) 0;
    gap: var(--spacing-2xl);
  }

  .hero-content h1 {
    font-size: var(--text-4xl);
  }

  .hero-subtitle {
    font-size: var(--text-lg);
  }

  .hero-buttons {
    flex-direction: column;
  }

  .hero-shape {
    height: 300px;
  }

  .about-grid {
    grid-template-columns: 1fr;
    gap: var(--spacing-2xl);
  }

  .about-content h2 {
    font-size: var(--text-2xl);
  }

  .image-placeholder {
    height: 300px;
  }

  .cta-content h2 {
    font-size: var(--text-2xl);
  }
}
</style>
