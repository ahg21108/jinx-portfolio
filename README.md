# jinx-portfolio
Art portfolio for my digital art work
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jinx — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600&family=Cormorant+Garamond:ital,wght@0,400;1,400&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{--bg:#0a0a0a;--surface:#111;--border:#1a1a1a;--text:#e8e8e8;--dim:#888;--accent:#c9a84c;--glow:rgba(201,168,76,.15);--body:'Space Grotesk',sans-serif;--display:'Cormorant Garamond',serif}
html{scroll-behavior:smooth}
body{font-family:var(--body);background:var(--bg);color:var(--text);line-height:1.6;overflow-x:hidden}
nav{position:fixed;top:0;width:100%;z-index:100;padding:1.5rem 3rem;display:flex;justify-content:space-between;align-items:center;background:rgba(10,10,10,.85);backdrop-filter:blur(20px);border-bottom:1px solid var(--border)}
nav .logo{font-family:var(--display);font-size:1.5rem;color:var(--accent);text-decoration:none;letter-spacing:.05em}
nav ul{display:flex;gap:2rem;list-style:none}
nav ul a{color:var(--dim);text-decoration:none;font-size:.85rem;letter-spacing:.1em;text-transform:uppercase;transition:color .3s}
nav ul a:hover{color:var(--accent)}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:5px}
.hamburger span{display:block;width:24px;height:2px;background:var(--text);transition:.3s}
.hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;padding:6rem 2rem 4rem;position:relative}
.hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 50% 30%,var(--glow) 0%,transparent 70%);pointer-events:none}
.hero h1{font-family:var(--display);font-size:clamp(3rem,8vw,7rem);font-weight:400;letter-spacing:.08em;margin-bottom:1rem}
.hero .tagline{font-size:1rem;color:var(--dim);letter-spacing:.2em;text-transform:uppercase;margin-bottom:2.5rem}
.hero .cta{padding:.8rem 2.5rem;border:1px solid var(--accent);color:var(--accent);text-decoration:none;font-size:.85rem;letter-spacing:.15em;text-transform:uppercase;transition:all .3s}
.hero .cta:hover{background:var(--accent);color:var(--bg)}
section{padding:6rem 3rem}
.section-title{font-family:var(--display);font-size:2.5rem;font-weight:400;margin-bottom:.5rem}
.section-line{width:60px;height:1px;background:var(--accent);margin-bottom:3rem}
.gallery-filters{display:flex;gap:1rem;margin-bottom:2rem;flex-wrap:wrap}
.filter-btn{background:none;border:1px solid var(--border);color:var(--dim);padding:.5rem 1.2rem;font-family:var(--body);font-size:.8rem;letter-spacing:.1em;text-transform:uppercase;cursor:pointer;transition:all .3s}
.filter-btn:hover,.filter-btn.active{border-color:var(--accent);color:var(--accent)}
.gallery-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:1.5rem}
.gallery-item{position:relative;aspect-ratio:1;overflow:hidden;background:var(--surface);border:1px solid var(--border);cursor:pointer;transition:transform .3s}
.gallery-item:hover{transform:scale(1.02)}
.gallery-item img{width:100%;height:100%;object-fit:cover}
.gallery-item .overlay{position:absolute;bottom:0;left:0;right:0;padding:1.5rem;background:linear-gradient(transparent,rgba(0,0,0,.85));transform:translateY(100%);transition:transform .3s}
.gallery-item:hover .overlay{transform:translateY(0)}
.overlay h3{font-size:1rem;margin-bottom:.25rem}
.overlay p{font-size:.8rem;color:var(--dim)}
.placeholder-img{width:100%;height:100%;display:flex;flex-direction:column;justify-content:center;align-items:center;color:var(--dim);font-size:.8rem;gap:.5rem}
.placeholder-img svg{width:32px;height:32px;stroke:var(--dim);fill:none}
.about-content{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center}
.about-photo{aspect-ratio:3/4;background:var(--surface);border:1px solid var(--border);display:flex;justify-content:center;align-items:center;color:var(--dim);font-size:.85rem}
.about-text p{color:var(--dim);margin-bottom:1.5rem;font-size:.95rem;line-height:1.8}
.about-text p:first-child{color:var(--text)}
.contact-wrapper{max-width:600px;margin:0 auto}
.contact-form{display:flex;flex-direction:column;gap:1.5rem}
.form-group{display:flex;flex-direction:column;gap:.5rem}
.form-group label{font-size:.8rem;letter-spacing:.1em;text-transform:uppercase;color:var(--dim)}
.form-group input,.form-group textarea{background:var(--surface);border:1px solid var(--border);color:var(--text);padding:.8rem 1rem;font-family:var(--body);font-size:.9rem;transition:border-color .3s;outline:none}
.form-group input:focus,.form-group textarea:focus{border-color:var(--accent)}
.form-group textarea{min-height:150px;resize:vertical}
.submit-btn{padding:.9rem 2rem;background:none;border:1px solid var(--accent);color:var(--accent);font-family:var(--body);font-size:.85rem;letter-spacing:.15em;text-transform:uppercase;cursor:pointer;transition:all .3s;align-self:flex-start}
.submit-btn:hover{background:var(--accent);color:var(--bg)}
footer{padding:3rem;border-top:1px solid var(--border);display:flex;justify-content:space-between;align-items:center}
.social-links{display:flex;gap:1.5rem}
.social-links a{color:var(--dim);text-decoration:none;font-size:.8rem;letter-spacing:.1em;text-transform:uppercase;transition:color .3s}
.social-links a:hover{color:var(--accent)}
.copyright{font-size:.75rem;color:var(--dim)}
.fade-in{opacity:0;transform:translateY(30px);transition:opacity .8s ease,transform .8s ease}
.fade-in.visible{opacity:1;transform:translateY(0)}
.lightbox{display:none;position:fixed;inset:0;background:rgba(0,0,0,.95);z-index:200;justify-content:center;align-items:center;cursor:pointer}
.lightbox.active{display:flex}
.lightbox img{max-width:90%;max-height:90%;object-fit:contain}
@media(max-width:768px){nav{padding:1rem 1.5rem}.hamburger{display:flex}nav ul{display:none;position:absolute;top:100%;left:0;right:0;flex-direction:column;background:rgba(10,10,10,.95);padding:2rem;border-bottom:1px solid var(--border)}nav ul.open{display:flex}section{padding:4rem 1.5rem}.about-content{grid-template-columns:1fr;gap:2rem}.gallery-grid{grid-template-columns:repeat(auto-fill,minmax(200px,1fr))}footer{flex-direction:column;gap:1rem;text-align:center}}
</style>
</head>
<body>

