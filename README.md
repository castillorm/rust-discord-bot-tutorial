# 🦀 Rust Discord Bot Tutorial

A hands-on project for building and deploying a Discord bot using Rust.
This tutorial walks through setup, coding with **Serenity** and **Tokio**, inviting the bot to your Discord server, and deploying it on **Railway** or **Render** — a perfect intro to async programming and API integration in Rust.

---

## 🚀 Features

* Responds to chat commands like `!ping`
* Built with async Rust using [Serenity](https://github.com/serenity-rs/serenity)
* Secure environment variable handling with `.env`
* Deployable to cloud platforms (Railway, Render, or self-hosted)
* Step-by-step instructions to add your bot to a Discord server

---

## 🧩 Prerequisites

Make sure you have:

* [Rust](https://www.rust-lang.org/tools/install) (latest stable)
* [Cargo](https://doc.rust-lang.org/cargo/)
* A [Discord account](https://discord.com) and server
* A bot token from the [Discord Developer Portal](https://discord.com/developers/applications)

---

## 🏗️ Setup

### 1. Clone the Repository

```bash
git clone https://github.com/rodcastillo/rust-discord-bot-tutorial.git
cd rust-discord-bot-tutorial
```

### 2. Install Dependencies

```bash
cargo build
```

### 3. Add Your Discord Bot Token

Create a `.env` file in the root folder:

```env
DISCORD_TOKEN=your_bot_token_here
```

> ⚠️ Never share or commit this token. Keep `.env` in your `.gitignore`.

---

## 🔗 Add Your Bot to a Discord Server

Once your bot is created in the **Discord Developer Portal**, follow these steps to add it to your own server:

### 1. Generate the Invite (OAuth2) Link

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Select your application (e.g. **RustyBot**)
3. Go to **OAuth2 → URL Generator**
4. Under **Scopes**, select:

   * ✅ `bot`
   * ✅ `applications.commands`
5. Under **Bot Permissions**, select:

   * ✅ `Read Messages/View Channels`
   * ✅ `Send Messages`
   * ✅ `Read Message History`
   * (Optional) `Use Slash Commands`, `Embed Links`, `Add Reactions`
6. Copy the generated URL at the bottom — it will look like this:

   ```
   https://discord.com/oauth2/authorize?client_id=123456789012345678&scope=bot+applications.commands&permissions=3072
   ```

### 2. Invite the Bot

1. Paste that URL into your browser
2. Choose the Discord server where you want to install the bot
3. Click **Continue → Authorize**

Your bot should now appear in the server’s **member list** (usually offline until you run it).

---

## 💬 Run Locally

Start your bot:

```bash
cargo run
```

If successful, you’ll see:

```
RustyBot#1234 is connected!
```

Now go to your Discord server and type:

```
!ping
```

Bot should reply:

```
Pong! 🦀
```

---

## 🌐 Deploy to the Cloud

### Option 1: Railway (Recommended)

1. Sign up at [railway.app](https://railway.app)
2. Deploy your GitHub repo
3. Add environment variable:

   ```
   DISCORD_TOKEN=your_bot_token
   ```
4. Add `Procfile`:

   ```
   worker: cargo run --release
   ```
5. Deploy → your bot runs 24/7!

### Option 2: Render

1. Go to [render.com](https://render.com)
2. Create new **Web Service**
3. Add same environment variable
4. Use build/start commands:

   ```bash
   cargo build --release
   cargo run --release
   ```

---

## 🧠 Learnings

This project helped me:

* Practice **async programming** with `Tokio`
* Explore **Serenity’s Discord API**
* Understand **event-driven architecture**
* Learn **secure deployment pipelines**

---

## 🪄 Next Steps

* Add slash commands (`/ping`)
* Create embeds or images
* Integrate APIs (e.g., OpenAI, GitHub)
* Add command modules for cleaner architecture

---

## 🧰 Tech Stack

| Tool     | Purpose                         |
| -------- | ------------------------------- |
| Rust     | Core language                   |
| Serenity | Discord API wrapper             |
| Tokio    | Async runtime                   |
| dotenv   | Environment variable management |

---

## 🤝 Connect

Created by [**Rod Castillo**](https://www.linkedin.com/in/rodcastillo/).
If you’re learning Rust or cybersecurity, feel free to connect or star ⭐ the repo!
