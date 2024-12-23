В данной работе решалась задача поиска похожих изображений по фотографиям лиц. За основу берётся обученный VAE, которому на инференсе подаётся одно фото для извлечения латентного представления. 
В этом латентном пространстве выбирается несколько изображений, которые наиболее близки к латентному вектору, подаваемому на вход VAE. В качестве метрики в латентном пространстве используется метрика 
Минковского между латентными векторами, которая является обобщением евклидовой и манхэттенской метрик. Между двумя точками $x$ и $y$ она вычисляется по формуле:

$$
d(x,y)=\left[\sum_{i=1}^{n}\lvert x_i - y_i \rvert^{p}\right]^{\frac{1}{p}},
$$

где $x_i, y_i~-~i$-ые координаты точек $(x, y) \in \mathbb{R}^{n}$; $n$ $-$ размерность латентного пространства; $p$ $-$ порядок расстояния Минковского. 

Сами реконструкции с VAE получились довольно размазанные, что неудивительно, поскольку архитектура довольно простая. Предпринимались попытки усложнения архитектуры, но они не принесли значимых результатов. Однако стоит отметить, что даже таких реконструкций вполне достаточно, чтобы идентифицировать похожие изображения. Результаты инференса визуализированы в конце ноутбука: входное изображение и нескольких реконструированных латентных векторов, которые по метрике наиболее близки к входному сэмплу. 
