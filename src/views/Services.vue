<template>
  <div class="services">
    <!-- Page Header -->
    <section class="page-header">
      <div class="container">
        <h1 class="fade-in-up">Nos Services</h1>
        <p class="fade-in-up">Solutions financières adaptées à vos besoins</p>
      </div>
    </section>

    <!-- Services Grid -->
    <section class="section services-section">
      <div class="container">
        <div class="services-grid">
          <div 
            v-for="(service, index) in services"
            :key="index"
            class="service-card fade-in-up"
            :style="{ animationDelay: `${index * 0.1}s` }"
          >
            <div class="service-header">
              <span class="service-icon">{{ service.icon }}</span>
              <h2>{{ service.title }}</h2>
            </div>
            <p class="service-description">{{ service.description }}</p>
            <ul class="service-features">
              <li v-for="(feature, i) in service.features" :key="i">
                <span class="feature-icon">✓</span> {{ feature }}
              </li>
            </ul>
            <button class="btn btn-primary">En Savoir Plus</button>
          </div>
        </div>
      </div>
    </section>

    <!-- Service Categories -->
    <section class="section categories-section">
      <div class="container">
        <h2 class="section-title">Catégories de Services</h2>
        <div class="categories-grid">
          <div class="category-card fade-in-up" style="animation-delay: 0.1s">
            <div class="category-header primary">
              <span class="category-icon">💰</span>
              <h3>Financement</h3>
            </div>
            <div class="category-body">
              <ul>
                <li>Microcrédits</li>
                <li>Crédits productifs</li>
                <li>Crédits à la consommation</li>
                <li>Lignes de crédit</li>
              </ul>
            </div>
          </div>

          <div class="category-card fade-in-up" style="animation-delay: 0.2s">
            <div class="category-header success">
              <span class="category-icon">💳</span>
              <h3>Paiements</h3>
            </div>
            <div class="category-body">
              <ul>
                <li>Transferts d'argent</li>
                <li>Paiements en ligne</li>
                <li>Comptes courants</li>
                <li>Cartes de débit</li>
              </ul>
            </div>
          </div>

          <div class="category-card fade-in-up" style="animation-delay: 0.3s">
            <div class="category-header warning">
              <span class="category-icon">🏦</span>
              <h3>Épargne & Placements</h3>
            </div>
            <div class="category-body">
              <ul>
                <li>Comptes d'épargne</li>
                <li>Dépôts à terme</li>
                <li>Plans d'épargne</li>
                <li>Titres sécurisés</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Why Choose Us -->
    <section class="section why-section">
      <div class="container">
        <h2 class="section-title">Pourquoi Nous Choisir ?</h2>
        <div class="why-grid">
          <div class="why-card fade-in-up" style="animation-delay: 0.1s">
            <div class="why-icon">🎯</div>
            <h3>Accessibilité</h3>
            <p>Nous offrons des services financiers accessibles à tous les segments de la population, sans discrimination.</p>
          </div>
          <div class="why-card fade-in-up" style="animation-delay: 0.2s">
            <div class="why-icon">💡</div>
            <h3>Innovation</h3>
            <p>Solutions technologiques modernes pour faciliter vos transactions et gérer vos finances.</p>
          </div>
          <div class="why-card fade-in-up" style="animation-delay: 0.3s">
            <div class="why-icon">🤝</div>
            <h3>Proximité</h3>
            <p>Nos agents présents dans vos localités pour un suivi personnalisé et une assistance quotidienne.</p>
          </div>
          <div class="why-card fade-in-up" style="animation-delay: 0.4s">
            <div class="why-icon">⚡</div>
            <h3>Rapidité</h3>
            <p>Procédures simplifiées pour un traitement rapide de vos demandes.</p>
          </div>
          <div class="why-card fade-in-up" style="animation-delay: 0.5s">
            <div class="why-icon">🔒</div>
            <h3>Sécurité</h3>
            <p>Vos fonds et données sont protégés par les normes les plus strictes de sécurité.</p>
          </div>
          <div class="why-card fade-in-up" style="animation-delay: 0.6s">
            <div class="why-icon">📚</div>
            <h3>Formation</h3>
            <p>Programmes d'éducation financière pour renforcer votre autonomie économique.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Pricing Section -->
    <section class="section pricing-section">
      <div class="container">
        <h2 class="section-title">Tarification Simple & Transparente</h2>
        <p class="pricing-intro">Nos frais sont clairs et sans frais cachés. Découvrez nos tarifs avantageux.</p>
        <div class="pricing-grid">
          <div class="pricing-card fade-in-up" style="animation-delay: 0.1s">
            <div class="pricing-header">
              <h3>Services Basiques</h3>
              <p class="price">Gratuit</p>
            </div>
            <ul class="pricing-features">
              <li>✓ Ouverture de compte</li>
              <li>✓ Consultation de solde</li>
              <li>✓ 5 retraits/mois</li>
              <li>✗ Carnet de chèques</li>
            </ul>
          </div>

          <div class="pricing-card featured fade-in-up" style="animation-delay: 0.2s">
            <div class="pricing-header">
              <h3>Services Premium</h3>
              <p class="price">2 500 FC</p>
              <span class="price-period">/ mois</span>
            </div>
            <ul class="pricing-features">
              <li>✓ Ouverture de compte</li>
              <li>✓ Retraits illimités</li>
              <li>✓ Carnet de chèques</li>
              <li>✓ Assurance compte</li>
            </ul>
            <button class="btn btn-primary">S'inscrire</button>
          </div>

          <div class="pricing-card fade-in-up" style="animation-delay: 0.3s">
            <div class="pricing-header">
              <h3>Services Professionnels</h3>
              <p class="price">Sur Devis</p>
            </div>
            <ul class="pricing-features">
              <li>✓ Crédit professionnel</li>
              <li>✓ Gestion d'actifs</li>
              <li>✓ Conseil financier</li>
              <li>✓ Support dédié</li>
            </ul>
            <button class="btn btn-secondary">Demander un Devis</button>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA -->
    <section class="section cta-section">
      <div class="container">
        <div class="cta-content fade-in-up">
          <h2>Démarrez Votre Parcours Financier</h2>
          <p>Rejoignez des milliers de clients satisfaits</p>
          <router-link to="/contact" class="btn btn-secondary">Nous Contacter</router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { reactive } from 'vue'

