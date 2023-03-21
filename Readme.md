# Ultra Cool Time Tracker 😎
Una herramienta simple pero poderosa para llevar un registro del uso del tiempo

Ideal para cualquier persona que quiera llevar un registro detallado pero sencillo de usar de su tiempo, ya sea en el trabajo en el hogar

> "Esta herramiento es Ultra Cool 😎"
>
> ---*Su creador*

## Herramientas Usadas
----
HTML, Vanilla JavaScript y CSS de Bootsrap 5 (con un poco de inline CSS aquí y allá)

## Uso
----------
Tú solamente escribe el nombre de lo que vas a hacer, selecciona la categoría, añade una descripción si quieres y haz clic en "Create", *el Time Tracker llevará el registro de cuanto tiempo ocupas, cuando empezó y cuando terminó*

Si te tomas un descanso y no quieres que se sume al tiempo de lo que hiciste, presiona "Pause" debajo del cronómetro y se detendrá. Cuando vuelvas, solo presiona "Start". Todo sin tener que empezar una nueva actividad

En la tabla, puedes ver las actividades que ya has terminado, su fecha de inicio termino y cuanto te tomaron. Al igual que una suma de cuantas actividades tienes registradas y su tiempo

Si deseas eliminar estos registros, solo haz clic en "Clear History" y confirma el prompt

## Disclaimer
----------
Este es un proyecto para uso personal hecho en mi tiempo libre. Así que si te parece engorrosa la (👉°ヮ°👉) "integración" 👈(°ヮ°👈)😆😂 con Notion, o si opinas que mi código no es profesional, recuerda que lo más importante es que funciona de manera confiable

## Histórico
----------
Esta herramienta está diseñada para llevar un registro a corto plazo (Yo mantengo una semana), si quieres guardar un registro más extenso, tenemos una (👉°ヮ°👉) "integración" 👈(°ヮ°👈)😆😂 con [Notion](https://www.notion.so/), solo sigue los siguientes pasos:

1. Crea en tu Workspace de Notion una tabla con las siguientes columnas:
    - "Name" (Esta es el titulo que viene por defecto)
    - "Description" (Tipo Texto)
    - "Start Date" (Tipo Fecha)
    - "Working time" (Tipo Número)
    - "End Date" (Tipo Fecha)
   
    (A la tabla le puedes poner el nombre que quieras, pero te recomendamos "Ultra Cool Time Tracker" 😉)  

2. Abre el Bloc de Notas (😮), escribe cualquier cosa y guardalo como "TimeTracker.csv" (o el nombre que prefieras, pero que termine en .csv) en esa carpeta regalona de tu computador donde tienes todo a mano

Los pasos anteriores solo los tienes que seguir una vez. Cuando quieras llevar el historico del Ultra Cool Task Tracker a Notion sigue los siguientes:

1. Haz clic derecho en "TimeTracker.csv" (el archivo que creaste en tu computador) y selecciona "Abrir con..." > "Bloc de Notas"
2. Borra el contenido anterior
3. En Ultra Cool Task Tracker, haz clic en "Copy History"
4. En "TimeTracker.csv", haz Ctrl+V (O Clic Derecho > "Pegar" si eres uno de esos que prefiere el mouse)
5. Guarda y cierra "TimeTracker.csv"
6. En Notion, en la tabla que creaste anteriormente, haz clic en los 3 puntos horizontales de la esquina superior derecha. Selecciona "Merge with CSV"
7. En la pantalla que se abra, selecciona "TimeTracker.csv" y luego "Abrir", debería aparecer más registros en la tabla
8. En Ultra Cool Task Tracker, haz clic en "Clear History" y luego en "Aceptar". Esto eliminará los registros en la herramienta, para que la siguiente vez que los subas a Notion no se duplique nada

"Et voilà" Los registros del Ultra Cool Task Tracker quedarán guardados en Notion

### Observaciones
----------
Las columnas que creamos en la tabla de Notion son las estrictamente necesarias, pero puedes crea otras si quieres. Te sugiero las siguientes:

- **Total Mins**: Esta es una columna de fórmula que muestra el tiempo total entre la fecha de inicio y la de término. Puedes crearla para llevar una comparación precisa del tiempo disponible y el usado (Working Time) en la actividad. La fórmula es la siguiente:
```javascript
dateBetween(prop("End Date"), prop("Start Date"), "minutes")
```
- **Work Percent**: Esta es una columna de fórmula que muestra el porcentaje del tiempo disponible que usaste en la actividad. Útil para comparar de un vistazo cuanto tiempo del total disponible usaste en la actividad. La fórmula es la siguiente:  

Si creaste la columna "Min Totales":
```javascript
round((prop("Working Time") * 100) / prop("Min Totales"))
```
Si no la creaste
```javascript
round((prop("Working Time") * 100) / dateBetween(prop("End Date"), prop("Start Date"), "minutes"))
```

## FAQs
-----
**¿Se pierde la información si refresco la página?**  
Claro que no: La actividad actual y el histórico se guardan en el Local Storage. Si tenías una actividad en curso y refrescaste la página y ves el cronómetro en cero y detenido, esto es normal, solo haz clic en "Start" y seguirá donde quedó (Eso sí, vas a tener que poner el nombre, categoría y descripción de nuevo)
Estoy trabajando para que mantenga el nombre, la categoría y descripción aún cuando refresque, pero como no es mi prioridad puede que no vean ninguna actualización pronto ¯\_(ツ)_/¯

**¿Qué tan confiable es?**  
Al momento de escribir esto, llevo usándolo más de un mes al mismo tiempo que el cronómetro que viene con Windows, y no hay diferencias

**¿Hay problema si no tengo la pestaña visible?**  
Si la pestaña no está visible en el Chrome, el cronómetro sigue andando igual de confiable

**¿Dónde puedo recompensar tanta genialidad?**  
Solo déjame una estrella y sé un poco mejor cada día 🤗 