---
layout: page
title: E-UMI
description: data acquisition device
img: assets/img/EUMI.jpg
importance: 5
category: work
---
受限于人力资源，ByteMini的数量无法大规模扩展，但模型对于数据的需求必须得到满足，因此有了E-UMI项目。该项目旨在快速采集机器人末端数据，是真机数据的补充。

E-UMI的开发也与ByteMini类似，从快速搭建版本到成熟版本，经历了多次迭代。

<style>
.eumi-flexrow { display: flex; flex-wrap: wrap; gap: 1rem; align-items: flex-start; justify-content: center; }
.eumi-flexrow figure { margin: 0; }
.eumi-flexrow img { height: 320px !important; width: auto !important; max-width: 100%; }
</style>

---

## E-UMI v1

快速搭建版本。

<div class="eumi-flexrow">
    {% include figure.liquid loading="eager" path="assets/img/eumiv1creo.jpeg" class="img-fluid rounded z-depth-1" caption="E-UMI v1: CAD Design" %}
    {% include figure.liquid loading="eager" path="assets/img/eumiv1.png" class="img-fluid rounded z-depth-1" caption="E-UMI v1: Prototype" %}
</div>

<div class="row">
    <div class="col-12 mt-3">
        <div class="embed-responsive embed-responsive-16by9">
            <video class="embed-responsive-item" controls preload="metadata" poster="/assets/img/eumiv1.jpg">
                <source src="/assets/video/eumiv1.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>
</div>

---

## E-UMI v2

为了准确反馈EUMI的位姿信息，加入了Quest手柄。

<div class="eumi-flexrow">
    {% include figure.liquid loading="eager" path="assets/img/eumiv2creo.jpeg" class="img-fluid rounded z-depth-1" caption="E-UMI v2: CAD Design" %}
    {% include figure.liquid loading="eager" path="assets/img/eumiv2.jpg" class="img-fluid rounded z-depth-1" caption="E-UMI v2: Prototype" %}
</div>

---

## E-UMI v3

由于Quest手柄安装位置离手腕旋转点太远，导致数据抖动，改变了Quest的安装位置。

<div class="eumi-flexrow">
    {% include figure.liquid loading="eager" path="assets/img/eumiv3creo.jpg" class="img-fluid rounded z-depth-1" caption="E-UMI v3: CAD Design" %}
    {% include figure.liquid loading="eager" path="assets/img/eumiv3.jpg" class="img-fluid rounded z-depth-1" caption="E-UMI v3: Prototype" %}
</div>

---

## E-UMI v4

根据采集任务，进一步调整Quest手柄安装位置，加入风扇等，整体更加可靠，稳定版本。

<div class="eumi-flexrow">
    {% include figure.liquid loading="eager" path="assets/img/eumiv4creo.jpg" class="img-fluid rounded z-depth-1" caption="E-UMI v4: CAD Design" %}
</div>

---

## E-UMI System

为了进一步与ByteMini相机对齐，使得数据更加有效，开发了一体化数据采集系统。

<div class="eumi-flexrow">
    {% include figure.liquid loading="eager" path="assets/img/eumisyscreo.jpg" class="img-fluid rounded z-depth-1" caption="E-UMI System: CAD Design" %}
    {% include figure.liquid loading="eager" path="assets/img/eumisys.png" class="img-fluid rounded z-depth-1" caption="E-UMI Integrated Data-collection System" %}
</div>
