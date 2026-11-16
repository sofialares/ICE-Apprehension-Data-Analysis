<p align="center">
  <img src="banner.jpg" width="100%">
</p>

# ICE-Apprehension-Data-Analysis
Autores: 
Sofia Del rosario Lares sanchez,
Juan Camilo Villarreal Olarte,
David Santiago Uscategui Zubieta.

Dataset:
https://github.com/deportationdata/ice/raw/refs/heads/main/data/arrests-latest.parquet

Diapositivas:
https://canva.link/5ddcdfjjn9d0c4e

Video:


Colab:
https://colab.research.google.com/drive/1Y1UCFWeE0yRHs5zPBPCCNcVNy39Nd2Dd?usp=sharing

Repositorio:
https://github.com/sofialares/ICE-Apprehension-Data-Analysis

proyecto de Machine Learning para analizar y predecir resultados relacionados con registros de aprehensiones de ICE

    Los datos utilizados en este proyecto provienen del Deportation Data Project (https://deportationdata.org/), una iniciativa 
    pública de investigación que recopila y sistematiza registros administrativos de operaciones migratorias de la 
    administración estadounidense.

    Los datos originales fueron recolectados por la U.S. Immigration and Customs Enforcement (ICE), agencia federal responsable 
    de la ejecución de leyes migratorias en Estados Unidos. ICE mantiene registros detallados de todas las aprehensiones, 
    procesamientos de casos, y remociones que realiza.

**Motivación**

    1). Predecir el programa por el que sera procesado una persona detenida por el ICE (final_program)
    2). Estimar cuntos dias pueden transcurrir desde el arresto hasta la salida del pais (days_until_departure)


**Problema**

    La información histórica de los arrestos realizados por el ICE permite analizar los casos registrados, 
    pero no ofrece directamente una estimación anticipada de su duración ni del programa por el que serán procesados. 
    Esto plantea la necesidad de identificar patrones en los datos que permitan estimar ambos resultados.


**Objetivo**

    Aplicar un modelo de machine learning para obtener las predicciones de nuestros targets

Resultados de los modelos en Clasificacion
  
              Modelo  Accuracy  Precision Macro  Recall Macro  F1 Macro    
    0  Decision Tree    0.8172           0.7078        0.6288    0.6592
    1  Random Forest    0.8239           0.7356        0.6126    0.6531
    2            SVM    0.7718           0.5933        0.6273    0.6078
    3     GaussianNB    0.4860           0.4580        0.5042    0.3576

<Figure size 1200x600 with 1 Axes><img width="1189" height="590" alt="image" src="https://github.com/user-attachments/assets/79be4fe6-996a-431b-b7db-7dc1eaed5c23" />

Resultados de los modelos en Regresion

