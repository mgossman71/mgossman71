# Hi, I'm Mark

Infrastructure engineer with **30+ years** in Unix/Linux, infrastructure, and automation. These days I run a Proxmox-based homelab with local GPUs, and I build the pieces that connect it to AI: **MCP servers** that give AI agents safe, scoped access to real infrastructure, **local LLM serving**, and the **automation and IaC** underneath it all.

Everything here runs in my own lab first. The READMEs document the path that actually worked, not the dead ends.

---

## 🤖 AI agents × infrastructure (MCP servers)

MCP servers that let Claude, Cline, and other agents observe and operate real systems. Each one uses scoped tokens and is **read-only or whitelisted by default**.

| Project | What it does |
|---|---|
| [proxmox-mcp](https://github.com/mgossman71/proxmox-mcp) | Manage Proxmox VE clusters through the REST API with a dedicated, scoped API token |
| [proxmox-cve-mcp](https://github.com/mgossman71/proxmox-cve-mcp) | Scan Proxmox guests for pending security updates and correlate packages against OSV.dev CVEs, with no agent installed |
| [Unifi-MCP](https://github.com/mgossman71/Unifi-MCP) | Read-only view of the UniFi network (gateway, switches, APs, clients) plus port-health checks for drop/error rates |
| [HAs-MCP](https://github.com/mgossman71/HAs-MCP) | Whitelisted Home Assistant control of approved lights and switches only |
| [comfyui-mcp](https://github.com/mgossman71/comfyui-mcp) | Drive ComfyUI to generate images (FLUX) and music, and return the media to the model |
| [Gmail-MCP](https://github.com/mgossman71/Gmail-MCP) | Gmail + Google Calendar as 17 MCP tools over HTTP |

## 🧠 Local LLM & GPU infrastructure

| Project | What it does |
|---|---|
| [vllm-install](https://github.com/mgossman71/vllm-install) | The working path to serving Qwen 27B with vLLM on an RTX 5090 (CUDA 13, Ubuntu 24.04) |
| [vllm-dashboard](https://github.com/mgossman71/vllm-dashboard) | Real-time vLLM monitoring: KV cache, throughput, TTFT/TPOT latency, alerts (React + Prometheus) |
| [token-logger](https://github.com/mgossman71/token-logger) | Transparent Ollama proxy that logs real token usage and estimates the equivalent OpenAI/Anthropic cost |
| [InvokeAI-on-Proxmox-LXC](https://github.com/mgossman71/InvokeAI-on-Proxmox-LXC-with-RTX-5070Ti) | GPU passthrough into a Proxmox LXC and an InvokeAI install on an RTX 5070 Ti |

## 🏗️ Infrastructure as Code & automation

| Project | What it does |
|---|---|
| [proxmox-iac](https://github.com/mgossman71/proxmox-iac) | Terraform modules and independent lab/prod stacks for Proxmox LXCs and VMs (bpg/proxmox) |
| [Bootstrap-Server](https://github.com/mgossman71/Bootstrap-Server) | One-command Ansible bootstrap for Ubuntu 24.04 VMs and LXCs, served from a small nginx container |
| [backup_sets](https://github.com/mgossman71/backup_sets) | Incremental rsync backup sets to USB disks, driven by YAML config with a web portal |
| [SelfHostedApps](https://github.com/mgossman71/SelfHostedApps) | Ready-to-use Docker Compose configs for self-hosted services (Authentik, Grafana, Docmost, and more) |

## 🧰 Self-hosted apps I've built

| Project | What it does |
|---|---|
| [TaskBoard](https://github.com/mgossman71/TaskBoard) | Multi-tenant project management: Kanban, dependencies, real-time collaboration (React + FastAPI + PostgreSQL) |
| [Maintenance-Tracker](https://github.com/mgossman71/Maintenance-Tracker) | Vehicle and equipment maintenance tracking by miles, hours, and calendar time |
| [home-dashboard](https://github.com/mgossman71/home-dashboard) | Fast homelab start page, editable entirely from the browser |

---

## How I build

- **Least privilege for agents.** AI gets dedicated tokens, read-only tools, and explicit whitelists, not root.
- **Reproducible over clever.** Docker Compose, Terraform, and Ansible so anything can be rebuilt from the repo.
- **Document the working path.** Exact versions, tested hardware, and the gotchas that cost me hours.

## Stack

- **Infra:** Proxmox VE · LXC/QEMU · Terraform · Ansible · Docker Compose · nginx · UniFi · Home Assistant
- **AI:** MCP · vLLM · Ollama · ComfyUI · InvokeAI · NVIDIA CUDA
- **Code:** TypeScript · Python · Bash · React · FastAPI · PostgreSQL
