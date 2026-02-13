<template>
  <div id="app">
    <!-- Particles Background -->
    <div id="particles-js"></div>
    
    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top">
      <div class="container">
        <a class="navbar-brand" href="#">MB<span>II</span></a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link" href="#home">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#about">About</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#skills">Skills</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#projects">Projects</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#contact">Contact</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Home Section -->
    <section id="home" class="section home-section">
      <div class="container">
        <div class="row align-items-center min-vh-100">
          <div class="col-lg-6">
            <h1 class="greeting">Hi, I'm</h1>
            <h2 class="name">Manuel Buenviaje II</h2>
            <h3 class="title">Web Developer</h3>
            <p class="description">
              I build responsive, user-friendly websites and applications with modern technologies.
            </p>
            <div class="cta-buttons">
              <a href="#contact" class="btn btn-primary">Hire Me</a>
              <a href="#projects" class="btn btn-outline-light">View Projects</a>
            </div>
            <div class="social-links mt-4">
              <a href="https://github.com/manuelbuenviajeII" target="_blank" class="social-link"><i class="fab fa-github"></i></a>
              <a href="https://www.linkedin.com/in/manuel-buenviaje-301a8b222/" target="_blank" class="social-link"><i class="fab fa-linkedin-in"></i></a>
              <a href="https://www.instagram.com/" target="_blank" class="social-link"><i class="fab fa-instagram"></i></a>
              <a href="https://www.facebook.com/profile.php?id=61577607387367" target="_blank" class="social-link"><i class="fab fa-facebook-f"></i></a>
            </div>
          </div>
          <div class="col-lg-6">
            <div class="profile-image-container">
              <img 
                :src="profileImage" 
                alt="Manuel Buenviaje II" 
                class="profile-image"
                @error="handleImageError"
              >
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about-section">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-lg-5">
            <div class="about-image-container">
              <img 
                :src="aboutImage" 
                alt="Manuel Buenviaje II - About" 
                class="about-image"
                @error="handleAboutImageError"
              >
            </div>
          </div>
          <div class="col-lg-7">
            <h2 class="section-title">About <span class="highlight">Me</span></h2>
            <h3 class="subtitle">Full Stack Developer</h3>
            <p class="about-text">
              I'm a passionate Full Stack Developer with a unique journey into tech. My career began in 
              <strong>physical security and customer service</strong>, where I developed strong problem-solving 
              skills and attention to detail over 7+ years of professional experience.
            </p>
            <p class="about-text">
              Transitioning into software development through <strong>Zuitt Coding Bootcamp</strong>, I've acquired 
              expertise in modern web technologies including React, Vue.js, Node.js, Express.js, and MongoDB. 
              I specialize in creating seamless user experiences backed by robust server-side logic.
            </p>
            <div class="personal-info">
              <div class="row">
                <div class="col-md-6">
                  <p><strong>Name:</strong> Manuel Buenviaje II</p>
                  <p><strong>Email:</strong> manuel.buenviajeii@gmail.com</p>
                </div>
                <div class="col-md-6">
                  <p><strong>Location:</strong> Urdaneta City, Pangasinan</p>
                  <p><strong>Freelance:</strong> Available</p>
                </div>
              </div>
            </div>
            
            <!--  UPDATED: GOOGLE DRIVE PREVIEW PAGE + DOWNLOAD OPTION -->
            <div class="resume-buttons mt-3">
              <a :href="resumePreviewLink" class="btn btn-primary" target="_blank">
                <i class="fas fa-eye"></i> Preview CV
              </a>
              <a :href="resumeDownloadLink" class="btn btn-outline-light ms-2" download>
                <i class="fas fa-download"></i> Download CV
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section skills-section">
      <div class="container">
        <div class="text-center mb-5">
          <h2 class="section-title">My <span class="highlight">Skills</span></h2>
          <p class="section-subtitle">Technologies I work with</p>
        </div>
        <div class="row g-4">
          <div v-for="(skill, index) in skills" :key="index" class="col-md-4 col-lg-2 col-6">
            <div class="skill-card">
              <div class="skill-icon">
                <i :class="skill.icon"></i>
              </div>
              <h4>{{ skill.name }}</h4>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section projects-section">
      <div class="container">
        <div class="text-center mb-5">
          <h2 class="section-title">My <span class="highlight">Projects</span></h2>
          <p class="section-subtitle">Recent work I'm proud of</p>
        </div>
        <div class="row g-4">
          <!-- Project 1: ManLiXpress Tech -->
          <div class="col-lg-4 col-md-6">
            <div class="project-card">
              <div class="project-img">
                <img src="https://placehold.co/600x400/2d2d2d/white?text=ManLiXpress+Tech" alt="ManLiXpress Tech">
              </div>
              <div class="project-info">
                <h3>ManLiXpress Tech</h3>
                <p>A gadget e-commerce platform with secure user authentication. Features phone number login, password validation, and a clean interface for premium tech products.</p>
                <div class="project-tech">
                  <span>HTML</span>
                  <span>CSS</span>
                  <span>JavaScript</span>
                </div>
                <div class="project-links">
                  <a href="https://manuelbuenviajeii.github.io/ManLiXpress-Tech/" target="_blank" class="btn btn-sm btn-primary">Live Demo</a>
                  <a href="https://github.com/manuelbuenviajeii/ManLiXpress-Tech" target="_blank" class="btn btn-sm btn-outline-primary">GitHub</a>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Project 2: Charles Babbage Portfolio -->
          <div class="col-lg-4 col-md-6">
            <div class="project-card">
              <div class="project-img">
                <img src="https://placehold.co/600x400/2d2d2d/white?text=Charles+Babbage" alt="Charles Babbage Portfolio">
              </div>
              <div class="project-info">
                <h3>Charles Babbage</h3>
                <p>A professional portfolio website honoring the "Father of Computers." Showcases the life, achievements, and legacy of Charles Babbage with a modern, responsive design.</p>
                <div class="project-tech">
                  <span>Vue.js</span>
                  <span>Vercel</span>
                  <span>Responsive</span>
                </div>
                <div class="project-links">
                  <a href="https://charles-babbage-portfolio-nine.vercel.app/" target="_blank" class="btn btn-sm btn-primary">Live Demo</a>
                  <a href="#" class="btn btn-sm btn-outline-primary">GitHub</a>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Project 3: Modern Airline Booking System -->
          <div class="col-lg-4 col-md-6">
            <div class="project-card">
              <div class="project-img">
                <img src="https://placehold.co/600x400/2d2d2d/white?text=Airline+Booking" alt="Modern Airline Booking System">
              </div>
              <div class="project-info">
                <h3>Modern Airline Booking System</h3>
                <p>A festive Christmas-themed airline booking interface. Features holiday-inspired design elements, smooth user experience, and modern booking UI components.</p>
                <div class="project-tech">
                  <span>HTML</span>
                  <span>CSS</span>
                  <span>Christmas Theme</span>
                </div>
                <div class="project-links">
                  <a href="https://github.com/Music2992/Modern-Airline-Booking-System-Christmas-Theme" target="_blank" class="btn btn-sm btn-primary">Live Demo</a>
                  <a href="https://github.com/Music2992/Modern-Airline-Booking-System-Christmas-Theme" target="_blank" class="btn btn-sm btn-outline-primary">GitHub</a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section contact-section">
      <div class="container">
        <div class="text-center mb-5">
          <h2 class="section-title">Get In <span class="highlight">Touch</span></h2>
          <p class="section-subtitle">Let's work together</p>
        </div>
        <div class="row">
          <div class="col-lg-8 mx-auto">
            <!-- Contact Form Card -->
            <div class="contact-card mb-5">
              <!-- WEB3FORMS INTEGRATION -->
              <form action="https://api.web3forms.com/submit" method="POST">
                <!-- Access Key -->
                <input type="hidden" name="access_key" value="2603f6e9-b6a8-44ed-bdc2-bad82d1b5a57">
                
                <!-- Bot Protection -->
                <input type="checkbox" name="botcheck" class="hidden" style="display: none;">
                
                <!-- Form Fields -->
                <div class="row g-3">
                  <div class="col-md-6">
                    <input type="text" name="name" class="form-control" placeholder="Your Name" required>
                  </div>
                  <div class="col-md-6">
                    <input type="email" name="email" class="form-control" placeholder="Your Email" required>
                  </div>
                  <div class="col-12">
                    <input type="text" name="subject" class="form-control" placeholder="Subject">
                  </div>
                  <div class="col-12">
                    <textarea name="message" class="form-control" rows="5" placeholder="Your Message" required></textarea>
                  </div>
                  
                  <div class="col-12 text-center">
                    <button type="submit" class="btn btn-primary">
                      <i class="fas fa-paper-plane"></i> Send Message
                    </button>
                  </div>
                </div>
              </form>
            </div>
            
            <!-- Google Maps -->
            <div class="map-container">
              <h3 class="map-title text-center mb-4">My Location</h3>
              <div class="map-wrapper">
                <iframe 
                  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d61371.807793682274!2d120.56077899999998!3d15.975053549999998!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x33913fb28b8acf8f%3A0x432ead83f669f54f!2sUrdaneta%20City%2C%20Pangasinan!5e0!3m2!1sen!2sph!4v1770902693047!5m2!1sen!2sph" 
                  width="100%" 
                  height="400" 
                  style="border:0; border-radius: 10px;" 
                  allowfullscreen="" 
                  loading="lazy" 
                  referrerpolicy="no-referrer-when-downgrade">
                </iframe>
              </div>
              <p class="map-caption text-center mt-3">
                <i class="fas fa-map-marker-alt text-primary me-2"></i>
                Urdaneta City, Pangasinan, Philippines
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <p>&copy; 2026 Manuel Buenviaje II. All rights reserved.</p>
        <div class="footer-social">
          <a href="https://github.com/manuelbuenviajeII" target="_blank"><i class="fab fa-github"></i></a>
          <a href="https://www.linkedin.com/in/manuel-buenviaje-301a8b222/" target="_blank"><i class="fab fa-linkedin"></i></a>
          <a href="https://www.instagram.com/ritsuhamano/" target="_blank"><i class="fab fa-instagram"></i></a>
          <a href="https://www.facebook.com/Story.Teller29" target="_blank"><i class="fab fa-facebook"></i></a>
        </div>
        <!-- Footer Resume Link -->
        <div class="footer-resume mt-3">
          <a :href="resumePreviewLink" target="_blank" class="text-muted">
            <i class="fas fa-file-pdf"></i> View Resume
          </a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Profile image mula sa Facebook
