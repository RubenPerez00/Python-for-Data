# 🐍Python for Data

En este repositorio he puesto lo más importante a mi criterio sobre este proyecto. Gracias al tema anterior de Python he ido cogiendo más soltura a la hora de hacer los ejercicios, cada vez entiendo mucho mejor el código, pero , en este proyecto me ha faltado ver mejor la parte de los gráficos ya que en el curso no se toca, directamente se menciona en el proyecto que hay que usarlos y la verdad que al principio me ha costado un poco... He intentando aprenderlo con videos y con la IA ya que son una herramienta más para poder realizar los trabajos.


## 📊 Tecnologías Utilizadas

* **Lenguaje**: Python 3.10+

* **Análisis y Manipulación de Datos**: pandas, numpy

* **Visualización**: matplotlib, seaborn

* **Lectura de archivos**: Jupyter Notebooks / Visual Studio Code


## 📋 Sobre el proyecto y los Notebooks

Para no mezclarlo todo en un único archivo eterno y poder trabajar con orden, dividí el proyecto en tres notebooks distintos según cada fase:

### 🔍 1. Carga y Exploración Inicial (01_carga_y_exploracion.ipynb)

Aquí simplemente me dediqué a mirar los datos con calma antes de tocar nada, para saber a qué me enfrentaba:

Juntar las piezas iniciales: Cargué el historial de llamadas (bank-additional.csv, con 43.000 registros) y las tres pestañas por años (2012, 2013 y 2014) del Excel customer-details.xlsx.

Buscar qué fallaba: Fui revisando qué columnas sobraban, dónde había nulos, si existían duplicados y por qué algunos números aparecían como texto.

### 🧹 2. Limpieza y Transformación (02_limpieza_de_datos.ipynb)

Esta fue la parte más entretenida y donde más tiempo invertí, porque de dejar bien esta base dependía todo lo demás:

Quitar ruido y arreglar formatos: Borré columnas que no aportaban nada (Unnamed: 0, latitude, longitude) y pasé a formato numérico los indicadores económicos (cons.price.idx, cons.conf.idx, euribor3m).

"Pelearme" con las fechas: Como las fechas venían en español, las procesé para poder extraer de forma limpia tanto el mes (contact_month) como el año (contact_year).

Decidir qué hacer con los nulos y datos raros: En lugar de borrar filas a lo loco, etiqueté los textos vacíos como 'desconocido', rellené las edades faltantes con la mediana, ajusté los indicadores económicos por periodo, traté el código 999 en pdays (que indicaba que no hubo contacto previo) y eliminé llamadas sin sentido de duración 0.

Cruzar toda la información: Uní las pestañas de clientes de 2012 a 2014 y las crucé con el registro de campañas, dejando listo el archivo bank_customers_limpio.csv (42.996 filas y 31 columnas).

### 📈 3. Análisis Descriptivo y Visualización (03_analisis_descriptivo.ipynb)

Ya con los datos limpios y ordenados, tocaba hacerse preguntas y ver qué contaban los números:

¿Cuánta gente dice que sí? (y): Vi que, de los 42.996 contactos válidos, solo 4.844 clientes acabaron contratando el depósito (un 11,27 % de éxito frente a un 88,73 % que dijo que no).

Entender el perfil de las llamadas: Saqué métricas y gráficos para ver cómo se comportaban variables clave como la edad de los clientes, cuánto duraban las llamadas, cuántas veces se les contactaba o cómo influía el momento económico.
