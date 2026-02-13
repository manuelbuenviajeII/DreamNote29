<!-- src/components/ToolsSection.vue -->
<template>
  <section id="tools" class="tools-section py-5">
    <div class="container">
      <div class="row">
        <div class="col-12 text-center mb-5">
          <h2 class="section-title">Tools & Technologies</h2>
          <p class="section-subtitle">Technologies and tools I work with to bring ideas to life</p>
        </div>
      </div>
      
      <!-- Frontend Tools -->
      <div class="row mb-5">
        <div class="col-12 text-center mb-4">
          <h3 class="h4">Frontend Development</h3>
          <p class="text-muted">Creating responsive and interactive user interfaces</p>
        </div>
        <div class="col-lg-3 col-md-4 col-sm-6 text-center mb-4" v-for="tool in frontendTools" :key="tool.name">
          <div class="tool-item p-4 rounded">
            <i :class="tool.icon + ' fa-3x ' + tool.color + ' mb-3'"></i>
            <h5>{{ tool.name }}</h5>
            <p class="small text-muted mt-2">{{ tool.description }}</p>
          </div>
        </div>
      </div>
      
      <!-- Backend Tools -->
      <div class="row mb-5">
        <div class="col-12 text-center mb-4">
          <h3 class="h4">Backend Development</h3>
          <p class="text-muted">Building robust server-side applications and APIs</p>
        </div>
        <div class="col-lg-3 col-md-4 col-sm-6 text-center mb-4" v-for="tool in backendTools" :key="tool.name">
          <div class="tool-item p-4 rounded">
            <i :class="tool.icon + ' fa-3x ' + tool.color + ' mb-3'"></i>
            <h5>{{ tool.name }}</h5>
            <p class="small text-muted mt-2">{{ tool.description }}</p>
          </div>
        </div>
      </div>
      
      <!-- Development Tools -->
      <div class="row">
        <div class="col-12 text-center mb-4">
          <h3 class="h4">Development Tools</h3>
          <p class="text-muted">Essential tools for efficient development workflow</p>
        </div>
        <div class="col-lg-3 col-md-4 col-sm-6 text-center mb-4" v-for="tool in devTools" :key="tool.name">
          <div class="tool-item p-4 rounded">
            <i :class="tool.icon + ' fa-3x ' + tool.color + ' mb-3'"></i>
            <h5>{{ tool.name }}</h5>
            <p class="small text-muted mt-2">{{ tool.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const frontendTools = ref([
  { name: 'HTML5', icon: 'fab fa-html5', color: 'text-danger', description: 'Semantic markup & structure' },
  { name: 'CSS3', icon: 'fab fa-css3-alt', color: 'text-primary', description: 'Styling & animations' },
  { name: 'JavaScript', icon: 'fab fa-js-square', color: 'text-warning', description: 'Interactive functionality' },
  { name: 'React', icon: 'fab fa-react', color: 'text-info', description: 'Component-based UI' }
])

const backendTools = ref([
  { name: 'Node.js', icon: 'fab fa-node-js', color: 'text-success', description: 'Server-side JavaScript' },
  { name: 'PHP', icon: 'fab fa-php', color: 'text-info', description: 'Web application development' },
  { name: 'Python', icon: 'fab fa-python', color: 'text-primary', description: 'Scripting & automation' },
  { name: 'MySQL', icon: 'fas fa-database', color: 'text-secondary', description: 'Database management' }
])

const devTools = ref([
  { name: 'Git', icon: 'fab fa-git-alt', color: 'text-danger', description: 'Version control system' },
  { name: 'Bootstrap', icon: 'fab fa-bootstrap', color: 'text-purple', description: 'CSS framework' },
  { name: 'Figma', icon: 'fab fa-figma', color: 'text-warning', description: 'UI/UX design tool' },
  { name: 'NPM', icon: 'fab fa-npm', color: 'text-danger', description: 'Package management' }
])
</script>