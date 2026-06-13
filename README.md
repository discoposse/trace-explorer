# Trace Explorer

Interactive replay of inference traces with synchronized views:

- **Fabric** — elastic schedule / KV / context layout
- **Streets** — flowing infrastructure topology
- **Stack** — hardware connectivity (Network, Storage, KV Cache, GPU, HBM)
- **Scatter** — metric scatter plot (time × latency × input depth)
- **Surface** — time × prefix-lane heat surface
- **UX dashboard** — TTFT, ITL, latency, throughput during playback

Supported trace formats: Mooncake JSONL and [RAGPulse](https://github.com/flashserve/RAGPulse) RAG workload traces.

## Live demo

https://discoposse.github.io/trace-explorer/

Use the **Trace** dropdown in the viewer — your selection persists across visits.

### Traces (2,000-request previews)

| Trace | Source | Link |
|-------|--------|------|
| Toolagent | Mooncake | [Open](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=mooncake_preview.json) |
| Conversation | Mooncake | [Open](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=conversation_preview.json) |
| Synthetic | Mooncake | [Open](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=synthetic_preview.json) |
| RAGPulse | [flashserve/RAGPulse](https://github.com/flashserve/RAGPulse) | [Open](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=ragpulse_preview.json) |

## Update the demo

From the [aiperf-toolkit](https://github.com/discoposse/ollama-aiperf-toolkit) repo:

```bash
./examples/trace-replay-elastic-viewer/publish-mooncake-previews.sh
cp -r docs/trace-explorer/* /path/to/trace-explorer/
cd /path/to/trace-explorer
git add -A && git commit -m "Update trace previews" && git push
```

Set `RAGPULSE_ROOT` if the RAGPulse clone is not at `~/Documents/RAGPulse`.

Export source: `export_mooncake_trace_layout.py` in aiperf-toolkit.