<script setup>
import ServiceIcon from '../components/ServiceIcon.vue'

const services = [
  { num: '01', icon: 'gauge', title: 'Engine Diagnostics', desc: 'Dealer-grade scan tools and targeted testing find the real fault before repairs are quoted.', tags: ['Fault Codes', 'Sensor Testing'] },
  { num: '02', icon: 'wrench', title: 'Mechanical Repairs', desc: 'Reliable repairs for all makes and models, from everyday wear items to more involved workshop jobs.', tags: ['General Repairs', 'All Makes'] },
  { num: '03', icon: 'brake', title: 'Brakes & Suspension', desc: 'Braking and handling issues resolved with quality parts, careful inspection and correct fitment.', tags: ['Pads & Discs', 'Suspension'] },
  { num: '04', icon: 'bolt', title: 'Electrical Systems', desc: 'Electrical faults diagnosed at the source, including charging, starting, wiring and vehicle electronics.', tags: ['Alternators', 'Starter Motors', 'Batteries'] },
]
</script>

<template>
  <!-- HERO -->
  <section class="hero">
    <div class="wrap hero-grid">
      <div>
        <div class="eyebrow">Ravenhall, VIC · Automotive Repair Shop</div>
        <h1>We keep your car <span>running smooth.</span></h1>
        <p class="hero-sub">
          Kingston Motor Works is a Ravenhall-based workshop servicing all makes and models —
          honest advice, fair prices, and repairs built to last.
        </p>
        <div class="hero-actions">
          <router-link to="/contact" class="btn-primary">Get In Touch</router-link>
          <router-link to="/services" class="btn-ghost">View Services</router-link>
        </div>
      </div>
      <div class="hero-card">
        <span class="hero-card-label">Why Book With Kingston</span>
        <div class="hero-card-row"><strong>10+ Years</strong> Turning Wrenches</div>
        <div class="chevron-divider"></div>
        <div class="hero-card-row"><strong>All Makes</strong> & Models Welcome</div>
        <div class="chevron-divider"></div>
        <div class="hero-card-row"><strong>Roadworthy</strong> Inspections</div>
      </div>
    </div>
  </section>

  <!-- SERVICES PREVIEW -->
  <section class="services-preview">
    <div class="wrap">
      <div class="section-head">
        <div class="eyebrow">What We Do</div>
        <h2>All makes. All models.</h2>
        <p>From routine servicing to full diagnostics, every car gets the same standard of work.</p>
      </div>
      <div class="service-grid">
        <div class="s-card" v-for="s in services" :key="s.num">
          <div class="s-icon-badge"><ServiceIcon :name="s.icon" /></div>
          <div class="s-num">{{ s.num }}</div>
          <h3>{{ s.title }}</h3>
          <p>{{ s.desc }}</p>
          <div class="s-tags"><span v-for="tag in s.tags" :key="tag">{{ tag }}</span></div>
        </div>
      </div>
      <router-link to="/services" class="btn-ghost see-all">See All Services</router-link>
    </div>
  </section>

  <!-- ABOUT PREVIEW -->
  <section class="about-preview">
    <div class="wrap about-grid">
      <div class="img-frame">
        <img
          src="https://images.pexels.com/photos/8478233/pexels-photo-8478233.jpeg?auto=compress&cs=tinysrgb&w=900"
          alt="Mechanic working on a car engine in the workshop"
        />
      </div>
      <div>
        <div class="eyebrow">About Us</div>
        <h2>A workshop that knows cars.</h2>
        <p class="about-text">
          Ten years spent under the bonnet of everything from daily runabouts to
          performance builds. That experience is what tells us the difference between
          a quick fix and a fix that actually lasts.
        </p>
        <router-link to="/about" class="btn-ghost">Meet The Workshop</router-link>
      </div>
    </div>
  </section>

  <!-- CONTACT PREVIEW -->
  <section v-if="false" class="contact-preview">
    <div class="wrap">
      <div class="section-head" style="margin-bottom:44px;">
        <div class="eyebrow">Visit The Workshop</div>
        <h2>Find us. Call us. Book in.</h2>
      </div>
      <div class="cp-grid">
        <div class="cp-item">
          <span class="eyebrow">Address</span>
          <p>12/18 Katherine Drive<br />Ravenhall VIC 3023</p>
        </div>
        <div class="cp-item">
          <span class="eyebrow">Phone</span>
          <a href="tel:0450224747">0450 224 747</a>
        </div>
        <div class="cp-item">
          <span class="eyebrow">Email</span>
          <a href="mailto:Victoria.kingstonmotorworks@gmail.com">Victoria.kingstonmotorworks@gmail.com</a>
        </div>
        <div class="cp-item">
          <span class="eyebrow">Hours</span>
          <p>Mon–Fri 8am–5:30pm<br />Sat 8am–1pm</p>
        </div>
      </div>
      <router-link to="/contact" class="btn-primary see-all">Get In Touch</router-link>
    </div>
  </section>
