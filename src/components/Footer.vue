<script setup>
import logoSrc from '../assets/kingston-motor-works-logo.png'

const year = new Date().getFullYear()
</script>

<template>
  <footer class="site-footer">
    <div class="wrap footer-grid">
      <div class="f-brand">
        <img :src="logoSrc" class="footer-logo" alt="Kingston Motor Works" />
        <p class="tagline">Quality work. Trusted service.</p>
      </div>

      <div class="f-col">
        <span class="eyebrow">Contact</span>
        <a href="tel:0450224747">0450 224 747</a>
        <a href="mailto:Victoria.kingstonmotorworks@gmail.com">Victoria.kingstonmotorworks@gmail.com</a>
      </div>

      <div class="f-col">
        <span class="eyebrow">Workshop</span>
        <p>12/18 Katherine Drive<br />Ravenhall VIC 3023</p>
      </div>

      <div class="f-col">
        <span class="eyebrow">Hours</span>
        <p>Mon–Fri: 8:00am – 5:30pm<br />Sat: 8:00am – 1:00pm</p>
      </div>

      <div class="f-col">
        <span class="eyebrow">Menu</span>
        <router-link to="/">Home</router-link>
        <router-link to="/services">Services</router-link>
        <router-link to="/about">About Us</router-link>
        <router-link to="/contact">Contact Us</router-link>
      </div>
    </div>

    <div class="chevron-divider wrap-divider"></div>

    <div class="wrap f-bottom">
      <span>© {{ year }} Kingston Motor Works. All rights reserved.</span>
      <span>Ravenhall's local automotive repair specialists.</span>
    </div>
  </footer>
</template>

<style scoped>
.site-footer{
  background:var(--surface);
  border-top:1px solid var(--hairline);
  padding-top:70px;
}
.footer-grid{
  display:grid;
  grid-template-columns:1.4fr 1fr 1fr 1fr 1fr;
  gap:30px;
  padding-bottom:50px;
}
.footer-logo{ display:block; height:74px; width:auto; max-width:285px; object-fit:contain; }
.tagline{ color:var(--muted); font-size:0.92rem; margin-top:16px; }

.f-col{ display:flex; flex-direction:column; gap:10px; }
.f-col .eyebrow{ margin-bottom:6px; font-size:0.75rem; }
.f-col a, .f-col p{ color:var(--muted); font-size:0.95rem; transition:color .2s; }
.f-col a:hover{ color:var(--sky-bright); }

.wrap-divider{ max-width:1200px; margin:0 auto; }

.f-bottom{
  display:flex; justify-content:space-between; flex-wrap:wrap; gap:12px;
  padding:26px 32px;
  font-family:var(--font-label); font-size:0.8rem; font-weight:600; letter-spacing:0.03em; text-transform:uppercase;
  color:var(--muted);
}

@media (max-width:860px){
  .footer-grid{ grid-template-columns:1fr 1fr; }
}
@media (max-width:520px){
  .footer-grid{ grid-template-columns:1fr; }
  .f-bottom{ flex-direction:column; }
}
</style>