const profileImage = ref('https://scontent.fmnl35-1.fna.fbcdn.net/v/t1.6435-9/31902046_2194411433908966_5421820797251485696_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=a5f93a&_nc_eui2=AeGF8YHEl_h4cyh7v8aUNE4cw4ghUExM-HrDiCFQTEz4erxrL6QceXlnatE5aNvJRhS1sdIwZhQg1qJitVy9EG-a&_nc_ohc=jyCqf2URU9QQ7kNvwHAcB9q&_nc_oc=AdkZhwYWmLQQbXWHZbME0YYkvsWN_FmMv5RyhOGC0xnQJvEAF6WUZ0zg-f3_M4jBiqE&_nc_zt=23&_nc_ht=scontent.fmnl35-1.fna&_nc_gid=ejza205jwImJ72N9zJWpag&oh=00_AfsBb4qEvn5ilMV3_TiTIVdE4dtiGRVSy78IrpVFP1vmLw&oe=69B52565')

// About image mula sa Facebook
const aboutImage = ref('https://scontent.fmnl35-1.fna.fbcdn.net/v/t39.30808-6/483526654_24155512354038892_4957505010177271580_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=a5f93a&_nc_eui2=AeHrqrkF_XykLble-Ep8lTKtR-_5807YLatH7_nzTtgtq65xIKQtI0c7r61mnFbXBsFMDDLBIKTPcgoUTauEs4OJ&_nc_ohc=wE6r51TUOBwQ7kNvwFDSjnZ&_nc_oc=AdkGtA93iBKFxCPZcZp9v8KQgIt0cI8vl87SApQ4dZvfWP3rC9BlZvTQRx1L13AHSkc&_nc_zt=23&_nc_ht=scontent.fmnl35-1.fna&_nc_gid=d-UKbCcYC2QxBIEUQL-GmQ&oh=00_Aft3-lGy7V18f37t_nggqdt1xTN8VUTnY4TeuyzFbKZ6GQ&oe=6993971F')

