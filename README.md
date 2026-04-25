# 🚀 BuildBuddy RBE Setup (Auto-Config)

This guide will help you quickly set up **BuildBuddy Remote Build Execution (RBE)** using an auto-configured script that loads silently in every new terminal session.

---

## 📥 Step 1: Clone the Repository

Clone the setup repository into your home directory under a hidden folder `.rbe`:

```bash
git clone https://github.com/Adarsh0127-Elite/BuildBuddy-RBE.git ~/.rbe
```

---

## ⚙️ Step 2: Add RBE Auto-Configuration to `.bashrc`

Append the following lines to your `.bashrc` to automatically source the RBE environment on every terminal launch (silently):

```bash
echo -e '\n# Source RBE setup silently\nif [[ $- == *i* ]]; then\n    source ~/.rbe/setup-rbe.sh > /dev/null\nfi' >> ~/.bashrc
```

---

## 🔄 Step 3: Reload `.bashrc`

Apply the changes immediately without restarting your terminal:

```bash
source ~/.bashrc
```

---

## 🔐 BuildBuddy API Token Setup

To use BuildBuddy Remote Build Execution (RBE), you need an API key and organization URL.

### 🧭 Steps to Generate Your API Key:

1. Go to [https://www.buildbuddy.io](https://www.buildbuddy.io)
2. **Create an account** (or log in if you already have one)
3. Navigate to:  
   `Settings` → `Organization` → `Org API Keys`
4. Click **“Generate API Key”** and copy it

---

## 📝 Update Your RBE Configuration

1. Open the config file:
   ```bash
   nano ~/.rbe/rbe.conf
   ```
2. Replace the placeholder values:
   ```ini
   BB_INSTANCE="your-org.buildbuddy.io"
   BB_API_KEY="paste-your-api-key-here"
   NINJA_REMOTE_NUM_JOBS=712
   ```

> Make sure the `BB_INSTANCE` matches your org URL (e.g., `myteam.buildbuddy.io`).

3. Save and exit (`Ctrl + O`, then `Enter`, then `Ctrl + X`)

---

3. Setup RBE:
   ```bash
   ./.rbe/setup-rbe.sh
   ```

## ✅ Done!

Now every new terminal session will:
- Automatically configure your environment for BuildBuddy RBE
- Run silently in the background
- Prompt you only if setup is incomplete

Happy building! 🛠️
