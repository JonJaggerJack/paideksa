<template>
  <div class="home">
    <!-- Hero Section with Carousel -->
    <section class="hero">
      <div class="hero-carousel-wrapper">
        <div class="carousel-slides">
          <div 
            v-for="(slide, index) in carouselSlides" 
            :key="index"
            class="carousel-slide"
            :class="{ active: index === currentSlideIndex }"
          >
            <img :src="slide.image" :alt="slide.title" class="slide-image">
          </div>
        </div>
        
        <div class="carousel-overlay"></div>

        <button class="carousel-btn prev" @click="prevSlide" title="Précédent">
          ❮
        </button>
        <button class="carousel-btn next" @click="nextSlide" title="Suivant">
          ❯
        </button>

        <!-- Carousel Indicators -->
        <div class="carousel-indicators">
          <button 
            v-for="(slide, index) in carouselSlides"
            :key="'indicator-' + index"
            class="indicator"
            :class="{ active: index === currentSlideIndex }"
            @click="goToSlide(index)"
            :title="'Aller au slide ' + (index + 1)"
          ></button>
        </div>
      </div>

      <div class="hero-content fade-in-up">
        <h1>Inclusion Financière pour Tous</h1>
        <p class="hero-subtitle">Vivre la finance inclusive et la solidarité économique avec PAIDEKSA</p>
        <div class="hero-buttons">
          <router-link to="/services" class="btn btn-primary">Nos Services</router-link>
          <router-link to="/contact" class="btn btn-secondary">Nous Contacter</router-link>
        </div>
      </div>
    </section>

    <!-- Services Section - Like IFRDC -->
    <section class="section services-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Nos Domaines d'Intervention</h2>
          <p class="section-subtitle">Accédez à des services financiers diversifiés et adaptés à vos besoins</p>
        </div>
        
        <div class="services-grid">
          <div class="service-item fade-in-up" style="animation-delay: 0.1s">
            <div class="service-icon">💰</div>
            <h3>Microfinance</h3>
            <p>Solutions de financement adaptées aux petits entrepreneurs et aux économies populaires pour stimuler votre croissance.</p>
            <router-link to="/services" class="service-link">En savoir plus →</router-link>
          </div>

          <div class="service-item fade-in-up" style="animation-delay: 0.2s">
            <div class="service-icon">🏦</div>
            <h3>Épargne</h3>
            <p>Produits d'épargne sécurisés pour constituer votre patrimoine progressivement avec des rendements attractifs.</p>
            <router-link to="/services" class="service-link">En savoir plus →</router-link>
          </div>

          <div class="service-item fade-in-up" style="animation-delay: 0.3s">
            <div class="service-icon">📱</div>
            <h3>Services Numériques</h3>
            <p>Accès mobile et digital pour gérer vos finances facilement, en toute sécurité et à tout moment.</p>
            <router-link to="/services" class="service-link">En savoir plus →</router-link>
          </div>

          <div class="service-item fade-in-up" style="animation-delay: 0.4s">
            <div class="service-icon">📚</div>
            <h3>Formation</h3>
            <p>Programme d'éducation financière pour renforcer vos compétences de gestion et de planification économique.</p>
            <router-link to="/services" class="service-link">En savoir plus →</router-link>
          </div>
        </div>

        <div class="section-cta">
          <router-link to="/services" class="btn btn-primary btn-large">Tous nos services</router-link>
        </div>
      </div>
    </section>

    <!-- Highlighted Events Section -->
    <section class="section featured-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Événements & Actualités</h2>
          <p class="section-subtitle">Découvrez nos actualités et nos initiatives pour l'inclusion financière</p>
        </div>

        <div class="featured-grid">
          <article class="featured-card fade-in-up" style="animation-delay: 0.1s">
            <div class="featured-image">
              <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?w=500&h=300&fit=crop" alt="Événement microfinance">
              <span class="featured-tag">Événement</span>
            </div>
            <div class="featured-content">
              <h3>Séminaire Microfinance 2025</h3>
              <p class="featured-date">📅 15 janvier 2025</p>
              <p>Rejoignez-nous pour un séminaire sur les dernières innovations en microfinance et inclusion financière.</p>
              <router-link to="/actualites" class="read-more">Lire la suite →</router-link>
            </div>
          </article>

          <article class="featured-card fade-in-up" style="animation-delay: 0.2s">
            <div class="featured-image">
              <img src="https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?w=500&h=300&fit=crop" alt="Formation financière">
              <span class="featured-tag featured-tag-formation">Formation</span>
            </div>
            <div class="featured-content">
              <h3>Atelier Formation Financière</h3>
              <p class="featured-date">📅 22 janvier 2025</p>
              <p>Apprenez les principes fondamentaux de la gestion financière personnelle et entrepreneuriale.</p>
              <router-link to="/actualites" class="read-more">Lire la suite →</router-link>
            </div>
          </article>

          <article class="featured-card fade-in-up" style="animation-delay: 0.3s">
            <div class="featured-image">
              <img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=500&h=300&fit=crop" alt="Technologie financière">
              <span class="featured-tag featured-tag-tech">Technologie</span>
            </div>
            <div class="featured-content">
              <h3>Lancement Plateforme Digitale</h3>
              <p class="featured-date">📅 30 janvier 2025</p>
              <p>Découvrez notre nouvelle plateforme numérique pour accéder à tous nos services en un seul clic.</p>
              <router-link to="/actualites" class="read-more">Lire la suite →</router-link>
            </div>
          </article>
        </div>

        <div class="section-cta">
          <router-link to="/actualites" class="btn btn-primary">Tous nos événements</router-link>
          <a href="#" class="btn btn-outline">Télécharger le programme</a>
        </div>
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
            <p>Nous facilitons l'accès des populations défavorisées et exclues du système bancaire classique aux services financiers et non financiers, en mettant l'accent sur l'éducation et l'accompagnement.</p>
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
              <div class="placeholder-icon">🎯</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- News Section -->
    <section class="section news-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Actualités du Réseau</h2>
          <p class="section-subtitle">Restez informé de nos dernières actualités et innovations</p>
        </div>

        <div class="news-grid">
          <article class="news-card fade-in-up" style="animation-delay: 0.1s">
            <div class="news-meta">
              <span class="news-category">Microfinance</span>
              <span class="news-date">5 jan 2025</span>
            </div>
            <h3>Expansion de PAIDEKSA dans le Kasai</h3>
            <p>Nous sommes fiers d'annoncer l'ouverture de deux nouveaux centres de microfinance dans la région du Kasai pour renforcer notre présence.</p>
            <router-link to="/actualites" class="read-more">Lire la suite →</router-link>
          </article>

          <article class="news-card fade-in-up" style="animation-delay: 0.2s">
            <div class="news-meta">
              <span class="news-category">Éducation</span>
              <span class="news-date">2 jan 2025</span>
            </div>
            <h3>1000 entrepreneurs formés en 2024</h3>
            <p>Notre programme de formation a permis à plus de 1000 entrepreneurs de développer leurs compétences en gestion financière.</p>
            <router-link to="/actualites" class="read-more">Lire la suite →</router-link>
          </article>

          <article class="news-card fade-in-up" style="animation-delay: 0.3s">
            <div class="news-meta">
              <span class="news-category">Technologie</span>
              <span class="news-date">28 déc 2024</span>
            </div>
            <h3>App mobile PAIDEKSA bientôt disponible</h3>
            <p>Notre nouvelle application mobile facilitera l'accès aux services financiers en un seul clic, partout en RDC.</p>
            <router-link to="/actualites" class="read-more">Lire la suite →</router-link>
          </article>
        </div>

        <div class="section-cta">
          <router-link to="/actualites" class="btn btn-primary">Voir plus d'actualités</router-link>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section class="section cta-section">
      <div class="container">
        <div class="cta-content fade-in-up">
          <h2>Prêt à Commencer ?</h2>
          <p>Rejoignez des milliers de clients qui ont transformé leur vie financière</p>
          <router-link to="/contact" class="btn btn-secondary btn-large">Nous Contacter Maintenant</router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlideIndex = ref(0)
