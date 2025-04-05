
---

```markdown
# 🤖 PETER-POWER-MD - WhatsApp Bot

**PETER-POWER-MD** is a powerful and feature-rich WhatsApp bot built using [@whiskeysockets/Baileys](https://github.com/whiskeysockets/Baileys). This bot supports various automation tools, group features, media handling, and more.

## ⚙️ CI Workflow (Continuous Integration)

This project uses **GitHub Actions** to automatically run tests and install dependencies when changes are pushed to the `main` branch.

### 📁 `.github/workflows/ci.yml`

#### 🔄 Triggers
- `push` to `main`
- `pull_request` to `main`

#### 🔧 What it does
- Checks out the code
- Sets up Node.js (v14)
- Installs dependencies
- Runs tests using `npm test`

This ensures all code pushed to the repository is valid and won’t break production.

---

## 🚀 Deploy Workflow

To automate bot deployment, this project includes a **Deploy workflow**.

### 📁 `.github/workflows/deploy.yml`

#### 🔄 Trigger
- Automatically runs on `push` to the `main` branch

#### 🔧 What it does
- Clones the repository
- Installs dependencies
- Executes custom deployment commands (you can customize these to deploy to a server or service)

> ⚠️ Make sure to configure your deployment logic under the `Deploy to server` step using tools like SSH or PM2.

#### 💡 Example:
```yaml
run: |
  ssh -i ${{ secrets.SSH_KEY }} user@your_server_ip "
    cd ~/PETER-POWER-MD &&
    git pull &&
    npm install &&
    pm2 restart peter-power
  "
```

---

## 🔌 How to Use the Bot

1. **Fork or clone** the repository:
   ```bash
   git clone https://github.com/Mrskymax/PETER-POWER-MD.git
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run the bot locally**:
   ```bash
   node index.js
   ```

4. **Configure environment** using `.env` or `config.js` for keys, number, and credentials.

5. **Deploy to server** using the deploy workflow or manually using your preferred method.

---

## 🛡 Security Tip

Use [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets) to store sensitive values like SSH keys, API keys, and tokens. These can be accessed in your workflows via `${{ secrets.YOUR_SECRET_NAME }}`.

---

## 👨‍💻 Maintained by
**Mrskymax**  
GitHub: [@Mrskymax](https://github.com/Mrskymax)

---

## 📎 License
MIT © Mrskymax
```

