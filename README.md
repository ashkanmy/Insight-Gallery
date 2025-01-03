
# Welcome to my Insight-Gallery. 
## Under continuous update!
Here, I mostly write my activities and explain what I enjoy to think and to do  . . . 



##   E-Lake 

Let us imagine a stormy day where swimmers decide to swim in a lake. We need to watch them in case they need help! We do it by a drone that can always locate the swimmer postions and investigate if their behaviour is normal or if they need help.

But wait, data collection might be a hard task here. Finding a stormy lake and people who are willing to swim is not easy and always possible. So, let us establish our electronic lake (E-Lake)! First we need a texture representing a stormy kind of water. We find it as a free texture file below (thanks to Jorge Vasconez for providing this free texture available!) :

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/Water.jpg" width="512" height="512">
</p>

Next we need few people to swim in our lake. We get them from animated figures provided in [1]. It is freely available as one needs to just a create an account and use the available figures.

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/swim.gif" width="128" height="128">
</p>

Now let use see the result of embedding the animated swimmers into a 3D model of E-Lake using [2]:

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/V-2.gif" width="512" height="512">
</p>

Next, we use [3] to see our swimmers are sometimes falsely classified as kite (green), bird (blue) and also person (white). This clearly reveals the Mask R-CNN pre-trained on MS COCO dataset [4] fails to watch our swimmers in our E-Lake.

### Qt GUI

However, to realise the whole pipeline as a product we aim to train also YOLOs and see if they perform quciker as Mask R-CNN. Below shows a suitable GUI developed by Qt and C++.

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/GUI.png" width="512" height="512">
</p>


### Future Plan
We aim to train YOLOs as well as Mask R-CNN to have a comparison on tracking and also speed of the swimmer localisation and classification while they enjoy our E-Lake! 

In a real life scenario, a drone will run the desired Mask R-CNN and flies over a real lake to watch the swimmers if they need help or performing suspicious pattern of movements. This is critical to avoid swimmers to sink.

### References
[1] www.mixamo.com

[2] https://clara.io/

[3] He, K., Gkioxari, G., Dollár, P., & Girshick, R. (2017). Mask R-CNN. arXiv. https://doi.org/10.48550/ARXIV.1703.06870

[4] https://cocodataset.org/#home


##   StyleGAN2 swimmers 

Another aspect of my work is about boosting existing data sets. As collecting images from the swimmer is technically a challenging task. One solution is to use StyleGAN2 [1] and boost the Swimmer data set [2] from the Kaggle. Below few created synthetic samples are shown to be realistically visualise the style of swimmers, namely back stroke, breast stroke, free and butterfly styles.
<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/fakes000500.png" width="1024" height="1024">
</p>

Below, a set of limited original images used to produce above shown synthetic images using [1].
<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/img00000000.png" width="128" height="128">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/img00000003.png" width="128" height="128">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/img00000006.png" width="128" height="128">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/img00000009.png" width="128" height="128">
</p>


### References
[1] https://github.com/NVlabs/stylegan2

[2] https://www.kaggle.com/datasets/3122f8d0287f6094b28d66e36b216b3a278eae858b6c7cb10f821010825397a2


##   Temperature prediction in 3D printing 

Our aim in this project was to simulate the movement of the laser-nozzle during the printing process and within a laser bed powder fusion (LBPF) context [1]. A controlled movement of the nozzle will help us to predict the temperature gradient during the printing process hence avoiding the final product to be deformed because of uneven temperature distribution across the printing board. 

To steer the nozzle moves, initially one can use a predefined trajectory, namely row-wise, zig-zag or a square-based approach as shown in below figure.
<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/Trajs.png">
</p>

However, a more optimal solution that we adopted was to apply the travel salesman problem (TSP) to minimise a cost function framed based on the temperature gradient:
<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/Cost.png" width="512" height="64">
</p>

with $u_m$ and $\nabla u_m$ are the temperature and its gradient values concerning the $m$ movement of the nozzle. Here, $u_g$ is the desired temperature on particular sub-area of the printing domain. In this project, we show that adopting TSP results to an optimum cost value, compared to other pre-defined technologies:

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/CompareCosts.png" width="296" height="256">
</p>

