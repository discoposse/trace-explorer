# Trace Explorer

Interactive replay of inference traces with synchronized views:

- **Fabric** — elastic schedule / KV / context layout
- **Streets** — flowing infrastructure topology
- **Stack** — hardware connectivity (Network, Storage, KV Cache, GPU, HBM)
- **Scatter** — metric scatter plot (time × latency × input depth)
- **Surface** — time × prefix-lane heat surface
- **UX dashboard** — TTFT, ITL, latency, throughput during playback

The first supported trace format is Mooncake JSONL; more formats will follow.

## Live demo

https://discoposse.github.io/trace-explorer/

### Traces (2,000-request previews)

| Trace | Link |
|-------|------|
| Toolagent | [Open](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=mooncake_preview.json) |
| Conversation | [Open](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=conversation_preview.json) |
| Synthetic | [Open](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=synthetic_preview.json) |

Example views (conversation trace):

- [Streets](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=conversation_preview.json&view=topology)
- [Stack](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=conversation_preview.json&view=stack)
- [Scatter](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=conversation_preview.json&view=scatter)
- [Surface](https://discoposse.github.io/trace-explorer/mooncake3d.html?data=conversation_preview.json&view=surface)

## Update the demo

From the [aiperf-toolkit](https://github.com/discoposse/ollama-aiperf-toolkit) repo:

```bash
./examples/trace-replay-elastic-viewer/publish-mooncake-previews.sh
cp -r docs/trace-explorer/* /path/to/trace-explorer/
cd /path/to/trace-explorer
git add -A && git commit -m "Update trace previews" && git push
```

Single trace:

```bash
./examples/trace-replay-elastic-viewer/publish-pages.sh /path/to/trace.jsonl output_preview.json
WRITE_INDEX=1 ./examples/trace-replay-elastic-viewer/publish-pages.sh ...  # also refresh index.html
```

Export source: `export_mooncake_trace_layout.py` in aiperf-toolkit.