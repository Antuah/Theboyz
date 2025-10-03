Es una aplicación móvil que permite a los usuarios descubrir, guardar y compartir lugares de interés. Desde un café oculto hasta un mirador secreto, la comunidad es la que construye el mapa de descubrimientos.

## 🎯 Alcance del Sprint 1 (Planificación y Arquitectura)

Este sprint se enfoca en establecer las bases técnicas y de planificación del proyecto. Los entregables clave incluyen:
- Definición de la arquitectura MVVM.
- Configuración del repositorio en GitHub.
- Creación y priorización del backlog inicial en GitHub Projects.
- Establecimiento de convenciones de código y de versionado.
- Estructura inicial de carpetas del proyecto Flutter.

## 🛠️ Instrucciones de Setup Local

1.  **Clonar el repositorio:**
    ```sh
    git clone [https://github.com/](https://github.com/)[TuOrganizacion]/UrbanExplorers.git
    cd UrbanExplorers
    ```
2.  **Instalar dependencias de Flutter:**
    ```sh
    flutter pub get
    ```
3.  **Ejecutar la aplicación:**
    ```sh
    flutter run
    ```

## 🌿 Convenciones de Ramas (Git Flow)

-   `main`: Contiene el código de producción estable. Solo se mezcla desde `develop` al final de un ciclo.
-   `develop`: Rama principal de desarrollo. Contiene las últimas funcionalidades integradas.
-   `feature/[nombre-feature]`: Ramas para nuevas funcionalidades. Se crean a partir de `develop` y se mezclan de vuelta a `develop`. (Ej: `feature/login-screen`)
-   `fix/[nombre-fix]`: Ramas para corregir bugs. Se crean a partir de `develop` y se mezclan de vuelta. (Ej: `fix/validation-error`)

## ✍️ Convenciones de Commits

Usamos el estándar de [Conventional Commits](https://www.conventionalcommits.org/).
**Formato:** `<tipo>(<ámbito>): <descripción>`
-   **Tipos:** `feat` (nueva funcionalidad), `fix` (corrección de bug), `docs` (documentación), `style` (formato), `refactor`, `test`, `chore` (tareas de mantenimiento).
-   **Ejemplo:** `feat(auth): add email and password validation to login screen`
