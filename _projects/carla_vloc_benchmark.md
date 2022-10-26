---
layout: project_page
title: Benchmarking Visual Localization for Autonomous Navigation
permalink: /carla_vloc_benchmark/
coauthors: [Suomela, Kalliola, Dag, Edelman, Kämäräinen]
affliations: Tampere University
venue: WACV 2023
arxiv: https://arxiv.org/abs/2203.13048
github: https://github.com/lasuomela/carla_vloc_benchmark 
supplementary: /assets/pdf/carla_vloc_supplementary.pdf
img: /assets/img/publication_preview/carla.gif
importance: 1
category:

---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carla_vloc_benchmark/carla.webp" title="Navigation with visual localization" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<br>


This work introduces a simulator-based benchmark for visual localization in the autonomous navigation context. The dynamic benchmark enables investigation of how variables such as the time of day, weather, and camera perspective affect the navigation performance of autonomous agents that utilize visual localization for closed-loop control. Our experiments study the effects of four such variables by evaluating state-of-the-art visual localization methods as part of the motion planning module of an autonomous navigation stack. The results show major variation in the suitability of the different methods for vision-based navigation. To the authors' best knowledge, the proposed benchmark is the first to study modern visual localization methods as part of a complete navigation stack.

<br>
## Benchmark

Visual localization is an active research topic in computer vision, but usually the localization methods are evaluated using static datasets and it is unclear how well the methods work when the visual localization output is used for closed-loop control. As a solution we present a benchmark which enables easy experimentation with different visual localization methods as part of a navigation stack. The platform enables investigating various factors that affect visual localization and subsequent navigation performance. The benchmark is based on the Carla autonomous driving simulator and our [ROS2 port](https://github.com/lasuomela/visual_robot_localization) of the [Hloc](https://github.com/cvg/Hierarchical-Localization) visual localization toolbox.


<div class="video-wrap">
  <div class="video-container">
    <iframe src="https://www.youtube.com/embed/qgFp68cqqd8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  </div>
</div>

<br>
<br>

## Experiments

We conducted experiments to determine how well different hierarchical visual localization methods cope with changes in gallery-to-query illumination, viewpoint and weather change.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carla_vloc_benchmark/experiment_conditions.png" title="Experiment conditions" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Examples of illumination (a-c), viewpoint (d-f), and weather changes (g-i).
</div>

<br>
## Results
<br>
Quantitative results on two metrics: localization recall rate and navigation failure rate.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carla_vloc_benchmark/failure_rate_figs.png" title="Failure rates" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Relationship of failure rate with illumination (a, b) and viewpoint change (c). Marker color indicates type for local features, shape for global features.
</div>

Combinations using SuperPoint achieve the lowest failure rates, and by a clear margin.
The best performing combination is that of SuperPoint and NetVLAD, followed by SuperPoint with Ap-GeM. This follows a general pattern: The local feature method seems to have more effect on the performance than the place recognition method. Of the two place recognition methods, NetVLAD provides a slightly better performance.


<br>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carla_vloc_benchmark/recall_rate_table.png" title="Recall rates" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The illumination experiment localization recall rates for the reference paths with thresholds T1 (≤0.25m, ≤2◦), T2 (≤0.50m,≤5◦) and T3 (≤5.00m, ≤10◦). Table with all values of k in the supplementary material.
</div>

<br>
<center>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carla_vloc_benchmark/failurerate_recall_correlation_Town01_accuracy_0.25m_2deg.png" title="Rate correlation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Relationship between the failure rate and recall rate T1 for the illumination experiments. Marker color and shape indicate feature type. See the supplementary material for the full set of figures.
</div>
</center>

SuperPoint, that achieves the lowest failure rates in different illumination conditions, also achieves the lowest failure rate for a given recall rate. There is a certain operation point, determined by odometry drift, after which changes in the recall rate become meaningless for autonomous navigation. Especially the second finding is interesting as it shows that visual localization performance needs to be sufficiently good in order to improve over wheel odometry only.
For Town01, the recall rate of a method at threshold T1 has to be above 60% to benefit navigation.
In other words, improving recall from 40% to 50% is almost meaningless while improvement from 60% to 70% is clearly significant.

<br>
### BibTex

    @inproceedings{
        title     = {Benchmarking Visual Localization for Autonomous Navigation},
        author    = {Suomela, Lauri and Kalliola, Jussi and Dag, Atakan and Edelman, Harry and Kämäräinen, Joni-Kristian},
        booktitle = {Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision (WACV)},
        year      = {2023},
        url = {https://arxiv.org/abs/2203.13048}
    }