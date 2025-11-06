
# Repositorio APT (Hosteado en GitHub Pages)

Este repositorio contiene paquetes `.deb` generados automáticamente.

## Cómo agregar este repositorio a tu sistema (Debian/Ubuntu/LukOs)

Sigue estos pasos en una terminal para agregar el repositorio e instalar paquetes.

### 1. Descargar y agregar la Clave GPG

Este comando descarga la clave pública (`public.key`) del repositorio y la guarda 
en el directorio de confianza de `apt`.

```bash
wget -O - https://luk-os.github.io/Kronos/public.key | sudo gpg --dearmor -o /usr/share/keyrings/lukos-repo-keyring.gpg
```

### 2. Agregar la Fuente del Repositorio a APT

Esto crea un archivo de lista que le dice a `apt` dónde encontrar los paquetes.

```bash
echo       "deb [arch=amd64 signed-by=/usr/share/keyrings/lukos-repo-keyring.gpg] https://luk-os.github.io/Kronos/ stable main"       | sudo tee /etc/apt/sources.list.d/lukos-repo.list > /dev/null
```

### 3. Actualizar e Instalar

Actualiza tu lista de paquetes locales e instala el software que desees.

```bash
sudo apt update

# Ejemplo de instalación:
# sudo apt install nombre-del-paquete
```