const autoplayInterval = ref(null)

const carouselSlides = [
  {
    image: 'https://images.unsplash.com/photo-1556740738-b6a63e27c4df?w=800&h=500&fit=crop',
    title: 'Services Financiers Accessibles',
    description: 'Nous rendons les services financiers accessibles à tous, indépendamment de votre situation économique.'
  },
  {
    image: 'https://images.unsplash.com/photo-1552664730-d307ca884978?w=800&h=500&fit=crop',
    title: 'Croissance Économique',
    description: 'Soutenez la croissance de votre entreprise avec nos solutions de financement adaptées.'
  },
  {
    image: 'https://images.unsplash.com/photo-1554224311-beee415c15c7?w=800&h=500&fit=crop',
    title: 'Sécurité et Confiance',
    description: 'Vos fonds sont sécurisés avec nos protocoles de sécurité avancés et notre transparence garantie.'
  },
  {
    image: 'https://images.unsplash.com/photo-1460925895917-adf4e5a30916?w=800&h=500&fit=crop',
    title: 'Formation Financière',
    description: 'Éduquez-vous et développez vos compétences en gestion financière avec nos programmes gratuits.'
  },
  {
    image: 'https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800&h=500&fit=crop',
    title: 'Technologie Moderne',
    description: 'Accédez à nos services via notre plateforme digitale innovante et facile à utiliser.'
  }
]