// ✅ RESUME LINKS - GOOGLE DRIVE PREVIEW + DOWNLOAD
const resumePreviewLink = ref('https://drive.google.com/file/d/1bRu1m4QFa7NMMT87B2K5cWttdLBH7nAU/view?usp=sharing')
const resumeDownloadLink = ref('https://drive.google.com/file/d/1bRu1m4QFa7NMMT87B2K5cWttdLBH7nAU/view?usp=sharing')

const skills = [
  { name: 'HTML5', icon: 'fab fa-html5' },
  { name: 'CSS3', icon: 'fab fa-css3-alt' },
  { name: 'JavaScript', icon: 'fab fa-js' },
  { name: 'Vue.js', icon: 'fab fa-vuejs' },
  { name: 'React', icon: 'fab fa-react' },
  { name: 'Node.js', icon: 'fab fa-node' },
  { name: 'Express.js', icon: 'fas fa-server' },
  { name: 'MongoDB', icon: 'fas fa-database' },
  { name: 'Bootstrap', icon: 'fab fa-bootstrap' },
  { name: 'Git', icon: 'fab fa-git-alt' },
  { name: 'GitHub', icon: 'fab fa-github' },
  { name: 'REST API', icon: 'fas fa-plug' }
]

// Fallback kung hindi mag-load ang images
const handleImageError = () => {
  console.log('Profile image failed to load, using placeholder')
  profileImage.value = 'https://placehold.co/600x600/1a1a1a/fff?text=Manuel+Buenviaje+II'
}