</template>

<style scoped>
.hero{
  padding-top:180px;
  background:
    linear-gradient(180deg, rgba(8,20,32,0.72) 0%, rgba(8,20,32,0.88) 90%),
    url('https://images.pexels.com/photos/8478219/pexels-photo-8478219.jpeg?auto=compress&cs=tinysrgb&w=1800') center/cover;
}
.hero-grid{ display:grid; grid-template-columns:1.2fr 0.8fr; gap:60px; align-items:center; padding-bottom:100px; }
.hero h1{
  font-size:clamp(2.8rem, 6vw, 5rem);
  margin-top:14px; color:#fff;
}
.hero h1 span{ color:var(--red); }
.hero-sub{
  color:#e6f1f8; font-size:1.05rem; max-width:42ch; margin-top:22px;
  font-family:var(--font-body); text-transform:none;
}
.hero .eyebrow{ color:#90d0ff; }
.hero-actions{ display:flex; gap:16px; margin-top:34px; flex-wrap:wrap; }

.hero-card{
  background:#fff; border:1px solid var(--hairline); padding:34px;
  border-radius:var(--radius); box-shadow:var(--shadow-md);
}
.hero-card-label{
  display:block; font-family:var(--font-label); font-size:0.72rem; font-weight:700;
  letter-spacing:0.14em; text-transform:uppercase; color:var(--sky); margin-bottom:6px;
}
.hero-card-row{ padding:14px 0; font-family:var(--font-label); font-size:1.05rem; font-weight:600; letter-spacing:0.02em; text-transform:uppercase; }
.hero-card-row strong{ color:var(--sky-bright); }

.service-grid{
  display:grid; grid-template-columns:repeat(4,1fr); gap:22px;
}
.s-card{
  background:#fff; padding:32px 26px; border-radius:var(--radius);
  border:1px solid var(--hairline); box-shadow:var(--shadow-sm);
  transition:box-shadow .25s, transform .25s, border-color .25s;
}
.s-card:hover{ box-shadow:var(--shadow-hover); transform:translateY(-6px); border-color:var(--sky); }
.s-icon-badge{
  width:52px; height:52px; border-radius:12px; background:#e7f3fc; color:var(--sky);
  display:flex; align-items:center; justify-content:center; margin-bottom:18px;
  transition:background .25s, color .25s;
}
.s-card:hover .s-icon-badge{ background:var(--sky); color:#fff; }
.s-num{ font-family:var(--font-label); font-weight:700; color:var(--sky); font-size:0.85rem; letter-spacing:0.08em; }
.s-card h3{ color:var(--text); font-size:1.4rem; margin-top:10px; transition:color .2s; }
.s-card:hover h3{ color:var(--sky-bright); }
.s-card p{ color:var(--muted); font-size:0.92rem; margin-top:8px; font-family:var(--font-body); text-transform:none; }
.s-tags{ display:flex; flex-wrap:wrap; gap:7px; margin-top:16px; }
.s-tags span{ border:1px solid var(--hairline); border-radius:999px; color:var(--muted); font-family:var(--font-label); font-size:.72rem; font-weight:700; letter-spacing:.06em; padding:4px 10px; text-transform:uppercase; transition:background .2s, border-color .2s, color .2s; }
.s-card:hover .s-tags span{ background:#eaf6ff; border-color:var(--sky); color:var(--sky-bright); }

.see-all{ margin-top:40px; }

.about-grid{ display:grid; grid-template-columns:0.9fr 1.1fr; gap:64px; align-items:center; }
.img-frame{ aspect-ratio:4/5; border:1px solid var(--hairline); overflow:hidden; border-radius:var(--radius); box-shadow:var(--shadow-md); }
.about-text{ color:var(--muted); margin:20px 0 30px; max-width:48ch; font-family:var(--font-body); }

.contact-preview{ background:var(--surface); }
.cp-grid{ display:grid; grid-template-columns:repeat(4,1fr); gap:40px; }
.cp-item{ border-top:2px solid var(--red); padding-top:18px; }
.cp-item p, .cp-item a{ margin-top:10px; font-size:1rem; display:block; }
.cp-item a:hover{ color:var(--red-bright); }

@media (max-width:900px){
  .hero{ padding-top:150px; }
  .hero-grid, .about-grid{ grid-template-columns:1fr; }
  .service-grid{ grid-template-columns:repeat(2,1fr); }
  .cp-grid{ grid-template-columns:1fr 1fr; }
}
</style>