const nextSlide = () => {
  currentSlideIndex.value = (currentSlideIndex.value + 1) % carouselSlides.length
  resetAutoplay()
}

const prevSlide = () => {
  currentSlideIndex.value = (currentSlideIndex.value - 1 + carouselSlides.length) % carouselSlides.length
  resetAutoplay()
}

const goToSlide = (index) => {
  currentSlideIndex.value = index
  resetAutoplay()
}

const startAutoplay = () => {
  autoplayInterval.value = setInterval(() => {
    nextSlide()
  }, 5000)
}

const stopAutoplay = () => {
  if (autoplayInterval.value) {
    clearInterval(autoplayInterval.value)
  }
}

const resetAutoplay = () => {
  stopAutoplay()
  startAutoplay()
}

onMounted(() => {
  startAutoplay()
})

onUnmounted(() => {
  stopAutoplay()
})
</script>

<style scoped>
.home {
  width: 100%;
}

/* Hero Section */
.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: var(--spacing-3xl);
  padding: var(--spacing-4xl) var(--spacing-md);
  min-height: 100vh;
  position: relative;
  overflow: hidden;
}

.hero-carousel-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
  text-align: center;
  max-width: 800px;
}

.hero-content h1 {
  font-size: var(--text-5xl);
  line-height: var(--line-height-tight);
  color: white;
  margin-bottom: var(--spacing-lg);
  text-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
}

.hero-subtitle {
  font-size: var(--text-xl);
  color: rgba(255, 255, 255, 0.95);
  margin-bottom: var(--spacing-2xl);
  line-height: var(--line-height-relaxed);
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
}

.hero-buttons {
  display: flex;
  gap: var(--spacing-lg);
  flex-wrap: wrap;
  justify-content: center;
}

/* Carousel Styles in Hero */
.carousel-slides {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}

.carousel-slide {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity var(--transition-slow);
}

.carousel-slide.active {
  opacity: 1;
  z-index: 1;
}

.slide-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.carousel-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, rgba(27, 58, 110, 0.5) 0%, rgba(0, 0, 0, 0.6) 100%);
  z-index: 1;
}

.carousel-btn {
  background: rgba(255, 255, 255, 0.2);
  border: 2px solid white;
  color: white;
  font-size: var(--text-2xl);
  width: 50px;
  height: 50px;
  border-radius: var(--radius-full);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all var(--transition-base);
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 5;
  font-weight: var(--font-bold);
}

.carousel-btn.prev {
  left: var(--spacing-xl);
}

.carousel-btn.next {
  right: var(--spacing-xl);
}

.carousel-btn:hover {
  background: rgba(255, 255, 255, 0.4);
  transform: translateY(-50%) scale(1.1);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
}

.carousel-indicators {
  position: absolute;
  bottom: var(--spacing-2xl);
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  justify-content: center;
  gap: var(--spacing-md);
  z-index: 5;
  flex-wrap: wrap;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: var(--radius-full);
  background: rgba(255, 255, 255, 0.4);
  border: 2px solid white;
  cursor: pointer;
  transition: all var(--transition-base);
}

