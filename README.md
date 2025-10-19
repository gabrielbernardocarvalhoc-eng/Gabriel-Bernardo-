<!doctype html>

<html lang="pt-BR">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Loja Exemplo — Seu Produto Aqui</title>
  <meta name="description" content="Loja online simples em HTML, CSS e JavaScript — pronta para personalizar.">
  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --accent:#ff6b6b; --muted:#94a3b8; --glass: rgba(255,255,255,0.04);
      --maxw:1200px; --radius:14px; --shadow: 0 6px 18px rgba(2,6,23,0.6);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{margin:0;background:linear-gradient(180deg,#071025 0%, #0b1220 100%);color:#e6eef8;min-height:100vh;display:flex;flex-direction:column}
    .container{width:calc(100% - 32px);max-width:var(--maxw);margin:28px auto}header{display:flex;align-items:center;justify-content:space-between;gap:16px}
.brand{display:flex;align-items:center;gap:12px}
.logo{width:44px;height:44px;background:var(--glass);border-radius:10px;display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--accent)}
nav a{color:var(--muted);text-decoration:none;margin-left:18px}
nav a:hover{color:#fff}

.hero{margin-top:28px;background:linear-gradient(90deg, rgba(255,255,255,0.03), transparent);padding:28px;border-radius:var(--radius);box-shadow:var(--shadow);display:flex;gap:20px;align-items:center}
.hero-left{flex:1}
.hero h1{margin:0;font-size:28px}
.hero p{color:var(--muted);margin-top:8px}
.cta{display:inline-block;margin-top:12px;padding:10px 16px;background:var(--accent);color:#081020;border-radius:10px;font-weight:600;text-decoration:none}

.products{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:18px;margin-top:22px}
.card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:14px;border-radius:12px;box-shadow:0 8px 20px rgba(2,6,23,0.6);display:flex;flex-direction:column}
.card img{width:100%;height:160px;object-fit:cover;border-radius:8px}
.card h3{margin:10px 0 6px;font-size:16px}
.price{font-weight:700}
.muted{color:var(--muted);font-size:14px}
.actions{margin-top:auto;display:flex;gap:8px;align-items:center}
.btn{padding:8px 10px;border-radius:10px;border:0;cursor:pointer}
.btn.secondary{background:transparent;color:var(--muted);border:1px solid rgba(255,255,255,0.04)}

/* Cart panel */
.cart-btn{position:relative}
.cart-count{position:absolute;top:-6px;right:-6px;background:var(--accent);color:#071022;border-radius:999px;padding:4px 7px;font-weight:700;font-size:12px}
.cart-panel{position:fixed;right:18px;top:80px;width:360px;max-width:calc(100% - 32px);background:linear-gradient(180deg,#061225 0%, #07182a 100%);border-radius:12px;padding:12px;box-shadow:var(--shadow);display:flex;flex-direction:column;gap:12px;z-index:60}
.cart-item{display:flex;gap:12px;align-items:center}
.cart-item img{width:56px;height:56px;object-fit:cover;border-radius:8px}
.qty{display:flex;gap:6px;align-items:center}
.total{font-weight:800;font-size:18px}
.empty{color:var(--muted);padding:18px;text-align:center}

/* Footer */
footer{margin-top:30px;padding:18px 0;color:var(--muted);text-align:center}

/* Responsive */
@media (max-width:600px){
  .hero{flex-direction:column;align-items:flex-start}
  .hero img{width:120px}
}

/* Simple inputs */
input,select,textarea{background:#081522;border:1px solid rgba(255,255,255,0.03);color:#e6eef8;padding:8px;border-radius:8px}
.checkout-form{display:flex;flex-direction:column;gap:8px}

  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">SV</div>
        <div>
          <div style="font-weight:700">Loja Exemplo</div>
          <div class="muted" style="font-size:12px">Produtos selecionados com carinho</div>
        </div>
      </div>
      <nav>
        <a href="#produtos">Produtos</a>
        <a href="#sobre">Sobre</a>
        <button id="open-cart" class="btn cart-btn" aria-label="Abrir carrinho">Carrinho <span id="cart-count" class="cart-count" style="display:none">0</span></button>
      </nav>
    </header><section class="hero" aria-labelledby="hero-title">
  <div class="hero-left">
    <h1 id="hero-title">A sua próxima compra começa aqui</h1>
    <p class="muted">Design limpo, checkout rápido e exemplo pronto para personalizar. Veja os produtos abaixo e experimente o carrinho.</p>
    <a class="cta" href="#produtos">Ver Produtos</a>
  </div>
  <div class="hero-right">
    <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=800&q=60&auto=format&fit=crop" alt="Produtos" style="width:220px;border-radius:12px;box-shadow:var(--shadow)">
  </div>
</section>

<main>
  <section id="produtos" class="products" aria-label="lista de produtos">
    <!-- cards gerados por JS -->
  </section>

  <section id="sobre" style="margin-top:26px;padding:18px;background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent);border-radius:12px">
    <h2>Sobre a loja</h2>
    <p class="muted">Este é um template em HTML, CSS e JavaScript (vanilla). Está pronto para você conectar a um back-end, gateway de pagamento ou converter em React/Next.js.</p>
  </section>
</main>

<footer>
  © <span id="ano"></span> Loja Exemplo — Desenvolvido por você
</footer>

  </div>  <!-- Cart panel (invisível até necessário) -->  <div id="cart-panel" class="cart-panel" style="display:none" role="dialog" aria-label="Carrinho de compras">
    <div style="display:flex;justify-content:space-between;align-items:center">
      <strong>Carrinho</strong>
      <button id="close-cart" class="btn secondary">Fechar</button>
    </div>
    <div id="cart-items"></div>
    <div id="cart-empty" class="empty">Seu carrinho está vazio</div>
    <div style="display:flex;justify-content:space-between;align-items:center;margin-top:6px">
      <div class="muted">Total</div>
      <div class="total">R$ <span id="cart-total">0.00</span></div>
    </div>
    <div style="display:flex;gap:8px;margin-top:8px">
      <button id="checkout-btn" class="btn">Finalizar compra</button>
      <button id="clear-cart" class="btn secondary">Limpar</button>
    </div><form id="checkout-form" class="checkout-form" style="display:none;margin-top:8px">
  <label>Nome completo<input id="name" required placeholder="João Silva"></label>
  <label>E-mail<input id="email" type="email" required placeholder="email@exemplo.com"></label>
  <label>Endereço<textarea id="address" rows="2" placeholder="Rua, número, cidade"></textarea></label>
  <div style="display:flex;gap:8px">
    <button type="submit" class="btn">Confirmar pedido</button>
    <button type="button" id="cancel-checkout" class="btn secondary">Cancelar</button>
  </div>
</form>

<div id="order-success" style="display:none;padding:12px;border-radius:10px;background:linear-gradient(180deg, rgba(20,120,70,0.08), transparent);">
  <strong>Pedido realizado!</strong>
  <div class="muted" id="order-summary"></div>
</div>

  </div>  <script>
    // Dados de exemplo — troque pelos seus produtos reais
    const products = [
      {id:1,name:'Tênis Minimal',price:239.90,desc:'Conforto para o dia a dia',img:'https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=800&q=60&auto=format&fit=crop'},
      {id:2,name:'Camiseta Básica',price:59.90,desc:'Algodão premium',img:'https://images.unsplash.com/photo-1602810315486-7e2f6d5be6a1?w=800&q=60&auto=format&fit=crop'},
      {id:3,name:'Mochila Urbana',price:179.90,desc:'Espaçosa e resistente',img:'https://images.unsplash.com/photo-1524758631624-e2822e304c36?w=800&q=60&auto=format&fit=crop'},
      {id:4,name:'Relógio Clássico',price:499.00,desc:'Mostrador elegante',img:'https://images.unsplash.com/photo-1519741491596-5f7b6a3f6c4f?w=800&q=60&auto=format&fit=crop'},
      {id:5,name:'Fone Bluetooth',price:299.00,desc:'Áudio cristalino',img:'https://images.unsplash.com/photo-1585386959984-a415522c3d3b?w=800&q=60&auto=format&fit=crop'},
      {id:6,name:'Caneca Ceramic',price:39.90,desc:'Perfeita para café',img:'https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=800&q=60&auto=format&fit=crop'}
    ];

    const productsEl = document.querySelector('.products');
    const cartPanel = document.getElementById('cart-panel');
    const cartItemsEl = document.getElementById('cart-items');
    const cartCount = document.getElementById('cart-count');
    const cartTotalEl = document.getElementById('cart-total');
    const cartEmpty = document.getElementById('cart-empty');
    const checkoutBtn = document.getElementById('checkout-btn');
    const checkoutForm = document.getElementById('checkout-form');
    const orderSuccess = document.getElementById('order-success');
    const orderSummary = document.getElementById('order-summary');

    let cart = JSON.parse(localStorage.getItem('cart_v1')) || {};

    document.getElementById('ano').textContent = new Date().getFullYear();

    function formatBRL(v){return v.toFixed(2).replace('.',',');}

    function renderProducts(){
      productsEl.innerHTML = '';
      products.forEach(p=>{
        const card = document.createElement('article');card.className='card';
        card.innerHTML = `
          <img src="${p.img}" alt="${p.name}">
          <h3>${p.name}</h3>
          <div class="muted">${p.desc}</div>
          <div style="display:flex;justify-content:space-between;align-items:center;margin-top:8px">
            <div><div class="price">R$ ${formatBRL(p.price)}</div></div>
            <div class="actions">
              <button class="btn secondary" data-id="${p.id}">Detalhes</button>
              <button class="btn" data-add="${p.id}">Adicionar</button>
            </div>
          </div>
        `;
        productsEl.appendChild(card);
      });
    }

    function saveCart(){localStorage.setItem('cart_v1', JSON.stringify(cart));}

    function updateCartUI(){
      const keys = Object.keys(cart);
      const count = keys.reduce((s,k)=>s+cart[k].qty,0);
      if(count>0){cartCount.style.display='inline-block';cartCount.textContent=count}else{cartCount.style.display='none'}

      // render list
      cartItemsEl.innerHTML='';
      if(keys.length===0){cartEmpty.style.display='block'} else {cartEmpty.style.display='none'}
      let total = 0;
      keys.forEach(k=>{
        const it = cart[k]; total += it.qty*it.price;
        const div = document.createElement('div');div.className='cart-item';
        div.innerHTML = `
          <img src="${it.img}" alt="${it.name}">
          <div style="flex:1">
            <div style="font-weight:700">${it.name}</div>
            <div class="muted">R$ ${formatBRL(it.price)} × ${it.qty}</div>
          </div>
          <div style="display:flex;flex-direction:column;gap:6px;align-items:flex-end">
            <div class="qty">
              <button class="btn secondary" data-dec="${k}">-</button>
              <div style="min-width:22px;text-align:center">${it.qty}</div>
              <button class="btn" data-inc="${k}">+</button>
            </div>
            <button class="btn secondary" data-rm="${k}">Remover</button>
          </div>
        `;
        cartItemsEl.appendChild(div);
      });
      cartTotalEl.textContent = formatBRL(total);
    }

    function addToCart(id){
      const p = products.find(x=>x.id==id); if(!p) return;
      if(cart[id]) cart[id].qty +=1; else cart[id] = {id:p.id,name:p.name,price:p.price,img:p.img,qty:1};
      saveCart(); updateCartUI();
    }

    function changeQty(id,delta){
      if(!cart[id]) return; cart[id].qty += delta; if(cart[id].qty<=0) delete cart[id]; saveCart(); updateCartUI();
    }

    function removeItem(id){ if(cart[id]){ delete cart[id]; saveCart(); updateCartUI(); } }

    // Eventos
    document.addEventListener('click',e=>{
      const add = e.target.closest('[data-add]'); if(add){ addToCart(add.getAttribute('data-add')); return }
      const dec = e.target.closest('[data-dec]'); if(dec){ changeQty(dec.getAttribute('data-dec'), -1); return }
      const inc = e.target.closest('[data-inc]'); if(inc){ changeQty(inc.getAttribute('data-inc'), 1); return }
      const rm = e.target.closest('[data-rm]'); if(rm){ removeItem(rm.getAttribute('data-rm')); return }
    });

    document.getElementById('open-cart').addEventListener('click',()=>{ cartPanel.style.display='flex'; updateCartUI(); });
    document.getElementById('close-cart').addEventListener('click',()=>{ cartPanel.style.display='none'; });
    document.getElementById('clear-cart').addEventListener('click',()=>{ cart={}; saveCart(); updateCartUI(); });

    checkoutBtn.addEventListener('click',()=>{
      checkoutForm.style.display='flex'; checkoutBtn.style.display='none';
    });
    document.getElementById('cancel-checkout').addEventListener('click',()=>{ checkoutForm.style.display='none'; checkoutBtn.style.display='inline-block'; });

    document.getElementById('checkout-form').addEventListener('submit',e=>{
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const address = document.getElementById('address').value.trim();
      if(!name||!email){ alert('Preencha nome e e-mail.'); return }
      // Simulação de pedido
      const items = Object.values(cart).map(i=>`${i.qty}x ${i.name}`).join(', ')||'(nenhum)';
      orderSummary.textContent = `Obrigado ${name}! Pedido: ${items}. Enviaremos confirmação para ${email}. Endereço: ${address}`;
      orderSuccess.style.display='block'; checkoutForm.style.display='none'; cart={}; saveCart(); updateCartUI();
    });

    // Inicialização
    renderProducts(); updateCartUI();

    // Melhorias possíveis (comentadas):
    // - Substituir imagens por imagens do seu catálogo
    // - Conectar à API de pagamento (Stripe, MercadoPago)
    // - Enviar o pedido ao back-end via fetch
  </script></body>
</html>
