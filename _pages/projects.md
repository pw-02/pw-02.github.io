---
layout: page
title: research
permalink: /research/
description:
nav: true
nav_order: 2
---

Selected research projects, ongoing work, and systems contributions.

<div class="research-project">
  <div class="research-project-header">
    <div>
      <span class="research-kicker">LLM inference · HPC · resource management</span>
      <h3>OPSERVE</h3>
      <p class="research-project-subtitle">Opportunistic LLM inference over fragmented GPU capacity in HPC systems</p>
    </div>
  </div>

  <p>
    Batch-scheduled supercomputers can leave substantial GPU capacity temporarily unused when free resources do not match the requirements of queued jobs. OPSERVE explores how LLM inference can turn that fragmented capacity into useful serving capacity without assuming the resources will remain available.
  </p>

  <p>
    The system combines a stable pool of persistent workers with opportunistically acquired transient workers. It adapts workers between colocated, prefill-only, and decode-only roles as both workload demand and resource availability change, while a shared KV-cache layer preserves completed prefill state when transient workers are reclaimed.
  </p>

  <div class="research-results">
    <div><strong>9.81%</strong><span>of operational node-hours observed as unallocated in a year-long Polaris trace</span></div>
    <div><strong>1.5–2.1×</strong><span>lower p95 end-to-end latency versus static prefill/decode allocation when both sustain load</span></div>
    <div><strong>14.3×</strong><span>lower observed p95 latency under overload in the evaluated scenarios</span></div>
  </div>

  <div class="research-tags">
    <span>LLM serving</span><span>KV cache</span><span>prefill/decode</span><span>malleable systems</span><span>HPC</span>
  </div>
</div>

<div class="research-project">
  <div class="research-project-header">
    <div>
      <span class="research-kicker">Training systems · data pipelines · scheduling</span>
      <h3>BatchFlow</h3>
      <p class="research-project-subtitle">Benefit-aware data pipeline allocation and batch reuse for multi-job training</p>
    </div>
    <a class="research-project-link" href="https://github.com/pw-02/BatchFlow" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
  </div>

  <p>
    Modern training jobs can stall not because accelerators are slow, but because data retrieval and preprocessing cannot supply mini-batches quickly enough. The problem becomes harder when multiple jobs compete for shared CPU, storage, memory, and network resources.
  </p>

  <p>
    BatchFlow treats data preparation as a shared cluster service. It uses online profiling to direct a finite pool of data workers toward the jobs that benefit most, while coordinating prefetching and cache management so prepared mini-batches can be reused across concurrent jobs.
  </p>

  <div class="research-results">
    <div><strong>3.8×</strong><span>higher aggregate training throughput in the evaluated multi-job workloads</span></div>
    <div><strong>2.1×</strong><span>higher cost efficiency relative to the evaluated prior systems</span></div>
    <div><strong>Shared</strong><span>worker allocation, prefetching, and reusable mini-batch caching across training jobs</span></div>
  </div>

  <div class="research-tags">
    <span>training systems</span><span>data pipelines</span><span>batch reuse</span><span>resource allocation</span><span>PyTorch</span>
  </div>
</div>
