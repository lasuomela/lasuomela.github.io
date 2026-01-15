---
layout: project_page
title: Data scaling for navigation in unknown environments
permalink: /navigation_scaling/
coauthors: [Suomela, Takahata, Kuruppu Arachchige, Edelman, Kämäräinen]
affliations: Tampere University
venue:
arxiv: https://arxiv.org/abs/2601.09444
github: https://github.com/lasuomela/NavigationScaling
huggingface_models: 
img: /assets/img/publication_preview/carla.gif
importance: 1
category:
images:
  slider: true
---

<div class="row">
<div class="container lazy" data-lazy-placeholder="https://placehold.it/1321x583?text=Loading" data-lazy-error="https://placehold.it/1321x583?text=Error">
  <div class="col-12 mx-auto mt-3 mt-md-0">
    {% include figure.html path="assets/img/nav_scaling/erc_pull-V4.jpg" title="Visual abstract" class="img-fluid z-depth-0" avoid_scaling=true zoomable=true %}
  </div>
</div>
</div>

<p style="text-align: justify;">
Generalization of imitation-learned navigation policies to environments unseen in training remains a major challenge. We address this by conducting the first large-scale study of how data quantity and data diversity affect real-world generalization in end-to-end, map-free visual navigation. Using a curated 4,565-hour crowd-sourced dataset collected across 161 locations in 35 countries, we train policies for point goal navigation and evaluate their closed-loop control performance on sidewalk robots operating in four countries, covering 125 km of autonomous driving.
</p>

<p style="text-align: justify;">
Our results show that large-scale training data enables zero-shot navigation in unknown environments, approaching the performance of policies trained with environment-specific demonstrations. Critically, we find that data diversity is far more important than data quantity. Doubling the number of geographical locations in a training set decreases navigation errors by ~15%, while performance benefit from adding data from existing locations saturates with very little data. We also observe that, with noisy crowd-sourced data, simple regression-based models outperform generative and sequence-based architectures.
</p>

<p style="margin-bottom:50px;"></p>
<h2 style="text-align: center;">Training data</h2>
<hr>

<div style="width: 100%; height: auto; display: flex; justify-content: center; align-items: center;">
  <iframe 
     src="https://www.google.com/maps/d/u/0/embed?mid=15EaDB-MD6LDCvBxxnSTD-NHvJGz8xWg&ehbc=2E312F&noprof=1"
     width="100%"
      height="480"
     frameborder="0"
     style="border:0;">
  </iframe>
</div>