.indicator.active {
  background: white;
  width: 24px;
  border-radius: var(--radius-md);
}

.indicator:hover {
  background: rgba(255, 255, 255, 0.7);
  transform: scale(1.2);
}

/* Services Section - IFRDC Style */
.services-section {
  background-color: var(--bg-white);
}

.section-header {
  text-align: center;
  margin-bottom: var(--spacing-3xl);
}

.section-title {
  font-size: var(--text-4xl);
  color: var(--primary);
  margin-bottom: var(--spacing-lg);
  font-weight: var(--font-bold);
  position: relative;
  display: inline-block;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 3px;
  background: var(--secondary);
  border-radius: var(--radius-full);
}

.section-subtitle {
  font-size: var(--text-lg);
  color: var(--text-light);
  max-width: 600px;
  margin: var(--spacing-xl) auto 0;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--spacing-2xl);
  margin-bottom: var(--spacing-2xl);
}

.service-item {
  background: white;
  padding: var(--spacing-2xl);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
  text-align: center;
  border-top: 4px solid var(--secondary);
}

.service-item:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-lg);
}

.service-icon {
  font-size: 3.5rem;
  margin-bottom: var(--spacing-lg);
  display: block;
}

.service-item h3 {
  font-size: var(--text-xl);
  color: var(--primary);
  margin-bottom: var(--spacing-md);
  font-weight: var(--font-bold);
}

.service-item p {
  color: var(--text-light);
  line-height: var(--line-height-normal);
  margin-bottom: var(--spacing-lg);
}

.service-link {
  color: var(--secondary);
  text-decoration: none;
  font-weight: var(--font-semibold);
  transition: color var(--transition-base);
}

.service-link:hover {
  color: var(--secondary-dark);
}

.section-cta {
  text-align: center;
  margin-top: var(--spacing-2xl);
}

/* Featured Events Section */
.featured-section {
  background-color: var(--bg-light);
}

.featured-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--spacing-2xl);
  margin-bottom: var(--spacing-2xl);
}

.featured-card {
  background: white;
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
}

.featured-card:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-lg);
}

.featured-image {
  position: relative;
  height: 250px;
  overflow: hidden;
}

.featured-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--transition-base);
}

.featured-card:hover .featured-image img {
  transform: scale(1.1);
}

.featured-tag {
  position: absolute;
  top: var(--spacing-lg);
  right: var(--spacing-lg);
  background: var(--primary);
  color: white;
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--radius-full);
  font-size: var(--text-sm);
  font-weight: var(--font-semibold);
}

.featured-tag-formation {
  background: var(--secondary);
}

.featured-tag-tech {
  background: var(--info);
}

.featured-content {
  padding: var(--spacing-2xl);
}

.featured-content h3 {
  font-size: var(--text-xl);
  color: var(--primary);
  margin-bottom: var(--spacing-md);
  font-weight: var(--font-bold);
}

.featured-date {
  color: var(--text-light);
  font-size: var(--text-sm);
  margin-bottom: var(--spacing-md);
}

.featured-content p {
  color: var(--text-light);
  line-height: var(--line-height-normal);
  margin-bottom: var(--spacing-lg);
}

.read-more {
  color: var(--secondary);
  text-decoration: none;
  font-weight: var(--font-semibold);
  transition: color var(--transition-base);
}

.read-more:hover {
  color: var(--secondary-dark);
}

/* Stats Section */
.stats-section {
  background-color: white;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: var(--spacing-lg);
}

.stat-card {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
  padding: var(--spacing-2xl);
  border-radius: var(--radius-lg);
  text-align: center;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
}

.stat-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-lg);
}

.stat-number {
  font-size: var(--text-4xl);
  font-weight: var(--font-bold);
  margin-bottom: var(--spacing-md);
}

.stat-label {
  font-size: var(--text-base);
  font-weight: var(--font-medium);
  opacity: 0.95;
}

/* About Section */
.about-section {
  background-color: var(--bg-white);
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--spacing-3xl);
  align-items: center;
}

.about-content h2 {
  font-size: var(--text-4xl);
  margin-bottom: var(--spacing-lg);
}

