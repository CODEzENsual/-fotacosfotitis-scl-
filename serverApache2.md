# 🗒️ **Bitácora de Configuración del Servidor Apache**  

### 📅 **Fecha:** 2025-04-19  

---

## 🔧 **Objetivo del Proyecto:**
La configuración de un servidor Apache con soporte SSL mediante Let's Encrypt, junto con la activación de un firewall utilizando **UFW (u otro)** para asegurar el entorno de producción de la aplicación.

---

## 📝 **Requisitos del Sistema:**
- **Sistema Operativo:** #?
- **Apache Version:** #?
- **Let's Encrypt Version:** #?
- **UFW (u otro Firewall):** 0.36
- **Hardware:**  
  - CPU: #? vCPUsorNPU
  - RAM: #?GB  
  - Almacenamiento: #?GB "M.2"orSSD

---

## 🔧 **Configuración Realizada**  

### 1️⃣ **Servidor Apache:**
- **Configuración de VirtualHost:** ✔️  
  Se configuró un VirtualHost para permitir la gestión de múltiples dominios de forma eficiente y con un balance adecuado de recursos.

### 2️⃣ **Certificado SSL:**
- **Let's Encrypt:** 🔒  
  Implementación exitosa de **Let's Encrypt** para asegurar la comunicación del servidor. Certificado emitido y configurado automáticamente.

### 3️⃣ **Firewall:**
- **UFW ((u otro)Uncomplicated Firewall):** 🔐  
  Activación y configuración de reglas para limitar el tráfico de red a los puertos esenciales, asegurando el acceso solo a los servicios autorizados.

---

## 🛠️ **Comandos y Scripts Ejecutados:**

```bash
# Instalación de Apache
sudo apt update
sudo apt install apache2

# Configuración de VirtualHost
echo "<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>" > /etc/apache2/sites-available/000-default.conf

# Certificado SSL con Let's Encrypt
sudo apt install certbot python3-certbot-apache
sudo certbot --apache

# Configuración de UFW
sudo ufw allow 'Apache Full'
sudo ufw enable
