<script setup>
import ServiceIcon from '../components/ServiceIcon.vue'

const services = [
  { num: '01', icon: 'gauge', title: 'Engine Diagnostics', desc: 'Dealer-grade scan tools, live data and targeted testing identify the true fault instead of replacing parts on a guess. We explain the findings and quote before work begins.', tags: ['Fault Codes', 'Sensor Testing', 'Scan Tools', 'Live Data'] },
  { num: '02', icon: 'wrench', title: 'Mechanical Repairs', desc: 'From cooling and drivetrain concerns to worn components and general workshop repairs, we keep all makes and models dependable with thorough, practical work.', tags: ['All Makes & Models', 'General Repairs', 'Cooling Systems', 'Drivetrain'] },
  { num: '03', icon: 'brake', title: 'Brakes & Suspension', desc: 'Whether it is a pad-and-rotor replacement, a suspension knock or a complete rebuild, we restore safe stopping performance, steering response and ride comfort.', tags: ['Brake Pads & Discs', 'Suspension', 'Shock Absorbers', 'Steering'] },
  { num: '04', icon: 'bolt', title: 'Electrical Systems', desc: 'We trace electrical faults at the source, repairing batteries, charging and starting systems, wiring issues and on-board electronics with proper diagnostic equipment.', tags: ['Batteries', 'Wiring', 'Electronics', 'Alternators', 'Starter Motors'] },
  { num: '05', icon: 'clipboard', title: 'Logbook Servicing', desc: "Manufacturer-scheduled servicing completed to your vehicle's logbook requirements, including essential inspections and fluids, to help protect performance and warranty coverage.", tags: ['Oil & Filter', 'Fluid Checks', 'Logbook Stamps', 'Warranty Safe'] },
  { num: '06', icon: 'shield', title: 'Roadworthy Inspections', desc: 'Roadworthy inspections are completed carefully and efficiently, checking the key safety items required for a certificate of roadworthiness.', tags: ['RWC', 'Safety Check', 'Vehicle Inspection', 'Compliance'] },
  { num: '07', icon: 'tyre', title: 'Tyres & Wheel Balancing', desc: 'Correct tyre fitting, rotation and precision balancing improve comfort, help tyres wear evenly and keep your vehicle tracking safely on the road.', tags: ['Tyre Fitting', 'Wheel Balancing', 'Tyre Rotation', 'Puncture Repairs'] },
  { num: '08', icon: 'engine', title: 'Performance & General Repairs', desc: 'From considered performance upgrades to ongoing general repairs, we apply the same careful workmanship so your vehicle remains responsive, reliable and enjoyable to drive.', tags: ['Performance', 'General Repairs', 'Upgrades', 'Workshop Advice'] },
]
</script>

<template>
  <section class="services-hero">
    <div class="wrap">
      <div class="eyebrow">Services</div>
      <h1>Every job, done properly.</h1>
      <p>Whether it's a warning light on the dash or a full brake rebuild, your car gets the same standard of work across all makes and models.</p>
    </div>
  </section>

  <section class="services-list">
    <div class="wrap">
      <div class="service-grid">
        <div class="service-card" v-for="s in services" :key="s.num">
          <div class="sc-top">
            <div class="s-icon-badge"><ServiceIcon :name="s.icon" /></div>
            <div class="sr-num">{{ s.num }}</div>
          </div>
          <h3>{{ s.title }}</h3>
          <p class="sr-desc">{{ s.desc }}</p>
          <div class="sr-tags"><span v-for="t in s.tags" :key="t">{{ t }}</span></div>
        </div>
      </div>
    </div>
  </section>

  <section class="cta-band">
    <div class="wrap">
      <h2>Not sure what your car needs?</h2>
      <p>Call the workshop and we'll talk you through it before anything is booked in.</p>
      <a href="tel:0455746249" class="btn-primary">Call 0455 746 249</a>
    </div>
  </section>
</template>

<style scoped>
.services-hero{ padding-top:180px; padding-bottom:60px; background:var(--surface); border-bottom:1px solid var(--hairline); }
.services-hero h1{ font-size:clamp(2.4rem, 5vw, 4rem); margin-top:14px; max-width:16ch; }
.services-hero p{ color:var(--muted); max-width:52ch; margin-top:18px; font-family:var(--font-body); text-transform:none; font-size:1.05rem; }

.services-list{ padding-top:70px; }
.service-grid{ display:grid; grid-template-columns:repeat(2,1fr); gap:24px; }
.service-card{
  background:#fff; border:1px solid var(--hairline); border-radius:var(--radius);
  padding:32px; box-shadow:var(--shadow-sm);
  transition:box-shadow .25s, transform .25s, border-color .25s;
}
.service-card:hover{ box-shadow:var(--shadow-hover); transform:translateY(-6px); border-color:var(--sky); }
.sc-top{ display:flex; align-items:center; justify-content:space-between; }
.s-icon-badge{
  width:52px; height:52px; border-radius:12px; background:#e7f3fc; color:var(--sky);
  display:flex; align-items:center; justify-content:center;
  transition:background .25s, color .25s;
}
.service-card:hover .s-icon-badge{ background:var(--sky); color:#fff; }
.sr-num{ font-family:var(--font-label); font-weight:700; color:var(--hairline); font-size:1.4rem; letter-spacing:.06em; }
.service-card h3{ color:var(--text); font-size:1.55rem; line-height:1.05; margin-top:20px; transition:color .2s; }
.service-card:hover h3{ color:var(--sky-bright); }
.sr-desc{ color:var(--muted); font-family:var(--font-body); text-transform:none; font-size:0.98rem; margin-top:12px; }
.sr-tags{ margin-top:18px; display:flex; gap:8px; flex-wrap:wrap; }
.sr-tags span{ font-family:var(--font-label); font-weight:600; font-size:.75rem; letter-spacing:.06em; text-transform:uppercase; border:1px solid var(--hairline); border-radius:999px; padding:6px 12px; color:var(--muted); transition:background .2s, border-color .2s, color .2s; }
.service-card:hover .sr-tags span{ background:#eaf6ff; border-color:var(--sky); color:var(--sky-bright); }

.cta-band{ text-align:center; background:var(--surface); border-top:1px solid var(--hairline); margin-top:20px; }
.cta-band h2{ font-size:clamp(1.8rem, 3.4vw, 2.6rem); }
.cta-band p{ color:var(--muted); margin:16px auto 30px; max-width:40ch; font-family:var(--font-body); text-transform:none; }

@media (max-width:800px){ .service-grid{ grid-template-columns:1fr; } }
</style>

