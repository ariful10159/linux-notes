
# 📌 2. GitHub note (copy-paste ready)



---

## 🟢 Manjaro GPU Driver Commands & Usage

### 🔧 Remove NVIDIA profile

```bash
sudo mhwd -r pci video-nvidia
```

👉 Removes NVIDIA mhwd configuration profile if installed
👉 Used when switching away from NVIDIA driver setup

---

### 🔧 Install Intel (video-linux) profile

```bash
sudo mhwd -i pci video-linux
```

👉 Installs open-source graphics stack
👉 Uses Intel integrated graphics by default
👉 Improves stability and reduces crashes in most systems

---

### 🔍 Check active GPU rendering

```bash
glxinfo | grep "OpenGL renderer"
```

👉 Shows which GPU is currently being used for rendering
👉 Example outputs:

* Intel → integrated graphics active
* NVIDIA → dedicated GPU active

---
