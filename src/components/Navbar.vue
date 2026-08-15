<script setup>
import { ref } from 'vue'
import logoSrc from '../assets/kingston-motor-works-logo.png'

const open = ref(false)
const toggle = () => (open.value = !open.value)
const close = () => (open.value = false)
</script>

<template>
  <header class="site-header">
    <nav class="wrap nav">
      <router-link to="/" class="brand" @click="close">
        <img :src="logoSrc" class="brand-logo" alt="Kingston Motor Works" />
      </router-link>

      <button class="nav-toggle" @click="toggle" :aria-expanded="open" aria-label="Toggle menu">
        <span :class="{ open }"></span>
      </button>

      <ul class="nav-links" :class="{ open }">
        <li><router-link to="/" @click="close">Home</router-link></li>
        <li><router-link to="/services" @click="close">Services</router-link></li>
        <li><router-link to="/about" @click="close">About Us</router-link></li>
        <li><router-link to="/contact" @click="close">Contact Us</router-link></li>
        <li class="nav-cta-wrap">
          <a href="tel:0450224747" class="nav-cta"><span>Call now</span><strong>0450 224 747</strong></a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.site-header{
  position:fixed; top:0; left:0; right:0; z-index:100;
  background:rgba(245,250,255,0.92);
  backdrop-filter:blur(10px);
  border-bottom:1px solid var(--hairline);
}
.nav{
  display:flex; align-items:center; justify-content:space-between;
  padding:16px 32px;
}
.brand{ display:flex; align-items:center; }
.brand-logo{ display:block; height:47px; width:auto; max-width:250px; object-fit:contain; }

.nav-links{
  display:flex; align-items:center; gap:32px;
  font-family:var(--font-label); font-size:1rem; font-weight:600; letter-spacing:0.04em; text-transform:uppercase;
}
.nav-links a{ color:var(--muted); transition:color .2s; padding:6px 0; }
.nav-links a:hover{ color:var(--sky-bright); }
.nav-links a.router-link-active{ color:var(--text); border-bottom:2px solid var(--red); }

.nav-cta{
  display:flex; flex-direction:column; align-items:flex-start; min-width:210px; white-space:nowrap; background:var(--red); color:#fff; padding:8px 30px 9px 20px; line-height:1;
  clip-path:polygon(0 0, 100% 0, 90% 100%, 0% 100%);
  transition:background .2s;
}
.nav-cta span{ font-size:.68rem; letter-spacing:.1em; opacity:.85; }
.nav-cta strong{ font-size:1rem; letter-spacing:.03em; margin-top:3px; }
.nav-cta:hover{ background:var(--red-bright); color:#fff; }
.nav-cta-wrap{ flex:0 0 210px; }

.nav-toggle{
  display:none; background:none; border:none; width:32px; height:24px;
  position:relative;
}
.nav-toggle span,
.nav-toggle span::before,
.nav-toggle span::after{
  content:''; position:absolute; left:0; width:100%; height:2px; background:var(--text);
  transition:transform .2s, opacity .2s;
}
.nav-toggle span{ top:11px; }
.nav-toggle span::before{ top:-8px; }
.nav-toggle span::after{ top:8px; }
.nav-toggle span.open{ background:transparent; }
.nav-toggle span.open::before{ transform:translateY(8px) rotate(45deg); }
.nav-toggle span.open::after{ transform:translateY(-8px) rotate(-45deg); }

@media (max-width:860px){
  .nav-toggle{ display:block; }
  .nav-links{
    position:fixed; top:79px; left:0; right:0; bottom:0;
    background:var(--bg); flex-direction:column; align-items:flex-start;
    padding:40px 32px; gap:28px; font-size:1.1rem;
    transform:translateX(100%); transition:transform .25s ease;
  }
  .nav-links.open{ transform:translateX(0); }
  .nav-cta-wrap{ margin-top:10px; }
  .nav-cta{ min-width:210px; }
}
</style>