const handleAboutImageError = () => {
  console.log('About image failed to load, using placeholder')
  aboutImage.value = 'https://placehold.co/600x600/1a1a1a/fff?text=About+Me'
}

onMounted(() => {
  // Initialize particles.js
  if (window.particlesJS) {
    window.particlesJS('particles-js', {
      particles: {
        number: {
          value: 80,
          density: {
            enable: true,
            value_area: 800
          }
        },
        color: {
          value: '#00d4ff'
        },
        shape: {
          type: 'circle'
        },
        opacity: {
          value: 0.5,
          random: false
        },
        size: {
          value: 3,
          random: true
        },
        line_linked: {
          enable: true,
          distance: 150,
          color: '#00d4ff',
          opacity: 0.4,
          width: 1
        },
        move: {
          enable: true,
          speed: 2,
          direction: 'none',
          random: false,
          straight: false,
          out_mode: 'out',
          bounce: false
        }
      },
      interactivity: {
        detect_on: 'canvas',
        events: {
          onhover: {
            enable: true,
            mode: 'repulse'
          },
          onclick: {
            enable: true,
            mode: 'push'
          },
          resize: true
        }
      },
      retina_detect: true
    })
  }
})
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&family=Open+Sans:wght@300;400;600&family=Roboto:wght@300;400;500;700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Open Sans', sans-serif;
  color: #fff;
  overflow-x: hidden;
  background: linear-gradient(135deg, #0a192f 0%, #0d2137 100%);
}

#app {
  position: relative;
  min-height: 100vh;
}

#particles-js {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  background: linear-gradient(135deg, #0a192f 0%, #0d2137 100%);
}

