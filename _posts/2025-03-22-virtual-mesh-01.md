---
title: "Virtual Mesh 01: Occlusion Culling"
tags: [Meshlets, Virtual Mesh, GPU Culling, Occlusion Culling, Unity, URP]
style: fill
color: secondary
comments: false
description: "Virtual Mesh Status Update: Occlusion Culling"
---

This week I have implemented Two-Pass Occlusion culling, which skips rendering geometry covered by other objects. The algorithm consists of the following steps:
1. (First Pass) Draw the geometry visible in the previous frame.
2. Generate a Hierarchical Depth Buffer (a.k.a. HDB/HZB/depth pyramid).
3. (False Negative Pass) Draw the geometry, which was occluded in the first pass but is visible now according to the newly generated HDB.

The described algorithm is executed fully on GPU and is 100% conservative, which means objects will not be popping in and out during quick camera movement.

The video demonstrates how enabling occlusion culling cuts triangle count of the main view by 25% and improves its rendering time by about 20%. There's a small performance overhead for culling and HDB generation, but it is worth it for most games.

<html>
    <video controls width="750"><source src="/assets/blog/2025-03-22-virtual-mesh-01.md.mp4" type="video/mp4" /></video>
</html>

## Relevant

[00: Reveal](/blog/virtual-mesh-00) < -- > [02: Triangle Culling](/blog/virtual-mesh-02)