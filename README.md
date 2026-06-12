# Trace Explorer

Interactive replay of inference traces with three synchronized views:

- **Fabric** — elastic schedule / KV / context layout
- **Streets** — flowing infrastructure topology
- **Stack** — hardware connectivity (Network, Storage, KV Cache, GPU, HBM)
- **UX dashboard** — TTFT, ITL, latency, throughput during playback

The first supported trace format is Mooncake toolagent JSONL; more formats will follow.

## Live demo

https://discoposse.github.io/trace-explorer/

Direct links:

- [Streets view](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=mooncake_preview.json&view=topology)
- [Hardware stack](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=mooncake_preview.json&view=stack)

## Update the demo

From the [aiperf-toolkit](https://github.com/discoposse/ollama-aiperf-toolkit) repo:

```bash
./examples/trace-replay-elastic-viewer/publish-pages.sh /path/to/trace.jsonl
cp -r docs/trace-explorer/* /path/to/trace-explorer/
cd /path/to/trace-explorer
git add -A && git commit -m "Update trace preview" && git push
```

Preview uses 2,000 requests (~4 MB). Export source: `export_mooncake_trace_layout.py` in aiperf-toolkit.