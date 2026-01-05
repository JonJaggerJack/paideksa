<template>
  <div class="contact">
    <!-- Page Header -->
    <section class="page-header">
      <div class="container">
        <h1 class="fade-in-up">Nous Contacter</h1>
        <p class="fade-in-up">Parlez avec notre équipe aujourd'hui</p>
      </div>
    </section>

    <!-- Contact Content -->
    <section class="section contact-section">
      <div class="container">
        <div class="contact-grid">
          <!-- Contact Form -->
          <div class="contact-form slide-in-left">
            <h2>Envoyez-nous un Message</h2>
            <form @submit.prevent="submitForm">
              <div class="form-group">
                <label for="name">Nom Complet *</label>
                <input 
                  v-model="form.name"
                  type="text" 
                  id="name" 
                  placeholder="Votre nom complet"
                  required
                >
              </div>

              <div class="form-group">
                <label for="email">Email *</label>
                <input 
                  v-model="form.email"
                  type="email" 
                  id="email" 
                  placeholder="votre@email.com"
                  required
                >
              </div>

              <div class="form-group">
                <label for="phone">Téléphone</label>
                <input 
                  v-model="form.phone"
                  type="tel" 
                  id="phone" 
                  placeholder="+243 ..."
                >
              </div>

              <div class="form-group">
                <label for="subject">Sujet *</label>
                <select v-model="form.subject" id="subject" required>
                  <option value="">Sélectionner un sujet</option>
                  <option value="general">Demande Générale</option>
                  <option value="account">Ouverture de Compte</option>
                  <option value="loan">Demande de Crédit</option>
                  <option value="savings">Produits d'Épargne</option>
                  <option value="support">Support Technique</option>
                  <option value="other">Autre</option>
                </select>
              </div>

              <div class="form-group">
                <label for="message">Message *</label>
                <textarea 
                  v-model="form.message"
                  id="message" 
                  rows="6"
                  placeholder="Décrivez votre demande..."
                  required
                ></textarea>
              </div>

              <div class="form-group checkbox">
                <input 
                  v-model="form.newsletter"
                  type="checkbox" 
                  id="newsletter"
                >
                <label for="newsletter">S'inscrire à notre newsletter</label>
              </div>

              <button type="submit" class="btn btn-primary">Envoyer le Message</button>

              <p v-if="submitMessage" :class="['submit-message', submitStatus]">
                {{ submitMessage }}
              </p>
            </form>
          </div>

          <!-- Contact Information -->
          <div class="contact-info slide-in-right">
            <h2>Coordonnées</h2>

            <div class="info-card">
              <div class="info-icon">📍</div>
              <div class="info-content">
                <h3>Siège Social</h3>
                <p>Kivu, République Démocratique du Congo</p>
              </div>
            </div>

            <div class="info-card">
              <div class="info-icon">📞</div>
              <div class="info-content">
                <h3>Téléphone</h3>
                <p><a href="tel:+243123456789">+243 (0) 123 456 789</a></p>
                <p><a href="tel:+243987654321">+243 (0) 987 654 321</a></p>
              </div>
            </div>

            <div class="info-card">
              <div class="info-icon">📧</div>
              <div class="info-content">
                <h3>Email</h3>
                <p><a href="mailto:info@paideksa.com">info@paideksa.com</a></p>
                <p><a href="mailto:support@paideksa.com">support@paideksa.com</a></p>
              </div>
            </div>

            <div class="info-card">
              <div class="info-icon">⏰</div>
              <div class="info-content">
                <h3>Horaires</h3>
                <p>Lundi - Vendredi: 08h00 - 17h00</p>
                <p>Samedi: 08h00 - 13h00</p>
                <p>Dimanche: Fermé</p>
              </div>
            </div>

            <div class="social-section">
              <h3>Suivez-nous</h3>
              <div class="social-links">
                <a href="#" class="social-btn">
                  <span>f</span> Facebook
                </a>
                <a href="#" class="social-btn">
                  <span>📷</span> Instagram
                </a>
                <a href="#" class="social-btn">
                  <span>𝕏</span> Twitter
                </a>
                <a href="#" class="social-btn">
                  <span>in</span> LinkedIn
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Branches Section -->
    <section class="section branches-section">
      <div class="container">
        <h2 class="section-title">Nos Branches</h2>
        <div class="branches-grid">
          <div class="branch-card fade-in-up" style="animation-delay: 0.1s">
            <div class="branch-header">
              <h3>Nord-Kivu</h3>
            </div>
            <div class="branch-body">
              <p><strong>Adresse:</strong> Goma, Nord-Kivu</p>
              <p><strong>Tél:</strong> +243 123 456 789</p>
              <p><strong>Horaires:</strong> Lun-Sam 08h-18h</p>
            </div>
          </div>

          <div class="branch-card fade-in-up" style="animation-delay: 0.2s">
            <div class="branch-header">
              <h3>Sud-Kivu</h3>
            </div>
            <div class="branch-body">
              <p><strong>Adresse:</strong> Bukavu, Sud-Kivu</p>
              <p><strong>Tél:</strong> +243 987 654 321</p>
              <p><strong>Horaires:</strong> Lun-Sam 08h-18h</p>
            </div>
          </div>

          <div class="branch-card fade-in-up" style="animation-delay: 0.3s">
            <div class="branch-header">
              <h3>Maniema</h3>
            </div>
            <div class="branch-body">
              <p><strong>Adresse:</strong> Kindu, Maniema</p>
              <p><strong>Tél:</strong> +243 555 666 777</p>
              <p><strong>Horaires:</strong> Lun-Ven 08h-17h</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="section faq-section">
      <div class="container">
        <h2 class="section-title">Questions Fréquentes</h2>
        <div class="faq-grid">
          <div 
            v-for="(item, index) in faqs"
            :key="index"
            class="faq-item fade-in-up"
            :style="{ animationDelay: `${index * 0.1}s` }"
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
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: '',
  newsletter: false
})