<nav>
  <a href="#" class="logo">JINX</a>
  <button class="hamburger" onclick="document.querySelector('nav ul').classList.toggle('open')">
    <span></span><span></span><span></span>
  </button>
  <ul>
    <li><a href="#gallery">Work</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<section class="hero">
  <h1>JINX</h1>
  <p class="tagline">Artist · Photographer · Creator</p>
  <a href="#gallery" class="cta">View Work</a>
</section>

<section id="gallery" class="fade-in">
  <h2 class="section-title">Selected Work</h2>
  <div class="section-line"></div>
  <div class="gallery-filters">
    <button class="filter-btn active" onclick="filterGallery('all')">All</button>
    <button class="filter-btn" onclick="filterGallery('photo')">Photography</button>
    <button class="filter-btn" onclick="filterGallery('digital')">Digital</button>
    <button class="filter-btn" onclick="filterGallery('mixed')">Mixed Media</button>
  </div>
  <div class="gallery-grid">
    <div class="gallery-item" data-category="photo" onclick="openLightbox(this)">
      <div class="placeholder-img"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg><span>Your image here</span></div>
      <div class="overlay"><h3>Project Title</h3><p>Photography</p></div>
    </div>
    <div class="gallery-item" data-category="digital" onclick="openLightbox(this)">
      <div class="placeholder-img"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg><span>Your image here</span></div>
      <div class="overlay"><h3>Project Title</h3><p>Digital Art</p></div>
    </div>
    <div class="gallery-item" data-category="mixed" onclick="openLightbox(this)">
      <div class="placeholder-img"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg><span>Your image here</span></div>
      <div class="overlay"><h3>Project Title</h3><p>Mixed Media</p></div>
    </div>
    <div class="gallery-item" data-category="photo" onclick="openLightbox(this)">
      <div class="placeholder-img"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg><span>Your image here</span></div>
      <div class="overlay"><h3>Project Title</h3><p>Photography</p></div>
    </div>
    <div class="gallery-item" data-category="digital" onclick="openLightbox(this)">
      <div class="placeholder-img"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg><span>Your image here</span></div>
      <div class="overlay"><h3>Project Title</h3><p>Digital Art</p></div>
    </div>
    <div class="gallery-item" data-category="photo" onclick="openLightbox(this)">
      <div class="placeholder-img"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg><span>Your image here</span></div>
      <div class="overlay"><h3>Project Title</h3><p>Photography</p></div>
    </div>
  </div>
