# Veiled Truths: Plataforma Personalizable de Generación de Contenido con IA

Este proyecto, "Veiled Truths", es una plataforma web desarrollada con Next.js que actúa como un **dashboard personalizable para la generación de contenido impulsado por inteligencia artificial**. Inicialmente concebido para un cliente específico con el fin de potenciar su estrategia de marketing digital, esta aplicación ha sido diseñada con la flexibilidad en mente, sirviendo ahora como un **template robusto y adaptable para la creación de soluciones de contenido a medida para una amplia gama de nichos de mercado**.

Como pieza clave en mi portfolio, "Veiled Truths" demuestra mi capacidad para construir herramientas digitales que **impulsan el engagement, aumentan el tráfico y, en última instancia, potencian las ventas** mediante la creación estratégica de contenido dirigido a audiencias específicas.

## Características Principales

- **Generación de Contenido con IA:** Automatiza la creación de ideas de contenido, borradores y textos optimizados para diferentes plataformas y audiencias.
- **Adaptabilidad a Nichos de Mercado:** Diseñado para ser fácilmente configurable y adaptado a las necesidades específicas de distintos verticales de negocio.
- **Impulso al Engagement:** Herramientas y sugerencias de contenido diseñadas para captar la atención y fomentar la interacción con la audiencia.
- **Optimización para Tráfico y Ventas:** Contenido generado con un enfoque en atraer visitantes cualificados y convertirlos en clientes.
- **Dashboard Intuitivo:** Interfaz de usuario amigable para gestionar y visualizar el proceso de generación de contenido.
- **Funcionalidades Modulares:** Componentes y flujos de trabajo que pueden ser activados o desactivados según los requerimientos del cliente o nicho.

## Tecnologías Utilizadas

- **Framework:** Next.js 15 (con Turbopack)
- **Lenguaje:** TypeScript
- **Estilos:** Tailwind CSS
- **UI Components:** Shadcn/ui (Radix UI)
- **IA:** Genkit + Google Gemini 2.0 Flash
- **Autenticación:** OAuth 2.0 (Twitter API v2)
- **Gráficos:** Recharts
- **Despliegue:** Vercel / Firebase App Hosting compatible
- **Gestor de Paquetes:** npm

El diseño y la guía de estilo, incluyendo la paleta de colores y tipografías, se encuentran documentados en `/docs/blueprint.md`.

## Use cases of Twitter's data and API

I will use the Twitter API to build and showcase a demo application called "Veiled Truths," a customizable AI-powered content manager dashboard. The platform helps generate, curate, and schedule marketing content, analyze audience interests, and identify relevant trends and conversations. This data will be used exclusively to enhance content recommendations, visualize engagement metrics, and demonstrate the capabilities of the dashboard to potential clients and as part of my personal portfolio. No data will be resold or redistributed.

## Próxima Función Planeada: Análisis Profundo de Nichos y Audiencias

Como parte de la evolución de "Veiled Truths", se está planificando la incorporación de una potente funcionalidad de **análisis profundo de nichos y identificación de audiencias**. Esta característica permitirá:

1. **Análisis Temático del Nicho:** Realizar un escrutinio detallado de los temas clave dentro del nicho de mercado objetivo, identificando tendencias, palabras clave relevantes y conversaciones predominantes.
2. **Identificación de Audiencia:** Localizar dónde se encuentra la audiencia objetivo, tanto geográficamente como en las plataformas online donde interactúan (redes sociales, foros, blogs, etc.).
3. **Definición de Buyer Personas:** Construir perfiles detallados de los clientes ideales (buyer personas) basándose en el análisis de datos de comportamiento de consumo, intereses y características demográficas.
4. **Predicción de Comportamiento:** Utilizar modelos de IA para predecir el comportamiento de consumo de los buyer personas identificados.
5. **Visualización Profesional:** Presentar los hallazgos de manera clara y concisa a través de **resúmenes pulidos y gráficos intuitivos**.

---

## Configuración e Instalación

### Requisitos Previos

- Node.js 20+ (recomendado)
- npm 10+ o yarn
- Cuenta de Google Cloud con API de Gemini habilitada
- Cuenta de desarrollador de Twitter/X con una App creada

### 1. Clonar el Repositorio

```bash
git clone https://github.com/JuanRoccia/autogen.git
cd autogen
```

### 2. Instalar Dependencias

```bash
npm install
```

### 3. Configurar Variables de Entorno

Copia el archivo de ejemplo y complétalo con tus credenciales:

```bash
cp .env.example .env.local
```

