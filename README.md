# Recurrent Neural Networks for Electricity Price Prediction
Predicción del precio de la electricidad en el mercado eléctrico español utilizando series temporales y redes neuronales recurrentes.

## Objetivo

Conocer el precio de la electricidad con anterioridad puede permitir tanto a los consumidores minimizar sus gastos y a las empresas adaptar sus procesos de producción, gestionando mejor sus consumos. Por no hablar de la posibilidad de especular dentro del mercado eléctrico como una herramienta de trading. En todo caso un predictor del precio de la electricidad tiene una gran cantidad de aplicaciones tanto para usuarios particulares, como empresas.

## Introducción

Dentro del coste total de la electricidad el coste de la energía solo representa un 35% del total. El 40% son costes regulados, es decir la parte de la factura eléctrica que corresponde a peajes de acceso a redes y se utilizan para pagar el mantenimiento y ampliación de las redes. El otro 25% son impuestos; el impuesto eléctrico que es del 5.1127% y se aplica tanto en el término de potencia como en el de consumo, el otro  es el IVA del 21% que se aplica sobre el impuesto eléctrico.

El precio de la energía se determina en el mercado diario. El mercado diario es el más importante, ya que su volumen de transacciones representa el 80% del consumo eléctrico de España y Portugal. Tiene lugar el día anterior al despacho de la energía y en él los agentes del mercado intercambian energía para cada hora del día siguiente. Es decir, hay 24 productos energéticos que se comercializan, uno por cada hora del día siguiente. Los agentes del mercado envían sus ofertas de compra y venta para cada una de las horas del
siguiente día. A partir de las ofertas recibidas se construyen las curvas de oferta y demanda para cada hora. El precio y el volumen de la energía intercambiado dependen del
cruce entre las curvas de oferta y demanda. Una vez se ha realizado la casación de las curvas se identifican las ofertas casadas que se convierten en compromisos de entrega de energía y se determina el precio de la energía para esa franja horaria.

El valor y forma de estas curvas viene determinado por una serie de factores diversas. La curva de oferta dependerá en primer lugar de la climatología por la disponibilidad de que entren las energías renovables (principalmente eólica y solar), el estado de las interconexiones internacionales y el precio de los combustibles fosiles, los derechos de emission del CO2 entre otros... Por otro lado la curva de compra vendrá determinada principalmente por la demanda de electricidad de las comercializadoras y grandes consumidores industriales.

## Construcción del Dataset

Toda esta información mencionada anteriormente se puede descargar casi toda de manera pública desde la plataforma de Red Eléctrica de España (https://www.esios.ree.es/es) y desde cualquier plataforma de inversión con los históricos del gas y derechos de emisión del CO2 (https://www.investing.com/).

Por lo tanto las 18 variables que constituyen el dataset son, la generación por fuente de energía, los derechos de emisión del CO2, la demanda, el precio del gas, el saldo en la conexiones internacionales y el precio spot en el mercado español:

Hidráulica, Eólica, Solar Fotovoltaica, Solar Térmica,Otras Renovables, Residuos Renovables, Nuclear, Turbinación bombeo, Ciclo combinado, Carbón, Fuel-gas, Cogeneración, Residuos no renovables, EUA SPOT, Demanda real, TTF GAS, Saldo Interconexiones, Price

El dataset abarcara toda esta información de manera horario desde el año 2015 al 2020.

## Descripción del Proyecto

Mediante el analisis exploratorio de datos se eliman cualquier tipo de outlier detectado 

## Recurrent-Neural-Networks-for-Electricity-Price-Prediction

## Recurrent-Neural-Networks-for-Electricity-Price-Prediction
