# Pterodactyl Ollama Egg - Run Local LLMs on Your Pterodactyl Panel

![Ollama Pterodactyl](https://img.shields.io/badge/Ollama-Pterodactyl-blue?style=for-the-badge&logo=ollama)
![Pterodactyl AI Egg](https://img.shields.io/badge/Pterodactyl-Egg-green?style=for-the-badge)
![Visitors](https://api.visitorbadge.io/api/visitors?path=joynalbokhsho.pterodactyl-ollama-egg&countColor=%23263759&style=for-the-badge)

A production-ready **Pterodactyl egg for Ollama** that allows you to easily run a local **LLM server** directly on your Pterodactyl Panel. If you are searching for an **Ollama Pterodactyl Egg** to host open-source AI models seamlessly, this is the complete, lightweight, and API-ready solution. 

This egg automatically installs the Ollama engine, starts the REST API server, and pulls your configured language models (like LLaMA 3.1, Qwen, Gemma) on server boot.

## 🌟 Key Features of this Ollama Egg

- 🚀 **Zero-Config Auto-Installation**: Automatically downloads and extracts the latest Ollama binaries for Linux (`amd64` or `arm64`) directly to your Pterodactyl node.
- 🤖 **Auto-Pull AI Models**: Configurable startup variable to automatically pull and load your desired LLM on server start. Run any model from the Ollama library.
- 🐳 **Standard Panel Images**: Uses standard `ghcr.io/parkervcp/yolks` Debian/Ubuntu base images for perfect Pterodactyl compatibility.
- ⚡ **API Ready**: Exposes the standard Ollama API on the assigned server port, allowing external applications, Discord bots, and AI agents to connect to your Pterodactyl server.

## 🚀 How to Install the Ollama Pterodactyl Egg

1. Download the `egg-ollama.json` file from this repository.
2. Go to your Pterodactyl Panel's **Admin Control Panel**.
3. Navigate to **Nests** -> **Import Egg**.
4. Upload the `egg-ollama.json` file.
5. Assign the egg to a nest of your choice (e.g., a "Generic", "AI", or "Bots" nest).
6. Create a new server using this **Ollama Egg**!

> **Warning**
> Ensure your Pterodactyl nodes have sufficient disk space. Language models (LLMs) can be several gigabytes in size.

## ⚙️ Configuration (Startup Variables)

When creating your Ollama server or under the **Startup** tab, you can configure the following variables:

| Variable | Environment Variable | Description | Default |
| :--- | :--- | :--- | :--- |
| **Model Name** | `MODEL_NAME` | The Ollama model to automatically pull and run on startup. Check the [Ollama Library](https://ollama.com/library) for available models (e.g., `llama3.1:8b`, `qwen2.5:3b`, `gemma2:9b`). | `qwen2.5:3b` |

## 💻 Usage & API Access

Once the Pterodactyl server is installed and started, it will:
1. Download the Ollama engine.
2. Start the Ollama API server bound to your Pterodactyl allocated IP and Port.
3. Automatically pull the model defined in the `MODEL_NAME` variable.

You can then interact with the Ollama API using the server's IP and port just like a local Ollama instance.

### Example API Request (Generating Text)

```bash
curl http://<YOUR_PTERODACTYL_SERVER_IP>:<YOUR_SERVER_PORT>/api/generate -d '{
  "model": "qwen2.5:3b",
  "prompt": "Why is the sky blue?",
  "stream": false
}'
```

## 🛠️ Troubleshooting Pterodactyl Ollama Issues

- **Server stuck on installing/extracting:** This is almost always caused by the Pterodactyl server running out of disk space. Check the daemon logs or ensure the server has a large enough disk quota to fit the LLM.
- **Model pull fails:** Ensure the `MODEL_NAME` is typed exactly as it appears on the Ollama registry. The server will continue to run even if the pull fails, but the model won't be available for inference.

## 🔍 SEO Keywords
*Pterodactyl Ollama Egg, Run Ollama on Pterodactyl, Local LLM Pterodactyl, Pterodactyl AI Server, Pterodactyl Eggs, Ollama Pterodactyl Panel integration, LLaMA Pterodactyl, Qwen Pterodactyl, AI Hosting Pterodactyl.*

## 📜 Credits & Author

- Author: `joynalbokhsho@gmail.com`
- Built for the [Pterodactyl](https://pterodactyl.io/) community.
- Powered by [Ollama](https://ollama.com/).
