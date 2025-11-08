
# Repositorio APT de Kronos

Este repositorio contiene paquetes `.deb`, hosteado en GitHub Pages.

---

🛠️ Instalación

### 1️⃣ Añadir la clave GPG

Descarga e instala la clave GPG pública del repositorio.

```bash
# Descargar e instalar la clave GPG
sudo mkdir -p /usr/share/keyrings
wget -qO - https://cdn.jsdelivr.net/gh/luk-os/Kronos@main/public.key | sudo gpg --dearmor -o /usr/share/keyrings/kronos.gpg
```

### 2️⃣ Añadir el repositorio

Añade la fuente APT a tu sistema.

```bash
# Añadir la fuente APT
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/kronos.gpg trusted=yes] https://cdn.jsdelivr.net/gh/luk-os/Kronos@main/ stable main"     | sudo tee /etc/apt/sources.list.d/kronos.list

# Actualizar índices
# (El --allow-insecure-repositories es un truco para repos de GitHub Pages)
sudo apt update --allow-insecure-repositories
```

### 3️⃣ Instalar paquetes

Ahora puedes instalar paquetes desde el repositorio.

```bash
sudo apt install nombre-del-paquete
```
