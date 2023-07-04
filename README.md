# Namer App

App que genera pares de palabras aleatorias y permite al usuario marcar como favoritos y ver el historial de generación

# Getting Started

La aplicación utiliza el patrón de estado notificable **ChangeNotifier** para administrar y compartir el estado entre los diferentes widgets.

## Classes

- La clase **MyApp** es un widget principal que extiende **StatelessWidget**. Este widget es el punto de entrada de la aplicación y define la estructura general de la interfaz de usuario 

- La clase **MyAppState** es un objeto que extiende **ChangeNotifier** contiene el estado de la aplicación

- La clase **MyHomePage** es un widget que muestra el contenido principal de la aplicación. Dependiendo del valor de **selectedIndex**

- La clase **GeneratorPage** es un widget que muestra el generador de pares de palabras

- La clase **FavoritesPage** es un widget que muestra la lista de pares de palabras favoritas

- La clase **HistoryListView** es un widget que muestra el historial de pares de palabras generados


## Properties

- **current**: Almacena el par de palabras actual
- **history**: Almacena el historial de pares de palabras generados
- **favorites**: Almacena los pares de palabras marcados como favoritos
- **selectedIndex** Almacena el índice de la página seleccionada en la navegación.
- **mainArea** Define un widget que envuelve el contenido principal de la página
- **LayoutBuilder** Construye un widget en función de las restricciones de diseño actuales

## Methods

### **void getNext()**

- Inserta el par de palabras actual **current** al inicio de la lista **history**

- Obtiene la referencia al estado actual de **AnimatedList** utilizando la clave **historyListKey** y lo guarda en la variable **animatedList**

- Inserta un elemento nuevo en la animación de la lista **animatedList** en la posición **0** para mostrar el nuevo par de palabras en la parte superior de la lista

- Genera un nuevo par de palabras aleatorias y lo asigna a la variable current

- Notifica a los escuchadores **listeners** que el estado ha cambiado llamando al método **notifyListeners(),** lo que actualiza la interfaz de usuario

### **void toggleFavorite([WordPair? pair])**

Puede recibir un par de palabras opcional **pair** como argumento, pero si no se proporciona, utiliza el par de palabras actual **current**

- Si el par de palabras ya está en la lista de favoritos **(favorites),** lo elimina

- Si el par de palabras no está en la lista de favoritos, lo agrega

### **void removeFavorite(WordPair pair)**

Elimina un par de palabras de la lista de favoritos. Recibe el par de palabras que se va a eliminar como argumento.

- Elimina el par de palabras de la lista de favoritos **(favorites)**

- Notifica a los escuchadores que el estado ha cambiado llamando al método **notifyListeners(),** lo que actualiza la interfaz de usuario.


# Environment

- **SDK**:  **'>=2.19.4 <4.0.0'**


# Screenshots

