# Trace Explorer

Interactive 3D replay of enterprise AI inference traces.

**Live:** https://discoposse.github.io/trace-explorer/

Open the site and pick a trace from the **Trace** dropdown (selection persists).

### Traces (2,000-request previews)

| Label | Source |
|-------|--------|
| Mooncake Tool & Agent | [Mooncake](https://github.com/kvcache-ai/Mooncake) |
| Mooncake Conversation | Mooncake |
| Mooncake Synthetic | Mooncake |
| RAGPulse | [flashserve/RAGPulse](https://github.com/flashserve/RAGPulse) |
| Azure LLM Conversation | [Azure/AzurePublicDataset](https://github.com/Azure/AzurePublicDataset) |
| BurstGPT | [HPMLL/BurstGPT](https://github.com/HPMLL/BurstGPT) |

Views: Fabric · Streets · Stack · Scatter · Surface · Feast

## Update

From [aiperf-toolkit](https://github.com/discoposse/ollama-aiperf-toolkit):

```bash
./examples/trace-replay-elastic-viewer/publish-mooncake-previews.sh
cp -r docs/trace-explorer/* /path/to/trace-explorer/
cd /path/to/trace-explorer && git add -A && git commit -m "Update trace previews" && git push
```