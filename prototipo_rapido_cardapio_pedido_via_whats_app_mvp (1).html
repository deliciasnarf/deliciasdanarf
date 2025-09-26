<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Delícias da Narf - Pedido WhatsApp (MVP)</title>
  <!-- Tailwind CDN para estilização rápida -->
  <script src="https://cdn.tailwindcss.com"></script>
  <meta name="color-scheme" content="light dark">
  <style>
    :root { color-scheme: light dark; }
    .btn { @apply px-4 py-2 rounded-2xl shadow font-medium; }
    .card { @apply rounded-2xl shadow p-4 bg-white/70 dark:bg-zinc-900/70; backdrop-filter: blur(6px); }
  </style>
</head>
<body class="min-h-screen bg-gradient-to-br from-emerald-50 to-emerald-100 dark:from-zinc-900 dark:to-zinc-950 text-zinc-900 dark:text-zinc-100">
  <!--
    ⚙️ COMO CONFIGURAR EM 1 MINUTO
    1) Troque o número do WhatsApp na constante OWNER_PHONE (somente dígitos c/ DDI, ex: 5561999999999).
    2) Edite o MENU com seus itens, preços, categorias e opcionais.
    3) Publique o arquivo em Vercel / GitHub Pages ou abra localmente no navegador e teste.

    ➕ Recursos do MVP
    - Cardápio com categorias.
    - Carrinho com total e observações.
    - Coleta de nome, tipo (retirada/entrega), endereço (se entrega) e forma de pagamento.
    - Gera mensagem e abre WhatsApp já preenchido.
  -->

  <header class="max-w-6xl mx-auto px-4 pt-6 pb-2">
    <div class="flex items-center justify-between gap-3">
      <div class="flex items-center gap-3">
        <img src="" id="brandLogo" alt="Logo Delícias da Narf" class="w-10 h-10 rounded-full object-cover ring-1 ring-black/10 hidden"/>
        <h1 class="text-2xl md:text-3xl font-bold">Delícias da Narf — Pedidos</h1>
      </div>
      <a id="qrLink" href="#" class="text-sm underline opacity-80">Gerar QR do Cardápio</a>
    </div>
    <p class="opacity-80 text-sm md:text-base">Faça seu pedido pelo WhatsApp. Escolha os itens, revise no carrinho e clique em “Enviar pelo WhatsApp”.</p>
  </header>

  <main class="max-w-6xl mx-auto px-4 py-4 grid md:grid-cols-3 gap-6">
    <!-- CATEGORIAS + ITENS -->
    <section class="md:col-span-2 space-y-6">
      <div class="card">
        <div class="flex items-center justify-between">
          <h2 class="text-xl font-semibold">Cardápio</h2>
          <div class="text-sm opacity-70">Preços em R$</div>
        </div>
        <div id="menuContainer" class="mt-4 space-y-6"></div>
      </div>
    </section>

    <!-- CARRINHO / CHECKOUT -->
    <aside class="space-y-6">
      <div class="card sticky top-4">
        <h2 class="text-xl font-semibold mb-3">Seu pedido</h2>
        <div id="cartContainer" class="space-y-3"></div>
        <div class="border-t border-zinc-200 dark:border-zinc-800 my-3"></div>
        <div class="flex items-center justify-between text-lg font-semibold">
          <span>Total</span>
          <span id="cartTotal">R$ 0,00</span>
        </div>
        <div class="mt-3">
          <label class="block text-sm mb-1">Observações (ex.: sem cebola, pouco sal)</label>
          <textarea id="notes" class="w-full rounded-xl px-3 py-2 bg-white dark:bg-zinc-800" rows="2"></textarea>
        </div>
        <div class="mt-3 grid grid-cols-1 gap-3">
          <label class="text-sm">Seu nome
            <input id="custName" class="w-full rounded-xl px-3 py-2 bg-white dark:bg-zinc-800" placeholder="Digite seu nome"/>
          </label>
          <label class="text-sm">Retirada ou Entrega
            <select id="fulfillment" class="w-full rounded-xl px-3 py-2 bg-white dark:bg-zinc-800">
              <option value="retirada">Retirada no balcão</option>
              <option value="entrega">Entrega</option>
            </select>
          </label>
          <label class="text-sm" id="addressLabel" style="display:none">Endereço para entrega
            <input id="address" class="w-full rounded-xl px-3 py-2 bg-white dark:bg-zinc-800" placeholder="Rua, número, complemento, bairro"/>
          </label>
          <label class="text-sm">Pagamento
            <select id="payment" class="w-full rounded-xl px-3 py-2 bg-white dark:bg-zinc-800">
              <option value="pix">Pix</option>
              <option value="dinheiro">Dinheiro</option>
              <option value="cartao">Cartão (maquininha)</option>
            </select>
          </label>
        </div>
        <button id="whatsBtn" class="btn w-full mt-4 bg-emerald-600 hover:bg-emerald-700 text-white">Enviar pelo WhatsApp</button>
        <button id="clearBtn" class="btn w-full mt-2 bg-zinc-200 dark:bg-zinc-800">Limpar carrinho</button>
      </div>
    </aside>
  </main>

  <footer class="max-w-6xl mx-auto px-4 pb-8 text-xs opacity-70">
    <p>Protótipo MVP — BSB FIT. Feito para teste rápido: cardápio + pedido via WhatsApp. © 2025</p>
  </footer>

  <script>
    // =============================
    // CONFIGURAÇÕES RÁPIDAS
    // =============================
    const OWNER_PHONE = "5561999999999"; // TODO: troque para seu número do WhatsApp (DDI + DDD + número)

    // Taxa de entrega padrão (pode evoluir por CEP/raio)
    const DELIVERY_FEE = 0; // R$ (ajuste se cobrar entrega)  // R$

    // Cardápio: edite como quiser
    const MENU = [
      {
        category: "Marmitas",
        items: [
          { id: "marmita-p", name: "Marmita P", price: 16.90, desc: "Escolha 1 carne.", options: [
            { id: "carne", label: "Carne", type: "single", required: true, choices: [
              { id: "frango", label: "Filé de frango", price: 0 },
              { id: "bisteca", label: "Bisteca suína", price: 0 },
              { id: "linguica", label: "Linguíça suína", price: 0 }
            ]}
          ]},
          { id: "marmita-g", name: "Marmita G", price: 22.00, desc: "Escolha 1 carne.", options: [
            { id: "carne", label: "Carne", type: "single", required: true, choices: [
              { id: "frango", label: "Filé de frango", price: 0 },
              { id: "bisteca", label: "Bisteca suína", price: 0 },
              { id: "linguica-assada", label: "Linguíça assada", price: 0 },
              { id: "carne-panela", label: "Carne de panela", price: 0 },
              { id: "churrasco", label: "Churrasco", price: 0 },
              { id: "feijoada", label: "Feijoada", price: 0 }
            ]}
          ]},
          { id: "marmita-g-mista", name: "Marmita G (Mista)", price: 25.00, desc: "Escolha 2 carnes.", options: [
            { id: "carne1", label: "Carne 1", type: "single", required: true, choices: [
              { id: "frango", label: "Filé de frango", price: 0 },
              { id: "bisteca", label: "Bisteca suína", price: 0 },
              { id: "linguica-assada", label: "Linguíça assada", price: 0 },
              { id: "carne-panela", label: "Carne de panela", price: 0 },
              { id: "churrasco", label: "Churrasco", price: 0 },
              { id: "feijoada", label: "Feijoada", price: 0 }
            ]},
            { id: "carne2", label: "Carne 2", type: "single", required: true, choices: [
              { id: "frango", label: "Filé de frango", price: 0 },
              { id: "bisteca", label: "Bisteca suína", price: 0 },
              { id: "linguica-assada", label: "Linguíça assada", price: 0 },
              { id: "carne-panela", label: "Carne de panela", price: 0 },
              { id: "churrasco", label: "Churrasco", price: 0 },
              { id: "feijoada", label: "Feijoada", price: 0 }
            ]}
          ]}
        ]
      }
    ];

    // =============================
    // ESTADO
    // =============================
    const state = {
      cart: [] // {id, name, basePrice, qty, options: [{groupId, choiceId, label, price}]}
    };

    // =============================
    // HELPERS
    // =============================
    const fmt = (n) => n.toLocaleString('pt-BR', { minimumFractionDigits: 2, maximumFractionDigits: 2 });

    function renderMenu() {
      const container = document.getElementById('menuContainer');
      container.innerHTML = '';
      MENU.forEach(block => {
        const section = document.createElement('div');
        section.innerHTML = `
          <h3 class="text-lg font-semibold mb-2">${block.category}</h3>
          <div class="grid md:grid-cols-2 gap-3" id="cat-${block.category}"></div>
        `;
        container.appendChild(section);

        const catGrid = section.querySelector(`#cat-${CSS.escape(block.category)}`);
        block.items.forEach(item => {
          const card = document.createElement('div');
          card.className = 'border border-zinc-200 dark:border-zinc-800 rounded-2xl p-3';
          card.innerHTML = `
            <div class="flex items-start justify-between gap-2">
              <div>
                <div class="font-medium">${item.name}</div>
                <div class="text-sm opacity-70">${item.desc || ''}</div>
                <div class="mt-1 font-semibold">R$ ${fmt(item.price)}</div>
              </div>
            </div>
            <div class="mt-2 space-y-2" id="opts-${item.id}"></div>
            <div class="mt-3 flex items-center gap-2">
              <button data-add="${item.id}" class="btn bg-emerald-600 hover:bg-emerald-700 text-white">Adicionar</button>
              <input type="number" min="1" value="1" class="w-16 px-2 py-1 rounded-xl bg-white dark:bg-zinc-800" id="qty-${item.id}"/>
            </div>
          `;
          catGrid.appendChild(card);

          // opções
          const optsWrap = card.querySelector(`#opts-${item.id}`);
          (item.options || []).forEach(group => {
            const optDiv = document.createElement('div');
            optDiv.innerHTML = `<label class="text-sm font-medium">${group.label}</label>`;
            const select = document.createElement('select');
            select.className = 'w-full rounded-xl px-3 py-2 bg-white dark:bg-zinc-800';
            select.dataset.groupId = group.id;
            group.choices.forEach(ch => {
              const o = document.createElement('option');
              o.value = ch.id;
              o.textContent = `${ch.label}${ch.price ? ` (+R$ ${fmt(ch.price)})` : ''}`;
              optDiv.appendChild(select);
              select.appendChild(o);
            });
            optsWrap.appendChild(optDiv);
          });

          // botão adicionar
          card.querySelector(`[data-add="${item.id}"]`).addEventListener('click', () => {
            const qty = Math.max(1, parseInt(card.querySelector(`#qty-${item.id}`).value || '1', 10));
            const chosen = [];
            optsWrap.querySelectorAll('select').forEach(sel => {
              const group = (item.options || []).find(g => g.id === sel.dataset.groupId);
              const choice = group.choices.find(c => c.id === sel.value);
              if (choice) {
                chosen.push({ groupId: group.id, choiceId: choice.id, label: `${group.label}: ${choice.label}` , price: Number(choice.price || 0) });
              }
            });
            addToCart({ id: item.id, name: item.name, basePrice: item.price, qty, options: chosen });
          });
        });
      });
    }

    function addToCart(entry) {
      // Se já existir o mesmo item com mesmas opções, agrupa
      const key = entry.id + '|' + (entry.options || []).map(o => `${o.groupId}:${o.choiceId}`).sort().join(',');
      const found = state.cart.find(c => c.key === key);
      if (found) {
        found.qty += entry.qty;
      } else {
        state.cart.push({ key, ...entry });
      }
      renderCart();
    }

    function removeFromCart(key) {
      state.cart = state.cart.filter(c => c.key !== key);
      renderCart();
    }

    function calcTotal() {
      const subtotal = state.cart.reduce((acc, item) => acc + (item.basePrice + (item.options||[]).reduce((a,b)=>a+b.price,0)) * item.qty, 0);
      const fulfillment = document.getElementById('fulfillment').value;
      const delivery = fulfillment === 'entrega' ? DELIVERY_FEE : 0;
      return { subtotal, delivery, total: subtotal + delivery };
    }

    function renderCart() {
      const wrap = document.getElementById('cartContainer');
      wrap.innerHTML = '';
      if (state.cart.length === 0) {
        wrap.innerHTML = '<div class="opacity-70 text-sm">Seu carrinho está vazio.</div>';
      } else {
        state.cart.forEach(item => {
          const li = document.createElement('div');
          const optsText = (item.options||[]).map(o => o.label).join(' • ');
          const unit = item.basePrice + (item.options||[]).reduce((a,b)=>a+b.price,0);
          li.className = 'flex items-start justify-between gap-3 border border-zinc-200 dark:border-zinc-800 rounded-xl p-2';
          li.innerHTML = `
            <div>
              <div class="font-medium">${item.qty}× ${item.name}</div>
              ${optsText ? `<div class="text-xs opacity-70">${optsText}</div>` : ''}
              <div class="text-sm opacity-80">R$ ${fmt(unit)} un.</div>
            </div>
            <div class="text-right">
              <div class="font-semibold">R$ ${fmt(unit * item.qty)}</div>
              <button class="text-xs underline opacity-70 mt-1" data-remove="${item.key}">remover</button>
            </div>
          `;
          wrap.appendChild(li);
        });
      }
      const totals = calcTotal();
      document.getElementById('cartTotal').textContent = `R$ ${fmt(totals.total)}`;
    }

    function buildWhatsMessage() {
      const name = (document.getElementById('custName').value || '').trim();
      const notes = (document.getElementById('notes').value || '').trim();
      const fulfillment = document.getElementById('fulfillment').value;
      const address = (document.getElementById('address').value || '').trim();
      const payment = document.getElementById('payment').value;
      const totals = calcTotal();

      const lines = [];
      lines.push(`*Novo pedido — Delícias da Narf*`);
      if (name) lines.push(`Cliente: ${name}`);
      lines.push('');
      state.cart.forEach(item => {
        const opts = (item.options||[]).map(o => o.label).join(' • ');
        const unit = item.basePrice + (item.options||[]).reduce((a,b)=>a+b.price,0);
        lines.push(`• ${item.qty}× ${item.name} — R$ ${fmt(unit * item.qty)}${opts ? ` ( ${opts} )` : ''}`);
      });
      lines.push('');
      lines.push(`Subtotal: R$ ${fmt(totals.subtotal)}`);
      if (fulfillment === 'entrega') lines.push(`Entrega: R$ ${fmt(totals.delivery)}`);
      lines.push(`Total: *R$ ${fmt(totals.total)}*`);
      lines.push('');
      lines.push(`Atendimento: ${fulfillment === 'entrega' ? 'Entrega' : 'Retirada'}`);
      if (fulfillment === 'entrega' && address) lines.push(`Endereço: ${address}`);
      lines.push(`Pagamento: ${payment.toUpperCase()}`);
      if (notes) { lines.push(''); lines.push(`Obs.: ${notes}`); }
      lines.push('');
      lines.push('Confirma por favor? ✅');

      return lines.join('\n');
    }

    function openWhats() {
      if (state.cart.length === 0) {
        alert('Seu carrinho está vazio. Adicione itens antes de enviar.');
        return;
      }
      const msg = buildWhatsMessage();
      const url = `https://wa.me/${OWNER_PHONE}?text=${encodeURIComponent(msg)}`;
      window.open(url, '_blank');
    }

    // Eventos UI básicos
    document.getElementById('whatsBtn').addEventListener('click', openWhats);
    document.getElementById('clearBtn').addEventListener('click', () => { state.cart = []; renderCart(); });

    document.getElementById('fulfillment').addEventListener('change', (e) => {
      const showAddr = e.target.value === 'entrega';
      document.getElementById('addressLabel').style.display = showAddr ? 'block' : 'none';
      renderCart();
    });

    // Link para QR do cardápio (usa o próprio URL da página)
    document.getElementById('qrLink').addEventListener('click', (e) => {
      e.preventDefault();
      const pageUrl = location.href;
      const qrApi = `https://api.qrserver.com/v1/create-qr-code/?size=300x300&data=${encodeURIComponent(pageUrl)}`;
      const w = window.open('', 'qr');
      w.document.write(`<title>QR do Cardápio</title><img alt='QR' src='${qrApi}' style='display:block;margin:24px auto;border-radius:16px;box-shadow:0 10px 30px rgba(0,0,0,.1)'/><p style='text-align:center;font-family:sans-serif'>Escaneie para abrir o cardápio</p>`);
    });

    // Inicialização
    renderMenu();
    renderCart();
  </script>
</body>
</html>
