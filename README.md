# 📈 Bot de Trading Automático na Binance

Este é um bot de trading automático que utiliza o indicador **RSI (Relative Strength Index)** para tomar decisões de compra e venda de **Bitcoin (BTC)** no par **BTC/USDT**. Ele se conecta à **API da Binance** para obter dados de mercado e executar ordens de compra e venda.

## 🚀 Funcionalidades

- Obtém os preços do BTC na Binance (Testnet ou real).
- Calcula o **RSI (Relative Strength Index)** para avaliar se o ativo está **sobrecomprado** ou **sobrevendido**.
- Executa **ordens de compra e venda automaticamente**, baseado no RSI.
- Usa **autenticação segura** com HMAC-SHA256 para assinar as requisições à API da Binance.

## 📌 Pré-requisitos

Antes de rodar o bot, você precisa:

1. Ter o **Node.js** instalado (versão 16+ recomendada).
2. Criar uma conta na **Binance Testnet** ([https://testnet.binance.vision/](https://testnet.binance.vision/)).
3. Gerar **chaves de API** no site da Binance Testnet para permitir autenticação.
4. Criar um arquivo `.env` para armazenar suas chaves API de forma segura.

## 🔧 Configuração

1️⃣ Clone este repositório:

```bash
 git clone https://github.com/seu-usuario/bot-cripto.git
```

2️⃣ Instale as dependências:

```bash
 cd bot-cripto
 npm install
```

3️⃣ Configure suas chaves de API:
Crie um arquivo `.env` na raiz do projeto e adicione:

```env
API_KEY=SEU_API_KEY_AQUI
SECRET_KEY=SEU_SECRET_KEY_AQUI
```

> **⚠️ Importante:** **NUNCA** compartilhe suas chaves de API publicamente. Elas dão acesso à sua conta Binance e podem ser usadas para executar ordens em seu nome.

4️⃣ Execute o bot:

```bash
 node index.js
```

## ⚙️ Como funciona?

O bot segue a seguinte lógica:

- Obtém os últimos **21 candles** do mercado BTC/USDT (15 minutos cada).
- Calcula o **RSI** (índice de força relativa) com **período 14**.
- **Compra BTC** se o RSI for **menor que 30** (sobrevendido).
- **Vende BTC** se o RSI for **maior que 70** (sobrecomprado).
- Repete o processo a cada **3 segundos**.

## 🛠 Tecnologias utilizadas

- **Node.js**
- **Axios** (para chamadas HTTP)
- **Crypto** (para assinatura de requisições HMAC-SHA256)

## 📜 Licença

Este projeto está sob a licença MIT. Sinta-se à vontade para contribuir e melhorar!

---

💡 **Dica:** Caso queira testar em conta real, substitua `https://testnet.binance.vision` por `https://api.binance.com` e gere novas chaves de API na Binance real.

