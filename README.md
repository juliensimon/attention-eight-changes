# Your LLM no longer reads every token

Slides and animations from the video "Your LLM no longer reads every token: eight attention designs, explained and measured".

The newest open models from Alibaba, Moonshot, DeepSeek and Z.AI have replaced full attention in most or all of their layers. The video walks through the eight designs that got us here, who tested them against full attention, and a cache and speed measurement of three ~30B models on a Mac.

- Video: <!-- YouTube link -->
- Article: [Eight Changes to Transformer Attention, and What Each Costs](https://www.airealist.ai/p/eight-changes-to-transformer-attention), The AI Realist, October 2026

## Contents

| File | What it is |
|---|---|
| `slides.pdf` | The deck, 24 pages. Each animation slide shows the animation's last frame |
| `animations/NN-name.mp4` | The build animation for each design, 1080p60, about 25 seconds, no sound |
| `animations/NN-name-loop.mp4` | A seamless loop of the same design, about 8 seconds: the last frame equals the first |

## Animations

| File | Design |
|---|---|
| `01-cold-open` | 48 layers that read everything become Qwen3.8-Flash-Next's 36 linear and 12 indexer layers |
| `00-full` | Full attention, 2017: every new token reads every earlier one |
| `01-gqa` | Grouped-query attention: same reads, smaller cache |
| `02-latent` | Latent attention (MLA): same reads, compressed cache |
| `03-window` | Sliding windows: most layers read only the recent tokens |
| `04-mamba2` | Mamba-2: no per-token cache, one fixed-size state |
| `05-linear-hybrid` | Linear hybrid: three state layers for each full-attention layer |
| `06-sparse` | Sparse attention: an indexer picks what the layer reads |
| `07-pooled-cache` | Pooled cache (DeepSeek V4): old tokens become summaries |
| `08-linear-sparse` | Linear plus sparse: no layer reads everything |

How to read them: the squares are the earlier tokens, oldest on the left. The black square on the right is the token being written. A blue line is an earlier token it reads directly. A black box is a fixed-size state. The grey cells under the tokens are the cache kept for each one. The small chart on the right shows the cache this design holds as tokens arrive, in blue, against full attention in grey.

## License

© 2026 Julien Simon. The slides and animations are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/): you may share and adapt them, including commercially, as long as you credit Julien Simon and link to the video.