.about-content p {
  font-size: var(--text-lg);
  margin-bottom: var(--spacing-lg);
  color: var(--text-light);
  line-height: var(--line-height-relaxed);
}

.features-list {
  list-style: none;
  margin: var(--spacing-2xl) 0;
  padding: 0;
}

.features-list li {
  padding: var(--spacing-md) 0;
  color: var(--text-dark);
  font-weight: var(--font-medium);
}

.image-placeholder {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  border-radius: var(--radius-lg);
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: var(--shadow-lg);
}

.placeholder-icon {
  font-size: 5rem;
}

/* News Section */
.news-section {
  background-color: var(--bg-light);
}

.news-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--spacing-2xl);
  margin-bottom: var(--spacing-2xl);
}

.news-card {
  background: white;
  padding: var(--spacing-2xl);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
  border-left: 4px solid var(--secondary);
}

.news-card:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-lg);
}

.news-meta {
  display: flex;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-md);
}

.news-category {
  display: inline-block;
  background: var(--primary);
  color: white;
  padding: 4px 12px;
  border-radius: var(--radius-full);
  font-size: var(--text-xs);
  font-weight: var(--font-semibold);
}

.news-date {
  color: var(--text-light);
  font-size: var(--text-sm);
  display: flex;
  align-items: center;
}

.news-card h3 {
  font-size: var(--text-xl);
  color: var(--primary);
  margin-bottom: var(--spacing-md);
  font-weight: var(--font-bold);
}

.news-card p {
  color: var(--text-light);
  line-height: var(--line-height-normal);
  margin-bottom: var(--spacing-lg);
}

/* CTA Section */
.cta-section {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
  text-align: center;
}

.cta-content {
  padding: var(--spacing-3xl) var(--spacing-2xl);
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

/* Button Styles */
.btn {
  display: inline-block;
  padding: var(--spacing-md) var(--spacing-2xl);
  border-radius: var(--radius-md);
  text-decoration: none;
  font-weight: var(--font-semibold);
  transition: all var(--transition-base);
  border: 2px solid transparent;
  cursor: pointer;
  font-size: var(--text-base);
  text-align: center;
}

.btn-primary {
  background: var(--primary);
  color: white;
}

.btn-primary:hover {
  background: var(--primary-dark);
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

.btn-secondary {
  background: var(--secondary);
  color: white;
}

.btn-secondary:hover {
  background: var(--secondary-dark);
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

.btn-outline {
  background: transparent;
  color: var(--primary);
  border-color: var(--primary);
}

.btn-outline:hover {
  background: var(--primary);
  color: white;
}

.btn-large {
  padding: var(--spacing-lg) var(--spacing-3xl);
  font-size: var(--text-lg);
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero {
    padding: var(--spacing-2xl);
    min-height: auto;
    padding-top: 200px;
  }

  .hero-content {
    width: 100%;
  }

  .hero-content h1 {
    font-size: var(--text-3xl);
  }

  .hero-subtitle {
    font-size: var(--text-base);
  }

  .hero-buttons {
    flex-direction: column;
    gap: var(--spacing-md);
  }

  .btn {
    width: 100%;
  }

  .carousel-btn {
    width: 40px;
    height: 40px;
    font-size: var(--text-lg);
  }

  .carousel-btn.prev {
    left: var(--spacing-md);
  }

  .carousel-btn.next {
    right: var(--spacing-md);
  }

  .carousel-indicators {
    bottom: var(--spacing-lg);
    gap: var(--spacing-sm);
  }

  .indicator {
    width: 10px;
    height: 10px;
  }

  .indicator.active {
    width: 20px;
  }

  .section-title {
    font-size: var(--text-2xl);
  }

  .section-subtitle {
    font-size: var(--text-base);
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: var(--spacing-lg);
  }

  .featured-grid {
    grid-template-columns: 1fr;
  }

  .featured-image {
    height: 200px;
  }

  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: var(--spacing-md);
  }

  .stat-card {
    padding: var(--spacing-lg);
  }

  .stat-number {
    font-size: var(--text-2xl);
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

  .news-grid {
    grid-template-columns: 1fr;
  }

  .cta-content h2 {
    font-size: var(--text-2xl);
  }
}
</style>
