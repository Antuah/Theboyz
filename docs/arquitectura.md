# 📐 Arquitectura del Proyecto: MVVM

Hemos elegido el patrón de arquitectura **Model-View-ViewModel (MVVM)** para garantizar una separación clara de responsabilidades, facilitar la mantenibilidad y mejorar la capacidad de realizar pruebas unitarias y de widgets.

## Diagrama de Flujo de Datos

El flujo de información sigue un ciclo unidireccional para mantener la consistencia del estado.




[View] <--> [ViewModel] <--> [Repository] <--> [Data Sources (API/DB Local)] | | (Notifica (Expone eventos estado y del usuario) lógica)

## Responsabilidades de las Capas

### 1. 📦 Model
-   **Responsabilidad:** Representar los datos y la lógica de negocio fundamental. Son clases PODO (Plain Old Dart Object) que definen la estructura de los datos.
-   **Ejemplos:** `User.dart`, `Discovery.dart`.
-   **Regla:** No deben tener conocimiento de ninguna otra capa.

### 2. 🖼️ View
-   **Responsabilidad:** Es la capa de UI (lo que el usuario ve). Su único trabajo es mostrar el estado proporcionado por el ViewModel y notificarle las interacciones del usuario (clics, texto ingresado, etc.).
-   **Ejemplos:** `LoginScreen.dart`, `HomeScreen.dart`, `DiscoveryCard.dart`.
-   **Regla:** No contiene lógica de negocio. Debe ser lo más "tonta" posible. Utiliza `StatelessWidget` o `StatefulWidget` para construir la UI.

### 3. 🧠 ViewModel
-   **Responsabilidad:** Actúa como el puente entre el Modelo y la Vista. Contiene el estado de la UI y la lógica de presentación. Expone los datos del Modelo a la Vista y maneja las acciones del usuario.
-   **Ejemplos:** `LoginViewModel.dart`, `HomeViewModel.dart`.
-   **Regla:** No debe tener ninguna referencia directa a los widgets de Flutter (ninguna importación de `material.dart`). Se comunica con la Vista a través de `ChangeNotifier`, `Streams` o gestores de estado como Provider/Riverpod.

### 4. ⚙️ Services / Repositories
-   **Responsabilidad:** Abstraer el origen de los datos. El ViewModel no sabe si los datos vienen de una API, una base de datos local o un archivo de cache. El repositorio es el único que tiene esa responsabilidad.
-   **Ejemplos:** `AuthRepository.dart` (con métodos `login`, `register`), `DiscoveryRepository.dart` (con `getDiscoveries`, `addDiscovery`).
-   **Regla:** Proporcionan una API limpia al ViewModel para acceder a los datos.
