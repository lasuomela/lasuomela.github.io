---
layout: project_page
title: Synthetic vs. Real Training Data for Visual Navigation
permalink: /faint/
coauthors: [Suomela, Kuruppu Arachchige, Torres, Edelman, Kämäräinen]
affliations: Tampere University
venue: 'CoRL 2025 Workshop on Making Sense of Data in Robotics'
arxiv: ''
github: https://github.com/lasuomela/faint
huggingface_models: https://huggingface.co/collections/lauriasuo/faint-67b71dbaf71f1b648986f382
img: /assets/img/publication_preview/carla.gif
importance: 1
category:
---

<div class="row">
<div class="container lazy" data-lazy-placeholder="https://placehold.it/1321x583?text=Loading" data-lazy-error="https://placehold.it/1321x583?text=Error">
  <div class="col-12 mx-auto mt-3 mt-md-0">
    {% include figure.html path="assets/img/faint/pull_traj.png" title="Visual abstract" class="img-fluid z-depth-0" %}
  </div>
</div>
</div>

<hr>

<p style="text-align: justify;">
This paper investigates how the performance of visual navigation policies trained in simulation compares to policies trained with real-world data.
Performance degradation of simulator-trained policies is often significant when they are evaluated in the real world. However, despite this well-known sim-to-real gap, we demonstrate that simulator-trained policies can match the performance of their real-world-trained counterparts.
</p>

<p style="text-align: justify;">
Central to our approach is a navigation policy architecture that bridges the sim-to-real appearance gap by leveraging pretrained visual representations and runs real-time on robot hardware.
Evaluations on a wheeled mobile robot show that the proposed policy, when trained in simulation, outperforms its real-world-trained version by 31% and the prior state-of-the-art methods by 50% in navigation success rate. Policy generalization is verified by deploying the same model onboard a drone.
</p>

<p style="text-align: justify;">
Our results highlight the importance of diverse image encoder pretraining for sim-to-real generalization, and identify on-policy learning as a key advantage of simulated training over training with real data.
</p>

<hr>
<div class="video-wrap">
  <div class="video-container">
    <iframe src="https://www.youtube.com/embed/ow7qDv9u51U?si=mtRiDVLhJLdyO7ZB" title="Presentation" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </div>
</div>

<hr>


### BibTex

    @InProceedings{suomela2025synthetic,
      title={Synthetic vs. Real Training Data for Visual Navigation},
      author={Suomela, Lauri and Kuruppu Arachchige, Sasanka and Torres, German F. and Edelman, Harry and Kämäräinen, Joni-Kristian}
      journal={arXiv:},
      year={2025}
    }

