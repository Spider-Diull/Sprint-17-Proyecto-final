# Sprint-17-Proyecto-final

# Condiciones de la asignación principal

Al operador de telecomunicaciones Interconnect le gustaría poder pronosticar su tasa de cancelación de clientes. Si se descubre que un usuario o usuaria planea irse, se le ofrecerán códigos promocionales y opciones de planes especiales. El equipo de marketing de Interconnect ha recopilado algunos de los datos personales de sus clientes, incluyendo información sobre sus planes y contratos.

### Servicios de Interconnect

Interconnect proporciona principalmente dos tipos de servicios:

1. Comunicación por teléfono fijo. El teléfono se puede conectar a varias líneas de manera simultánea.
2. Internet. La red se puede configurar a través de una línea telefónica (DSL, *línea de abonado digital*) o a través de un cable de fibra óptica.

Algunos otros servicios que ofrece la empresa incluyen:

- Seguridad en Internet: software antivirus (*ProtecciónDeDispositivo*) y un bloqueador de sitios web maliciosos (*SeguridadEnLínea*).
- Una línea de soporte técnico (*SoporteTécnico*).
- Almacenamiento de archivos en la nube y backup de datos (*BackupOnline*).
- Streaming de TV (*StreamingTV*) y directorio de películas (*StreamingPelículas*)

La clientela puede elegir entre un pago mensual o firmar un contrato de 1 o 2 años. Puede utilizar varios métodos de pago y recibir una factura electrónica después de una transacción.

### Descripción de los datos

Los datos consisten en archivos obtenidos de diferentes fuentes:

- `contract.csv` — información del contrato;
- `personal.csv` — datos personales del cliente;
- `internet.csv` — información sobre los servicios de Internet;
- `phone.csv` — información sobre los servicios telefónicos.

En cada archivo, la columna `customerID` (ID de cliente) contiene un código único asignado a cada cliente. La información del contrato es válida a partir del 1 de febrero de 2020.

## Plan de trabajo propuesto

### Cargar datos y bibliotecas

- Inspeccionar conjuntos de datos para preprocesamiento, EDA e ingeniería de características

### Procesar datos

- Llevar a cabo los planes indicados anteriormente con cada dataframe.
- Combinar los dataframes individuales en customerID para crear un dataframe con todos los datos.

### Análisis exploratorio

- Historgrama de tiempo antes de que canceleren los contratos.
- Gráfico de barras que muestra los contratos cancelados en contra a los vigentes y los tipos de contrato.
- Gráfico de barras que muestra los contratos cancelados en contra a los vigentes y los tipos de pago.
- Diagramas de caja y bigotes que muestran la distribución de:
    - Cargos mensuales de clientes que han cancelado contrato.
    - Cargos totales de clientes que han cancelado contrato.
    - Cargos mensuales de clientes vigentes.
    - Cargos totales de clientes vigentes.
- Gráfico de barras que muestra la información personal de los clientes han cancelado contrato en contra a los clientes vigentes a traves de los valores totales por:
    - Género
    - si estan jubilados
    - si estan en pareja
    - si son dependientes
- Gráfico de barras que muestra el tipo de contrato en relación con la información personal a traves de los valores totales por:
    - Género
    - si estan jubilados
    - si estan en pareja
    - si son dependientes
- Gráfico de barras para los clientes que cancelaron contrato y estan vigentes en relación con el tipo de servicio de Internet.
- Gráfico de barras para el tipo de contrato en relación con el tipo de servicio de Internet.
- Gráfico de barras que muestra los servicios de Internet y las multiples lineas telefonicas de los clientes que cancelaron contrato y estan vigentes a traves de los valores totales por:
    - Seguridad en línea
    - Copia de seguridad en línea
    - Protección de dispositivos
    - Soporte técnico
    - Transmisión de TV
    - Transmisión de películas
    - Multiples lineas telefonicas
- Gráfico de barras que muestra el tipo de contrato de los clientes con los servicios de Internet y multiples lineas telefonicas a traves de los valores totales por:
    - Seguridad en línea
    - Copia de seguridad en línea
    - Protección de dispositivos
    - Soporte técnico
    - Transmisión de TV
    - Transmisión de películas
    - Multiples lineas telefonicas

### Ingeniería de características.

- Crear nuevas columnas con el objetivo de:
    - Determinar meses restantes de los contratos.
    - Determianar el promedio de cargos por cliente y cargos adicionales.
    - Determinar precio por servicio
- Aplicar codificacion de datos.

### Entrenamiento de modelos.

- Se dividirán conjuntos de entrenamiento, validación y prueba en una proporción de 3:1:1.
- La división se estratificará en función de la rotación para garantizar una distribución uniforme entre los dos conjuntos.
- Las características serán casi todas las columnas, con la excepción de 'customer_id', 'begin_date', 'end_date','contract_duration_months'.
- El objetivo será la columna contract_cancelled.
- Entrenar y evaluar modelos de arbol de decisiones, bosque aletorio y regresion logistica.
- La puntuación utilizada será AUC-ROC con un objetivo de 0,90 o superior.
- Seleccionar el modelo con mejor rendimiento en función de AUC_ROC.

### Conclusión

- Se resumirán los hallazgos de la EDA.
- El modelo seleccionado será recomendado.