tenemos nuestro mejor modelo regresor evaluado en multiples intervalos

    Intervalo	  Rango de días reales que tiene el caso.
    Registros	  Cantidad de casos que pertenecen a ese intervalo.
    MAE	          Error absoluto medio, expresado en días.
    RMSE	      Raíz del error cuadrático medio, expresada en días.
    Aceptacion_7	  Porcentaje de predicciones cuyo error es de máximo 7 días.
    Aceptacion_14	  Porcentaje de predicciones cuyo error es de máximo 14 días.
    Aceptacion_30	  Porcentaje de predicciones cuyo error es de máximo 30 días.
    Aceptacion_60	  Porcentaje de predicciones cuyo error es de máximo 60 días.

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Modelo</th>
      <th>Intervalo</th>
      <th>Registros</th>
      <th>MAE</th>
      <th>RMSE</th>
      <th>Aceptacion_7</th>
      <th>Aceptacion_14</th>
      <th>Aceptacion_30</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>SVR</td>
      <td>0-30 dias</td>
      <td>27429</td>
      <td>11.69</td>
      <td>15.00</td>
      <td>37.86</td>
      <td>66.06</td>
      <td>95.67</td>
    </tr>
    <tr>
      <th>1</th>
      <td>SVR</td>
      <td>31-90 dias</td>
      <td>12472</td>
      <td>20.49</td>
      <td>26.09</td>
      <td>22.96</td>
      <td>43.22</td>
      <td>75.06</td>
    </tr>
    <tr>
      <th>2</th>
      <td>SVR</td>
      <td>91-180 dias</td>
      <td>4229</td>
      <td>82.88</td>
      <td>87.82</td>
      <td>0.21</td>
      <td>0.64</td>
      <td>1.51</td>
    </tr>
    <tr>
      <th>3</th>
      <td>SVR</td>
      <td>181-365 dias</td>
      <td>1649</td>
      <td>202.47</td>
      <td>209.94</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.06</td>
    </tr>
    <tr>
      <th>4</th>
      <td>SVR</td>
      <td>Mas de 365 dias</td>
      <td>319</td>
      <td>361.98</td>
      <td>364.49</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Random Forest</td>
      <td>0-30 dias</td>
      <td>27429</td>
      <td>15.55</td>
      <td>24.39</td>
      <td>45.02</td>
      <td>63.97</td>
      <td>83.24</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Random Forest</td>
      <td>31-90 dias</td>
      <td>12472</td>
      <td>24.38</td>
      <td>31.96</td>
      <td>18.48</td>
      <td>36.63</td>
      <td>69.11</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Random Forest</td>
      <td>91-180 dias</td>
      <td>4229</td>
      <td>49.10</td>
      <td>58.35</td>
      <td>6.79</td>
      <td>14.54</td>
      <td>31.26</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Random Forest</td>
      <td>181-365 dias</td>
      <td>1649</td>
      <td>151.05</td>
      <td>164.32</td>
      <td>0.61</td>
      <td>1.15</td>
      <td>2.67</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Random Forest</td>
      <td>Mas de 365 dias</td>
      <td>319</td>
      <td>301.84</td>
      <td>309.30</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Decision Tree</td>
      <td>0-30 dias</td>
      <td>27429</td>
      <td>16.06</td>
      <td>26.05</td>
      <td>45.62</td>
      <td>63.93</td>
      <td>82.33</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Decision Tree</td>
      <td>31-90 dias</td>
      <td>12472</td>
      <td>25.95</td>
      <td>35.53</td>
      <td>17.98</td>
      <td>35.65</td>
      <td>68.53</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Decision Tree</td>
      <td>91-180 dias</td>
      <td>4229</td>
      <td>52.94</td>
      <td>62.43</td>
      <td>5.91</td>
      <td>11.87</td>
      <td>28.28</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Decision Tree</td>
      <td>181-365 dias</td>
      <td>1649</td>
      <td>155.36</td>
      <td>169.42</td>
      <td>0.42</td>
      <td>1.21</td>
      <td>3.27</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Decision Tree</td>
      <td>Mas de 365 dias</td>
      <td>319</td>
      <td>301.99</td>
      <td>312.30</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.31</td>
    </tr>
  </tbody>
</table>
</div>

## Puntos de comparación

  Como los targets son distintos, no tiene sentido comparar accuracy contra MAE directamente. 
  Comparamos cosas que sí son equivalentes:
  
  Porcentaje de predicciones aceptables en una misma escala: en el classifier una predicción es aceptable si acierta
  la clase, y en el regresor si el error es de máximo 7, 14 o 30 días. Se prueban varias tolerancias porque el resultado
  del regresor depende de qué tan estricta sea.

## Conclusion; Mejores modelos 

    Para predecir el programa (`final_program`) elegimos el Decision Tree, con F1 Macro de 0.659 y accuracy de 0.817 en validación,
    y resultados consistentes en test. Para estimar los días hasta la salida (`days_until_departure`) elegimos el Random Forest, 
    con MAE de 27.8 días, RMSE de 50.7 y R² de 0.35.
