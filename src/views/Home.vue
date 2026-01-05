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
        <p class="hero-subtitle">Accès aux services financiers pour les populations défavorisées de la RDC</p>
        <div class="hero-buttons">
          <router-link to="/services" class="btn btn-primary">Nos Services</router-link>
          <router-link to="/contact" class="btn btn-secondary">Nous Contacter</router-link>
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

    <!-- Partners Section -->
    <section class="section partners-section">
      <div class="container">
        <h2 class="section-title">Nos Partenaires</h2>
        <div class="partners-grid">
          <div class="partner-card fade-in-up" style="animation-delay: 0.1s">
            <div class="partner-logo">🏛️</div>
            <h3>Gouvernement RDC</h3>
            <p>En partenariat avec les autorités gouvernementales pour l'inclusion financière</p>
          </div>
          <div class="partner-card fade-in-up" style="animation-delay: 0.2s">
            <div class="partner-logo">🏦</div>
            <h3>Banque Centrale</h3>
            <p>Collaboration pour la régulation et le développement du secteur financier</p>
          </div>
          <div class="partner-card fade-in-up" style="animation-delay: 0.3s">
            <div class="partner-logo">🤝</div>
            <h3>ONG Locales</h3>
            <p>Travail conjoint avec les organisations locales pour le développement communautaire</p>
          </div>
          <div class="partner-card fade-in-up" style="animation-delay: 0.4s">
            <div class="partner-logo">🌍</div>
            <h3>Partenaires Internationaux</h3>
            <p>Soutien des institutions financières internationales pour la croissance</p>
          </div>
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
  }, 5000) // Change slide every 5 seconds
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
.hero-carousel-wrapper {
  display: flex;
  align-items: center;
  position: absolute;
  width: 100%;
  height: 100%;
}

.carousel-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, rgba(0, 121, 107, 0.4) 0%, rgba(0, 0, 0, 0.6) 100%);
  z-index: 1;
}

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

/* Carousel Indicators */
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

/* Carousel Section */
.carousel-section {
  background-color: var(--bg-light);
  padding: var(--spacing-3xl) 0;
}

.carousel-container {
  display: flex;
  align-items: center;
  gap: var(--spacing-lg);
  position: relative;
}

.carousel-wrapper {
  flex: 1;
  overflow: hidden;
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-lg);
  height: 500px;
  position: relative;
  background: white;
}

.carousel-slides {
  position: relative;
  width: 100%;
  height: 100%;
}

.carousel-slide {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity var(--transition-slow);
  display: flex;
  align-items: flex-end;
  background: white;
}

.carousel-slide.active {
  opacity: 1;
  z-index: 10;
}

.slide-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: 1;
}

.slide-content {
  position: relative;
  z-index: 2;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
  width: 100%;
  padding: var(--spacing-2xl);
  color: white;
  text-align: left;
}

.slide-content h3 {
  font-size: var(--text-2xl);
  margin-bottom: var(--spacing-md);
  color: white;
}

.slide-content p {
  font-size: var(--text-lg);
  color: rgba(255, 255, 255, 0.9);
  line-height: var(--line-height-normal);
}

.carousel-btn {
  background: white;
  border: 2px solid var(--primary);
  color: var(--primary);
  font-size: var(--text-2xl);
  width: 50px;
  height: 50px;
  border-radius: var(--radius-full);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all var(--transition-base);
  flex-shrink: 0;
  font-weight: var(--font-bold);
}

.carousel-btn:hover {
  background: var(--primary);
  color: white;
  transform: scale(1.1);
  box-shadow: var(--shadow-md);
}

.carousel-btn.prev {
  order: -1;
}

/* Carousel Indicators */
.carousel-indicators {
  display: flex;
  justify-content: center;
  gap: var(--spacing-md);
  margin-top: var(--spacing-xl);
  flex-wrap: wrap;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: var(--radius-full);
  background: var(--border-color);
  border: 2px solid var(--primary);
  cursor: pointer;
  transition: all var(--transition-base);
}

.indicator.active {
  background: var(--primary);
  width: 24px;
  border-radius: var(--radius-md);
}

.indicator:hover {
  transform: scale(1.2);
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

/* Partners Section */
.partners-section {
  background-color: white;
}

.partners-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-lg);
}

.partner-card {
  background: white;
  padding: var(--spacing-2xl);
  border-radius: var(--radius-lg);
  text-align: center;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
  border-left: 4px solid transparent;
}

.partner-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-lg);
  border-left-color: var(--primary);
}

.partner-logo {
  font-size: 3.5rem;
  margin-bottom: var(--spacing-lg);
  display: block;
  transition: transform var(--transition-base);
}

.partner-card:hover .partner-logo {
  transform: scale(1.15);
}

.partner-card h3 {
  font-size: var(--text-xl);
  margin-bottom: var(--spacing-md);
  color: var(--primary);
}

.partner-card p {
  color: var(--text-light);
  line-height: var(--line-height-normal);
  margin: 0;
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
    text-align: center;
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

  .partners-grid {
    grid-template-columns: 1fr;
  }

  .cta-content h2 {
    font-size: var(--text-2xl);
  }
}
</style>
