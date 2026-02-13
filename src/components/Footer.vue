<template>
  <footer class="footer py-4">
    <div class="container">
      <div class="row">
        <div class="col-12 text-center">
          <p class="mb-2">&copy; {{ currentYear }} Manuel Buenviaje II. All Rights Reserved.</p>
          <p class="mb-0">
            Designed with <i class="fas fa-heart text-danger"></i> by Manuel Buenviaje II
          </p>
          <p class="mt-3">
            <a href="#landing" class="back-to-top">
              <i class="fas fa-arrow-up me-1"></i> Back to Top
            </a>
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'

const currentYear = ref(new Date().getFullYear())
</script>

<style scoped>
.footer {
  background-color: #0f172a;
  border-top: 1px solid var(--border-color);
  color: #94a3b8;
}

.back-to-top {
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.back-to-top:hover {
  color: #60a5fa;
  text-decoration: underline;
}

.text-danger {
  color: #ef4444 !important;
}

@media (max-width: 768px) {
  .footer {
    padding-top: 2rem;
    padding-bottom: 2rem;
  }
}
</style>