const submitMessage = ref('')
const submitStatus = ref('')
const activeFaq = ref(null)

const faqs = [
  {
    question: 'Comment ouvrir un compte chez PAIDEKSA ?',
    answer: 'Vous pouvez ouvrir un compte en visitant l\'une de nos branches avec une pièce d\'identité valide et un justificatif de domicile. Le processus prend généralement 30 minutes.'
  },
  {
    question: 'Quel est le montant minimum pour un microcrédit ?',
    answer: 'Le montant minimum pour un microcrédit est de 100 000 FC. Le montant maximum dépend de votre historique de crédit et de vos capacités de remboursement.'
  },
  {
    question: 'Quels sont les taux d\'intérêt appliqués ?',
    answer: 'Nos taux d\'intérêt sont compétitifs et varient selon le type de produit. Consultez notre page Tarification ou contactez une agence pour les taux exacts.'
  },
  {
    question: 'Puis-je accéder à mon compte depuis mon téléphone ?',
    answer: 'Oui ! Notre application mobile sécurisée vous permet de gérer votre compte 24h/24 et 7j/7. Téléchargez-la depuis l\'App Store ou Google Play.'
  },
  {
    question: 'Que se passe-t-il si j\'ai des difficultés de remboursement ?',
    answer: 'Contactez-nous immédiatement. Nous offrons des solutions de restructuration de crédit et des délais supplémentaires selon votre situation.'
  },
  {
    question: 'Mes fonds sont-ils assurés ?',
    answer: 'Oui, tous les dépôts jusqu\'à 5 000 000 FC sont assurés conformément à la réglementation bancaire en vigueur.'
  }
]

const toggleFaq = (index) => {
  activeFaq.value = activeFaq.value === index ? null : index
}

const submitForm = () => {
  if (!form.name || !form.email || !form.subject || !form.message) {
    submitMessage.value = 'Veuillez remplir tous les champs obligatoires.'
    submitStatus.value = 'error'
    return
  }

  // Simulation d'envoi
  submitStatus.value = 'success'
  submitMessage.value = 'Merci ! Votre message a été envoyé avec succès. Nous vous répondrons bientôt.'
  
  // Réinitialiser le formulaire
  setTimeout(() => {
    form.name = ''
    form.email = ''
    form.phone = ''
    form.subject = ''
    form.message = ''
    form.newsletter = false
    submitMessage.value = ''
  }, 3000)
}
</script>

