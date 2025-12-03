# BEAUTY PALOZZA — Hostable Website Files

This document contains a complete, hostable website for **BEAUTY PALOZZA** split into separate files. Copy each code block into its respective file in a single folder and open `index.html` to run locally.

---

## `index.html`
```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>BEAUTY PALOZZA — Home</title>
  <link rel="stylesheet" href="style.css">
  <link rel="stylesheet" href="screen.css">
</head>
<body>
  <header class="site-header">
    <div class="brand">
      <img src="logo.svg" alt="Beauty Palozza logo" class="logo">
      <h1>BEAUTY PALOZZA</h1>
    </div>
    <nav class="main-nav">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#apply">Apply</a>
      <a href="#checkout">Tickets</a>
      <a href="#dashboard" id="admin-link">Dashboard</a>
    </nav>
    <button class="cta" id="open-apply">Apply Now</button>
  </header>

  <main>
    <section id="home" class="hero">
      <div class="hero-content">
        <h2>Where Confidence Meets the Crown</h2>
        <p>Join BEAUTY PALOZZA — the most dazzling beauty pageant experience. Applications open now.</p>
        <div class="hero-actions">
          <button class="btn" id="hero-apply">Apply</button>
          <a class="btn secondary" href="#checkout">Buy Tickets</a>
        </div>
      </div>
      <div class="hero-art" aria-hidden="true"></div>
    </section>

    <section id="about" class="info">
      <h3>About Us</h3>
      <p>BEAUTY PALOZZA celebrates talent, poise, and purpose. We run regional and national competitions with scholarships and career opportunities for winners.</p>
      <div class="cards">
        <article class="card">
          <h4>Mission</h4>
          <p>Empower through confidence and community.</p>
        </article>
        <article class="card">
          <h4>Events</h4>
          <p>Regional qualifiers, final gala, and winners' mentorship.</p>
        </article>
        <article class="card">
          <h4>Support</h4>
          <p>Workshops, styling partners, and coaching for contestants.</p>
        </article>
      </div>
    </section>

    <section id="apply" class="apply-section">
      <h3>Application</h3>
      <p>Complete the form to apply as a contestant. Fields marked * are required.</p>
      <form id="application-form" class="form-card" novalidate>
        <div class="row">
          <label>Full name *<input name="fullname" required></label>
          <label>Email *<input type="email" name="email" required></label>
        </div>
        <div class="row">
          <label>Age *<input type="number" name="age" min="13" max="50" required></label>
          <label>Phone<input type="tel" name="phone"></label>
        </div>
        <label>City / Region<input name="city"></label>
        <label>Short bio *<textarea name="bio" rows="4" required></textarea></label>

        <label>Category *
          <select name="category" required>
            <option value="">Choose...</option>
            <option>Miss</option>
            <option>Mrs</option>
            <option>Teen</option>
            <option>Open</option>
          </select>
        </label>

        <label>Upload headshot (optional)<input type="file" name="photo" accept="image/*"></label>

        <div class="form-actions">
          <button type="submit" class="btn">Submit Application</button>
          <button type="button" class="btn ghost" id="save-draft">Save Draft</button>
        </div>

        <p class="disclaimer">By submitting, you agree to our <a href="#">terms &amp; privacy</a>.</p>
      </form>
    </section>

    <section id="checkout" class="checkout">
      <h3>Tickets & Checkout</h3>
      <div class="products">
        <div class="product">
          <h4>General Admission</h4>
          <p>Standard seating.</p>
          <div class="price">$25</div>
          <button class="btn add-to-cart" data-title="General Admission" data-price="25">Add</button>
        </div>
        <div class="product">
          <h4>VIP Ticket</h4>
          <p>Front row + meet & greet.</p>
          <div class="price">$120</div>
          <button class="btn add-to-cart" data-title="VIP Ticket" data-price="120">Add</button>
        </div>
      </div>
      <div id="cart" class="cart">
        <h4>Your Cart</h4>
        <ul id="cart-items"></ul>
        <div class="cart-total">Total: $<span id="cart-total">0</span></div>
        <button class="btn" id="checkout-btn">Checkout</button>
      </div>
    </section>

    <section id="redirect" class="redirect-hidden" aria-live="polite">
      <!-- Redirection result will render here -->
    </section>
  </main>

  <footer class="site-footer">
    <div>© <span id="year"></span> BEAUTY PALOZZA</div>
    <div class="socials">
      <a href="#">Instagram</a> · <a href="#">Facebook</a> · <a href="#">TikTok</a>
    </div>
  </footer>

  <script src="script.js"></script>
</body>
</html>
```

---

