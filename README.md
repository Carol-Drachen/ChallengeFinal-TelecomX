# ChallengeFinal-TelecomX
Modelo de predicción de evasión de clientes para TelecomX

# 🔔 Insight

Con base en el análisis de correlación y el análisis VIF, las variables que parecen tener mayor influencia en la tasa de abandono o evasión son:

  •	customer.tenure: con una correlación negativa significativa con la tasa de abandono (-0.35), lo que indica que los clientes con mayor antigüedad tienen menos probabilidad de abandonar el servicio.
  
•	internet.InternetService_Fiber optic: con una correlación positiva con la tasa de abandono (+0.31), lo que sugiere que los clientes con servicio de internet de fibra óptica tienen mayor probabilidad de abandonar el servicio.

•	account.PaymentMethod_Electronic check: También presenta una correlación positiva con la tasa de abandono (+0.30), lo que indica que los clientes que utilizan cheques electrónicos para pagar son más propensos a abandonar el servicio.

•	account.Contract_Two year: Presenta una fuerte correlación negativa con la tasa de abandono (-0.30), lo que implica que los clientes con contratos de dos años tienen menos probabilidad de abandonar el servicio, lo cual es previsible, ya que los contratos más largos indican un mayor compromiso.

•	internet.InternetService_No: Presenta una correlación negativa con la tasa de abandono (-0.23), lo que sugiere que los clientes que no utilizan internet tienen menos probabilidad de abandonar el servicio.

Si bien el análisis VIF ayudó a identificar y abordar problemas de multicolinealidad, también destacó las sólidas relaciones entre account.Charges.Monthly y account.Charges.Total con otras variables, en particular la permanencia del cliente. Incluso después de eliminar account.Charges.Total, account.Charges.Monthly aún presenta un VIF alto, lo que indica una alta correlación con otros predictores. Esto sugiere que los cargos mensuales son un factor significativo, pero su influencia está entrelazada con la antigüedad y otras variables relacionadas con el servicio.

Por otro lado, del modelo de regresión logística se obtuvo una precisión de 0.75 y un AUC ROC de 0.85. El informe de clasificación muestra una buena tasa de recuperación para la clase "Verdadero", es decir, identifica correctamente en un alto porcentaje la evasión o abandono, pero con menor precisión.

En contraste, con el modelo de bosque aleatorio se obtuvo una precisión ligeramente superior de 0.78, pero un AUC ROC inferior de 0.82, en comparación con la regresión logística. El informe de clasificación muestra una mayor precisión para la clase "Falso", es decir, clientes que no abandonan, con una precisión y recuperación más equilibradas para ambas clases.
La curva ROC confirma visualmente que el modelo de regresión logística tiene una capacidad ligeramente superior para distinguir entre clientes que abandonan y clientes que no abandonan en general (mayor AUC). Sin embargo, el bosque aleatorio presenta un mejor equilibrio entre precisión y recuperación. 

# 🥇 Conclusión

El objetivo de la empresa TelecomX es obtener un modelo que permita predecir la evasión de clientes, la elección del modelo con base en identificar el mayor número posible de clientes que abandonan el servicio reduciendo los falsos negativos, es el modelo de regresión logística, con una precisión del 75%.  
Además, algunas características del cliente como su antigüedad con el servicio, el tipo de servicio de internet, el método de pago y la duración del contrato (contratos de dos años) son los factores más importantes que influyen en la pérdida de clientes.