Below figure shows few instances where TSP deciding the $5$ adjacent movement of the nozzle.
<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/_TSPTemp-1.png" width="296" height="256">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/_TSPTemp-2.png" width="296" height="256">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/_TSPTemp-3.png" width="296" height="256">
</p> 
Note that, all temperature in above heat-maps produced by partial differential equation toolbox of Matlab are in Kelvin measure.

### References

[1] Strauch, A., Hardes, C., Röttger, A., Uhlenwinkel, V., Baqerzadeh Chehreh, A.,
Theisen, W., Walther, F., Zoch, H, Laser additive manufacturing of hot work tool steel
by means of a starting powder containing partly spherical pure elements and ferroalloys.
Procedia CIRP. 94, pp. 46–51 (2020)


## Cloud detection

In contrast to AI based methods, we opt to devised a very quick, explainable and canonical approach to detect cloud existence based on the optical remote sensing images provided by multi-spectral images obtianed by Sentinel-2. 

The used dataset PASTIS [1] in this approach is composed of $2433$ one square kilometer-patches (See Fig. below) each of size $128\times 128$ taken from the French metropolitan territory for which sequences of satellite observations are assembled into a four-dimensional spatio-temporal tensor. 

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20000.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20001.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10022.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10025.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20002.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20003.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10019.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20004.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10007.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20005.png" width="64" height="64">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10013.png" width="64" height="64">
</p> 

Though we only use one band for now, but certainely there is a potential of fusing other useful spectral bands to come out with a more effective method. We took a subset of PASTIS and visualized them in two dimensional space being clustered using t-SNE [2]. A clear distinction is observed in two dimension among the dimensionally reduced images 

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/t-SNEResults.png" width="400" height="400">
</p> 
few of which are shown below taken from each cluster to belong either to the cloud shown as first row or the agricultural parcels and water visualized in second row.

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20000.png" width="128" height="128">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20003.png" width="128" height="128">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/0__S2_20010.png" width="128" height="128">
</p> 
<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10007.png" width="128" height="128">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10013.png" width="128" height="128">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/1__S2_10014.png" width="128" height="128">
</p> 

### References
[1] Vivien Sainte Fare Garnot and Loic Landrieu. Panoptic segmentation of satellite image time series with convolutional temporal attention networks. ICCV, 2021.

[2] T. Tony Cai and Rong Ma. Theoretical foundations of t-sne for visualizing high-dimensional clustered data, 2022.


##   The Convex / Concave ambiguity in Shape-from-Shading 

<p align="center">
</p> 

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/22.png.png" width="400" height="200">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/23.png" width="400" height="200">
</p> 

<p align="center">
</p> 

The (left) convex hemisphere $u\left(x,y\right)=-\sqrt{R^2-x^2-y^2}$ and the (right) concave hemisphere $u\left(x,y\right)=+\sqrt{R^2-x^2-y^2}$ with an arbitrarily chosen point $\left(x_1,y_1,u\left(x_1,y_1\right)\right)$ within the third quarter located on thier surfaces. An orthographic camera looks from infinity along the positive side of the $z$ axis and observes the same angle $\theta$ among the light reflected from the surfaces and their corresponding incident normals $\left(\nabla u, 1\right)$ both at the chosen points. In case the surface is Lambertian, the reflected irradiance light from the both convex and concave surfaces at $\left(x_1,y_1,u\left(x_1,y_1\right)\right)$ will be the same and ambigous to reveal the geometry of the surface at those point [1].

### References
[1] Michael Breuß, Ashkan Mansouri Yarahmadi, and Douglas W. Cunningham. The Convex-Concave Ambiguity in Perspective Shape from Shading, proceedings of the OAGM workshop on medical image analysis. 2018.

##   E-Mail summarization using LLM / C#

We used the Enron email dataset contains approximately 500,000 emails generated by employees of the Enron Corporation [1]. A suitable GUI using C# was developed and the Ollama 
as the background was adopted to use open source large language models. User can see a list of E-Mails and use a LLM to provide an abstract version of the E-Mail body to the user.


<p align="center">
</p> 

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/AutoEmail-2.png" width="800" height="400">
</p> 

<p align="center">
</p> 

The application is very much useful, in case a user needs to read a huge volume of E-Mails in daily bases.

### References
[1] https://www.cs.cmu.edu/~./enron/

![Visitor Count](https://komarev.com/ghpvc/?username=ashkanmy&color=blue)

