<!-- src/components/ContactSection.vue -->
<template>
  <section id="contact" class="contact-section py-5">
    <div class="container">
      <div class="row">
        <div class="col-12 text-center mb-5">
          <h2 class="section-title">Contact Me</h2>
          <p class="section-subtitle">Get in touch for collaborations or inquiries</p>
          
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d61371.807793682274!2d120.56077899999998!3d15.975053549999998!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x33913fb28b8acf8f%3A0x432ead83f669f54f!2sUrdaneta%20City%2C%20Pangasinan!5e0!3m2!1sen!2sph!4v1759240267199!5m2!1sen!2sph" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
      </div>

      <div class="row">
        <div class="col-lg-6 mb-4 mb-lg-0">
          <h3 class="mb-4">Let's Connect</h3>
          <p class="mb-4">I'm always open to discussing new opportunities, creative ideas, or partnerships to bring your vision to life. Whether you have a project in mind or just want to say hello, I'd love to hear from you.</p>
          
          <div class="contact-info mb-4">
            <div class="d-flex align-items-center mb-3" v-for="info in contactInfo" :key="info.type">
              <div class="contact-icon me-3">
                <i :class="info.icon"></i>
              </div>
              <div>
                <h5 class="mb-1">{{ info.title }}</h5>
                <p class="mb-0">{{ info.value }}</p>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <a v-for="social in socialLinks" :key="social.name" :href="social.url" class="social-link me-3" :title="social.title + ' Profile'" target="_blank">
              <i :class="social.icon + ' fa-2x'"></i>
            </a>
          </div>
        </div>
        <div class="col-lg-6">
          <div class="contact-form-container p-4 rounded">
            <h4 class="mb-4">Send Me a Message</h4>
            <form @submit.prevent="submitForm">
              <div class="mb-3">
                <label for="name" class="form-label">Your Full Name</label>
                <input type="text" class="form-control" id="name" v-model="formData.name" placeholder="Enter your full name" required>
              </div>
              <div class="mb-3">
                <label for="email" class="form-label">Your Email Address</label>
                <input type="email" class="form-control" id="email" v-model="formData.email" placeholder="Enter your email address" required>
              </div>
              <div class="mb-3">
                <label for="subject" class="form-label">Message Subject</label>
                <input type="text" class="form-control" id="subject" v-model="formData.subject" placeholder="What is this regarding?" required>
              </div>
              <div class="mb-3">
                <label for="message" class="form-label">Your Message</label>
                <textarea class="form-control" id="message" rows="5" v-model="formData.message" placeholder="Tell me about your project or inquiry..." required></textarea>
              </div>
              <button type="submit" class="btn btn-primary btn-lg w-100">Send Message</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const contactInfo = ref([
  { type: 'location', icon: 'fas fa-map-marker-alt', title: 'Location', value: 'Urdaneta Pangasinan, Philippines' },
  { type: 'email', icon: 'fas fa-envelope', title: 'Email', value: 'manuel.buenviajeii@gmail.com' },
  { type: 'phone', icon: 'fas fa-phone', title: 'Phone', value: '+(639) 91-260-8220' }
])

const socialLinks = ref([
  { name: 'github', icon: 'fab fa-github', url: 'https://github.com/manuelbuenviajeII', title: 'GitHub' },
  { name: 'linkedin', icon: 'fab fa-linkedin', url: 'https://www.linkedin.com/in/manuel-buenviaje-301a8b222/', title: 'LinkedIn' },
  { name: 'twitter', icon: 'fab fa-twitter', url: 'https://twitter.com/manuelbuenviaje', title: 'Twitter' },
  { name: 'instagram', icon: 'fab fa-instagram', url: 'https://www.instagram.com/', title: 'Instagram' }
])

const formData = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const submitForm = () => {
  // This data to a backend?
  console.log('Form submitted:', formData.value);
  alert('Thank you for your message! I will get back to you soon.');
  
  // Reset form
  formData.value = {
    name: '',
    email: '',
    subject: '',
    message: ''
  };
}
</script>