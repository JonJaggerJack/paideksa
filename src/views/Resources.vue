<template>
  <div class="resources">
    <!-- Page Header -->
    <section class="page-header">
      <div class="container">
        <h1 class="animate-fadeInUp">Ressources</h1>
        <p class="animate-fadeInUp">Téléchargez nos guides, documents et outils financiers</p>
      </div>
    </section>

    <!-- Resources Grid -->
    <section class="section resources-section">
      <div class="container">
        <div class="resources-grid">
          <div 
            v-for="(resource, index) in resources"
            :key="index"
            class="resource-card animate-fadeInUp"
            :style="{ animationDelay: `${index * 0.1}s` }"
          >
            <div class="resource-header" :style="{ background: resource.color }">
              <span class="resource-icon">{{ resource.icon }}</span>
              <span class="file-type">{{ resource.type }}</span>
            </div>
            <div class="resource-content">
              <h3>{{ resource.title }}</h3>
              <p>{{ resource.description }}</p>
              <div class="resource-meta">
                <span class="file-size">{{ resource.size }}</span>
                <span class="update-date">{{ resource.date }}</span>
              </div>
              <a href="#" class="btn btn-primary btn-sm">Télécharger</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Categories Section -->
    <section class="section categories-section">
      <div class="container">
        <h2 class="section-title">Catégories</h2>
        <div class="categories-grid">
          <div 
            v-for="(category, index) in categories"
            :key="index"
            class="category-item animate-fadeInUp"
            :style="{ animationDelay: `${index * 0.1}s` }"
          >
            <div class="category-icon">{{ category.icon }}</div>
            <h3>{{ category.name }}</h3>
            <p>{{ category.count }} ressources</p>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="section faq-section">
      <div class="container">
        <h2 class="section-title">Questions Fréquentes</h2>
        <div class="faq-list">
          <div 
            v-for="(item, index) in faqs"
            :key="index"
            class="faq-item"
          >
            <button 
              class="faq-question"
              @click="toggleFaq(index)"
              :class="{ active: activeFaq === index }"
            >
              <span>{{ item.question }}</span>
              <span class="faq-icon">▼</span>
            </button>
            <div v-if="activeFaq === index" class="faq-answer">
              {{ item.answer }}
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Support Section -->
    <section class="section support-section">
      <div class="container">
        <h2 class="section-title">Besoin d'Aide ?</h2>
        <div class="support-grid">
          <div class="support-card">
            <div class="support-icon">📧</div>
            <h3>Email</h3>
            <p>Envoyez-nous vos questions à</p>
            <a href="mailto:support@paideksa.com">support@paideksa.com</a>
          </div>
          <div class="support-card">
            <div class="support-icon">📞</div>
            <h3>Téléphone</h3>
            <p>Appelez-nous au</p>
            <a href="tel:+243123456789">+243 (0) 123 456 789</a>
          </div>
          <div class="support-card">
            <div class="support-icon">💬</div>
            <h3>Chat</h3>
            <p>Discutez directement avec un agent</p>
            <router-link to="/contact" class="btn btn-primary btn-sm">Démarrer le chat</router-link>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const activeFaq = ref(null)

const resources = [
  {
    title: 'Guide d\'ouverture de compte',
    description: 'Toutes les étapes pour ouvrir rapidement un compte PAIDEKSA',
    type: 'PDF',
    size: '2.4 MB',
    date: '5 jan 2026',
    icon: '📄',
    color: 'linear-gradient(135deg, #ff6f00 0%, #ffb74d 100%)'
  },
  {
    title: 'Conditions et tarifs 2026',
    description: 'Découvrez nos tarifs actualisés et conditions de service',
    type: 'PDF',
    size: '1.8 MB',
    date: '4 jan 2026',
    icon: '💰',
    color: 'linear-gradient(135deg, #00796b 0%, #004d40 100%)'
  },
  {
    title: 'Manuel de l\'application mobile',
    description: 'Guide complet pour utiliser l\'application PAIDEKSA',
    type: 'PDF',
    size: '3.2 MB',
    date: '2 jan 2026',
    icon: '📱',
    color: 'linear-gradient(135deg, #0277bd 0%, #01579b 100%)'
  },
  {
    title: 'Formulaire de demande de crédit',
    description: 'Téléchargez et complétez le formulaire de demande de crédit',
    type: 'Excel',
    size: '0.5 MB',
    date: '30 déc 2025',
    icon: '📋',
    color: 'linear-gradient(135deg, #2e7d32 0%, #1b5e20 100%)'
  },
  {
    title: 'Plan financier personnel',
    description: 'Modèle pour vous aider à planifier vos finances personnelles',
    type: 'Excel',
    size: '0.7 MB',
    date: '28 déc 2025',
    icon: '📊',
    color: 'linear-gradient(135deg, #f57c00 0%, #e65100 100%)'
  },
  {
    title: 'Rapport annuel 2025',
    description: 'Retrouvez notre rapport annuel avec tous les chiffres clés',
    type: 'PDF',
    size: '5.1 MB',
    date: '25 déc 2025',
    icon: '📈',
    color: 'linear-gradient(135deg, #c62828 0%, #b71c1c 100%)'
  }
]

const categories = [
  { name: 'Guides', icon: '📚', count: 12 },
  { name: 'Formulaires', icon: '📋', count: 8 },
  { name: 'Vidéos', icon: '🎥', count: 15 },
  { name: 'Webinaires', icon: '🎤', count: 6 }
]

