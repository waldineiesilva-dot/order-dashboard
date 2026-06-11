# Order Tracking Dashboard

Dashboard automático de acompanhamento de ordens SKF / TATA / Vulcan.

---

## Como funciona

```
Tu saves o Excel  →  Fazes upload no GitHub  →  GitHub corre o script automaticamente
→  Dashboard atualiza em ~1 min  →  Link permanece o mesmo para todos
```

---

## Configuração inicial (única vez)

### 1 — Criar conta GitHub
Acede a [github.com](https://github.com) e cria uma conta gratuita.

### 2 — Criar repositório
- Clica em **New repository**
- Nome: `order-dashboard` (ou o que preferires)
- Visibilidade: **Private** ← importante para controlar acesso
- Clica **Create repository**

### 3 — Fazer upload dos ficheiros
Arrasta para o repositório todos os ficheiros desta pasta:
```
order_dashboard.html
Purchasing_management_Rev_3.xlsx
scripts/
  update_dashboard.py
.github/
  workflows/
    update_dashboard.yml
```

### 4 — Ativar GitHub Pages
- Vai a **Settings → Pages**
- Source: **Deploy from a branch**
- Branch: **main** / pasta: **/ (root)**
- Clica **Save**
- O teu link será: `https://SEU-UTILIZADOR.github.io/order-dashboard/order_dashboard.html`

### 5 — Proteger com password (acesso restrito)
O ficheiro `order_dashboard.html` já tem um ecrã de login integrado.

Para definir as passwords, abre o ficheiro `order_dashboard.html` e localiza esta linha perto do topo do `<script>`:

```js
const PASSWORDS = ['vulcan2024', 'tata2024', 'skf2024'];
```

Altera para as passwords que quiseres e faz upload novamente.

---

## Como atualizar (uso diário)

1. Abre o teu ficheiro Excel e faz as alterações normalmente
2. Guarda o Excel
3. Vai ao repositório GitHub no browser
4. Clica no ficheiro `Purchasing_management_Rev_3.xlsx`
5. Clica no ícone do lápis (✏️) ou no botão **...** → **Upload file**
6. Arrasta o Excel atualizado → **Commit changes**
7. O GitHub corre o script automaticamente → em ~60 segundos o dashboard está atualizado

---

## Partilhar acesso

Envia o link do dashboard + a password correspondente:

| Empresa | Link | Password |
|---------|------|----------|
| Vulcan  | https://SEU-UTILIZADOR.github.io/order-dashboard/order_dashboard.html | vulcan2024 |
| TATA    | (mesmo link) | tata2024 |
| SKF     | (mesmo link) | skf2024 |

Podes usar passwords diferentes por empresa ou a mesma para todos.

---

## Verificar se o update correu

Após o upload do Excel, vai a **Actions** no repositório GitHub.  
Deves ver um job a correr (círculo amarelo) ou concluído (visto verde).  
Se aparecer ❌ vermelho, verifica se o nome do ficheiro Excel está correto.