/* Navigation */
.navbar {
  background: rgba(10, 25, 47, 0.95);
  backdrop-filter: blur(10px);
  padding: 1rem 0;
  z-index: 1000;
  transition: all 0.3s ease;
}

.navbar-brand {
  font-size: 1.8rem;
  font-weight: 700;
  color: #fff !important;
  font-family: 'Montserrat', sans-serif;
}

.navbar-brand span {
  color: #00d4ff;
}

.nav-link {
  color: #fff !important;
  margin: 0 0.5rem;
  font-weight: 500;
  transition: color 0.3s ease;
  position: relative;
}

.nav-link:hover {
  color: #00d4ff !important;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 2px;
  background: #00d4ff;
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 80%;
}

/* Sections */
.section {
  position: relative;
  z-index: 1;
  padding: 80px 0;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #fff;
  font-family: 'Montserrat', sans-serif;
  margin-bottom: 1rem;
  position: relative;
  display: inline-block;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 60px;
  height: 3px;
  background: #00d4ff;
}

.section-title .highlight {
  color: #00d4ff;
}

.section-subtitle {
  color: #a0aec0;
  font-size: 1.1rem;
}

/* Home Section */
.home-section {
  padding-top: 100px;
}

.greeting {
  font-size: 1.5rem;
  color: #00d4ff;
  font-weight: 400;
  margin-bottom: 0.5rem;
}

.name {
  font-size: 3.5rem;
  font-weight: 700;
  color: #fff;
  margin-bottom: 0.5rem;
  font-family: 'Montserrat', sans-serif;
}

.title {
  font-size: 2rem;
  color: #a0aec0;
  font-weight: 400;
  margin-bottom: 1rem;
}

.description {
  font-size: 1.1rem;
  color: #a0aec0;
  margin-bottom: 2rem;
  max-width: 600px;
}

.cta-buttons {
  display: flex;
  gap: 1rem;
}

.btn {
  padding: 0.8rem 2rem;
  border-radius: 5px;
  font-weight: 600;
  transition: all 0.3s ease;
  border: none;
}

.btn-primary {
  background: #00d4ff;
  color: #0a192f;
}

.btn-primary:hover {
  background: #00b8d9;
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 212, 255, 0.3);
}

.btn-outline-light {
  border: 2px solid #fff;
  color: #fff;
  background: transparent;
}

.btn-outline-light:hover {
  background: #fff;
  color: #0a192f;
  transform: translateY(-2px);
}

.btn-outline-primary {
  border: 1px solid #00d4ff;
  color: #00d4ff;
  background: transparent;
  padding: 0.4rem 1rem;
}

.btn-outline-primary:hover {
  background: #00d4ff;
  color: #0a192f;
}

/* Profile Image */
.profile-image-container {
  position: relative;
  width: 400px;
  height: 400px;
  margin: 0 auto;
  border-radius: 50%;
  overflow: hidden;
  border: 3px solid #00d4ff;
  box-shadow: 0 0 30px rgba(0, 212, 255, 0.3);
  animation: float 6s ease-in-out infinite;
}

.profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

/* About Section */
.about-image-container {
  position: relative;
  width: 100%;
  max-width: 400px;
  margin: 0 auto;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
}

.about-image {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.5s ease;
}

.about-image:hover {
  transform: scale(1.05);
}

.about-text {
  color: #a0aec0;
  font-size: 1.1rem;
  margin-bottom: 1rem;
}

.subtitle {
  color: #00d4ff;
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
}

.personal-info {
  background: rgba(255, 255, 255, 0.05);
  padding: 1.5rem;
  border-radius: 10px;
  margin: 1.5rem 0;
}

.personal-info p {
  color: #a0aec0;
  margin-bottom: 0.5rem;
}

.personal-info strong {
  color: #00d4ff;
}

/* Resume Buttons */
.resume-buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.ms-2 {
  margin-left: 0.5rem;
}

/* Skills Section */
.skills-section {
  background: rgba(10, 25, 47, 0.5);
  backdrop-filter: blur(5px);
}