## `style.css`
```css
/* Base color system: vibrant, modern, and colorful */
:root{
  --bg:#fff6ff;
  --panel:#fff;
  --accent:#ff5aa5;
  --accent-2:#6d5cff;
  --muted:#6b6b6b;
  --glass: rgba(255,255,255,0.7);
}
*{box-sizing:border-box}
html,body{height:100%}
body{font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial; margin:0; background:linear-gradient(120deg,var(--bg), #f3f6ff); color:#222}

.site-header{display:flex;align-items:center;justify-content:space-between;padding:14px 24px;background:linear-gradient(90deg,var(--panel), #fff);box-shadow:0 4px 18px rgba(13,12,22,0.06);position:sticky;top:0;z-index:20}
.brand{display:flex;align-items:center;gap:12px}
.logo{width:48px;height:48px;border-radius:10px;background:linear-gradient(45deg,var(--accent),var(--accent-2));display:inline-block}
.main-nav a{margin:0 12px;color:var(--muted);text-decoration:none}
.cta{background:linear-gradient(90deg,var(--accent),var(--accent-2));color:#fff;border:none;padding:8px 14px;border-radius:12px;cursor:pointer}
.btn{background:var(--accent);border:none;color:#fff;padding:10px 14px;border-radius:10px;cursor:pointer}
.btn.secondary{background:transparent;color:var(--accent-2);border:2px solid rgba(109,92,255,0.08)}
.btn.ghost{background:transparent;border:1px dashed #ccc;color:var(--muted)}

.hero{display:grid;grid-template-columns:1fr 360px;gap:24px;padding:48px 24px;align-items:center}
.hero-content h2{font-size:36px;margin:0 0 8px}
.hero-content p{margin:0 0 18px;color:var(--muted)}
.hero-art{height:260px;border-radius:16px;background:conic-gradient(from 200deg,rgba(109,92,255,0.15),rgba(255,90,165,0.12));box-shadow:inset 0 10px 40px rgba(0,0,0,0.02)}

.info{padding:32px 24px}
.cards{display:flex;gap:16px;margin-top:12px}
.card{background:var(--panel);border-radius:12px;padding:18px;flex:1;box-shadow:0 6px 20px rgba(100,80,160,0.05)}

.apply-section{padding:24px}
.form-card{max-width:880px;background:var(--panel);padding:18px;border-radius:12px;box-shadow:0 10px 30px rgba(0,0,0,0.04)}
.row{display:flex;gap:12px}
label{display:block;margin:10px 0;font-size:14px;color:#333}
input,textarea,select{width:100%;padding:10px;border-radius:8px;border:1px solid #e8e8f1}
.form-actions{display:flex;gap:10px;margin-top:12px}
.disclaimer{font-size:12px;color:var(--muted);margin-top:12px}

.checkout{padding:24px}
.products{display:flex;gap:12px}
.product{background:var(--panel);padding:16px;border-radius:12px;flex:1}
.price{font-weight:700;margin:10px 0}
.cart{margin-top:18px;background:linear-gradient(180deg,rgba(255,255,255,0.9),#fff);padding:16px;border-radius:12px}

.site-footer{display:flex;justify-content:space-between;padding:16px 24px;border-top:1px solid rgba(0,0,0,0.04);margin-top:28px}

@media (max-width:900px){
  .hero{grid-template-columns:1fr;}
  .cards{flex-direction:column}
  .row{flex-direction:column}
}
```

---

## `screen.css`
```css
/* Extra styles for screens, animations, and accessibility tweaks */
:root{--slow:600ms}
*{scroll-behavior:smooth}
.hero-content h2{animation:slideIn var(--slow) ease both}
@keyframes slideIn{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:none}}

button:focus, input:focus, select:focus, textarea:focus{outline:3px solid rgba(109,92,255,0.12);outline-offset:3px}

/* Small helper for hidden redirect section */
.redirect-hidden{display:none}
.redirect-visible{display:block;padding:20px;background:linear-gradient(90deg,#fff,#fffefc);border-radius:12px}

/* Print rules */
@media print{header, .main-nav, .cta, .btn{display:none}body{background:#fff}}
```

---

