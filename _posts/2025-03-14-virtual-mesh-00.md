---
title: "Virtual Mesh 00: Reveal"
tags: [Meshlets, Virtual Mesh, Unity, URP]
style: fill
color: secondary
comments: false
description: "First version of my Nanite-inspired virtualized geometry solution for Unity"
---
I'm excited to share the first version of my Nanite-inspired virtualized geometry solution for Unity - Virtual Mesh!

What it can already do:
- Continuous LOD graph – meshlets are dynamically selected based on an error metric, ensuring smooth transitions with minimal LOD popping.
- GPU-driven culling – per-instance, per-meshlet, and even per-triangle culling to minimize vertex shader work.
- Fewer draw calls – instances with the same materials are drawn in a single draw call, even if their meshes differ.
- Streaming – mesh vertices and triangles get dynamically loaded/unloaded based on what is currently used and requested on the GPU.

Everything runs in Unity 6 + URP + DX11, with no strict hardware requirements (no need for Mesh Shader support).

The video showcases how enabling the plugin dramatically boosts performance in a 72 million triangle scene.

<html>
    <video controls width="750"><source src="/assets/blog/2025-03-14-virtual-mesh-00.md.mp4" type="video/mp4" /></video>
</html>

## Relevant

-- > [01: Occlusion Culling](/blog/virtual-mesh-01)