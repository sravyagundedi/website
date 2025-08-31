<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>giftAboquet— Flower Shop</title>
  <meta name="description" content="Fresh bouquets, bespoke arrangements, and same‑day delivery. Shop roses, lilies, orchids, and seasonal blooms." />
  <meta name="theme-color" content="#ffeff6" />
  <style>
    :root{
      --bg:#fff;
      --muted:#6b7280; /* gray-500 */
      --text:#111827; /* gray-900 */
      --brand:#e11d48; /* rose-600 */
      --brand-2:#fda4af; /* rose-300 */
      --brand-3:#fff1f2; /* rose-50 */
      --card:#ffffff;
      --ring: rgba(225,29,72,.35);
      --shadow: 0 10px 25px rgba(0,0,0,.08);
      --radius: 18px;
      --radius-sm: 12px;
      --container: 1180px;
    }
    *{box-sizing:border-box}
    html,body{margin:0}
    body{
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji", "Segoe UI Emoji";
      color:var(--text); background:var(--bg); line-height:1.6;
    }
    .container{max-width:var(--container); margin-inline:auto; padding:0 20px}
    a{color:inherit; text-decoration:none}
    img{max-width:100%; display:block}
    button{font:inherit}

    /* Header */
    header{
      position:sticky; top:0; z-index:50; background:rgba(255,255,255,.8); backdrop-filter:saturate(180%) blur(10px);
      border-bottom:1px solid #f3f4f6;
    }
    .nav{display:flex; align-items:center; justify-content:space-between; padding:14px 0}
    .brand{display:flex; align-items:center; gap:10px; font-weight:800; letter-spacing:.2px}
    .brand .mark{width:36px; height:36px; border-radius:50%; background:radial-gradient(circle at 30% 30%, #fff, var(--brand-2)); display:grid; place-items:center; box-shadow:var(--shadow)}
    .brand .mark:after{content:"\1F337"; font-size:20px}
    .nav a{padding:8px 12px; border-radius:10px}
    .nav a:hover{background:#f9fafb}
    .actions{display:flex; align-items:center; gap:8px}
    .btn{padding:10px 14px; border-radius:12px; border:1px solid #e5e7eb; background:#fff; cursor:pointer}
    .btn.primary{background:var(--brand); color:#fff; border-color:transparent}
    .btn.icon{display:inline-grid; place-items:center; width:40px; height:40px}
    .badge{min-width:18px; height:18px; border-radius:999px; background:var(--brand); color:#fff; display:inline-grid; place-items:center; font-size:11px; padding:0 4px; transform:translate(-8px, -10px)
    
    }

    /* Hero */
    .hero{position:relative; padding:72px 0 48px; background:linear-gradient(180deg,var(--brand-3),#fff)}
    .hero-grid{display:grid; grid-template-columns:1.1fr .9fr; gap:40px; align-items:center}
    .eyebrow{font-weight:700; color:var(--brand); text-transform:uppercase; letter-spacing:.12em; font-size:12px}
    .h1{font-size:48px; line-height:1.1; margin:8px 0 12px}
    .lead{color:var(--muted); font-size:18px}
    .hero-card{background:var(--card); border:1px solid #ffe4e6; border-radius:var(--radius); padding:16px; box-shadow:var(--shadow)}
    .hero-img{border-radius:var(--radius); overflow:hidden}
    .hero-bullets{display:grid; grid-template-columns:repeat(3,1fr); gap:12px; margin-top:16px}
    .pill{background:#fff; border:1px dashed #fecdd3; color:#9f1239; border-radius:999px; padding:10px 12px; text-align:center; font-weight:600}

    /* Controls */
    .controls{display:flex; gap:12px; align-items:center; margin:26px 0 10px}
    .input{flex:1; display:flex; align-items:center; gap:8px; border:1px solid #e5e7eb; border-radius:12px; padding:10px 12px}
    .input input{border:0; outline:0; width:100%; background:transparent}
    .select{border:1px solid #e5e7eb; border-radius:12px; padding:10px 12px; background:#fff}

    /* Grid */
    .grid{display:grid; grid-template-columns:repeat(4,1fr); gap:18px}
    .card{background:#fff; border:1px solid #f3f4f6; border-radius:var(--radius-sm); overflow:hidden; box-shadow:var(--shadow); display:flex; flex-direction:column}
    .card .media{aspect-ratio:4/3; background:#fff1f2; display:grid; place-items:center}
    .card .body{padding:14px}
    .price{font-weight:800}
    .chip{font-size:12px; color:#9ca3af}
    .add{margin-top:10px}

    /* Sections */
    section{padding:54px 0}
    .section-title{font-size:28px; margin:0 0 12px}
    .muted{color:var(--muted)}

    /* Feature banner */
    .banner{background:linear-gradient(90deg,#fff1f2,#fee2e2); border:1px solid #fee2e2; border-radius:var(--radius); padding:22px; display:flex; align-items:center; justify-content:space-between; gap:12px}

    /* Cart */
    dialog{border:0; border-radius:18px; padding:0; box-shadow:var(--shadow); width:min(680px, 92vw)}
    .cart{padding:18px}
    .cart h3{margin:0 0 8px}
    .cart .line{display:flex; align-items:center; justify-content:space-between; gap:12px; padding:10px 0; border-bottom:1px dashed #f3f4f6}
    .cart .qty{display:inline-flex; border:1px solid #e5e7eb; border-radius:10px; overflow:hidden}
    .cart .qty button{width:32px; height:32px; border:0; background:#fff; cursor:pointer}
    .cart .summary{display:flex; justify-content:space-between; font-weight:700; padding-top:12px}
    .close{position:absolute; top:10px; right:10px}

    /* Footer */
    footer{border-top:1px solid #f3f4f6; padding:28px 0; color:#6b7280}

    /* Responsive */
    @media (max-width: 980px){
      .hero-grid{grid-template-columns:1fr}
      .grid{grid-template-columns:repeat(2,1fr)}
    }
    @media (max-width: 560px){
      .h1{font-size:36px}
      .grid{grid-template-columns:1fr}
      .actions .btn{padding:8px 10px}
    }
    /* Focus */
    :focus-visible{outline:2px solid var(--ring); outline-offset:2px}
  </style>
</head>
<body>
  <header>
    <div class="container nav" role="navigation" aria-label="Primary">
      <a class="brand" href="#home" aria-label="giftAboque">
        <span class="mark" aria-hidden="true"></span>
        <span>giftAboquet</span>
      </a>
      <nav class="links" aria-label="Site">
        <a href="#shop">Shop</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>
      <div class="actions">
  <button class="btn" id="btn-track" aria-label="Track your order">Track</button>
  <button class="btn icon" id="btn-wishlist" aria-label="Open wishlist">
    ❤️<span class="badge" id="wishlist-count" aria-live="polite">0</span>
  </button>
  <button class="btn icon" id="btn-cart" aria-label="Open cart">
    🛒<span class="badge" id="cart-count" aria-live="polite">0</span>
  </button>
</div>
    </div>

  </header>

  <main id="home" class="hero">
    <div class="container hero-grid">
      <div>
        <div class="eyebrow">Hand-tied with love</div>
        <h1 class="h1">Fresh flowers delivered in under 3 hours</h1>
        <pre class="lead">Choose from best-selling bouquets or build your own arrangement.
->Free gift note. Eco-friendly packaging.</pre>
        <div class="controls" role="search">
          <label class="input" aria-label="Search bouquets">
            🔎<input id="search" type="search" placeholder="Search roses, lilies, orchids..." />
          </label>
          <label>
            <select id="sort" class="select" aria-label="Sort products">
              <option value="featured">Featured</option>
              <option value="price-asc">Price: Low to High</option>
              <option value="price-desc">Price: High to Low</option>
            </select>
          </label>
          <button class="btn primary" id="btn-explore">Explore bouquets</button>
        </div>
        <div class="hero-bullets" aria-hidden="true">
          <div class="pill">Same-day delivery</div>
          <div class="pill">Locally sourced</div>
          <div class="pill">7-day freshness</div>
        </div>
      </div>
      <div class="hero-card">
        <div class="hero-img">
          <!-- Replace src with your own: C:\Users\...\website\assets\hero.jpg -->
          <img src="https://static.vecteezy.com/system/resources/thumbnails/061/057/113/small/bright-pink-flowers-peonies-and-roses-paired-with-lush-green-ferns-against-a-soft-pastel-pink-background-photo.jpg" alt="Lush pink bouquet on a pastel background" onerror="this.src='data:image/svg+xml;utf8,<?xml version=\'1.0\'?><svg xmlns=\'http : //www.w3.org/2000/svg\' width=\'800\' height=\'600\'><rect width=\'100%\' height=\'100%\' fill=\'%23fff1f2'/><text x=\'50%\' y=\'50%\' dominant-baseline=\'middle\' text-anchor=\'middle\' fill=\'%239f1239\' font-size=\'24\'>Add assets/hero.jpg</text></svg>'">
        </div>
      </div>
    </div>
  </main>

  <section id="shop">
    <div class="container">
      <h2 class="section-title">Best Sellers</h2>
      <p class="muted">Classic bouquets and seasonal arrangements our customers adore.</p>

      <div id="product-grid" class="grid" aria-live="polite">
        <!-- Cards rendered by JS using the products[] list below -->
      </div>

      <div class="banner" style="margin-top:22px">
        <div>
          <strong>Custom arrangements</strong><br>
          Prefer a unique mix? Tell us your palette and budget — our florists will craft it.
        </div>
        <button class="btn" id="btn-custom">Build my bouquet</button>
      </div>
    </div>
  </section>

  <section id="about">
    <div class="container">
      <h2 class="section-title">About giftAboquet
      </h2>
      <pre class="muted">  We partner with local growers and practice foam-free, sustainable floristry.
  Every stem is conditioned same‑day for lasting freshness.
  Find the perfect bouquet for every moment.
  Our curated collections help you express exactly what's in your heart.</pre>
    </div>
  </section>

  <section id="contact">
    <div class="container">
      <h2 class="section-title">Get in touch</h2>
      <form id="contact-form" class="grid" style="grid-template-columns:1fr 1fr; gap:14px; max-width:760px">
        <label> Name
          <input required class="input" style="display:block" name="name" placeholder="Your name" />
        </label>
        <label> Email
          <input required type="email" class="input" style="display:block" name="email" placeholder="you@example.com" />
        </label>
        <label> Mobile Number
        <input required type="tel" class="input" style="display:block" name="mobile" placeholder="e.g. +91 9876543210" pattern="[0-9]{10}" />
        </label>
        <label style="grid-column:1/-1"> Message
          <textarea required class="input" style="display:block; min-height:120px" name="message" placeholder="How can we help?"></textarea>
        </label>
        <div style="grid-column:1/-1; display:flex; gap:8px; align-items:center">
          <button class="btn primary" type="submit">Send message</button>
          <span id="contact-status" class="muted" role="status" aria-live="polite"></span>
        </div>
      </form>
    </div>
  </section>

  <footer>
    <div class="container" style="display:flex; justify-content:space-between; align-items:center; gap:12px; flex-wrap:wrap">
      <small>© <span id="year"></span> giftAboquet. All rights reserved.</small>
      <div>
        <a href="#" aria-label="Instagram">📸</a>
        <a href="#" aria-label="WhatsApp" style="margin-left:8px">💬</a>
        <a href="#" aria-label="Email" style="margin-left:8px">✉️</a>
      </div>
    </div>
  </footer>

  <!-- Cart Modal -->
  <dialog id="cart-modal" aria-label="Shopping cart">
    <div class="cart">
      <button class="btn icon close" id="cart-close" aria-label="Close cart">✖</button>
      <h3>Your cart</h3>
      <div id="cart-lines"></div>
      <div class="summary"><span>Subtotal</span><span id="cart-subtotal">₹0</span></div>
      <div style="display:flex; gap:8px; margin-top:12px">
        <button class="btn" id="cart-clear">Clear</button>
        <button class="btn primary" id="cart-checkout">Checkout</button>
      </div>
    </div>
  </dialog>
  <!-- Wishlist Modal -->
<dialog id="wishlist-modal" aria-label="Wishlist">
  <div class="cart">
    <button class="btn icon close" id="wishlist-close" aria-label="Close wishlist">✖</button>
    <h3>Your Wishlist</h3>
    <div id="wishlist-lines"></div>
    <div style="display:flex; gap:8px; margin-top:12px">
      <button class="btn" id="wishlist-clear">Clear Wishlist</button>
    </div>
  </div>
</dialog>


  <script>
    // --- Product Data ---
    const products = [
      {id:'rose-delight', name:'Rose Delight', price:999, tag:'Roses', img:'https://imgcdn.floweraura.com/DSC_1243_0.jpg'},
      {id:'sunny-mix', name:'Sunny Mix', price:1099, tag:'Seasonal', img:'https://blacktulipflowers.in/wp-content/uploads/2023/11/15-1-1.png'},
      {id:'orchid-elegance', name:'Orchid Elegance', price:1009, tag:'Orchids', img:'https://media-api.xogrp.com/images/e2bf0ea4-0c9d-4c86-905b-d2443f0a1d03?auto=format&fit=max&w=1200&q=70'},
      {id:'lilies-love', name:'Lilies Love', price:1209, tag:'Lilies', img:'https://www.plantshed.com/media/catalog/product/cache/1bc1660c0d72b88d548f5f9299e45a83/p/s/ps10802-white-lilies-bouquet-5_3.jpg'},
      {id:'mixedflowers', name:'mixedflowers', price:999, tag:'mixedflowers', img:'https://bouqs.com/media/W1siZiIsIjIwMjUvMDUvMDIvMTgvNDQvMzIvZWJhNTIyNTQtNmVmZS00NmYyLWFlOTMtNDBkM2JmNmIyM2IwL1NVTTI1X1dpbGRBYm91dFlvdV9PSF82NjdfV2ViICgxKS5qcGciXV0/SUM25_WildAboutYou_OH_667_Web%20%281%29.jpg?sha=2bd2854a85c02923'},
      {id:'blushing-bride', name:'Blushing Bride', price:2009, tag:'Premium', img:'https://i.etsystatic.com/13921532/r/il/292874/3661245857/il_fullxfull.3661245857_jbup.jpg'},
      {id:'tulip-stem', name:'tulip-stem', price:1599, tag:'tulip-stem', img:'https://vijayflorist.com/wp-content/uploads/2024/08/Group-113-2024-08-01T142740.216.png'},
      {id:'scarlet-soiree', name:'Scarlet Soiree', price:1599, tag:'Roses', img:'https://fiftyflowers.com/cdn/shop/files/scarlett-red-flower-bouquet-centerpieces-online-hand_49dd2_nc020.webp?v=1754517804&width=800'},
    ];

    // --- Utilities ---
    const fmt = n => new Intl.NumberFormat('en-IN', { style:'currency', currency:'INR', maximumFractionDigits:0 }).format(n);
    const $ = sel => document.querySelector(sel);

    // --- Render Products ---
    const grid = $('#product-grid');
    function placeholder(name){
      const encoded = encodeURIComponent(`<?xml version='1.0'?><svg xmlns='http://www.w3.org/2000/svg' width='800' height='600'><rect width='100%' height='100%' fill='%23fff1f2'/><text x='50%' y='50%' dominant-baseline='middle' text-anchor='middle' fill='%239f1239' font-size='20'>Add assets/${name}.jpg</text></svg>`);
      return `data:image/svg+xml;utf8,${encoded}`;
    }
    function renderCards(list){
      grid.innerHTML = '';
      list.forEach(p => {
        const card = document.createElement('article');
        card.className = 'card';
        card.setAttribute('data-name', p.name.toLowerCase());
        card.setAttribute('data-price', p.price);
        card.innerHTML = `
          <div class="media"><img alt="${p.name} bouquet" src="${p.img}" onerror="this.src='${placeholder(p.id)}'" /></div>
          <div class="body">
            <div style="display:flex; justify-content:space-between; gap:8px; align-items:start">
              <div>
                <strong>${p.name}</strong>
                <div class="chip">${p.tag}</div>
              </div>
              <div class="price">${fmt(p.price)}</div>
            </div>
            <button class="btn add" data-add="${p.id}">Add to cart</button>
          </div>`;
        grid.appendChild(card);
      });
    }

    // --- Search + Sort ---
    const search = $('#search');
    const sort = $('#sort');
    function applyFilters(){
      let list = [...products];
      const q = (search.value || '').toLowerCase();
      if(q) list = list.filter(p => p.name.toLowerCase().includes(q) || p.tag.toLowerCase().includes(q));
      switch(sort.value){
        case 'price-asc': list.sort((a,b)=>a.price-b.price); break;
        case 'price-desc': list.sort((a,b)=>b.price-a.price); break;
        default: /* featured */ break;
      }
      renderCards(list);
    }

    search.addEventListener('input', applyFilters);
    sort.addEventListener('change', applyFilters);
    $('#btn-explore').addEventListener('click', ()=> document.getElementById('shop').scrollIntoView({behavior:'smooth'}));

    // --- Cart State ---
    const CART_KEY = 'bloom_cart_v1';
    const cart = JSON.parse(localStorage.getItem(CART_KEY) || '{}'); // {id: qty}
    function saveCart(){ localStorage.setItem(CART_KEY, JSON.stringify(cart)); updateBadge(); }
    function updateBadge(){
      const count = Object.values(cart).reduce((a,b)=>a+b,0);
      document.getElementById('cart-count').textContent = count;
    }

    // Add handlers (event delegation)
    grid.addEventListener('click', (e)=>{
      const btn = e.target.closest('[data-add]');
      if(!btn) return;
      const id = btn.getAttribute('data-add');
      cart[id] = (cart[id]||0) + 1; saveCart();
      openCart();
    });

    // --- Cart Modal Render ---
    const dlg = document.getElementById('cart-modal');
    const lines = document.getElementById('cart-lines');
    const subtotalEl = document.getElementById('cart-subtotal');

    function openCart(){ renderCart(); if(!dlg.open) dlg.showModal(); }
    function closeCart(){ if(dlg.open) dlg.close(); }

    function renderCart(){
      lines.innerHTML = '';
      let subtotal = 0;
      for(const [id, qty] of Object.entries(cart)){
        const p = products.find(x=>x.id===id);
        if(!p) continue;
        subtotal += p.price * qty;
        const row = document.createElement('div');
        row.className = 'line';
        row.innerHTML = `
          <div style="display:flex; align-items:center; gap:10px">
            <img alt="${p.name}" src="${p.img}" width="64" height="48" onerror="this.src='${placeholder(p.id)}'" style="border-radius:8px; border:1px solid #f3f4f6"/>
            <div>
              <div><strong>${p.name}</strong></div>
              <small class="muted">${fmt(p.price)}</small>
            </div>
          </div>
          <div style="display:flex; align-items:center; gap:10px">
            <div class="qty" role="group" aria-label="Change quantity">
              <button data-dec="${id}" aria-label="Decrease">−</button>
              <div style="width:36px; text-align:center">${qty}</div>
              <button data-inc="${id}" aria-label="Increase">+</button>
            </div>
            <strong>${fmt(p.price * qty)}</strong>
            <button class="btn" data-remove="${id}" aria-label="Remove">Remove</button>
          </div>`;
        lines.appendChild(row);
      }
      subtotalEl.textContent = fmt(subtotal);
    }

    lines.addEventListener('click', (e)=>{
      const inc = e.target.closest('[data-inc]');
      const dec = e.target.closest('[data-dec]');
      const rem = e.target.closest('[data-remove]');
      if(inc){ const id = inc.getAttribute('data-inc'); cart[id] = (cart[id]||1)+1; saveCart(); renderCart(); }
      if(dec){ const id = dec.getAttribute('data-dec'); cart[id] = Math.max(0,(cart[id]||1)-1); if(cart[id]===0) delete cart[id]; saveCart(); renderCart(); }
      if(rem){ const id = rem.getAttribute('data-remove'); delete cart[id]; saveCart(); renderCart(); }
    });

    document.getElementById('btn-cart').addEventListener('click', openCart);
    document.getElementById('cart-close').addEventListener('click', closeCart);
    document.getElementById('cart-clear').addEventListener('click', ()=>{ for(const k of Object.keys(cart)) delete cart[k]; saveCart(); renderCart(); });
    document.getElementById('cart-checkout').addEventListener('click', ()=>{
      alert('Demo checkout — replace with your payment flow (Razorpay/Stripe/COD).');
    });
    // --- Wishlist State ---
const WISHLIST_KEY = 'giftabouquet_wishlist_v1';
const wishlist = JSON.parse(localStorage.getItem(WISHLIST_KEY) || '[]'); // [id]

function saveWishlist() {
  localStorage.setItem(WISHLIST_KEY, JSON.stringify(wishlist));
  updateWishlistBadge();
}

function updateWishlistBadge() {
  document.getElementById('wishlist-count').textContent = wishlist.length;
}

// Add wishlist button to each product card
function renderCards(list) {
  grid.innerHTML = '';
  list.forEach(p => {
    const card = document.createElement('article');
    card.className = 'card';
    card.setAttribute('data-name', p.name.toLowerCase());
    card.setAttribute('data-price', p.price);
    card.innerHTML = `
      <div class="media"><img alt="${p.name} bouquet" src="${p.img}" /></div>
      <div class="body">
        <div style="display:flex; justify-content:space-between; gap:8px; align-items:start">
          <div>
            <strong>${p.name}</strong>
            <div class="chip">${p.tag}</div>
          </div>
          <div class="price">${fmt(p.price)}</div>
        </div>
        <div style="display:flex; gap:8px; margin-top:10px">
          <button class="btn add" data-add="${p.id}">Add to cart</button>
          <button class="btn" data-wish="${p.id}">♡ Wishlist</button>
        </div>
      </div>`;
    grid.appendChild(card);
  });
}

// --- Wishlist Modal ---
const wishDlg = document.getElementById('wishlist-modal');
const wishLines = document.getElementById('wishlist-lines');

function openWishlist() { renderWishlist(); if(!wishDlg.open) wishDlg.showModal(); }
function closeWishlist() { if(wishDlg.open) wishDlg.close(); }

function renderWishlist() {
  wishLines.innerHTML = '';
  if(wishlist.length === 0) {
    wishLines.innerHTML = '<p class="muted">No items in wishlist.</p>';
    return;
  }
  wishlist.forEach(id => {
    const p = products.find(x => x.id===id);
    if(!p) return;
    const row = document.createElement('div');
    row.className = 'line';
    row.innerHTML = `
      <div style="display:flex; align-items:center; gap:10px">
        <img alt="${p.name}" src="${p.img}" width="64" height="48" style="border-radius:8px; border:1px solid #f3f4f6"/>
        <div><strong>${p.name}</strong><br><small class="muted">${fmt(p.price)}</small></div>
      </div>
      <div>
        <button class="btn" data-remove-wish="${id}">Remove</button>
      </div>`;
    wishLines.appendChild(row);
  });
}

grid.addEventListener('click', (e) => {
  const btn = e.target.closest('[data-wish]');
  if(!btn) return;
  const id = btn.getAttribute('data-wish');
  if(!wishlist.includes(id)) wishlist.push(id);
  saveWishlist();
  openWishlist();
});

wishLines.addEventListener('click', (e)=>{
  const rem = e.target.closest('[data-remove-wish]');
  if(rem){ 
    const id = rem.getAttribute('data-remove-wish');
    const idx = wishlist.indexOf(id);
    if(idx>-1) wishlist.splice(idx,1);
    saveWishlist(); renderWishlist();
  }
});

document.getElementById('btn-wishlist').addEventListener('click', openWishlist);
document.getElementById('wishlist-close').addEventListener('click', closeWishlist);
document.getElementById('wishlist-clear').addEventListener('click', ()=>{ wishlist.length=0; saveWishlist(); renderWishlist(); });

// Init
updateWishlistBadge();


    // --- Contact Form (demo) ---
    document.getElementById('contact-form').addEventListener('submit', (e)=>{
      e.preventDefault();
      const data = Object.fromEntries(new FormData(e.target).entries());
      document.getElementById('contact-status').textContent = 'Thanks, '+ (data.name||'friend') + '! We\'ll reply shortly.';
      e.target.reset();
    });

    // --- Misc ---
    document.getElementById('btn-track').addEventListener('click', ()=>{
      prompt('Enter your order ID to track:');
    });
    document.getElementById('btn-custom').addEventListener('click', ()=>{
      alert('Tell us your palette and budget in the contact form — we\'ll tailor a bouquet for you.');
    });
    document.getElementById('year').textContent = new Date().getFullYear();

    // Init
    renderCards(products);
    updateBadge();
    applyFilters();
  </script>
</body>
</html>
