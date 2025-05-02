# Aztec Sequencer Node Setup (Testnet)

This repository provides a simple and clean guide to run an **Aztec Sequencer Node** on your own VPS (e.g., Ubuntu 22.04). Useful for testnet participation, contributing to the Aztec ecosystem, and potentially future airdrops.

## ✅ Requirements

- VPS or local server (recommended: Ubuntu 22.04+, 2 vCPU, 4GB+ RAM)
- Docker & Docker Compose installed
- At least 30GB of free disk space
- Basic command-line knowledge

## ⚙️ Step 1: System Preparation

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install curl git docker.io docker-compose -y
sudo usermod -aG docker $USER && newgrp docker
```

> For manual Docker installation, see: [Docker Install Guide](https://docs.docker.com/engine/install/ubuntu/)

## 📦 Step 2: Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/aztec-sequencer-node.git
cd aztec-sequencer-node
```

## 🛠️ Step 3: Start the Node

```bash
docker-compose up -d
```

> The sequencer will be available at `http://localhost:8080` after startup.

## 🔍 Step 4: Check Logs & Status

```bash
docker logs -f aztec-sequencer
```

> Adjust the container name if you’ve changed it in `docker-compose.yml`.

## 📁 Project Structure

```text
aztec-sequencer-node/
├── docker-compose.yml
└── README.md
```

## 📄 Example `docker-compose.yml`

```yaml
version: '3.8'

services:
  aztec-sequencer:
    image: aztecprotocol/aztec-sequencer:latest
    ports:
      - "8080:8080"
    restart: unless-stopped
```

> You can replace `latest` with a specific version (e.g., `v0.18.0`) for more control.

## 🧠 Useful Commands

Stop the node:
```bash
docker-compose down
```

Restart the node:
```bash
docker-compose restart
```

Clean up old Docker images:
```bash
docker image prune -af
```

## 🌐 Resources

- [Aztec GitHub](https://github.com/AztecProtocol)
- [Aztec Docs](https://docs.aztec.network)
- [Aztec Discord](https://discord.gg/aztec)

## ✨ Contribute

Feel free to open issues or submit pull requests if you find bugs or want to improve this setup.

## ⚠️ Disclaimer

This is a community-driven guide with no official support. Use at your own risk.