.skill-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  padding: 1.5rem;
  text-align: center;
  transition: all 0.3s ease;
  height: 100%;
}

.skill-card:hover {
  transform: translateY(-5px);
  background: rgba(255, 255, 255, 0.1);
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
}

.skill-icon {
  font-size: 2.5rem;
  color: #00d4ff;
  margin-bottom: 0.5rem;
}

.skill-card h4 {
  font-size: 1rem;
  color: #fff;
  margin: 0;
}

/* Projects Section */
.project-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  overflow: hidden;
  transition: all 0.3s ease;
  height: 100%;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
}

.project-img {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.project-img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.project-card:hover .project-img img {
  transform: scale(1.1);
}

.project-info {
  padding: 1.5rem;
}

.project-info h3 {
  color: #fff;
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.project-info p {
  color: #a0aec0;
  font-size: 0.9rem;
  margin-bottom: 1rem;
  line-height: 1.6;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.project-tech span {
  background: rgba(0, 212, 255, 0.1);
  color: #00d4ff;
  padding: 0.25rem 0.75rem;
  border-radius: 20px;
  font-size: 0.8rem;
}

.project-links {
  display: flex;
  gap: 0.5rem;
}

/* Contact Section */
.contact-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  padding: 2rem;
  margin-bottom: 2rem;
}

.form-control {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.1);
  color: #fff;
  padding: 0.8rem;
}

.form-control:focus {
  background: rgba(255, 255, 255, 0.15);
  border-color: #00d4ff;
  color: #fff;
  box-shadow: 0 0 0 0.2rem rgba(0, 212, 255, 0.25);
}

.form-control::placeholder {
  color: rgba(255, 255, 255, 0.5);
}

/* Map Styles */
.map-container {
  margin-top: 2rem;
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 20px;
  backdrop-filter: blur(5px);
}

.map-title {
  color: #fff;
  font-family: 'Montserrat', sans-serif;
  font-size: 1.5rem;
  font-weight: 600;
}

.map-wrapper {
  position: relative;
  width: 100%;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
}

.map-caption {
  color: #a0aec0;
  font-size: 1rem;
}

.map-caption i {
  color: #00d4ff;
}

/* Hidden checkbox for bot prevention */
.hidden {
  display: none;
}

/* Social Links */
.social-links, .footer-social {
  display: flex;
  gap: 1rem;
}

.social-link, .footer-social a {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: #fff;
  transition: all 0.3s ease;
}

.social-link:hover, .footer-social a:hover {
  background: #00d4ff;
  color: #0a192f;
  transform: translateY(-3px);
}

/* Footer */
.footer {
  background: rgba(10, 25, 47, 0.95);
  padding: 2rem 0;
  text-align: center;
  position: relative;
  z-index: 1;
}

.footer p {
  color: #a0aec0;
  margin-bottom: 1rem;
}

.footer-social {
  justify-content: center;
}

.footer-resume a {
  color: #a0aec0;
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s ease;
}

.footer-resume a:hover {
  color: #00d4ff;
}

.footer-resume i {
  margin-right: 0.3rem;
}

/* Responsive Design */
@media (max-width: 991px) {
  .profile-image-container {
    width: 300px;
    height: 300px;
    margin-top: 2rem;
  }
  
  .name {
    font-size: 2.5rem;
  }
  
  .title {
    font-size: 1.5rem;
  }
  
  .section {
    padding: 60px 0;
  }
}

@media (max-width: 767px) {
  .profile-image-container {
    width: 250px;
    height: 250px;
  }
  
  .name {
    font-size: 2rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .cta-buttons {
    flex-direction: column;
  }
  
  .btn {
    width: 100%;
  }
  
  .map-wrapper iframe {
    height: 350px;
  }
  
  .resume-buttons {
    flex-direction: column;
  }
  
  .ms-2 {
    margin-left: 0 !important;
  }
}

@media (max-width: 576px) {
  .profile-image-container {
    width: 200px;
    height: 200px;
  }
  
  .map-wrapper iframe {
    height: 300px;
  }
}
</style>