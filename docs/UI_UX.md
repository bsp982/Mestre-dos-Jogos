# 🎨 UI/UX Design

## 🎯 Princípios de Design

### Design System
- **Framework UI**: Angular Material
- **CSS Framework**: Tailwind CSS
- **Ícones**: Material Icons
- **Tipografia**: Google Fonts
- **Cores**: Material Design Color System
- **Componentes**: Angular Material Components
- **Animações**: Angular Animations

## Design System

### 🎨 Cores
```scss
// Cores Principais
$primary: #2C3E50;    // Azul escuro
$secondary: #E74C3C;  // Vermelho
$accent: #F1C40F;     // Amarelo

// Tons de Cinza
$gray-100: #F8F9FA;
$gray-200: #E9ECEF;
$gray-300: #DEE2E6;
$gray-400: #CED4DA;
$gray-500: #ADB5BD;
$gray-600: #6C757D;
$gray-700: #495057;
$gray-800: #343A40;
$gray-900: #212529;

// Estados
$success: #2ECC71;
$warning: #F39C12;
$danger: #E74C3C;
$info: #3498DB;
```

### 📝 Tipografia
```scss
// Fontes
$font-primary: 'Roboto', sans-serif;
$font-secondary: 'Montserrat', sans-serif;
$font-display: 'Playfair Display', serif;

// Tamanhos
$font-size-xs: 0.75rem;    // 12px
$font-size-sm: 0.875rem;   // 14px
$font-size-base: 1rem;     // 16px
$font-size-lg: 1.125rem;   // 18px
$font-size-xl: 1.25rem;    // 20px
$font-size-2xl: 1.5rem;    // 24px
$font-size-3xl: 1.875rem;  // 30px
$font-size-4xl: 2.25rem;   // 36px
```

### 📏 Espaçamento
```scss
$spacing-unit: 0.25rem;  // 4px

$space-1: $spacing-unit;     // 4px
$space-2: $spacing-unit * 2; // 8px
$space-3: $spacing-unit * 3; // 12px
$space-4: $spacing-unit * 4; // 16px
$space-5: $spacing-unit * 5; // 20px
$space-6: $spacing-unit * 6; // 24px
```

### 🔲 Bordas e Sombras
```scss
// Bordas
$border-radius-sm: 0.25rem;
$border-radius: 0.5rem;
$border-radius-lg: 1rem;
$border-radius-full: 9999px;

// Sombras
$shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
$shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1);
$shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
```

## Componentes

### 🔘 Botões
```html
<!-- Botão Primário -->
<button class="btn-primary">
  Alugar Jogo
</button>

<!-- Botão Secundário -->
<button class="btn-secondary">
  Cancelar
</button>

<!-- Botão de Ação -->
<button class="btn-action">
  <i class="icon"></i>
  Adicionar aos Favoritos
</button>
```

### 🎴 Cards de Jogos
```html
<div class="game-card">
  <img class="game-image" src="jogo.jpg" alt="Nome do Jogo">
  <div class="game-info">
    <h3>Nome do Jogo</h3>
    <div class="game-meta">
      <span>2-4 jogadores</span>
      <span>30 min</span>
    </div>
    <div class="game-price">
      <span>R$ 25,00</span>
      <span class="period">por dia</span>
    </div>
  </div>
</div>
```

## Layout

### 📱 Breakpoints
```scss
$breakpoints: (
  'sm': 640px,
  'md': 768px,
  'lg': 1024px,
  'xl': 1280px,
  '2xl': 1536px
);
```

### 📐 Grid System
```scss
.container {
  width: 100%;
  margin-right: auto;
  margin-left: auto;
  padding-right: 1rem;
  padding-left: 1rem;
  
  @media (min-width: 640px) { max-width: 640px; }
  @media (min-width: 768px) { max-width: 768px; }
  @media (min-width: 1024px) { max-width: 1024px; }
  @media (min-width: 1280px) { max-width: 1280px; }
}
```

## Animações

### 🎭 Transições
```scss
// Duração
$transition-duration-fast: 150ms;
$transition-duration-normal: 300ms;
$transition-duration-slow: 500ms;

// Timing Functions
$ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
$ease-in: cubic-bezier(0.4, 0, 1, 1);
$ease-out: cubic-bezier(0, 0, 0.2, 1);
```

## Princípios de UX

### 📱 Mobile First
- Design inicialmente para dispositivos móveis
- Adaptação progressiva para telas maiores
- Foco em conteúdo e funcionalidades essenciais

### 🎯 Hierarquia Visual
1. Títulos principais (24-36px)
2. Subtítulos (18-24px)
3. Texto de conteúdo (16px)
4. Informações secundárias (14px)
5. Metadados (12px)

### ⚡ Performance
- Lazy loading de imagens
- Otimização de assets
- Caching estratégico
- Prefetch de dados críticos

## Padrões de Interação

### 📋 Formulários
- Labels claros e descritivos
- Validação em tempo real
- Mensagens de erro específicas
- Autocomplete quando possível

### 🔄 Loading States
```html
<!-- Spinner -->
<div class="loading-spinner">
  <svg><!-- ... --></svg>
  <span>Carregando...</span>
</div>

<!-- Skeleton Loading -->
<div class="skeleton-loader">
  <div class="skeleton-image"></div>
  <div class="skeleton-text"></div>
</div>
```

### 📢 Feedback
- Toasts para notificações
- Modais para confirmações
- Snackbars para ações
- Progress bars para processos

## Acessibilidade

### ♿ Diretrizes
- Contraste mínimo de 4.5:1
- Suporte a navegação por teclado
- Labels ARIA apropriados
- Textos alternativos para imagens

### 🎯 Checklist
- [ ] Semântica HTML correta
- [ ] Foco visível em elementos interativos
- [ ] Textos legíveis (mínimo 16px)
- [ ] Suporte a screen readers

## Responsividade

### 📱 Layout Mobile
- Menu hamburguer
- Cards em coluna única
- Imagens adaptativas
- Touch targets adequados (mínimo 44x44px)

### 💻 Layout Desktop
- Menu horizontal
- Grid de cards
- Sidebars quando necessário
- Hover states

## Componentes Específicos

### 🎲 Catálogo de Jogos
```html
<div class="games-grid">
  <div class="filters-sidebar">
    <!-- Filtros -->
  </div>
  <div class="games-list">
    <!-- Cards de Jogos -->
  </div>
</div>
```

### 📅 Calendário de Aluguel
```html
<div class="rental-calendar">
  <div class="calendar-header">
    <!-- Navegação -->
  </div>
  <div class="calendar-grid">
    <!-- Dias e Disponibilidade -->
  </div>
</div>
```

## Ícones e Assets

### 🎨 Sistema de Ícones
```html
<!-- Usando SVG Sprites -->
<svg class="icon">
  <use xlink:href="#icon-name"></use>
</svg>
```

### 📸 Imagens
- Formato: WebP com fallback para JPG
- Thumbnails: 200x200px
- Cards: 400x400px
- Detalhes: 800x800px

## Temas

### 🌞 Tema Claro
```scss
[data-theme="light"] {
  --bg-primary: #ffffff;
  --text-primary: #212529;
  --border-color: #dee2e6;
}
```

### 🌚 Tema Escuro
```scss
[data-theme="dark"] {
  --bg-primary: #212529;
  --text-primary: #ffffff;
  --border-color: #495057;
}
``` 