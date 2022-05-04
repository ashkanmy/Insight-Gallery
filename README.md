

# Welcome to my homepage!
Here, I mostly write my opensource activities and explain the projects that I do.

### E-Lake

Let us imagine a stormy day where swimmers decided to swim in a lake. We need to watch them in case they need help! We do it by a drone that can always locate the swimmer postions and investigate if their behaviour is normal or if they need help.

But wait, data collection might be a hard task here. Finding a stormy lake and people who are willing to swim is not easy and always possible. So, let us establish our electronic lake (E-Lake)! First we need a texture representing a stormy kind of water. We find it as a free texture file below (thanks to Jorge Vasconez for providing this free texture available!) :

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/Water.jpg" width="1024" height="1024">
</p>

Next we need few people to swim in our lake. We get them from animated figures provided in [1]. It is freely available as one needs to just a create an account and use the available figures.

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/swim.gif" width="256" height="256">
</p>

Now let use see the result of embedding the animated swimmers into a 3D model of E-Lake using [2]:

<p align="center">
  <img src="https://github.com/ashkanmy/ashkanmy.github.io/blob/main/Figs/V-2.gif" width="1024" height="1024">
</p>

Next, we use [3] to see our swimmers are sometimes falsely classified as kite (green), bird (blue) and also person (white). This clearly reveals the Mask R-CNN pre-trained on MS COCO dataset [4] fails to watch our swimmers in our E-Lake.

### Future Plan
We aim to train Mask R-CNN so that it can correctly locate, classify and watch the swimmers enjoying our E-Lake!
### References
[1] www.mixamo.com

[2] https://clara.io/

[3] He, K., Gkioxari, G., Dollár, P., & Girshick, R. (2017). Mask R-CNN. arXiv. https://doi.org/10.48550/ARXIV.1703.06870

[4] https://cocodataset.org/#home