## `script.js`
```javascript
/* Main site behavior: form handling, cart, redirection */
document.addEventListener('DOMContentLoaded', ()=>{
  document.getElementById('year').textContent = new Date().getFullYear();

  const openApplyBtns = [document.getElementById('open-apply'), document.getElementById('hero-apply')];
  openApplyBtns.forEach(btn => btn && btn.addEventListener('click', ()=>{
    document.getElementById('apply').scrollIntoView({behavior:'smooth'});
  }));

  // Application form submission -> simulate server, redirect
  const form = document.getElementById('application-form');
  form.addEventListener('submit', (e)=>{
    e.preventDefault();
    const data = new FormData(form);
    // Basic client validation
    if(!data.get('fullname') || !data.get('email') || !data.get('bio')){
      alert('Please complete all required fields.');
      return;
    }
    // Here you would send data to server. We'll simulate and redirect to a 'thank you'
    showRedirect({title:'Application received', message:`Thanks ${data.get('fullname')} — your application was submitted.`});
  });

  document.getElementById('save-draft').addEventListener('click', ()=>{
    const data = new FormData(form);
    const draft = {};
    for(const [k,v] of data.entries()){ draft[k]=v }
    localStorage.setItem('bp_application_draft', JSON.stringify(draft));
    alert('Draft saved locally.');
  });

  // Restore draft if present
  const saved = localStorage.getItem('bp_application_draft');
  if(saved){
    try{
      const obj = JSON.parse(saved);
      Object.keys(obj).forEach(k=>{
        const el = form.elements[k]; if(el) el.value = obj[k];
      })
    }catch(e){}
  }

  // Cart system
  const cart = [];
  const cartItems = document.getElementById('cart-items');
  const cartTotalEl = document.getElementById('cart-total');

  function renderCart(){
    cartItems.innerHTML='';
    let total = 0;
    cart.forEach((it, i)=>{
      const li = document.createElement('li');
      li.textContent = `${it.title} — $${it.price}`;
      const remove = document.createElement('button'); remove.textContent='x'; remove.className='btn ghost';
      remove.style.marginLeft='8px'; remove.addEventListener('click', ()=>{ cart.splice(i,1); renderCart(); });
      li.appendChild(remove);
      cartItems.appendChild(li);
      total += Number(it.price);
    });
    cartTotalEl.textContent = total.toFixed(2);
  }

  document.querySelectorAll('.add-to-cart').forEach(btn=>{
    btn.addEventListener('click', ()=>{
      cart.push({title:btn.dataset.title, price:btn.dataset.price});
      renderCart();
    })
  });

  document.getElementById('checkout-btn').addEventListener('click', ()=>{
    if(cart.length===0){ alert('Your cart is empty.'); return }
    // Simulate redirect to checkout page — in a real site you'd integrate Stripe/PayPal
    showRedirect({title:'Checkout', message:`Proceeding to checkout — total $${cart.reduce((s,i)=>s+Number(i.price),0).toFixed(2)}`});
  });

  // Simple redirect renderer
  function showRedirect({title,message}){
    const section = document.getElementById('redirect');
    section.className = 'redirect-visible';
    section.innerHTML = `<h3>${title}</h3><p>${message}</p><p><a href='index.html'>Return to home</a></p>`;
    section.scrollIntoView({behavior:'smooth'});
  }

});
```

---

## `dashboard.css`
```css
/* Admin dashboard styles */
:root{--surface:#fff;--muted:#666}
body.dashboard{font-family:Inter, sans-serif;background:#f6f8ff;margin:0}
.topbar{display:flex;justify-content:space-between;align-items:center;padding:12px 20px;background:linear-gradient(90deg,#fff,#faf8ff);box-shadow:0 6px 16px rgba(10,10,40,0.05)}
.container{display:grid;grid-template-columns:260px 1fr;gap:18px;padding:20px}
.sidebar{background:var(--surface);padding:12px;border-radius:12px}
.card{background:var(--surface);padding:14px;border-radius:10px;box-shadow:0 8px 30px rgba(100,80,160,0.04)}
.table{width:100%;border-collapse:collapse}
.table th,.table td{padding:10px;border-bottom:1px solid #f1f1fb}
.badge{background:#6d5cff;color:#fff;padding:6px 10px;border-radius:999px}
```

---

## `dashboard.js`
```javascript
/* Minimal dashboard for viewing applications (simulate local data) */
(function(){
  // Only run if dashboard elements present
  if(!document.querySelector('.dashboard')) return;
  const sample = JSON.parse(localStorage.getItem('bp_applications')||'[]');

  function render(){
    const tbody = document.getElementById('apps-body');
    if(!tbody) return;
    tbody.innerHTML = '';
    sample.forEach((a,i)=>{
      const tr = document.createElement('tr');
      tr.innerHTML = `<td>${a.fullname||'—'}</td><td>${a.email||'—'}</td><td>${a.category||'—'}</td><td><button data-i="${i}" class="view">View</button></td>`;
      tbody.appendChild(tr);
    });
    document.querySelectorAll('.view').forEach(b=>b.addEventListener('click', e=>{
      const idx = e.target.dataset.i; alert(JSON.stringify(sample[idx], null, 2));
    }));
  }
  render();
})();
```

---

### Notes & Next steps
- This is a self-contained starter front-end. Replace the simulated `showRedirect` and localStorage use with real server endpoints and a payment provider (Stripe/PayPal) for production.
- For hosting: place all files in a single directory and upload to any static host (Netlify, Vercel, GitHub Pages) or a standard web server.

---

If you want, I can now:
- Convert this into a zip file for download,
- Add real Stripe checkout integration (requires keys),
- Create an admin HTML page that uses `dashboard.css` and `dashboard.js` (already prepared) — or
- Customize the look (colors, fonts, imagery).

Tell me which one and I’ll update the files.

