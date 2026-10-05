# 🚕 Drive App - Calculadora de Corridas Particulares

Aplicativo web progressivo (PWA / Mobile-first) criado para cálculo dinâmico e transparente do valor de corridas particulares (estilo Uber/99), com integração direta ao Google Maps e geolocalização em tempo real.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat&logo=tailwind-css&logoColor=white)
![Google Maps API](https://img.shields.io/badge/Google_Maps_API-4285F4?style=flat&logo=google-maps&logoColor=white)
![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?style=flat&logo=vercel&logoColor=white)

---

## 📌 Funcionalidades

- **🗺️ Integração com Google Maps:**
  - Autocomplete inteligente de endereços de embarque e desembarque.
  - Traçado de rota otimizado em tempo real.
  - Cálculo automático de distância percorrida (km) e tempo previsto com trânsito (minutos).
- **📍 Geolocalização em Tempo Real:**
  - Detecção da posição atual do motorista via GPS.
  - Botão de atalho rápido para definir o local de embarque como a localização atual.
- **💰 Tarifação Dinâmica Personalizável:**
  - Definição de **Tarifa Base** (bandeirada).
  - Preço por **Quilômetro Rodado (R$/km)**.
  - Preço por **Minuto de Corrida (R$/min)**.
  - Definição de **Valor Mínimo** por corrida.
  - Persistência das taxas no navegador (`LocalStorage`) para não perder suas preferências.
- **📱 Design Responsivo / Mobile-First:**
  - Interface otimizada para uso no smartphone preso ao suporte veicular.
  - Suporte para fixação como Web App na tela inicial do celular.

---

## 🧮 Fórmula de Cálculo

O valor da corrida é calculado pela fórmula padrão de serviços de transporte individual:

$$\text{Valor Total} = \max\Big(\text{Tarifa Mínima}, \text{Tarifa Base} + (\text{Distância (km)} \times \text{Preço/km}) + (\text{Tempo (min)} \times \text{Preço/min})\Big)$$

---

## 🚀 Como Executar Localmente

Como o projeto é construído em HTML, CSS (Tailwind via CDN) e JavaScript nativo, não há dependência de compilação ou instalação de pacotes:

1. Clone o repositório:
   ```bash
   git clone https://github.com/igorribasr/drive-app.git
   cd drive-app
   ```
2. Abra o arquivo `index.html` diretamente em seu navegador ou utilize uma extensão de servidor local (ex: *Live Server* no VS Code).

> **Atenção:** Recursos de geolocalização e mapas necessitam de conexão com a internet e permissão de GPS no navegador.

---

## 🔑 Configuração da Google Maps API

Para utilizar suas próprias credenciais:

1. Obtenha uma chave no [Google Cloud Console](https://console.cloud.google.com/).
2. Habilite as APIs:
   - **Maps JavaScript API**
   - **Places API**
   - **Directions API**
3. No arquivo `index.html`, localize o script do Google Maps e insira sua chave:
   ```html
   <script async defer src="https://maps.googleapis.com/maps/api/js?key=SUA_CHAVE_AQUI&libraries=places&callback=initMap"></script>
   ```
4. *(Recomendado)* No painel do Google Cloud, restrinja o uso da chave apenas aos domínios da sua aplicação (ex: `*.vercel.app/*`).

---

## 🌐 Deploy

O projeto é 100% estático e pode ser hospedado gratuitamente com deploy contínuo em:
- [Vercel](https://vercel.com)
- [GitHub Pages](https://pages.github.com)
- [Netlify](https://www.netlify.com)

---

## 📄 Licença

Distribuído sob a licença [MIT](LICENSE). Consulte o arquivo `LICENSE` para mais detalhes.
