<!-- src/components/LandingSection.vue -->
<template>
  <section id="landing" class="landing-section">
    <div class="landing-overlay"></div>
    <div class="landing-particles" id="particles-js"></div>
    <div class="container">
      <div class="row align-items-center min-vh-100">
        <div class="col-lg-6 order-md-1 order-2">
          <h1 class="display-4 fw-bold mb-4">Hi, I'm <span class="text-primary">Manuel Buenviaje II</span></h1>
          <h2 class="h3 mb-4">Full Stack Web Developer</h2>
          <p class="lead mb-5">I create modern, responsive websites and applications that deliver exceptional user experiences across all devices. With a background in client service and a passion for technology, I bridge the gap between user needs and technical solutions.</p>
          <div class="d-flex flex-wrap gap-3">
            <button @click="$emit('scroll-to', 'projects')" class="btn btn-primary btn-lg">View My Work</button>
            <button @click="$emit('scroll-to', 'contact')" class="btn btn-outline-light btn-lg">Contact Me</button>
            <a href="https://drive.google.com/file/d/1L_u0NnTaYCmrA1iXnZofTJdPgttva4tK/view?usp=sharing" target="_blank" class="btn btn-outline-light btn-lg">
              <i class="fas fa-file-pdf me-2"></i>View Resume
            </a>
          </div>
        </div>
        <div class="col-lg-6 text-center mt-5 mt-lg-0">
          <div class="profile-image-container">
            <img src="https://scontent.fmnl35-1.fna.fbcdn.net/v/t1.6435-9/31902046_2194411433908966_5421820797251485696_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=a5f93a&_nc_eui2=AeGF8YHEl_h4cyh7v8aUNE4cw4ghUExM-HrDiCFQTEz4erxrL6QceXlnatE5aNvJRhS1sdIwZhQg1qJitVy9EG-a&_nc_ohc=xgcJSeRhCVsQ7kNvwGJKKzm&_nc_oc=AdmTPn2PwrqGXEYaudBdx2OKJrkv2x2cZmv4BnVvsU1vkjze9UsRMQrHWT1loDfNJaE&_nc_zt=23&_nc_ht=scontent.fmnl35-1.fna&_nc_gid=FNTO28pDaIFJ7uONvOc8CA&oh=00_AfponVR9gyBtxd8pNk2daczrRBb0S4uaY-ToTVwoujIsJQ&oe=698C46E5" alt="Manuel Buenviaje II - Web Developer" class="profile-image">
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'

defineEmits(['scroll-to'])

onMounted(() => {
  // Initialize particles.js if available
  if (typeof window !== 'undefined' && window.particlesJS) {
    window.particlesJS('particles-js', {
      particles: {
        number: { value: 80, density: { enable: true, value_area: 800 } },
        color: { value: "#ffffff" },
        shape: { type: "circle" },
        opacity: { value: 0.5, random: false },
        size: { value: 3, random: true },
        line_linked: {
          enable: true,
          distance: 150,
          color: "#ffffff",
          opacity: 0.4,
          width: 1
        },
        move: {
          enable: true,
          speed: 6,
          direction: "none",
          random: false,
          straight: false,
          out_mode: "out",
          bounce: false
        }
      },
      interactivity: {
        detect_on: "canvas",
        events: {
          onhover: { enable: true, mode: "repulse" },
          onclick: { enable: true, mode: "push" }
        }
      },
      retina_detect: true
    });
  }
})
</script>