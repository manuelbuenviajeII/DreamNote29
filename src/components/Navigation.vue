<template>
  <nav class="navbar navbar-expand-lg fixed-top custom-navbar" :class="{ 'navbar-scrolled': isScrolled }">
    <div class="container">
      <a class="navbar-brand fw-bold" href="#landing">PORTFOLIO</a>
      <button 
        class="navbar-toggler" 
        type="button" 
        data-bs-toggle="collapse" 
        data-bs-target="#navbarNav"
        aria-controls="navbarNav" 
        aria-expanded="false" 
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link" href="#landing">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#about-me">About Me</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#projects">Projects</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#tools">Tools</a>
          </li>
          <li class="nav-item">
            <a class="nav-link resume-link" href="https://drive.google.com/file/d/1L_u0NnTaYCmrA1iXnZofTJdPgttva4tK/view?usp=sharing" target="_blank">
              <i class="fas fa-file-pdf me-1"></i>Resume
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#contact">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.custom-navbar {
  background-color: rgba(15, 23, 42, 0.95);
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  padding: 1rem 0;
  border-bottom: 1px solid var(--border-color);
}

.navbar-scrolled {
  padding: 0.5rem 0;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.navbar-brand {
  font-size: 1.8rem;
  color: var(--primary-color) !important;
  font-family: 'Montserrat', sans-serif;
}

.nav-link {
  color: #cbd5e1 !important;
  font-weight: 500;
  padding: 0.5rem 1rem !important;
  transition: color 0.3s ease;
  position: relative;
}

.nav-link:hover,
.nav-link.active {
  color: var(--primary-color) !important;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2px;
  background-color: var(--primary-color);
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-link:hover::after,
.nav-link.active::after {
  width: 80%;
}

.resume-link {
  color: #ef4444 !important;
}

.resume-link:hover {
  color: #dc2626 !important;
}

.navbar-toggler {
  border-color: var(--border-color) !important;
}

.navbar-toggler-icon {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba%2859, 130, 246, 0.75%29' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e") !important;
}

@media (max-width: 992px) {
  .nav-link::after {
    display: none;
  }
  
  .navbar-collapse {
    background-color: rgba(15, 23, 42, 0.98);
    padding: 1rem;
    border-radius: 0.5rem;
    margin-top: 0.5rem;
  }
}
</style>