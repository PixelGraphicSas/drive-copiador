# 📁 Drive Copiador

Herramienta web para búsqueda y copia masiva de archivos en Google Drive.  
Funciona directamente en el navegador, sin instalar nada.

## 🚀 Uso en GitHub Pages

**URL de acceso:**
```
https://TU_USUARIO.github.io/drive-copiador/
```

---

## ⚙️ Configuración inicial (solo una vez)

### 1. Clona o descarga el repositorio

```bash
git clone https://github.com/TU_USUARIO/drive-copiador.git
cd drive-copiador
```

### 2. Crea tu archivo de credenciales

```bash
cp config.example.js config.js
```

Edita `config.js` con tus credenciales de [Google Cloud Console](https://console.cloud.google.com):

```js
window.DRIVE_COPIADOR_CONFIG = {
  apiKey:   'TU_API_KEY',
  clientId: 'TU_CLIENT_ID.apps.googleusercontent.com'
};
```

> ⚠️ `config.js` está en `.gitignore` — nunca se sube a GitHub automáticamente.

### 3. Autoriza tu dominio en Google Cloud Console

En **APIs y servicios → Credenciales → OAuth Client ID**, agrega en **Orígenes autorizados**:

```
https://TU_USUARIO.github.io
```

---

## 📋 Cómo obtener las credenciales

1. Ve a [console.cloud.google.com](https://console.cloud.google.com)
2. Selecciona tu proyecto **Busqueda Digital**
3. **APIs y servicios → Habilitar APIs** → activa **Google Drive API**
4. **APIs y servicios → Credenciales**:
   - **API Key** → copia el valor
   - **OAuth 2.0 Client ID** → copia el Client ID

---

## 🗂 Estructura del proyecto

```
drive-copiador/
├── index.html          ← Aplicación principal
├── config.js           ← TUS credenciales (NO está en GitHub)
├── config.example.js   ← Plantilla de credenciales (sí está en GitHub)
├── .gitignore          ← Excluye config.js del repositorio
└── README.md           ← Este archivo
```

---

## 🔒 Seguridad

- Las credenciales **nunca** se suben a GitHub gracias al `.gitignore`
- El repositorio puede ser público sin riesgo
- Cada persona que use la herramienta necesita su propio `config.js`

---

## ✨ Funcionalidades

- **3 procesos independientes:** Indexar → Buscar → Copiar
- **Caché de índice** por catálogo con fecha de última actualización
- **Pausa / Cancelar** en cualquier momento
- **Pausa automática** ante límites de Drive (5 min de espera)
- **Copia a Drive o a carpeta local** del equipo
- **Modo oscuro / claro**
- **Configuración de catálogos** editable sin tocar código
- **Exportar CSV** con resultados por proceso
- **Informe final** con KPIs completos

