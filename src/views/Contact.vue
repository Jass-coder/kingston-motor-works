<script setup></script>

<template>
  <section class="contact-hero">
    <div class="wrap">
      <div class="eyebrow">Contact Us</div>
      <h1>Let's get your car booked in.</h1>
      <p>Call, email, or drop by the workshop — we're happy to talk through what your car needs.</p>
    </div>
  </section>

  <section class="contact-body">
    <div class="wrap contact-grid">
      <div class="contact-info">
        <dl>
          <div>
            <dt class="eyebrow">Address</dt>
            <dd>12/18 Katherine Drive<br />Ravenhall VIC 3023<br />Australia</dd>
          </div>
          <div>
            <dt class="eyebrow">Phone</dt>
            <dd><a href="tel:0450224747">0450 224 747</a></dd>
          </div>
          <div>
            <dt class="eyebrow">Email</dt>
            <dd><a href="mailto:Victoria.kingstonmotorworks@gmail.com">Victoria.kingstonmotorworks@gmail.com</a></dd>
          </div>
        </dl>

        <div class="hours-table">
          <div><span>Monday – Friday</span><span>8:00am – 5:30pm</span></div>
          <div><span>Saturday</span><span>8:00am – 1:00pm</span></div>
          <div><span>Sunday</span><span>Closed</span></div>
        </div>
      </div>

      <div class="map-frame">
        <iframe
          src="https://www.google.com/maps?q=12/18+Katherine+Drive,+Ravenhall+VIC+3023,+Australia&output=embed"
          loading="lazy"
          title="Kingston Motor Works location map"
        ></iframe>
      </div>
    </div>
  </section>

  <section class="cta-band">
    <div class="wrap">
      <h2>Your car, sorted properly.</h2>
      <a href="tel:0450224747" class="btn-primary">Call 0450 224 747</a>
    </div>
  </section>
</template>

<style scoped>
.contact-hero{
  padding-top:180px; padding-bottom:50px;
  background:var(--surface); border-bottom:1px solid var(--hairline);
}
.contact-hero h1{ font-size:clamp(2.4rem, 5vw, 3.6rem); margin-top:14px; }
.contact-hero p{
  color:var(--muted); margin-top:16px; max-width:48ch;
  font-family:var(--font-body); text-transform:none; font-size:1.02rem;
}

.contact-grid{ display:grid; grid-template-columns:0.9fr 1.1fr; gap:64px; }
.contact-info dl{ display:flex; flex-direction:column; gap:26px; }
.contact-info dt{ margin-bottom:6px; }
.contact-info dd{ font-size:1.1rem; }
.contact-info dd a:hover{ color:var(--sky-bright); }

.hours-table{ margin-top:34px; border-top:1px solid var(--hairline); padding-top:20px; }
.hours-table div{
  display:flex; justify-content:space-between; padding:8px 0; font-size:0.94rem;
  color:var(--muted); border-bottom:1px solid var(--hairline);
}
.hours-table div span:last-child{ color:var(--text); }

.map-frame{ border:1px solid var(--hairline); aspect-ratio:4/3; overflow:hidden; border-radius:var(--radius); box-shadow:var(--shadow-md); }
.map-frame iframe{ width:100%; height:100%; border:0; filter:none; }

.cta-band{ text-align:center; background:var(--surface); border-top:1px solid var(--hairline); }
.cta-band h2{ font-size:clamp(1.8rem, 3.4vw, 2.6rem); margin-bottom:30px; }

@media (max-width:900px){
  .contact-hero{ padding-top:150px; }
  .contact-grid{ grid-template-columns:1fr; }
}
</style>
