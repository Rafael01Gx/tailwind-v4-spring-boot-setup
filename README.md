# Tailwind v4 + Spring Boot — Setup Completo e Moderno 🚀  
Um guia definitivo, visual e interativo para configurar **TailwindCSS v4.1** com **Spring Boot + Thymeleaf**.  
Inclui passos claros, comandos prontos, exemplos reais e seções estilizadas para fácil leitura.

---

<div align="center">
  <img src="https://img.shields.io/badge/Tailwind%20CSS-v4.1-38BDF8?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Java-17+-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-100%25%20Funcional-brightgreen?style=for-the-badge" />
</div>

---

## 📌 Sobre este Repositório
Este repositório demonstra como integrar **TailwindCSS v4.1** em um projeto **Spring Boot + Thymeleaf** de forma simples, rápida e totalmente funcional.

👉 *Ideal para quem quer usar Tailwind no backend Java sem complicações.*

---

## 📂 Estrutura Final do Projeto
```
src/
 └── main/
     ├── java/... (código Spring)
     ├── resources/
     │   ├── static/
     │   │   └── css/
     │   │       └── style.css         ← gerado automaticamente
     │   ├── css/
     │   │   └── input.css             ← seu arquivo de origem
     │   └── templates/
     │       └── home.html
package.json
pom.xml
README.md
```

---

# 🛠️ Passo a Passo Completo

---

# 1️⃣ Inicializar o Node.js no Projeto

Abra o terminal na raiz do seu projeto:

```bash
npm init -y
```

Isso cria o **package.json**, necessário para instalar o Tailwind.

---

# 2️⃣ Instalar o Tailwind v4.1 + CLI Oficial

```bash
npm install -D tailwindcss @tailwindcss/cli
```

---

# 3️⃣ Criar o Arquivo de Origem CSS

Crie:

```
src/main/resources/css/input.css
```

E coloque:

```css
@import "tailwindcss";

@source "./src/main/resources/templates/**/*.html";

@theme {
  --color-brand: #3b82f6;
  --font-display: "Inter", "sans-serif";
}

@layer base {
  h1 {
    @apply text-2xl font-bold;
  }
}
```

---

# 4️⃣ Configurar Scripts no package.json

Substitua **tudo** dentro de `"scripts"`:

```json
"scripts": {
  "build-css": "npx @tailwindcss/cli -i ./src/main/resources/css/input.css -o ./src/main/resources/static/css/style.css --minify",
  "watch-css": "npx @tailwindcss/cli -i ./src/main/resources/css/input.css -o ./src/main/resources/static/css/style.css --watch"
}
```

---

# 5️⃣ Linkar o CSS Gerado no HTML (Thymeleaf)

Exemplo:

```html
<link rel="stylesheet" th:href="@{/css/style.css}">
```

---

# 6️⃣ Iniciar o Workflow de Desenvolvimento

Terminal 1 — Tailwind:

```bash
npm run watch-css
```

Terminal 2 — Spring Boot:

```bash
./mvnw spring-boot:run
```

Ou na sua IDE.


---

# 🧩 Exemplo de Componente Usando Tailwind

```html
<div class="p-6 rounded-xl bg-brand/10 border border-brand">
  <h1 class="font-display text-brand">Spring + Tailwind funcionando! 🎉</h1>
  <p class="text-gray-700 mt-2">
    Agora você pode usar qualquer utilitário Tailwind diretamente no Thymeleaf.
  </p>
</div>
```

---

# 🤝 Créditos
Este guia foi criado por **Rafael (GitHub: @Rafael01Gx)**.  
O objetivo é ajudar desenvolvedores Java a utilizarem Tailwind v4 de forma simples e profissional.

---

# ⭐ Gostou do projeto?
Deixe um **star ⭐** no repositório — isso ajuda muito!  

---

# 📜 Licença
MIT — Livre para uso, modificação e distribuição.
