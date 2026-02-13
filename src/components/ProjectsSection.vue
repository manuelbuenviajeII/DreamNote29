<!-- src/components/ProjectsSection.vue -->
<template>
  <section id="projects" class="projects-section py-5">
    <div class="container">
      <div class="row">
        <div class="col-12 text-center mb-5">
          <h2 class="section-title">My Projects</h2>
          <p class="section-subtitle">Some of my recent work showcasing my skills in web development</p>
        </div>
      </div>
      <div class="row">
        <!-- Project Items -->
        <div class="col-lg-4 col-md-6 mb-4" v-for="project in projects" :key="project.id">
          <div class="card project-card h-100">
            <div class="project-image">
              <img :src="project.image" class="card-img-top" :alt="project.title">
            </div>
            <div class="card-body d-flex flex-column">
              <h5 class="card-title">{{ project.title }}</h5>
              <p class="card-text">{{ project.description }}</p>
              <div class="project-tech mb-3">
                <span class="badge bg-light text-dark" v-for="tech in project.technologies" :key="tech">{{ tech }}</span>
              </div>
              <div class="mt-auto">
                <a :href="project.liveLink" class="btn btn-primary me-2" target="_blank" v-if="project.liveLink">
                  <i :class="project.liveIcon + ' me-1'"></i> {{ project.liveText }}
                </a>
                <a :href="project.sourceLink" class="btn btn-outline-primary" target="_blank" v-if="project.sourceLink">
                  <i :class="project.sourceIcon + ' me-1'"></i> {{ project.sourceText }}
                </a>
                <button v-if="project.isPlaceholder" @click="$emit('scroll-to', 'contact')" class="btn btn-outline-primary w-100">
                  Suggest a Project
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

defineEmits(['scroll-to'])

const projects = ref([
  {
    id: 1,
    title: 'E-commerce API Documentation',
    description: 'Dynamic E-Commerce Workflow Management. The system features dynamic routes for order processing, real-time inventory updates, and secure user authentication. It also supports seamless automated order reporting and comprehensive product management. Documented Backend API published publicy using Postman',
    image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=700&q=80',
    technologies: ['API', 'Swagger', 'OpenAPI', 'Markdown'],
    liveLink: '#',
    liveIcon: 'fas fa-external-link-alt',
    liveText: 'View Docs',
    sourceLink: '#',
    sourceIcon: 'fab fa-github',
    sourceText: 'Source Code'
  },
  {
    id: 2,
    title: 'Course Booking API Documentation',
    description: 'RESTful API for managing course enrollments, featuring user registration, authentication, and retrieval of user details. Supports course creation, updates, archieving activation, and student enrollment. Publicy documented using Postman',
    image: 'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?ixlib=rb-4.0.3&auto=format&fit=crop&w=700&q=80',
    technologies: ['REST API', 'Postman', 'JSON', 'Documentation'],
    liveLink: '#',
    liveIcon: 'fas fa-external-link-alt',
    liveText: 'View Docs',
    sourceLink: '#',
    sourceIcon: 'fab fa-github',
    sourceText: 'Source Code'
  },
  {
    id: 3,
    title: 'Course Booking Application',
    description: 'MREN-stack couse enrollment system featuring user registration, authentication, and profile management. Authenticated users can create, update, archieve, and acitvate courses. The Platform also allows user to browse available courses and enroll seamlessly.',
    image: 'https://images.unsplash.com/photo-1501504905252-473c47e087f8?ixlib=rb-4.0.3&auto=format&fit=crop&w=700&q=80',
    technologies: ['React', 'Node.js', 'MongoDB', 'Stripe API'],
    liveLink: '#',
    liveIcon: 'fas fa-external-link-alt',
    liveText: 'Live Demo',
    sourceLink: '#',
    sourceIcon: 'fab fa-github',
    sourceText: 'Source Code'
  },
  {
    id: 4,
    title: 'E-commerce Application',
    description: 'MRN E-Commerce Platform features dynamic product catalog with filtering and sorting real-time search, seamless cart updates, secure checkout, and a comprehensive admin dashboard with a real-time analytics and user management capabilities.',
    image: 'https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?ixlib=rb-4.0.3&auto=format&fit=crop&w=700&q=80',
    technologies: ['Vue.js', 'Express', 'MySQL', 'PayPal API'],
    liveLink: '#',
    liveIcon: 'fas fa-external-link-alt',
    liveText: 'Live Demo',
    sourceLink: '#',
    sourceIcon: 'fab fa-github',
    sourceText: 'Source Code'
  },
  {
    id: 5,
    title: 'Airline Booking System Mockup',
    description: 'Side Project Conceptual design showcasing an intuative UI for fight search\\seat selection\\ and booking confirmation\\ focusing on user experience and workflow efficiency.',
    image: 'https://images.unsplash.com/photo-1436491865332-7a61a109cc05?ixlib=rb-4.0.3&auto=format&fit=crop&w=700&q=80',
    technologies: ['Figma', 'UI Design', 'Wireframing', 'Prototyping'],
    liveLink: '#',
    liveIcon: 'fas fa-external-link-alt',
    liveText: 'View Mockup',
    sourceLink: '#',
    sourceIcon: 'fab fa-figma',
    sourceText: 'Design File'
  },
  {
    id: 6,
    title: 'Airline Booking System Prototype',
    description: 'Interactive prototype of an airline booking system with functional flight search, booking flow, and payment simulation for user testing.',
    image: 'https://images.unsplash.com/photo-1436491865332-7a61a109cc05?ixlib=rb-4.0.3&auto=format&fit=crop&w=700&q=80',
    technologies: ['Figma', 'Prototyping', 'User Testing', 'Interaction Design'],
    liveLink: '#',
    liveIcon: 'fas fa-external-link-alt',
    liveText: 'View Prototype',
    sourceLink: '#',
    sourceIcon: 'fab fa-figma',
    sourceText: 'Design File'
  },
  {
    id: 7,
    title: 'Short Courses Capstone Project',
    description: 'Placeholder for yourShort courses capstone.',
    image: 'https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&auto=format&fit=crop&w=700&q=80',
    technologies: ['HTML/CSS', 'JavaScript', 'Bootstrap', 'REST API'],
    liveLink: '#',
    liveIcon: 'fas fa-external-link-alt',
    liveText: 'Live Demo',
    sourceLink: '#',
    sourceIcon: 'fab fa-github',
    sourceText: 'Source Code'
  },
  {
    id: 8,
    title: 'Future Project',
    description: 'This space is reserved for my next exciting project. Stay tuned for updates as I continue to expand my portfolio with new technologies and innovative solutions.',
    image: '',
    technologies: ['Coming Soon'],
    isPlaceholder: true
  }
])
</script>