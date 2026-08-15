<script setup>
const values = [
  { title: 'Honest Advice', desc: "You'll always know what a job needs and why — explained plainly, before we touch the car." },
  { title: 'Fair Prices', desc: 'Straightforward pricing with no inflated line items or surprise add-ons.' },
  { title: 'Lasting Results', desc: 'Repairs done properly the first time, so they stay fixed.' },
]
</script>

<template>
  <section class="about-hero">
    <div class="wrap about-hero-grid">
      <div>
        <div class="eyebrow">About Kingston Motor Works</div>
        <h1>Ten years under the bonnet.</h1>
        <p class="lead">
          Kingston Motor Works started with a genuine love of cars and grew into a
          Ravenhall workshop that owners actually trust — servicing every make and
          model, from daily drivers to weekend builds.
        </p>
        <blockquote class="quote-block">
          "I don't send a car back out unless I'd be happy driving it myself. That's
          the only standard that matters here."
          <cite>— Kingston Motor Works</cite>
        </blockquote>
      </div>
      <div class="img-frame">
        <img
          src="https://images.pexels.com/photos/8478225/pexels-photo-8478225.jpeg?auto=compress&cs=tinysrgb&w=900"
          alt="Mechanic's hands closely inspecting a car engine"
        />
      </div>
    </div>
  </section>

  <section class="values-section">
    <div class="wrap">
      <div class="section-head">
        <div class="eyebrow">Why Owners Trust Us</div>
        <h2>Standards we don't bend on.</h2>
        <p>This is the whole philosophy behind Kingston Motor Works, boiled down to three things every customer can expect.</p>
      </div>
      <div class="values-grid">
        <div class="v-card" v-for="v in values" :key="v.title">
          <h3>{{ v.title }}</h3>
          <p>{{ v.desc }}</p>
        </div>
      </div>
    </div>
  </section>

  <section class="gallery-section">
    <div class="wrap">
      <div class="eyebrow">In The Workshop</div>
      <div class="gallery-grid">
        <div class="g-item">
          <img src="https://images.pexels.com/photos/8478228/pexels-photo-8478228.jpeg?auto=compress&cs=tinysrgb&w=700" alt="Mechanic inspecting an open engine bay and battery" />
        </div>
        <div class="g-item">
          <img src="https://images.pexels.com/photos/3806249/pexels-photo-3806249.jpeg?auto=compress&cs=tinysrgb&w=700" alt="Mechanic changing a car tyre in the workshop" />
        </div>
        <div class="g-item">
          <img src="https://images.pexels.com/photos/6870331/pexels-photo-6870331.jpeg?auto=compress&cs=tinysrgb&w=700" alt="Mechanic replacing a tyre on an SUV in the repair bay" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-hero{ padding-top:180px; }
.about-hero-grid{ display:grid; grid-template-columns:1.1fr 0.9fr; gap:64px; align-items:center; }
.about-hero h1{ font-size:clamp(2.4rem, 5vw, 3.6rem); margin-top:14px; max-width:15ch; }
.lead{
  color:var(--muted); font-size:1.05rem; margin-top:22px; max-width:46ch;
  font-family:var(--font-body); text-transform:none;
}
.quote-block{
  margin-top:30px; padding-left:22px; border-left:2px solid var(--red);
  font-size:1.15rem; font-style:italic; font-family:var(--font-body); font-weight:400;
}
.quote-block cite{
  display:block; margin-top:14px; font-family:var(--font-label); font-style:normal;
  font-size:0.72rem; letter-spacing:0.1em; text-transform:uppercase; color:var(--muted);
}
.img-frame{ aspect-ratio:1/1.05; border:1px solid var(--hairline); overflow:hidden; border-radius:var(--radius); box-shadow:var(--shadow-md); }

.values-section{ background:var(--surface); }
.values-grid{
  display:grid; grid-template-columns:repeat(3,1fr); gap:22px; margin-top:10px;
}
.v-card{ background:#fff; border:1px solid var(--hairline); border-radius:var(--radius); padding:36px 30px; box-shadow:var(--shadow-sm); transition:box-shadow .25s, transform .25s, border-color .25s; }
.v-card:hover{ box-shadow:var(--shadow-hover); transform:translateY(-6px); border-color:var(--sky); }
.v-card h3{ font-size:1.4rem; }
.v-card p{ color:var(--muted); font-size:0.92rem; margin-top:10px; font-family:var(--font-body); text-transform:none; }

.gallery-grid{ display:grid; grid-template-columns:repeat(3,1fr); gap:16px; margin-top:40px; }
.g-item{ aspect-ratio:4/5; overflow:hidden; border-radius:var(--radius); box-shadow:var(--shadow-sm); }
.g-item img{ transition:transform .5s; }
.g-item:hover img{ transform:scale(1.06); }

@media (max-width:900px){
  .about-hero{ padding-top:150px; }
  .about-hero-grid{ grid-template-columns:1fr; }
  .values-grid{ grid-template-columns:1fr; }
  .gallery-grid{ grid-template-columns:1fr 1fr; }
}
</style>
