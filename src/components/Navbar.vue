<template>
  <nav class="navbar navbar-expand-lg fixed-top custom-navbar">
    <div class="container">
      <a class="navbar-brand" href="#" @click.prevent="scrollToTop">PORTFOLIO</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link" href="#" @click.prevent="scrollToSection('landing')">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" @click.prevent="scrollToSection('about-me')">About Me</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" @click.prevent="scrollToSection('projects')">Projects</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" @click.prevent="scrollToSection('tools')">Tools</a>
          </li>
          <li class="nav-item">
            <a class="nav-link resume-link" 
               href="https://drive.google.com/file/d/1L_u0NnTaYCmrA1iXnZofTJdPgttva4tK/view?usp=sharing" 
               target="_blank">
                <i class="fas fa-file-pdf me-1"></i>Resume
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" @click.prevent="scrollToSection('contact')">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  methods: {
    scrollToSection(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        const offset = 80;
        const elementPosition = element.getBoundingClientRect().top;
        const offsetPosition = elementPosition + window.pageYOffset - offset;
        
        window.scrollTo({
          top: offsetPosition,
          behavior: 'smooth'
        });
        
        // Close mobile menu
        const navbarCollapse = document.getElementById('navbarNav');
        if (navbarCollapse && navbarCollapse.classList.contains('show')) {
          navbarCollapse.classList.remove('show');
        }
      }
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    }
  }
}
</script>