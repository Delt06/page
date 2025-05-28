---
title: "Virtual Mesh 02: Triangle Culling"
tags: [Meshlets, Virtual Mesh, GPU Culling, Triangle Culling, Unity, URP]
style: fill
color: secondary
comments: false
description: "Virtual Mesh Status Update: Triangle Culling"
---

This week I have finished implementing compute-based Triangle Culling. Instead of relying on hardware to drop small or out of frustum primitives, the meshlet pipeline allows this to be done before rendering has even started. This reduces the pressure on both programmable and fixed-function vertex processing units, which in turn may give a nice performance win.

Virtual Mesh currently supports the following methods of per-primitive culling:
- Backface culling.
- Culling off-screen triangles.
- Culling triangles in front of the near frustum plane.
- Small triangle culling: dropping triangles that wouldn't produce any fragments.

Performance-wise, this results in a whopping 67% speed-up for shadows and 15% for the main view. While my solution benefits from triangle culling on this particular hardware, the outcome is dependent on mesh shader usage, GPU vendor/architecture, and many other factors.

<html>
    <video controls width="85%"><source src="/assets/blog/2025-04-03-virtual-mesh-02.md.mp4" type="video/mp4" /></video>
</html>

## Other Posts

[01: Occlusion Culling](/blog/virtual-mesh-01) < -- > Coming Soon