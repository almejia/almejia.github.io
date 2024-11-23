---
layout: page
title: ELEctrocatalytic PHase-field Numerical modeling Tool (ELEPHANT)
description: MOOSE-based APP
img: assets/img/SOEC_cell.jpg
importance: 1
category: work
related_publications: true
---

This project is part of my doctorate degree research.
It involves modeling a working 2D Solid Oxide Electrolysis Cell for CO<sub>2</sub> reduction.
The model uses defect thermodynamics to determine the near-surface chemistry of dopants (Ce<sub>Gd</sub>), oxygen vacancies (V<sub>O</sub>) and electrons (Ce<sup>3+</sup>) point defects.

The model derivation relies on Variational Calculus as follows:

Semi-grand potential $$\Omega$$

$$\Omega(y,v,q,\phi;T)=\Phi (y(0),v(0),q(0),T)+\int (W(y,v,q,T)+\frac{1}{2}\beta _y|\nabla y|^2+\frac{1}{2}\beta _v|\nabla v|^2+\frac{1}{2}\beta _q|\nabla q|^2-\frac{1}{2}\epsilon _r\epsilon 0|\nabla \phi|^2+F\phi(2n_vv-n_yy-n_qq))dV$$

Euler-Lagrange Equations:

- $$ 2n_{yy}f_{yy}y+n_{yv}f_{yv}v+n_{yq}f_{yq}q+n_yRT(\ln \frac{y}{1-y-q} )-\beta _y\nabla^2y-F\phi n_y=0 $$
- $$ 2n_{vv}f_{vv}v+n_{yv}f_{yv}y+n_{vq}f_{vq}q+n_vRT(\ln \frac{v}{1-v} )-\beta _v\nabla^2v+2F\phi n_v=0 $$
- $$ 2n_{qq}f_{qq}q+n_{yq}f_{yq}y+n_{vq}f_{vq}v+n_qRT(\ln \frac{q}{1-y-q} )-\beta _q\nabla^2q-F\phi n_q=0 $$
- $$ -\epsilon _r\epsilon _0\nabla ^2\phi+F(2n_vv-n_yy-n_qq)=0 $$

For a kinetic model for the electrochemical potentials ($$\tilde{\mu}$$):

- $$u_qn_qq\nabla^2\mu _q=0$$
- $$u_vn_vv\nabla^2\mu _v=0$$



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/SOEC_cell.jpg" title="SOEC layout" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Solid Oxide Electrolysis Cell layout.
</div>

The electrochemical surface reaction for CO<sub>2</sub> reduction is given as follows:

$$\ce { CO_2 + V^{..}_O + 2Ce^'_{Ce} <=> CO + O^x_O + 2Ce^x_{Ce} } $$

Ads: $$\ce { CO_2 + O^x_O <=> CO_2-O } $$

Inc: $$\ce{ CO_2-O + V^{..}_O + 2Ce^'_{Ce} <=> CO + O^x_O + 2Ce^x_{Ce} } $$

Therefore, the reaction model can be described with the adsorption and incorporation intermediate reactions:

<div class="row">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Mesh.jpg" title="2D mesh" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Coverage.jpg" title="Coverage plot" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: an approximation of the 2D domain with a refined mesh for the surface. Right, Sequential Monte Carlo results showing the data coverage by the 'best' models.
</div>



<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
