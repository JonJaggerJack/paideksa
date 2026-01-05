<template>
  <header class="header">
    <nav class="navbar">
      <div class="container nav-content">
        <div class="logo">
          <router-link to="/">
            <span class="logo-text">PAIDEKSA</span>
          </router-link>
        </div>

        <button 
          class="mobile-toggle"
          @click="toggleMenu"
          :class="{ active: isMenuOpen }"
        >
          <span></span>
          <span></span>
          <span></span>
        </button>

        <ul class="nav-menu" :class="{ active: isMenuOpen }">
          <li>
            <router-link to="/" @click="closeMenu">
              Accueil
            </router-link>
          </li>
          <li>
            <router-link to="/mission" @click="closeMenu">
              Mission & Vision
            </router-link>
          </li>
          <li>
            <router-link to="/services" @click="closeMenu">
              Services
            </router-link>
          </li>
          <li>
            <router-link to="/contact" @click="closeMenu">
              Contact
            </router-link>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<style scoped>
.header {
  background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
  box-shadow: var(--shadow-md);
  position: sticky;
  top: 0;
  z-index: var(--z-fixed);
}

.navbar {
  padding: var(--spacing-md) 0;
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-text {
  font-size: var(--text-2xl);
  font-weight: var(--font-bold);
  color: white;
  letter-spacing: 2px;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.logo a {
  color: white;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: var(--spacing-lg);
  align-items: center;
}

.nav-menu li a {
  color: white;
  font-weight: var(--font-medium);
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--radius-md);
  transition: all var(--transition-base);
  display: flex;
  align-items: center;
  gap: var(--spacing-sm);
}

.nav-menu li a:hover,
.nav-menu li a.router-link-active {
  background-color: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.mobile-toggle {
  display: none;
  flex-direction: column;
  background: none;
  padding: 0;
  width: 30px;
  height: 24px;
  gap: var(--spacing-sm);
  cursor: pointer;
  border: none;
}

.mobile-toggle span {
  display: block;
  width: 100%;
  height: 3px;
  background-color: white;
  border-radius: var(--radius-sm);
  transition: all var(--transition-base);
}

.mobile-toggle.active span:nth-child(1) {
  transform: rotate(45deg) translate(8px, 8px);
}

.mobile-toggle.active span:nth-child(2) {
  opacity: 0;
}

.mobile-toggle.active span:nth-child(3) {
  transform: rotate(-45deg) translate(8px, -8px);
}

@media (max-width: 768px) {
  .mobile-toggle {
    display: flex;
  }

  .nav-menu {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    flex-direction: column;
    gap: 0;
    background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
    max-height: 0;
    overflow: hidden;
    transition: max-height var(--transition-base);
  }

  .nav-menu.active {
    max-height: 300px;
  }

  .nav-menu li {
    width: 100%;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  }

  .nav-menu li a {
    padding: var(--spacing-lg);
    width: 100%;
  }

  .nav-menu li:last-child {
    border-bottom: none;
  }
}
</style>
