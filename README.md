![IronHack Logo](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_d5c5793015fec3be28a63c4fa3dd4d55.png)

# Recurrent Neural Networks for Electricity Price Prediction
Predicción del precio de la electricidad en el mercado eléctrico español utilizando series temporales y redes neuronales recurrentes.

---

## Objetivo ✏

Conocer el precio de la electricidad con anterioridad puede permitir tanto a los consumidores minimizar sus gastos y a las empresas adaptar sus procesos de producción, gestionando mejor sus consumos. Por no hablar de la posibilidad de especular dentro del mercado eléctrico como una herramienta de trading. En todo caso un predictor del precio de la electricidad tiene una gran cantidad de aplicaciones tanto para usuarios particulares, como empresas.

---

## Introducción ✔

Dentro del coste total de la electricidad el coste de la energía solo representa un 35% del total. El 40% son costes regulados, es decir la parte de la factura eléctrica que corresponde a peajes de acceso a redes y se utilizan para pagar el mantenimiento y ampliación de las redes. El otro 25% son impuestos; el impuesto eléctrico que es del 5.1127% y se aplica tanto en el término de potencia como en el de consumo, el otro  es el IVA del 21% que se aplica sobre el impuesto eléctrico.

El precio de la energía se determina en el mercado diario. El mercado diario es el más importante, ya que su volumen de transacciones representa el 80% del consumo eléctrico de España y Portugal. Tiene lugar el día anterior al despacho de la energía y en él los agentes del mercado intercambian energía para cada hora del día siguiente. Es decir, hay 24 productos energéticos que se comercializan, uno por cada hora del día siguiente. Los agentes del mercado envían sus ofertas de compra y venta para cada una de las horas del
siguiente día. A partir de las ofertas recibidas se construyen las curvas de oferta y demanda para cada hora. El precio y el volumen de la energía intercambiado dependen del
cruce entre las curvas de oferta y demanda. Una vez se ha realizado la casación de las curvas se identifican las ofertas casadas que se convierten en compromisos de entrega de energía y se determina el precio de la energía para esa franja horaria.

El valor y forma de estas curvas viene determinado por una serie de factores diversas. La curva de oferta dependerá en primer lugar de la climatología por la disponibilidad de que entren las energías renovables (principalmente eólica y solar), el estado de las interconexiones internacionales y el precio de los combustibles fosiles, los derechos de emission del CO2 entre otros... Por otro lado la curva de compra vendrá determinada principalmente por la demanda de electricidad de las comercializadoras y grandes consumidores industriales.

---

## Construcción del Dataset  ⚙

Toda esta información mencionada anteriormente se puede descargar de manera pública desde la plataforma de Red Eléctrica de España (https://www.esios.ree.es/es) y desde cualquier plataforma de inversión con los históricos del gas y derechos de emisión del CO2 (https://www.investing.com/).

Por lo tanto las 18 variables que constituyen el dataset son, la generación por fuente de energía, los derechos de emisión del CO2, la demanda, el precio del gas, el saldo en la conexiones internacionales y el precio spot en el mercado español:

Hidráulica, Eólica, Solar Fotovoltaica, Solar Térmica,Otras Renovables, Residuos Renovables, Nuclear, Turbinación bombeo, Ciclo combinado, Carbón, Fuel-gas, Cogeneración, Residuos no renovables, EUA SPOT, Demanda real, TTF GAS, Saldo Interconexiones, Price

Todas estás variables afectan sobre el precio de la electricidad y por lo tanto tienen poder predictivo sobre ella.

El dataset abarcará de manera horaria desde el año 2015 al 2020.

Este dataset se dividirá en 3 partes: un dataset de entrenamiento con el 70% de los datos, un dataset de validación con el 20% de los datos y un dataset de testeo con el  10% restante.

---

## Descripción del Proyecto 📚

Durante el analisis exploratorio de datos se han detectado algunos outliers que se han eliminado y algunas variables con poco poder predtictivo, que han sido descartadas. 

El escalado de los datos se ha realizado mediante el método MinMaxScaler() de la libreria sklearn. El entrenamiento del escalado se ha realizado únicamente sobre los datos de entrenamiento pero la transformación se ha aplicado sobre los 3 datasets: el de entrenamiento, el de validación y el de testeo.

Al ser un analisis de series temporales para mayor simplicidad a la hora de trabajar con los distintos modelos, se ha utilizado una clase que se encarga de crear las ventanas de secuencias con el tamaño indicado. En este caso la ventana cuenta con un input de 168 y un label de 24, con un offset de 24, es decir se introducen secuencias de 7 días para predecir el día siguiente.

Todo el proyecto se ha realizado mediante Google Colab gracias su simplicidad de maneja y la posibilidad de utilizar GPUs para el entrenamiento de los modelos.

Los modelos testeados han sido basicamente los 5 siguientes:

* Multi Step Dense
* Single Step Convolutional 
* Single Step Recurrent
* Multi Step Convolutional
* Multi Step Recurrent
* Encoder Decoder LSTM

La métrica utilizada para su evaluación ha sido el Mean Absolute Error