<p></p>
<p style="text-align: justify;">
We extract clean demonstrations from a raw 8,000 hour crowd-sourced dataset, and cluster the resulting 4,565 hours of navigation data into 161 distinct locations around the world. The locations span 35 countries and diverse environments, including urban, suburban, park, campus, and rural settings.
</p>
<p></p>
<div class="row g-0 justify-content-center">
  <div class="col-10 px-0 justify-content-center align-items-center">
      {% include video.html loading="lazy" path="assets/img/nav_scaling/mosaic_level_63.mp4" caption="Examples from a subset of the training locations." class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
  </div>
</div>

<p style="margin-bottom:50px;"></p>
<h2 style="text-align: center;">Test locations</h2>
<hr>

<div class="swiper-wrap">
  <swiper-container 
    keyboard="true" 
    navigation="true" 
    pagination="true" 
    pagination-clickable="true" 
    pagination-dynamic-bullets="true" 
    rewind="true" 
    slides-per-view="2"
    space-between="10">
    <swiper-slide>
      {% include figure.html loading="lazy" path="assets/img/nav_scaling/Wuhan.jpeg" caption="Wuhan, China" class="img-fluid rounded z-depth-1" %}
    </swiper-slide>
    <swiper-slide>
      {% include figure.html loading="lazy" path="assets/img/nav_scaling/Kisumu.jpeg" caption="Kisumu, Kenya" class="img-fluid rounded z-depth-1" %}
    </swiper-slide>
    <swiper-slide>
      {% include figure.html loading="lazy" path="assets/img/nav_scaling/PortLouis.jpeg" caption="Port Louis, Mauritius" class="img-fluid rounded z-depth-1" %}
    </swiper-slide>
    <swiper-slide>
      {% include figure.html loading="lazy" path="assets/img/nav_scaling/Selebi.jpeg" caption="Selebi-Phikwe, Botswana" class="img-fluid rounded z-depth-1" %}
    </swiper-slide>
  </swiper-container>
</div>

<p style="text-align: justify;">
We test our policies in 4 distinct locations around the world. These locations were not included in the training data, allowing us to evaluate the generalization capabilities of the navigation policies.
</p>

<p style="margin-bottom:50px;"></p>
<h2 style="text-align: center;">Policy deployment examples</h2>
<hr>

<div class="swiper-wrap">
  <swiper-container 
    keyboard="true" 
    navigation="true" 
    pagination="true" 
    pagination-clickable="true" 
    pagination-dynamic-bullets="true" 
    rewind="true" 
    slides-per-view="1">
    <swiper-slide>
      <div style="width: 100%; height: auto; justify-content: center; align-items: center; margin-bottom: 40px;">
      {% include video.html loading="lazy" path="assets/img/nav_scaling/WuhanClip.mp4" caption="" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
      </div>
    </swiper-slide>
    <swiper-slide>
      {% include video.html loading="lazy" path="assets/img/nav_scaling/KisumuClip.mp4" caption="" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </swiper-slide>
    <swiper-slide>
      {% include video.html loading="lazy" path="assets/img/nav_scaling/PortLouisClip.mp4" caption="" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </swiper-slide>
    <swiper-slide>
      {% include video.html loading="lazy" path="assets/img/nav_scaling/SelebiClip.mp4" caption="" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </swiper-slide>
  </swiper-container>
</div>

<p style="text-align: justify;">
The policies were deployed on the <a href="https://shop.frodobots.com/collections/earth-rovers/products/earthroverzero"> Earth Rover Zero</a> robots. The robots streamed sensor observations to a remote desktop machine running policy inference, and the computed control commands were sent back to the robots over a 4G connection.
</p>

<p style="margin-bottom:50px;"></p>
<h2 style="text-align: center;">Data scaling results</h2>
<hr>

<p style="text-align: justify;">
We trained policies with subsets of the total dataset, varying both the <b>number of training locations</b> and the <b>amount of training data per location</b>.
</p>

<div class="row g-0 justify-content-center">
  <div class="col-6 px-0 justify-content-center align-items-center">
    {% include figure.html path="assets/img/nav_scaling/fixed_totH_success@1.png" zoomable=true caption="<i>Success rate</i> ($\uparrow$) as function of number of train locations, for <b>fixed amounts of total training data</b>." class="img-fluid rounded z-depth-0" %}
  </div>
  <div class="col-6 px-0 justify-content-center align-items-center">
    {% include figure.html path="assets/img/nav_scaling/fixed_NLoc_success@1.png" zoomable=true caption="<i>Success rate</i> ($\uparrow$) as function of training data per location, for <b>fixed numbers of training locations</b>." class="img-fluid rounded z-depth-0" %}
  </div>
</div>

<p style="text-align: justify;">
The results indicate that navigation performance scales well with the number of training locations, while benefit from increasing the amount of data per location saturates early, below the range we considered in our experiments. This highlights the importance of data diversity for generalization in visual navigation.
</p>

<div class="row g-0 justify-content-center">
  <div class="col-9 px-0 justify-content-center align-items-center">
    {% include figure.html path="assets/img/nav_scaling/scaling_law_Hours per Location.png" zoomable=true caption="Power law fits and correlation coefficients $r$ for <i>Total Dataset Size = 128H</i> and <i>Hours per Location = 16H</i> on a log-log scale." class="img-fluid rounded z-depth-0" %}
  </div>
</div>

<p style="text-align: justify;">
Fitting a model $Y = \beta \cdot X^{\alpha}$ to the results, we find that the navigation <i> Failure Rate = 1 - Success Rate </i> follows the number of training locations with a power law relationship. Substituting the coefficients from the left panel, doubling the number of locations decreases failures by $1-\frac{Y(2X)}{Y(X)}=1-2^{-0.229}\approx15\%$.
</p>

<p style="margin-bottom:50px;"></p>
<h2 style="text-align: center;">Training with the full dataset</h2>
<hr>

<p style="text-align: justify;">
We also experimented with training on the full dataset. We compared the policy trained with the full train set (<b>Zero-Shot</b>) to a policy trained with both the full train set and additional in-domain data from the test locations (<b>Scale + in-domain</b>), and environment-specific policies trained only with data from each test location (<b>In-domain only</b>).
</p>

<div class="row g-0 justify-content-center">
    {% include figure.html path="assets/img/nav_scaling/generalization_success@1.png" zoomable=true avoid_scaling=true caption="Policies trained with large-scale data achieve higher success rates compared to environment-specific policies. The zero-shot policy almost matches the policy that incorporates both large-scale data and data from the test environments." class="img-fluid rounded z-depth-0" %}
</div>

<p></p>
<h2 style="text-align: center;">Full runs</h2>
<hr>

<p style="text-align: justify;"> The videos demonstrate one complete navigation run from each test location. </p>

<div class="swiper-wrap">
  <swiper-container 
    keyboard="true" 
    navigation="true" 
    pagination="true" 
    pagination-clickable="true" 
    pagination-dynamic-bullets="true" 
    rewind="true" 
    slides-per-view="1">
    <swiper-slide>
    <div style="width: 100%; height: auto; justify-content: center; align-items: center; margin-bottom: 40px;">
      <iframe width="100%" height="315" src="https://www.youtube.com/embed/6SUp4tYGesY?si=iB71b1QFlTKAfo5h" caption="Wuhan Clip" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
    </swiper-slide>
    <swiper-slide>
      <iframe width="100%" height="315" src="https://www.youtube.com/embed/yAQTY0YstA0?si=3e4WL0vPUqkBzUQK" title="Kisumu Clip" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </swiper-slide>
    <swiper-slide>
      <iframe width="100%" height="315" src="https://www.youtube.com/embed/kDpC0kWpXVc?si=MMggsn0ifIsf6V_p" title="Port Louis Clip" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </swiper-slide>
    <swiper-slide>
      <iframe width="100%" height="315" src="https://www.youtube.com/embed/DGeEMgLRzcI?si=pzPRmBSoqeRZbnU6" title="Selebi Clip" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </swiper-slide>
  </swiper-container>
</div>


<p style="margin-bottom:50px;"></p>
### BibTex

    @misc{suomela2026data_scaling,
      title={Data Scaling for Navigation in Unknown Environments},
      author={Suomela, Lauri and Takahata, Naoki and Kuruppu Arachchige, Sasanka and Edelman, Harry and Kämäräinen, Joni-Kristian},
      journal={arXiv:2601.09444},
      year={2026},
    }

