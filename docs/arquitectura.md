# Arquitectura del Proyecto

Este documento describe la arquitectura del proyecto Theboyz.

## Estructura de Carpetas

```
├── android/                    # Código y configuración específica de Android
├── ios/                        # Código y configuración específica de iOS
├── lib/
│   ├── main.dart              # Punto de entrada de la aplicación
│   ├── app/
│   │   ├── config/            # Configuración (rutas, temas, inyección de dependencias)
│   │   ├── services/          # Lógica de negocio no visual (API, DB, etc.)
│   │   └── utils/             # Clases de ayuda, constantes, extensiones
│   ├── core/
│   │   ├── models/            # Modelos de datos (User, Discovery, etc.)
│   │   ├── viewmodels/        # ViewModels de cada vista
│   │   └── repositories/      # Abstracción para obtener datos (API o local)
│   └── ui/
│       ├── views/             # Pantallas/Vistas de la aplicación (Login, Home, etc.)
│       └── widgets/           # Widgets reutilizables (botones, cards, etc.)
├── test/                      # Carpeta para pruebas unitarias y de widgets
└── docs/
    └── arquitectura.md        # Documentación de la arquitectura
```

## Capas de la Arquitectura

### 1. Capa de Presentación (UI)
- **views/**: Contiene las pantallas principales de la aplicación
- **widgets/**: Widgets reutilizables que componen las vistas

### 2. Capa de Lógica de Negocio (Core)
- **viewmodels/**: Manejan el estado y la lógica de negocio de las vistas
- **models/**: Modelos de datos que representan las entidades del dominio
- **repositories/**: Interfaces que abstraen el acceso a datos

### 3. Capa de Servicios (App)
- **services/**: Implementaciones de servicios (API, base de datos, autenticación)
- **config/**: Configuración de la aplicación (rutas, temas, DI)
- **utils/**: Utilidades, constantes y extensiones

## Principios de Diseño

1. **Separación de responsabilidades**: Cada capa tiene una responsabilidad específica
2. **Inyección de dependencias**: Las dependencias se inyectan para facilitar el testing
3. **Reutilización**: Los widgets y servicios son reutilizables
4. **Mantenibilidad**: Código organizado y fácil de mantener

## Flujo de Datos

1. La **UI** solicita datos al **ViewModel**
2. El **ViewModel** obtiene datos del **Repository**
3. El **Repository** usa **Services** para obtener datos de API o DB
4. Los datos se transforman en **Models**
5. El **ViewModel** actualiza el estado
6. La **UI** se actualiza automáticamente
