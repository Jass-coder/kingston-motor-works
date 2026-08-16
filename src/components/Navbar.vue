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
          <a href="tel:0450224747" class="nav-phone">
            <span class="nav-phone-icon">
              <svg viewBox="0 0 24 24" width="15" height="15" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
                <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z" />
              </svg>
            </span>
            <span class="nav-phone-number">0450 224 747</span>
          </a>
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
  padding:19px 32px;
}
.brand{ display:flex; align-items:center; }
.brand-logo{ display:block; height:47px; width:auto; max-width:250px; object-fit:contain; }

.nav-links{
  display:flex; align-items:center; gap:36px;
  font-family:var(--font-label); font-size:1rem; font-weight:600; letter-spacing:0.03em; text-transform:uppercase;
}
.nav-links a{ color:var(--muted); transition:color .2s; padding:6px 0; }
.nav-links a:hover{ color:var(--sky-bright); }
.nav-links > li:not(.nav-cta-wrap) > a.router-link-active{
  color:var(--sky-bright); background:var(--surface-2); border-radius:999px; padding:8px 14px;
}

.nav-links .nav-phone{
  display:flex; align-items:center; gap:10px;
  background:var(--text); border-radius:999px;
  padding:6px 18px 6px 6px;
  transition:background .2s, transform .15s;
}
.nav-links .nav-phone:hover{ background:#000; color:#fff; transform:translateY(-1px); }
.nav-phone-icon{
  width:30px; height:30px; border-radius:50%;
  background:var(--red); color:#fff;
  display:flex; align-items:center; justify-content:center; flex-shrink:0;
}
.nav-phone-number{
  font-family:var(--font-label); font-size:.95rem; font-weight:600;
  color:#fff; white-space:nowrap;
}
.nav-cta-wrap{ margin-left:4px; }

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
    position:fixed; top:85px; left:0; right:0; bottom:0;
    background:var(--bg); flex-direction:column; align-items:flex-start;
    padding:40px 32px; gap:28px; font-size:1.1rem;
    transform:translateX(100%); transition:transform .25s ease;
  }
  .nav-links.open{ transform:translateX(0); }
  .nav-cta-wrap{ margin:12px 0 0; }
  .nav-phone{ min-height:42px; }
}
</style>