Edita `.env.local` con las siguientes variables:

```env
# Google AI / Genkit
GOOGLE_GENAI_API_KEY=your_google_api_key_here

# Twitter API v2
TWITTER_CLIENT_ID=your_twitter_client_id
TWITTER_CLIENT_SECRET=your_twitter_client_secret

# App URL (para callbacks OAuth)
NEXT_PUBLIC_BASE_URL=http://localhost:9000
```

#### Obtener GOOGLE_GENAI_API_KEY

1. Ve a [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Crea una nueva API key
3. Copiala a tu `.env.local`

#### Obtener credenciales de Twitter

1. Ve a [Twitter Developer Portal](https://developer.twitter.com/en/portal/dashboard)
2. Crea un nuevo proyecto y aplicación
3. Configura OAuth 2.0 con los siguientes settings:
   - Type of App: Web App
   - Callback URL: `http://localhost:9000/api/twitter/callback`
   - Website URL: `http://localhost:9000`
4. Genera el Client ID y Client Secret
5. Habilita los permisos: `tweet.read`, `tweet.write`, `users.read`, `offline.access`

### 4. Ejecutar en Desarrollo

Inicia el servidor de desarrollo (Next.js):

```bash
npm run dev
```

Para iniciar Genkit (AI flows):

```bash
npm run genkit:dev
```

Abre [http://localhost:9000](http://localhost:9000) en tu navegador.

### 5. Build para Producción

```bash
npm run build
npm start
```

### Scripts Disponibles

| Script | Descripción |
|--------|-------------|
| `npm run dev` | Inicia servidor dev en puerto 9000 con Turbopack |
| `npm run genkit:dev` | Inicia Genkit en modo desarrollo |
| `npm run genkit:watch` | Inicia Genkit con watch mode |
| `npm run build` | Build de producción |
| `npm run start` | Inicia servidor de producción |
| `npm run lint` | Linting con Next.js |
| `npm run typecheck` | Verificación de tipos TypeScript |

### Estructura del Proyecto

```
src/
├── app/                    # Rutas de la aplicación
│   ├── [lang]/            # Rutas con i18n (en, es-AR)
│   │   ├── dashboard/     # Páginas del dashboard
│   │   │   ├── theme-generator/
│   │   │   ├── content-aligner/
│   │   │   ├── publisher/
│   │   │   └── scheduler/
│   │   └── page.tsx       # Redirect a /dashboard
│   ├── api/
│   │   └── twitter/       # API routes de OAuth y publicación
│   └── actions/           # Server Actions
├── components/
│   ├── ui/               # Componentes shadcn/ui
│   ├── dashboard/        # Componentes del dashboard
│   └── language-switcher.tsx
├── ai/                   # AI Flows (Genkit)
│   ├── genkit.ts         # Configuración principal
│   ├── dev.ts           # Punto de entrada para desarrollo
│   └── flows/           # Flujos de IA disponibles
├── lib/
│   ├── utils.ts         # Utilidades
│   ├── twitter.ts       # Cliente Twitter API
│   └── dictionaries.ts  # Configuración i18n
├── hooks/               # Custom React hooks
├── dictionaries/        # Archivos de traducción (en.json, es-AR.json)
└── middleware.ts        # Middleware i18n
```

### AI Flows Disponibles

| Flow | Descripción |
|------|-------------|
| `generateConspiracyThemes` | Genera temas conspirativos basados en eventos actuales, keywords, tono y plataforma |
| `analyzeTrends` | Analiza tendencias de redes sociales para un tema |
| `generateSuggestions` | Genera sugerencias aleatorias de temas y keywords |
| `expandToThread` | Expande contenido a thread narrativo de 9 etapas |
| `refineContent` | Refina contenido existente según instrucciones del usuario |
| `generateImage` | Genera imágenes con Gemini 2.0 Flash |
| `generateEngagementStrategy` | Genera estrategias de engagement con estilo filosófico (Nietzschean, Socratic, Stoic) |
| `alignPlatformContent` | Adapta contenido para diferentes plataformas |

### Sistema de Idiomas

La aplicación soporta **Inglés (en)** y **Español Argentino (es-AR)**. El idioma se detecta automáticamente según las preferencias del navegador y puede cambiarse desde el sidebar.

### Despliegue

El proyecto es compatible con cualquier hosting para Next.js:

1. **Vercel** (recomendado): `vercel deploy`
2. **Firebase App Hosting**: Configuración en `apphosting.yaml`
3. **Docker/Railway/Render**: Build con `npm run build` y serve con `npm start`