</section>

<section id="about" class="fade-in">
  <h2 class="section-title">About</h2>
  <div class="section-line"></div>
  <div class="about-content">
    <div class="about-photo">Your photo here</div>
    <div class="about-text">
      <p>I create art. That's it. That's the job.</p>
      <p>Working across photography, digital media, and mixed media — each piece is built from whatever the vision demands. No rules, no single lane, just the work.</p>
      <p>Based in Georgia. Available for commissions, collaborations, and hired shoots.</p>
    </div>
  </div>
</section>

<section id="contact" class="fade-in">
  <h2 class="section-title">Get In Touch</h2>
  <div class="section-line"></div>
  <div class="contact-wrapper">
    <form class="contact-form" onsubmit="event.preventDefault();alert('Hook this up to Formspree or Netlify Forms to receive messages.')">
      <div class="form-group"><label for="name">Name</label><input type="text" id="name" required></div>
      <div class="form-group"><label for="email">Email</label><input type="email" id="email" required></div>
      <div class="form-group"><label for="message">Message</label><textarea id="message" required></textarea></div>
      <button type="submit" class="submit-btn">Send Message</button>
    </form>
  </div>
</section>

<footer>
  <div class="social-links">
    <a href="https://instagram.com/jinx.grim" target="_blank">Instagram</a>
    <a href="https://tiktok.com/@jinx.djinn" target="_blank">TikTok</a>
    <a href="#" target="_blank">LinkedIn</a>
  </div>
  <p class="copyright">© 2026 Jinx. All rights reserved.</p>
</footer>

<div class="lightbox" onclick="this.classList.remove('active')"><img src="" alt=""></div>

<script>
document.querySelectorAll('a[href^="#"]').forEach(a=>{
  a.addEventListener('click',function(e){
    e.preventDefault();
    document.querySelector(this.getAttribute('href')).scrollIntoView({behavior:'smooth'});
    document.querySelector('nav ul').classList.remove('open');
  });
});
const obs=new IntersectionObserver(e=>{
  e.forEach(x=>{if(x.isIntersecting)x.target.classList.add('visible')});
},{threshold:.1});
document.querySelectorAll('.fade-in').forEach(el=>obs.observe(el));
function filterGallery(cat){
  document.querySelectorAll('.filter-btn').forEach(b=>b.classList.remove('active'));
  event.target.classList.add('active');
  document.querySelectorAll('.gallery-item').forEach(i=>{
    i.style.display=(cat==='all'||i.dataset.category===cat)?'block':'none';
  });
}
function openLightbox(el){
  const img=el.querySelector('img');
  if(img){document.querySelector('.lightbox img').src=img.src;document.querySelector('.lightbox').classList.add('active');}
}
</script>
</body>
</html>
