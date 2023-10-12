---
layout: project_page
title: PlaceNav&#58; Topological Navigation through Place Recognition
permalink: /placenav/
coauthors: [Suomela, Kalliola, Edelman, Kämäräinen]
affliations: Tampere University
arxiv: https://arxiv.org/abs/2309.17260
github: https://github.com/lasuomela/placenav
img: /assets/img/publication_preview/carla.gif
importance: 1
category:

---

<div class="row">
<div class="container lazy" data-lazy-placeholder="https://placehold.it/1321x583?text=Loading" data-lazy-error="https://placehold.it/1321x583?text=Error">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/placenav/output_mosaic_website.webp" title="Navigation with visual localization" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
</div>

<hr>

<br>
<h2 style="text-align: center;">Abstract</h2>

<p style="text-align: justify;">
Recent results suggest that splitting topological navigation into robot-independent and robot-specific components improves navigation performance by enabling the robot-independent part to be trained with data collected by different robot types. However, the navigation methods are still limited by the scarcity of suitable training data and suffer from poor computational scaling.
</p>

<p style="text-align: justify;">
In this work, we present PlaceNav, which subdivides the robot-independent part into navigation-specific and generic computer vision components. We utilize visual place recognition for the subgoal selection of the topological navigation pipeline. 
</p>

<p style="text-align: justify;">
This makes subgoal selection more efficient and enables leveraging large-scale datasets from non-robotics sources, increasing training data availability.
Bayesian filtering, enabled by place recognition, further improves navigation performance by increasing the temporal consistency of subgoals.
Our experimental results verify the design and the new model obtains a 76% higher success rate in indoor and 23% higher in outdoor navigation tasks with higher computational efficiency.
</p>

<br>


<hr>
<h2 style="text-align: center;">Navigation examples</h2>
<div class="video-wrap">
  <div class="video-container">
    <iframe src="https://www.youtube.com/embed/g-MZbf68Dlc" title="PlaceNav navigation examples" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </div>
</div>

<hr>

<h2 style="text-align: center;">System</h2>
<p style="text-align: justify;">
Topological navigation enables a robot to navigate without metric maps. The robot first localizes by retrieving a 'subgoal' image from a recorded previous traversal of the route. Then, it navigates to the subgoal using an image-based goal-reaching policy.
</p>
<br>
<div class="row justify-content-center">
    <div class="col-sm d-flex justify-content-center align-items-center">
        {% include figure.html path="assets/img/placenav/toponav_idea.webp" title="Navigation with visual localization" class="img-fluid rounded z-depth-0" %}
    </div>
</div>
<br>
<p style="text-align: justify;">

PlaceNav conducts the subgoal selection using place recognition. This is more efficient compared to the previous approaches, and increases the amount of available training data by enabling the use of large-scale datasets from non-robotics sources.

</p>
<br>
<div class="row">
<div class="container lazy" data-lazy-placeholder="https://placehold.it/1321x583?text=Loading" data-lazy-error="https://placehold.it/1321x583?text=Error">
    <div class="col-9 mx-auto mt-3 mt-md-0">
        {% include figure.html path="assets/img/placenav/opener_latent.png" title="Place recognition pipeline" class="img-fluid z-depth-0" %}
    </div>
    <div class="caption">
        Visual place recognition finds which map image \(I_s\) was captured closest to the robot's observation \(I_t\) by efficient matching of image embeddings \(\mathbf{z}\).
    </div>
</div>
</div>



<br>
### BibTex

    @InProceedings{Suomela_2023_Placenav,
    author    = {Suomela, Lauri and Kalliola, Jussi and Edelman, Harry and Kämäräinen, Joni-Kristian},
    title     = {PlaceNav: Topological Navigation through Place Recognition},
    booktitle = {arXiv pre-print},
    year      = {2023},
    url       = {https://arxiv.org/abs/2309.17260},
    }

