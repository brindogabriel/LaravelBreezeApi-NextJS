# Laravel Breeze API + Next.js TypeScript

Un template moderno y profesional que combina un backend robusto con Laravel 12 y un frontend elegante con Next.js 16, TypeScript y Tailwind CSS. Este proyecto es una extensión mejorada de [Laravel Breeze Next TypeScript](https://github.com/Byandev/laravel-breeze-next-typescript) con funcionalidades adicionales en el backend.

## 🎯 Descripción

Este template proporciona una solución fullstack completa y lista para producción, combinando:

- **Backend**: API RESTful moderna con Laravel 12, autenticación mediante Sanctum y una estructura escalable
- **Frontend**: Aplicación React moderna con TypeScript, Tailwind CSS y componentes respetuosos con la accesibilidad

Ideal para desarrollar aplicaciones web SPA (Single Page Application) con seguridad robusta y experiencia de usuario moderna.

## 🚀 Características Principales

### Backend (Laravel 12)
- ✅ **Laravel 12** - Framework PHP moderno y maduro
- ✅ **Laravel Sanctum** - Autenticación API segura con tokens
- ✅ **CORS Configurado** - Comunicación segura entre frontend y backend
- ✅ **Breeze Starter Kit** - Estructura de autenticación preconfigurada
- ✅ **Pest Testing** - Framework moderno de testing para PHP
- ✅ **Base de datos** - Migraciones y seeders listos
- ✅ **Queue Support** - Sistema de colas para tareas asincrónicas
- ✅ **PHP 8.2+** - Últimas características del lenguaje

### Frontend (Next.js 16)
- ✅ **Next.js 16** - Framework React con soporte SSR y optimizaciones
- ✅ **TypeScript** - Tipado estático para mejor experiencia de desarrollo
- ✅ **Tailwind CSS** - Framework CSS moderno y utilitario
- ✅ **React 19** - Última versión de React
- ✅ **Formik + Yup** - Manejo de formularios y validaciones
- ✅ **Axios** - Cliente HTTP para consumir la API
- ✅ **SWR** - Fetching de datos con caching y revalidación
- ✅ **ESLint** - Análisis de código estático
- ✅ **Headless UI** - Componentes accesibles sin estilos

## 📋 Requisitos Previos

Antes de comenzar, asegúrate de tener instalado:

- **PHP 8.2 o superior** - Verificar con `php --version`
- **Composer** - Gestor de dependencias de PHP
- **Node.js 18+** - Runtime de JavaScript
- **npm o pnpm** - Gestor de paquetes (recomendado pnpm)
- **Git** - Control de versiones
- **MySQL o PostgreSQL** - Base de datos (opcional, SQLite para desarrollo)

## 🔧 Instalación Rápida

### 1️⃣ Clonar el Repositorio

```bash
git clone <tu-repositorio>
cd LaravelBreezeApi_Nextjs
```

### 2️⃣ Configuración del Backend

```bash
cd Backend

# Instalar dependencias
composer install

# Copiar archivo de configuración
cp .env.example .env

# Generar clave de aplicación
php artisan key:generate

# Ejecutar migraciones
php artisan migrate

# (Opcional) Ejecutar seeders
php artisan db:seed
```

### 3️⃣ Configuración del Frontend

```bash
cd ../Frontend

# Instalar dependencias
pnpm install
# o si usas npm
npm install
```

## 🏃 Ejecución

### Opción 1: Ejecutar Todo Junto (Recomendado)

Desde la raíz del proyecto Backend:

```bash
composer run dev
```

Esto ejecutará en paralelo:
- Servidor Laravel (`php artisan serve`)
- Cola de trabajos (`php artisan queue:listen`)
- Servidor de desarrollo de Next.js (`npm run dev`)

### Opción 2: Ejecutar Manualmente

**Terminal 1 - Backend:**
```bash
cd Backend
php artisan serve
```

**Terminal 2 - Frontend:**
```bash
cd Frontend
pnpm dev
# o npm run dev
```

### Acceso a la Aplicación

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:8000/api

## 📁 Estructura del Proyecto

```
LaravelBreezeApi_Nextjs/
├── Backend/                          # API Laravel 12
│   ├── app/
│   │   ├── Http/
│   │   │   ├── Controllers/         # Controladores API
│   │   │   ├── Middleware/          # Middlewares personalizados
│   │   │   └── Requests/            # Form Requests (validación)
│   │   └── Models/                  # Modelos Eloquent
│   ├── config/                       # Archivos de configuración
│   ├── database/
│   │   ├── migrations/              # Migraciones BD
│   │   ├── seeders/                 # Seeders de datos
│   │   └── factories/               # Factories para testing
│   ├── routes/
│   │   ├── api.php                  # Rutas API
│   │   └── auth.php                 # Rutas autenticación
│   ├── tests/                        # Tests con Pest
│   └── storage/                      # Archivos y logs
│
├── Frontend/                         # App Next.js 14
│   ├── src/
│   │   ├── app/                     # App Router de Next.js
│   │   ├── components/              # Componentes React
│   │   ├── hooks/                   # Custom React Hooks
│   │   ├── lib/                     # Utilidades y helpers
│   │   └── types/                   # Tipos TypeScript
│   ├── public/                       # Assets estáticos
│   └── tailwind.config.ts           # Configuración Tailwind
│
└── README.md                         # Este archivo
```

## 🔐 Autenticación

El proyecto utiliza **Laravel Sanctum** para autenticación API:

1. El usuario se registra/inicia sesión en el frontend
2. El backend valida las credenciales y genera un token
3. El token se almacena en el frontend (localStorage/cookies)
4. Todas las peticiones incluyen el token en el header `Authorization: Bearer <token>`

### Endpoints Principales de Autenticación

```
POST   /api/auth/register          # Registrar nuevo usuario
POST   /api/auth/login              # Iniciar sesión
POST   /api/auth/logout             # Cerrar sesión
GET    /api/user                    # Obtener datos del usuario actual
POST   /api/auth/forgot-password    # Solicitar reset de contraseña
```

## 📚 Documentación y Recursos

### Backend (Laravel)
- [Documentación Oficial de Laravel](https://laravel.com/docs)
- [Laravel Sanctum](https://laravel.com/docs/sanctum)
- [Pest Testing](https://pestphp.com)

### Frontend (Next.js)
- [Documentación Oficial de Next.js](https://nextjs.org/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [TypeScript en React](https://www.typescriptlang.org/docs/handbook/react.html)

## 🧪 Testing

### Backend
```bash
cd Backend

# Ejecutar todos los tests
composer test

# Ejecutar tests específicos
php artisan test Feature/Auth
```

### Frontend
```bash
cd Frontend

# Ejecutar linter
pnpm lint
```

## 🚀 Despliegue

### Requisitos para Producción

- Hosting con soporte para PHP 8.2+
- Node.js en el servidor (para Next.js)
- HTTPS obligatorio
- Base de datos de producción (MySQL/PostgreSQL)
- Variable de entorno `APP_ENV=production`

### Build para Producción

**Backend:**
```bash
cd Backend
composer install --no-dev --optimize-autoloader
composer dump-autoload
```

**Frontend:**
```bash
cd Frontend
pnpm build
pnpm start
```

## 🤝 Contribuir

Las contribuciones son bienvenidas. Para cambios principales:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo [LICENSE.md](LICENSE.md) para más detalles.

## 🙏 Créditos

- **Frontend Base**: [Laravel Breeze Next TypeScript](https://github.com/Byandev/laravel-breeze-next-typescript) por [@Byandev](https://github.com/Byandev)
- **Backend**: Laravel 12 y Laravel Breeze oficial
- **Comunidad**: Laravel y Next.js communities

## 📞 Soporte

Si encuentras problemas:

1. Revisa la sección de Issues en GitHub
2. Consulta la documentación oficial de Laravel y Next.js
3. Verifica que todas las dependencias estén correctamente instaladas
4. Asegúrate de que las variables de entorno estén configuradas

---

**Hecho con ❤️ usando Laravel 12 y Next.js 16**
