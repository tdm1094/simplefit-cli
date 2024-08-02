# Aplicación CLI para [SimpleFit](https://www.simplefit.org/2024/01/home.html)

Aplicación Java hecha con el framework
[Spring Shell](https://docs.spring.io/spring-shell)

## Referencia de ejercicios

- Día 1: Tantas rondas como sea posible en 20 minutos.
- Día 2: 5 rondas en el menor tiempo posible con 3 minutos de descanso entre
  cada uno (no contar descansos para tiempo final)
- Día 3: Hacer una ronda en el menor tiempo posible. Contar los tiempos de
  descanso. Si se hace en menos de 5 minutos se pasa al siguiente nivel. Si se
  tarda más de 30 minutos se retrocede un nivel.

## Funcionalidades

- Tener una base de datos SQLite con todos los niveles y cantidad de ejercicios
  que figuran en la página.
- Al comenzar la aplicación, preguntar qué día es (1, 2 o 3) y qué nivel.
- Tras seleccionar el día y nivel, mostrar en pantalla los ejercicios a
  realizar.
- Por debajo de los ejercicios a realizar mostrar:
  - Si es día 1: Temporizador de 20 minutos frenado.
    - Al presionar barra espaciadora comienza la cuenta regresiva.
    - Al presionar barra espaciadora nuevamente, se registra el tiempo que llevó
      la primera ronda y comienza a registrar el tiempo que se tarda el primer
      descanso.
    - Al presionar nuevamente la barra espaciadora, se registra el tiempo del
      primer descanso y comienza el tiempo de la segunda ronda.
    - Se repite el proceso hasta finalizar los 20 minutos.
    - Una vez finalizado, se muestra en pantalla las estadísticas en formato
      tabla de cuánto tiempo se le asignó a cada ronda y descanso.
    - Se almacena en base de datos el registro de tiempo de cada ronda y
      descanso.
  - Si es día 2: Cronómetro para medir ronda y temporizador de 3 minutos para
    medir descansos.
    - Al presionar barra espaciadora comienza el cronómetro.
    - Al presionar barra espaciadora nuevamente, el cronómetro frena y registra
      el tiempo para la primera ronda.
    - Inmediatamente comienza un temporizador de 3 minutos.
    - Tras la cuenta regresiva, inmediatamente comienza el cronómetro para la
      segunda ronda.
    - Se repite el proceso hasta finalizar las 5 rondas.
    - Una vez finalizado, se muestra en pantalla de cuánto tiempo se tardó cada
      ronda.
    - Se almacena en base de datos el registro de tiempo de cada ronda y cuánto
      tiempo fue asignado al descanso.
  - Si es día 3: Cronómetro para medir única ronda
    - Al presionar barra espaciadora comienza el cronómetro.
    - (Opcional) Al presionar barra espaciadora nuevamente se indica que en el
      tiempo transcurrido se terminó con la primer serie de ejercicios. Se
      repite dos veces más para tener una métrica más fina de qué tiempo llevó
      cada bloque de ejercicios.
    - Al presionar por última vez barra espaciadora, el cronómetro se frena.
    - Si el tiempo total es menor a 5 minutos, se avisa que se ha pasado al
      siguiente nivel.
    - Si el tiempo total es mayor a 30 minutos, se avisa que se debe retroceder
      un nivel.
- Para cada día almacenado en base de datos, también se debe registrar la fecha
  y horario del entrenamiento.
- (Opcional) Opción para exportar el histórico de entrenamientos a formato .csv
  para poder abrirlo en aplicaciones como Excel y realizar gráficos.
- (Opcional) Opción para exportar el histórico de entrenamientos a formato JSON
  para importarlo en otra instancia de la aplicación.
- (Opcional) Opción para importar un histórico de entrenamientos desde un
  archivo JSON.