<style scoped>
.contact {
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

/* Contact Section */
.contact-section {
  background-color: var(--bg-light);
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
}

.contact-form h2,
.contact-info h2 {
  font-size: 2rem;
  color: var(--primary);
  margin-bottom: 30px;
}

/* Form Styling */
.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  margin-bottom: 8px;
  font-weight: 600;
  color: var(--text-dark);
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid var(--border-color);
  border-radius: 6px;
  font-size: 1rem;
  font-family: inherit;
  transition: all 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--primary);
  box-shadow: 0 0 0 3px rgba(0, 121, 107, 0.1);
}

.form-group.checkbox {
  display: flex;
  align-items: center;
  gap: 10px;
}

.form-group.checkbox input {
  width: auto;
  margin: 0;
}

.form-group.checkbox label {
  margin: 0;
}

.submit-message {
  margin-top: 15px;
  padding: 12px;
  border-radius: 6px;
  text-align: center;
  font-weight: 500;
}

.submit-message.success {
  background-color: #c8e6c9;
  color: var(--success);
  border: 1px solid var(--success);
}

.submit-message.error {
  background-color: #ffcdd2;
  color: var(--error);
  border: 1px solid var(--error);
}

/* Contact Info */
.info-card {
  display: flex;
  gap: 20px;
  margin-bottom: 30px;
  padding: 20px;
  background: white;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.info-icon {
  font-size: 2rem;
  min-width: 50px;
  text-align: center;
  line-height: 1.5;
}

.info-content h3 {
  color: var(--primary);
  margin: 0 0 8px 0;
  font-size: 1.1rem;
}

.info-content p {
  margin: 4px 0;
  color: var(--text-dark);
}

.info-content a {
  color: var(--primary);
  text-decoration: none;
  font-weight: 500;
}

.info-content a:hover {
  color: var(--secondary);
  text-decoration: underline;
}

/* Social Links */
.social-section {
  margin-top: 40px;
  padding-top: 30px;
  border-top: 1px solid var(--border-color);
}

.social-section h3 {
  color: var(--primary);
  margin-bottom: 15px;
}

.social-links {
  display: grid;
  gap: 10px;
}

.social-btn {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 12px;
  background: white;
  border: 1px solid var(--border-color);
  border-radius: 6px;
  text-decoration: none;
  color: var(--primary);
  font-weight: 500;
  transition: all 0.3s ease;
}

.social-btn:hover {
  background: var(--primary);
  color: white;
  border-color: var(--primary);
}

.social-btn span {
  font-size: 1.3rem;
}

/* Branches Section */
.branches-section {
  background-color: white;
}

.branches-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.branch-card {
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.branch-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 12px 30px rgba(0, 121, 107, 0.2);
}

.branch-header {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  color: white;
  padding: 25px;
}

.branch-header h3 {
  margin: 0;
  font-size: 1.3rem;
}

.branch-body {
  padding: 25px;
  background: var(--bg-light);
}

.branch-body p {
  margin: 10px 0;
  color: var(--text-dark);
}

/* FAQ Section */
.faq-section {
  background-color: var(--bg-light);
}

.faq-grid {
  display: grid;
  gap: 15px;
  max-width: 800px;
  margin: 0 auto;
}

.faq-item {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.faq-question {
  width: 100%;
  padding: 20px;
  text-align: left;
  background: white;
  border: none;
  border-bottom: 1px solid var(--border-color);
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 1.05rem;
  font-weight: 600;
  color: var(--primary);
  transition: all 0.3s ease;
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
  transition: transform 0.3s ease;
}

.faq-question.active .faq-icon {
  transform: rotate(180deg);
}

.faq-answer {
  padding: 20px;
  color: var(--text-dark);
  line-height: 1.8;
  animation: fadeInUp 0.3s ease;
}

@media (max-width: 768px) {
  .page-header h1 {
    font-size: 2.5rem;
  }

  .contact-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .contact-form h2,
  .contact-info h2 {
    font-size: 1.7rem;
  }

  .branches-grid {
    grid-template-columns: 1fr;
  }
}
</style>
