<template>
  <div class="news">
    <!-- Page Header -->
    <section class="page-header">
      <div class="container">
        <h1 class="animate-fadeInUp">Actualités</h1>
        <p class="animate-fadeInUp">Suivez les dernières nouvelles et événements de PAIDEKSA</p>
      </div>
    </section>

    <!-- Filter Section -->
    <section class="section filter-section">
      <div class="container">
        <div class="filters">
          <button 
            v-for="category in categories"
            :key="category"
            :class="['filter-btn', { active: activeCategory === category }]"
            @click="activeCategory = category"
          >
            {{ category }}
          </button>
        </div>
      </div>
    </section>

    <!-- News Grid -->
    <section class="section news-grid-section">
      <div class="container">
        <div class="news-grid">
          <article 
            v-for="(article, index) in filteredArticles"
            :key="index"
            class="news-card animate-fadeInUp"
            :style="{ animationDelay: `${index * 0.1}s` }"
          >
            <div class="news-image">
              <div class="image-placeholder">{{ article.icon }}</div>
              <span class="category-badge">{{ article.category }}</span>
            </div>
            <div class="news-content">
              <div class="news-meta">
                <span class="date">{{ article.date }}</span>
                <span class="reading-time">{{ article.readTime }} min</span>
              </div>
              <h3>{{ article.title }}</h3>
              <p>{{ article.excerpt }}</p>
              <a href="#" class="read-more">Lire la suite →</a>
            </div>
          </article>
        </div>

        <div v-if="filteredArticles.length === 0" class="no-articles">
          <p>Aucun article dans cette catégorie pour le moment.</p>
        </div>
      </div>
    </section>

    <!-- Newsletter Section -->
    <section class="section newsletter-section">
      <div class="container-sm">
        <h2 class="section-title">Restez Informé</h2>
        <p class="text-center text-light mb-lg">Recevez nos actualités directement dans votre boîte mail</p>
        <form @submit.prevent="subscribeNewsletter" class="newsletter-form">
          <input 
            v-model="newsletter.email"
            type="email" 
            placeholder="Votre adresse email"
            required
          >
          <button type="submit" class="btn btn-primary">S'inscrire</button>
        </form>
        <p v-if="newsletter.message" :class="['newsletter-message', newsletter.status]">
          {{ newsletter.message }}
        </p>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const activeCategory = ref('Tous')

const categories = ['Tous', 'Finance', 'Événements', 'Conseils', 'Actualité']

const articles = [
  {
    title: '5 astuces pour gérer votre épargne efficacement',
    excerpt: 'Découvrez nos conseils pratiques pour optimiser votre épargne et atteindre vos objectifs financiers.',
    category: 'Conseils',
    date: '3 janvier 2026',
    readTime: 5,
    icon: '💰'
  },
  {
    title: 'Lancement du programme de microcrédit pour PME',
    excerpt: 'PAIDEKSA annonce le lancement d\'un nouveau programme de financement destiné aux petites et moyennes entreprises.',
    category: 'Finance',
    date: '2 janvier 2026',
    readTime: 4,
    icon: '📈'
  },
  {
    title: 'Forum annuel de l\'inclusion financière',
    excerpt: 'Rejoignez-nous pour notre grand forum annuel où experts et entrepreneurs partagent leurs expériences.',
    category: 'Événements',
    date: '1er janvier 2026',
    readTime: 6,
    icon: '🎤'
  },
  {
    title: 'Comment demander un crédit chez PAIDEKSA',
    excerpt: 'Guide complet pour comprendre les étapes et les conditions pour obtenir un crédit auprès de nos services.',
    category: 'Conseils',
    date: '30 décembre 2025',
    readTime: 7,
    icon: '📋'
  },
  {
    title: 'Bilan 2025 : 50 000 clients satisfaits',
    excerpt: 'Retour sur une année riche en succès avec nos clients à travers les trois provinces du Kivu.',
    category: 'Actualité',
    date: '28 décembre 2025',
    readTime: 8,
    icon: '🏆'
  },
  {
    title: 'Nouvelle application mobile PAIDEKSA disponible',
    excerpt: 'Téléchargez notre toute nouvelle application pour gérer votre compte en toute facilité depuis votre téléphone.',
    category: 'Finance',
    date: '25 décembre 2025',
    readTime: 5,
    icon: '📱'
  },
  {
    title: 'Formation gratuite : Gestion d\'entreprise',
    excerpt: 'PAIDEKSA organise une série de formations gratuites sur la gestion et la planification financière d\'entreprise.',
    category: 'Événements',
    date: '20 décembre 2025',
    readTime: 4,
    icon: '📚'
  },
  {
    title: 'Les avantages du compte épargne PAIDEKSA',
    excerpt: 'Comprenez tous les bénéfices et taux intéressants de nos produits d\'épargne spécialement conçus pour vous.',
    category: 'Conseils',
    date: '18 décembre 2025',
    readTime: 6,
    icon: '🏦'
  }
]

