# ActiveVLN engine demo media

Public presentation assets for EmbodiRun v0.1. `activevln_engines_1x.mp4` is the final 4.9-second, original-speed edit, with one shared EmbodiRun container for EmbodiInfer, SGLang and vLLM. Its poster comes from the published MP4.

The panes show actual simulator frames using their measured monotonic timestamps. Only elapsed task time and current geodesic distance to goal are displayed. This is one R2R validation-unseen episode (17), not a dataset-wide performance result. Each selected run has 49 primitive steps and 11 policy calls and stops 0.673 m from the goal. Elapsed times are 1.979 s (EmbodiInfer), 2.736 s (SGLang) and 2.682 s (vLLM).

All runs use the same ActiveVLN Qwen2.5-VL 3B checkpoint, BF16, batch 1 and greedy decoding on one RTX 4090. Timing includes inference, communication and simulation after one warmup episode; it excludes service startup, scene loading and video encoding.

SGLang uses the first recorded rerun after restarting its service, selected before measuring the reruns, not the fastest of three. The original run stopped 2.458 m away; all three reruns reached 0.673 m. Cross-startup variation remains unexplained. All original recordings remain in the experiment archive outside this media repository.

The video uses the measured experimental service adapters; packaging the reusable vLLM service has separate software validation.
