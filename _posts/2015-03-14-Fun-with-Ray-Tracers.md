---
title: Fun with Ray Tracers
layout: post
img: /img/ray_tracer.jpg
---

For my last assignment of computer graphics we were tasked with creating a ray tracer program. Initially it seemed very tedious but as I got into coding and actually understanding 
what was going on it quickly became one of my favourite projects I've ever done in university. So lets get to what Ray Tracing is all about:


###What is Ray Tracing?
Ray tracing is a technique for generating an image by tracing the path of light through pixels in an image plane and simulating the effects of its encounters with objects. Basically we define a set of objects and light sources and the ray tracer measures the path the light takes as it illuminates those objects. Although it is very computationally heavy, ray tracing uses a realistic simulation of lighting over other rendering methods. This ensures special effects such as shadows, reflection and refraction are a natural result of the algorithm.


###How to do this:

We need to breakdown ray tracing into different parts:

1) Define eye and view point of the image.

2) Shading Model: In my program I use the [Phong shading model](http://en.wikipedia.org/wiki/Phong_shading) to compute how an object will be shaded depending on its properties.

3) Calculating Intersections: We need a way to calculate intersections of rays with objects.

4) Recursive Ray Tracing: On every intersection 3 new rays are formed (Reflection, Refraction and Shadow) to compute these effects.

The basic concept is that we shoot one ray per pixel from the eye and find the closest object blocking the path of that ray. Then using the material properties and the effect of
the defined light sources we compute the shading of this object. 


###Special Effects:

1) Reflection: On each intersection with an object we compute a reflected ray and then calculate the shading of the pixel by taking into account the light sources and
the reflected ray.

2) Refraction: Similar to reflection but we compute a refracted ray, it differs in it's direction and it is more complicated to compute.

3) Shadows: On each intersection we compute a ray towards the light source, if the ray intersects with anything then we say that intersection point will be in the shadow.


###Examples:

Below are several pictures created by the ray tracer program:

![alt text](/img/glossyReflection.bmp "glossy reflection")
![alt text](/img/anti-aliasing1.bmp "anti aliasing")

![alt text](/img/depthoffield.bmp "depth of field")
![alt text](/img/softShadows.bmp "soft shadows")


###Ohh cool, some source code:
[Source code](https://github.com/faizanrashid/ray-tracer.git)

















