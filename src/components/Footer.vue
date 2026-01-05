<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="container">
        <div class="footer-grid">
          <div class="footer-section">
            <h3>PAIDEKSA</h3>
            <p>Contribuer au renforcement du tissu économique et à la redynamisation de l'économie populaire en RDC.</p>
            <div class="social-links">
              <a href="#" title="Facebook" class="social-icon">f</a>
              <a href="#" title="Instagram" class="social-icon">📷</a>
              <a href="#" title="Twitter" class="social-icon">𝕏</a>
              <a href="#" title="LinkedIn" class="social-icon">in</a>
            </div>
          </div>

          <div class="footer-section">
            <h4>Navigation</h4>
            <ul>
              <li><router-link to="/">Accueil</router-link></li>
              <li><router-link to="/mission">Mission & Vision</router-link></li>
              <li><router-link to="/services">Services</router-link></li>
              <li><router-link to="/contact">Contact</router-link></li>
            </ul>
          </div>

          <div class="footer-section">
            <h4>Contact</h4>
            <p>Email: <a href="mailto:info@paideksa.com">info@paideksa.com</a></p>
            <p>Téléphone: <a href="tel:+243123456789">+243 (0) 123 456 789</a></p>
            <p>Adresse: Kivu, RDC</p>
          </div>

          <div class="footer-section">
            <h4>Zone de service</h4>
            <ul>
              <li>Nord-Kivu</li>
              <li>Sud-Kivu</li>
              <li>Maniema</li>
              <li>Extension prévue...</li>
            </ul>
          </div>
        </div>

        <div class="footer-bottom">
          <p>&copy; 2025 PAIDEKSA SA. Tous droits réservés.</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
.footer {
  background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary) 100%);
  color: white;
  margin-top: var(--spacing-4xl);
}

.footer-content {
  padding: var(--spacing-3xl) 0 var(--spacing-md);
}

.footer-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-xl);
  margin-bottom: var(--spacing-2xl);
}

.footer-section h3 {
  font-size: var(--text-xl);
  margin-bottom: var(--spacing-md);
}

.footer-section h4 {
  font-size: var(--text-lg);
  margin-bottom: var(--spacing-md);
}

.footer-section p {
  line-height: var(--line-height-relaxed);
  opacity: 0.9;
  margin-bottom: var(--spacing-sm);
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section ul li {
  margin-bottom: var(--spacing-sm);
}

.footer-section a {
  color: white;
  transition: all var(--transition-base);
  border-bottom: 1px solid transparent;
  padding-bottom: 2px;
}

.footer-section a:hover {
  color: var(--secondary-light);
  border-bottom-color: var(--secondary-light);
}

.social-links {
  display: flex;
  gap: var(--spacing-md);
  margin-top: var(--spacing-lg);
}

.social-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  background-color: rgba(255, 255, 255, 0.2);
  border-radius: var(--radius-full);
  transition: all var(--transition-base);
  font-weight: var(--font-bold);
}

.social-icon:hover {
  background-color: var(--secondary);
  transform: translateY(-3px);
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.2);
  padding-top: var(--spacing-lg);
  text-align: center;
  opacity: 0.8;
}

@media (max-width: 768px) {
  .footer-grid {
    grid-template-columns: 1fr;
    gap: var(--spacing-lg);
  }

  .footer-content {
    padding: var(--spacing-2xl) 0 var(--spacing-md);
  }
}
</style>
