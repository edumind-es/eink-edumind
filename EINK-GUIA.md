# E-Ink Style System v2.0

Sistema CSS para simular pantallas de tinta electrónica. Reduce luz azul e mellora a experiencia de lectura.

---

## Instalación Rápida

### 1. Enlaza o CSS

```html
<head>
  <!-- Fontes recomendadas (opcional) -->
  <link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible:wght@400;700&family=Literata:wght@400;600;700&display=swap" rel="stylesheet">
  
  <!-- E-Ink CSS -->
  <link rel="stylesheet" href="eink.css">
</head>
```

### 2. Aplica a clase ao HTML

```html
<html class="eink">
  <body>
    <div class="eink-container">
      <!-- O teu contido aquí -->
    </div>
  </body>
</html>
```

---

## Modos Dispoñibles

| Modo | Clase | Descrición |
|------|-------|------------|
| Normal | `eink` | Modo día, papel cálido |
| Noite | `eink eink-night` | Máis cálido, menos luz azul |
| Escuro | `eink eink-dark` | Inversión tipo Kindle |

### Cambiar modo con JavaScript

```javascript
function setMode(mode) {
  const html = document.documentElement;
  html.classList.remove('eink-night', 'eink-dark');
  
  if (mode === 'night') {
    html.classList.add('eink-night');
  } else if (mode === 'dark') {
    html.classList.add('eink-dark');
  }
}
```

---

## Compoñentes Principais

### Tipografía

```html
<h1>Título Principal</h1>
<h2>Subtítulo</h2>
<p class="eink-dropcap">Parágrafo con letra capitular...</p>
<p>Parágrafo normal con <strong>énfase</strong> e <code>código</code>.</p>
```

### Botóns

```html
<button class="eink-btn">Primario</button>
<button class="eink-btn eink-btn--outline">Secundario</button>
<button class="eink-btn eink-btn--small">Pequeno</button>
<button class="eink-btn eink-btn--large">Grande</button>
<button class="eink-btn eink-btn--block">Ancho completo</button>
```

### Tarxetas

```html
<div class="eink-card">
  <h4 class="eink-card__title">Título da Tarxeta</h4>
  <p>Contido da tarxeta...</p>
</div>

<!-- Con header e footer -->
<div class="eink-card">
  <div class="eink-card__header">
    <h4 class="eink-card__title">Título</h4>
  </div>
  <p>Contido...</p>
  <div class="eink-card__footer">
    <button class="eink-btn eink-btn--small">Acción</button>
  </div>
</div>
```

### Formularios

```html
<div class="eink-form-group">
  <label class="eink-label">Nome:</label>
  <input type="text" class="eink-input" placeholder="O teu nome">
</div>

<div class="eink-form-group">
  <label class="eink-label">Opción:</label>
  <select class="eink-select">
    <option>Selecciona...</option>
    <option>Opción 1</option>
  </select>
</div>

<label class="eink-checkbox">
  <input type="checkbox">
  <span>Acepto os termos</span>
</label>
```

### Alertas

```html
<div class="eink-alert">Alerta básica</div>
<div class="eink-alert eink-alert--info">Información</div>
<div class="eink-alert eink-alert--success">Éxito</div>
<div class="eink-alert eink-alert--warning">Aviso</div>
<div class="eink-alert eink-alert--error">Erro</div>
```

### Badges

```html
<span class="eink-badge">Normal</span>
<span class="eink-badge eink-badge--dark">Escuro</span>
```

### Táboas

```html
<table class="eink-table">
  <thead>
    <tr>
      <th>Columna 1</th>
      <th>Columna 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Dato 1</td>
      <td>Dato 2</td>
    </tr>
  </tbody>
</table>
```

### Navegación

```html
<nav class="eink-nav">
  <a href="#" class="eink-nav__brand">📖 MiApp</a>
  <ul class="eink-nav__links">
    <li><a href="#" class="eink-nav__link eink-nav__link--active">Inicio</a></li>
    <li><a href="#" class="eink-nav__link">Sobre</a></li>
  </ul>
</nav>
```

---

## Utilidades

### Texto

```html
<p class="eink-text-muted">Texto secundario</p>
<p class="eink-text-center">Centrado</p>
<p class="eink-text-small">Pequeno</p>
<p class="eink-text-large">Grande</p>
```

### Espaciado

```html
<!-- Margin top/bottom -->
<div class="eink-mt-md">Margin top medio</div>
<div class="eink-mb-lg">Margin bottom grande</div>

<!-- Padding -->
<div class="eink-p-md">Padding medio</div>
```

### Layout

```html
<!-- Grid de 2 columnas -->
<div class="eink-grid-2">
  <div>Columna 1</div>
  <div>Columna 2</div>
</div>

<!-- Flex -->
<div class="eink-flex eink-flex-between eink-gap-md">
  <div>Esquerda</div>
  <div>Dereita</div>
</div>
```

---

## Personalización

Podes sobreescribir as variables CSS:

```css
:root {
  /* Cambiar cor do papel */
  --eink-paper: #e0dbd3;
  
  /* Cambiar cor da tinta */
  --eink-ink: #1a1a18;
  
  /* Cambiar tipografía */
  --eink-font-serif: 'Georgia', serif;
  --eink-font-sans: 'Arial', sans-serif;
  
  /* Cambiar tamaño base */
  --eink-font-size: 18px;
}
```

---

## Variables Dispoñibles

| Variable | Valor por defecto | Descrición |
|----------|-------------------|------------|
| `--eink-paper` | `#d4cfc7` | Cor de fondo principal |
| `--eink-paper-light` | `#ddd8d0` | Fondo claro |
| `--eink-paper-dark` | `#c9c4bb` | Fondo escuro |
| `--eink-ink` | `#252422` | Cor de texto |
| `--eink-ink-soft` | `#3d3a36` | Texto secundario |
| `--eink-ink-light` | `#5c5853` | Texto terciario |
| `--eink-font-size` | `17px` | Tamaño base |
| `--eink-line-height` | `1.65` | Altura de liña |

---

## Exemplo Completo

```html
<!DOCTYPE html>
<html lang="gl" class="eink">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>A Miña App E-Ink</title>
  <link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible:wght@400;700&family=Literata:wght@400;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="eink.css">
</head>
<body>
  <div class="eink-container">
    <nav class="eink-nav">
      <a href="#" class="eink-nav__brand">📖 MiApp</a>
    </nav>
    
    <h1>Benvido</h1>
    <p>Esta é a miña aplicación con estilo e-ink.</p>
    
    <div class="eink-card">
      <h4 class="eink-card__title">Tarxeta de exemplo</h4>
      <p>Contido da tarxeta...</p>
      <button class="eink-btn">Acción</button>
    </div>
  </div>
</body>
</html>
```

---

**EDUmind Project | 2025**
