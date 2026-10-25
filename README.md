# 🧮 Redline Calc — Calculadora de Produção & Insumos

Calculadora web interativa, moderna e responsiva desenvolvida em **React** e **Tailwind CSS**, criada para otimizar o cálculo de produção, insumos, custos e margem de lucro de itens, encomendas e combos no GTA RP.

---

## 🚀 Funcionalidades

- 📦 **Cálculo Preciso de Insumos**: Calcula automaticamente todos os ingredientes e matérias-primas necessárias para a produção em lote de qualquer quantidade de itens (munições, kits, armas, combos, etc.).
- 💰 **Preços e Margens de Lucro**: Visualize custos de insumos, valor sugerido de venda e lucro líquido estimado.
- 📋 **Gerenciador de Pedidos & Encomendas**: Monte pedidos completos com múltiplos itens e copie um relatório formatado pronto para enviar no Discord com apenas 1 clique.
- ⚙️ **Configuração de Preços Personalizada**: Altere os valores de compra e venda de cada item diretamente pela interface gráfica.
- 💾 **Funcionamento Offline por Padrão**: Não requer nenhuma configuração de servidor para funcionar! Os dados de preços e pedidos são salvos automaticamente no navegador via `LocalStorage`.
- ☁️ **Sincronização em Nuvem (Opcional)**: Suporte integrado ao Firebase Firestore para manter os preços sincronizados em tempo real entre todos os membros da equipe.
- 🌓 **Tema Claro e Escuro**: Alternância suave entre Dark Mode e Light Mode.

---

## 🛠️ Tecnologias Utilizadas

- **Frontend**: [React 18](https://react.dev/) (via CDN) com Babel Standalone
- **Estilização**: [Tailwind CSS](https://tailwindcss.com/)
- **Ícones**: Componentes SVG dinâmicos integrados
- **Nuvem (Opcional)**: [Google Firebase](https://firebase.google.com/) Firestore Compat (v9)

---

## 💻 Como Executar Localmente

### Opção 1: Direto no Navegador (Mais Rápido)
Basta dar um duplo clique ou abrir o arquivo `public/index.html` em qualquer navegador web moderno (Google Chrome, Edge, Firefox, Brave, etc.).

### Opção 2: Extensão Live Server (VS Code)
1. Abra a pasta do projeto no VS Code.
2. Clique com botão direito em `public/index.html` e selecione **Open with Live Server**.

### Opção 3: Node.js (npx serve)
```bash
npx serve public
```

---

## ☁️ Configuração do Firebase (Opcional)

Por padrão, a calculadora funciona perfeitamente sem Firebase. Caso queira que as tabelas de preços sejam sincronizadas entre vários usuários via nuvem:

1. Acesse o [Firebase Console](https://console.firebase.google.com/) e crie um projeto.
2. Ative o **Cloud Firestore** em modo de produção ou teste.
3. Obtenha as credenciais da aplicação Web (`</>`) no Firebase.
4. Abra o arquivo `public/index.html` e localize o bloco por volta da linha 154:

```javascript
// --- CONFIGURAÇÃO FIREBASE (OPCIONAL) ---
const firebaseConfig = {
    apiKey: "SUA_API_KEY_AQUI",
    authDomain: "SEU_PROJETO.firebaseapp.com",
    projectId: "SEU_PROJETO_ID",
    storageBucket: "SEU_PROJETO.firebasestorage.app",
    messagingSenderId: "SEU_MESSAGING_SENDER_ID",
    appId: "SEU_APP_ID",
    measurementId: "SEU_MEASUREMENT_ID"
};
```

Substitua os valores com as credenciais do seu projeto. Assim que a `apiKey` for diferente de `"SUA_API_KEY_AQUI"`, o Firebase será conectado automaticamente.

---

## 🌐 Como Fazer Deploy

### GitHub Pages (Gratuito e Simples)
1. Crie um repositório no GitHub para este projeto.
2. Suba os arquivos (conforme as instruções da seção Git abaixo).
3. Vá em **Settings > Pages** no seu repositório.
4. Em **Build and deployment > Source**, selecione **Deploy from a branch**.
5. Escolha a branch `main` e a pasta `/ (root)` ou `/public`.

### Firebase Hosting
1. Instale o Firebase CLI:
   ```bash
   npm install -g firebase-tools
   ```
2. Vincule seu projeto:
   ```bash
   firebase login
   firebase use --add
   ```
3. Faça o deploy:
   ```bash
   firebase deploy --only hosting
   ```

---

## 📂 Estrutura de Arquivos

```text
├── public/
│   ├── index.html          # Aplicação completa em React (HTML, lógica, Tailwind e componentes)
│   └── LOGO-REDLINE-2.png  # Logotipo da aplicação
├── .firebaserc             # Arquivo de configuração de projeto Firebase Hosting
├── firebase.json           # Configuração de rotas estáticas
├── .gitignore              # Arquivos e pastas ignorados pelo Git
└── README.md               # Documentação completa
```

---

## 📄 Licença

Este projeto é de código aberto e livre para adaptações conforme as necessidades do seu grupo ou organização.