const services = reactive([
  {
    title: 'Microfinance',
    icon: '💰',
    description: 'Solutions de financement adaptées aux petits entrepreneurs et micro-entreprises.',
    features: [
      'Montants flexibles de 100 000 à 10 000 000 FC',
      'Taux d\'intérêt compétitif',
      'Délais de remboursement adaptés',
      'Procédure rapide et simplifiée'
    ]
  },
  {
    title: 'Épargne & Dépôts',
    icon: '🏦',
    description: 'Produits d\'épargne sécurisés pour constituer votre patrimoine.',
    features: [
      'Taux d\'intérêt attractifs',
      'Liquidité garantie',
      'Assurance des dépôts',
      'Accès facile à vos fonds'
    ]
  },
  {
    title: 'Services Numériques',
    icon: '📱',
    description: 'Gestion de vos finances depuis votre téléphone ou ordinateur.',
    features: [
      'Application mobile sécurisée',
      'Virement instantané',
      'Consultation 24h/24',
      'Support technique permanent'
    ]
  },
  {
    title: 'Assurances',
    icon: '🛡️',
    description: 'Protection de vos économies et de votre famille.',
    features: [
      'Assurance compte courant',
      'Assurance crédit',
      'Assurance vie',
      'Couverture accidents'
    ]
  },
  {
    title: 'Conseil Financier',
    icon: '📊',
    description: 'Accompagnement personnalisé dans vos décisions financières.',
    features: [
      'Plans d\'épargne personnalisés',
      'Gestion budgétaire',
      'Investissements sécurisés',
      'Planification financière'
    ]
  },
  {
    title: 'Éducation Financière',
    icon: '📚',
    description: 'Formations pour améliorer vos compétences en gestion financière.',
    features: [
      'Ateliers gratuits',
      'Webinaires en ligne',
      'Ressources éducatives',
      'Certification financière'
    ]
  }
])
</script>

<style scoped>
.services {
  width: 100%;
}

/* Page Header */
.page-header {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
  padding: 80px 0;
  text-align: center;
}

.page-header h1 {
  font-size: 3rem;
  margin-bottom: 15px;
}

.page-header p {
  font-size: 1.3rem;
  opacity: 0.95;
}

/* Services Grid */
.services-section {
  background-color: var(--bg-light);
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 30px;
}

.service-card {
  background: white;
  padding: 40px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
}