const faqs = [
  {
    question: 'Comment télécharger les ressources ?',
    answer: 'Cliquez simplement sur le bouton "Télécharger" sur la ressource que vous souhaitez. Les fichiers seront automatiquement téléchargés sur votre ordinateur ou téléphone.'
  },
  {
    question: 'Les ressources sont-elles à jour ?',
    answer: 'Oui, nous mettons à jour régulièrement nos ressources. La date de mise à jour est indiquée pour chaque document.'
  },
  {
    question: 'Puis-je imprimer les documents ?',
    answer: 'Bien sûr ! Vous pouvez imprimer tous les documents PDF après les avoir téléchargés. Consultez les instructions sur votre navigateur pour l\'impression.'
  },
  {
    question: 'Existe-t-il des ressources en d\'autres langues ?',
    answer: 'Actuellement, tous nos documents sont disponibles en français. Nous travaillons sur des versions en anglais et d\'autres langues.'
  },
  {
    question: 'Comment puis-je suggérer une nouvelle ressource ?',
    answer: 'Envoyez-nous vos suggestions à support@paideksa.com avec le titre et la description de la ressource que vous aimeriez voir disponible.'
  }
]

const toggleFaq = (index) => {
  activeFaq.value = activeFaq.value === index ? null : index
}
</script>

<style scoped>
.resources {
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

/* Resources Grid */
.resources-section {
  background-color: white;
}

.resources-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: var(--spacing-lg);
}

.resource-card {
  background: white;
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
  display: flex;
  flex-direction: column;
}

.resource-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-lg);
}

.resource-header {
  height: 150px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  color: white;
}

.resource-icon {
  font-size: 3rem;
  margin-bottom: var(--spacing-md);
}

.file-type {
  position: absolute;
  top: var(--spacing-md);
  right: var(--spacing-md);
  background-color: rgba(255, 255, 255, 0.3);
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--radius-md);
  font-size: var(--text-xs);
  font-weight: var(--font-bold);
}

.resource-content {
  padding: var(--spacing-lg);
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.resource-content h3 {
  font-size: var(--text-lg);
  margin-bottom: var(--spacing-md);
  color: var(--primary);
}

.resource-content p {
  color: var(--text-light);
  margin-bottom: auto;
  line-height: var(--line-height-normal);
}

.resource-meta {
  display: flex;
  justify-content: space-between;
  margin: var(--spacing-lg) 0;
  padding-top: var(--spacing-lg);
  border-top: 1px solid var(--border-color);
  font-size: var(--text-sm);
  color: var(--text-light);
}

.resource-content .btn {
  align-self: flex-start;
  margin-top: auto;
}

/* Categories Section */
.categories-section {
  background-color: var(--bg-light);
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: var(--spacing-xl);
}

.category-item {
  background: white;
  padding: var(--spacing-xl);
  border-radius: var(--radius-lg);
  text-align: center;
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
}

.category-item:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-lg);
}

.category-icon {
  font-size: 3rem;
  margin-bottom: var(--spacing-lg);
  display: block;
}

.category-item h3 {
  font-size: var(--text-xl);
  margin-bottom: var(--spacing-md);
  color: var(--primary);
}

.category-item p {
  color: var(--text-light);
  margin: 0;
}

/* FAQ Section */
.faq-section {
  background-color: white;
}

.faq-list {
  max-width: 800px;
  margin: 0 auto;
  display: grid;
  gap: var(--spacing-lg);
}

.faq-item {
  background: var(--bg-light);
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
}

.faq-question {
  width: 100%;
  padding: var(--spacing-lg);
  text-align: left;
  background: white;
  border: none;
  border-bottom: 1px solid var(--border-color);
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: var(--text-base);
  font-weight: var(--font-semibold);
  color: var(--primary);
  transition: all var(--transition-base);
}

.faq-question:hover {
  background: var(--bg-light);
}

.faq-question.active {
  background: linear-gradient(135deg, rgba(0, 121, 107, 0.05) 0%, rgba(0, 121, 107, 0.1) 100%);
  border-bottom-color: var(--primary);
}

.faq-icon {
  font-size: 0.8rem;
  transition: transform var(--transition-base);
}

.faq-question.active .faq-icon {
  transform: rotate(180deg);
}

.faq-answer {
  padding: var(--spacing-lg);
  color: var(--text-dark);
  line-height: var(--line-height-relaxed);
  animation: fadeInUp 0.3s ease;
}

/* Support Section */
.support-section {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
}

.support-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-lg);
}

.support-card {
  background: rgba(255, 255, 255, 0.1);
  padding: var(--spacing-xl);
  border-radius: var(--radius-lg);
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all var(--transition-base);
}

.support-card:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateY(-5px);
}

.support-icon {
  font-size: 3rem;
  margin-bottom: var(--spacing-lg);
  display: block;
}

.support-card h3 {
  font-size: var(--text-xl);
  margin-bottom: var(--spacing-md);
}

.support-card p {
  margin-bottom: var(--spacing-lg);
  opacity: 0.9;
}

.support-card a {
  color: white;
  font-weight: var(--font-semibold);
  text-decoration: underline;
  transition: all var(--transition-base);
}

.support-card a:hover {
  opacity: 0.8;
}

@media (max-width: 768px) {
  .page-header h1 {
    font-size: var(--text-4xl);
  }

  .resources-grid {
    grid-template-columns: 1fr;
  }

  .categories-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