const filteredArticles = computed(() => {
  if (activeCategory.value === 'Tous') {
    return articles
  }
  return articles.filter(article => article.category === activeCategory.value)
})

const newsletter = ref({
  email: '',
  message: '',
  status: ''
})

const subscribeNewsletter = () => {
  if (!newsletter.value.email) {
    newsletter.value.message = 'Veuillez entrer une adresse email.'
    newsletter.value.status = 'error'
    return
  }

  newsletter.value.status = 'success'
  newsletter.value.message = 'Merci ! Vous êtes maintenant inscrit à notre newsletter.'
  newsletter.value.email = ''
  
  setTimeout(() => {
    newsletter.value.message = ''
  }, 3000)
}
</script>

<style scoped>
.news {
  width: 100%;
}

/* Page Header */
.page-header {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
  padding: var(--spacing-4xl) 0;
  text-align: center;
}

.page-header h1 {
  font-size: var(--text-5xl);
  margin-bottom: var(--spacing-lg);
}

.page-header p {
  font-size: var(--text-lg);
  opacity: 0.95;
}

/* Filter Section */
.filter-section {
  background-color: var(--bg-light);
}

.filters {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: var(--spacing-md);
}

.filter-btn {
  padding: var(--spacing-sm) var(--spacing-lg);
  border: 2px solid var(--border-color);
  border-radius: var(--radius-full);
  background-color: white;
  color: var(--text-dark);
  font-weight: var(--font-medium);
  cursor: pointer;
  transition: all var(--transition-base);
}

.filter-btn:hover {
  border-color: var(--primary);
  color: var(--primary);
}

.filter-btn.active {
  background-color: var(--primary);
  color: white;
  border-color: var(--primary);
}

/* News Grid */
.news-grid-section {
  background-color: white;
}

.news-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: var(--spacing-lg);
}

.news-card {
  background: white;
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
  display: flex;
  flex-direction: column;
}

.news-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-lg);
}

.news-image {
  position: relative;
  height: 200px;
  background: linear-gradient(135deg, var(--primary-lighter) 0%, var(--primary) 100%);
  display: flex;
  align-items: center;
  justify-content: center;
}

.image-placeholder {
  font-size: 4rem;
  animation: pulse 2s ease-in-out infinite;
}

.category-badge {
  position: absolute;
  top: var(--spacing-md);
  right: var(--spacing-md);
  background-color: var(--secondary);
  color: white;
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--radius-md);
  font-size: var(--text-xs);
  font-weight: var(--font-bold);
}

.news-content {
  padding: var(--spacing-lg);
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.news-meta {
  display: flex;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-md);
  font-size: var(--text-sm);
  color: var(--text-light);
}

.date {
  display: flex;
  align-items: center;
  gap: 4px;
}

.reading-time {
  display: flex;
  align-items: center;
  gap: 4px;
}

.news-card h3 {
  font-size: var(--text-xl);
  margin-bottom: var(--spacing-md);
  color: var(--primary);
  line-height: var(--line-height-tight);
}

.news-card p {
  color: var(--text-light);
  margin-bottom: auto;
  line-height: var(--line-height-normal);
}

.read-more {
  color: var(--primary);
  font-weight: var(--font-semibold);
  margin-top: var(--spacing-md);
  transition: all var(--transition-base);
}

.read-more:hover {
  color: var(--secondary);
  transform: translateX(4px);
}

.no-articles {
  grid-column: 1 / -1;
  text-align: center;
  padding: var(--spacing-3xl) var(--spacing-lg);
  color: var(--text-light);
}

/* Newsletter Section */
.newsletter-section {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
}

.newsletter-form {
  display: flex;
  gap: var(--spacing-md);
  max-width: 500px;
  margin: var(--spacing-lg) auto;
  flex-wrap: wrap;
}

.newsletter-form input {
  flex: 1;
  min-width: 250px;
  padding: var(--spacing-md);
  border: none;
  border-radius: var(--radius-md);
  font-size: var(--text-base);
}

.newsletter-form button {
  padding: var(--spacing-md) var(--spacing-xl);
}

.newsletter-message {
  text-align: center;
  margin-top: var(--spacing-md);
  padding: var(--spacing-md);
  border-radius: var(--radius-md);
}

.newsletter-message.success {
  background-color: rgba(46, 125, 50, 0.2);
  color: #c8e6c9;
  border: 1px solid rgba(46, 125, 50, 0.5);
}

.newsletter-message.error {
  background-color: rgba(198, 40, 40, 0.2);
  color: #ffcdd2;
  border: 1px solid rgba(198, 40, 40, 0.5);
}

@media (max-width: 768px) {
  .page-header h1 {
    font-size: var(--text-4xl);
  }

  .news-grid {
    grid-template-columns: 1fr;
  }

  .newsletter-form {
    flex-direction: column;
  }

  .newsletter-form input {
    min-width: 100%;
  }
}
</style>