.service-card:hover {
  transform: translateY(-15px);
  box-shadow: 0 15px 40px rgba(0, 121, 107, 0.2);
}

.service-header {
  margin-bottom: 20px;
}

.service-icon {
  font-size: 2.5rem;
  display: block;
  margin-bottom: 15px;
}

.service-card h2 {
  color: var(--primary);
  font-size: 1.4rem;
  margin: 0;
}

.service-description {
  color: var(--text-light);
  margin: 15px 0 20px;
  line-height: 1.6;
  flex-grow: 1;
}

.service-features {
  list-style: none;
  margin: 20px 0;
}

.service-features li {
  padding: 8px 0;
  color: var(--text-dark);
  display: flex;
  align-items: center;
  gap: 10px;
}

.feature-icon {
  color: var(--success);
  font-weight: bold;
}

.service-card .btn {
  margin-top: auto;
}

/* Categories Section */
.categories-section {
  background-color: white;
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.category-card {
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.category-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.15);
}

.category-header {
  padding: 30px;
  color: white;
  display: flex;
  align-items: center;
  gap: 15px;
}

.category-header.primary {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
}

.category-header.success {
  background: linear-gradient(135deg, var(--success) 0%, #4caf50 100%);
}

.category-header.warning {
  background: linear-gradient(135deg, var(--secondary) 0%, var(--warning) 100%);
}

.category-icon {
  font-size: 2rem;
}

.category-header h3 {
  margin: 0;
  font-size: 1.3rem;
}

.category-body {
  padding: 25px;
  background: var(--bg-light);
}

.category-body ul {
  list-style: none;
}

.category-body li {
  padding: 8px 0;
  color: var(--text-dark);
  border-bottom: 1px solid var(--border-color);
}

.category-body li:last-child {
  border-bottom: none;
}

/* Why Choose Us */
.why-section {
  background-color: var(--bg-light);
}

.why-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.why-card {
  background: white;
  padding: 40px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.why-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 12px 30px rgba(0, 121, 107, 0.2);
}

.why-icon {
  font-size: 3rem;
  margin-bottom: 15px;
  display: block;
}

.why-card h3 {
  color: var(--primary);
  font-size: 1.2rem;
  margin-bottom: 10px;
}

.why-card p {
  color: var(--text-light);
  line-height: 1.6;
  margin: 0;
}

/* Pricing Section */
.pricing-section {
  background-color: white;
}

.pricing-intro {
  text-align: center;
  font-size: 1.1rem;
  color: var(--text-light);
  margin-bottom: 40px;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.pricing-card {
  background: white;
  border: 2px solid var(--border-color);
  padding: 40px;
  border-radius: 12px;
  text-align: center;
  transition: all 0.3s ease;
}

.pricing-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 12px 30px rgba(0, 121, 107, 0.2);
}

.pricing-card.featured {
  border-color: var(--primary);
  background: linear-gradient(135deg, rgba(0, 121, 107, 0.05) 0%, rgba(0, 121, 107, 0.1) 100%);
  transform: translateY(-20px);
}

.pricing-card.featured:hover {
  transform: translateY(-30px);
}

.pricing-header h3 {
  color: var(--primary);
  font-size: 1.5rem;
  margin-bottom: 15px;
}

.price {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--secondary);
  margin: 0;
}

.price-period {
  font-size: 0.9rem;
  color: var(--text-light);
}

.pricing-features {
  list-style: none;
  margin: 30px 0;
  text-align: left;
}

.pricing-features li {
  padding: 12px 0;
  border-bottom: 1px solid var(--border-color);
  color: var(--text-dark);
}

.pricing-features li:last-child {
  border-bottom: none;
}

.pricing-card .btn {
  width: 100%;
  margin-top: 20px;
}

/* CTA Section */
.cta-section {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
  text-align: center;
}

.cta-content h2 {
  font-size: 2.5rem;
  margin-bottom: 15px;
  color: white;
}

.cta-content p {
  font-size: 1.2rem;
  margin-bottom: 30px;
  opacity: 0.95;
}

@media (max-width: 768px) {
  .page-header h1 {
    font-size: 2.5rem;
  }

  .services-grid {
    grid-template-columns: 1fr;
  }

  .pricing-card.featured {
    transform: none;
  }

  .pricing-card.featured:hover {
    transform: translateY(-10px);
  }

  .cta-content h2 {
    font-size: 2rem;
  }
}
</style>
