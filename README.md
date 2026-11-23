# Persona Lenses

**What Makes a Vision-Language Model See Through Its Persona's Eyes?**

Yoonho Shin, LG Uplus

Paper: [arXiv:2611.25508](https://arxiv.org/abs/2611.25508)

## About

Vision-language models have been used to simulate where a user looks on a web page. However, a persona in the prompt reaches the simulated gaze only partly. We measure this reach as the difference in one model's gaze between two personas that differ in a single attribute, and we introduce persona lenses, which place the persona between the model and the page.

| Lens | What it does |
|---|---|
| Text lens | A two-step prompt in which the model first writes what the persona would look at |
| Pixel lens | Marks on the region of the page that matches the persona's interests |
| Weight lens | A LoRA adapter trained with a dwell reward that is gated to keep the scanpath natural |

Using Qwen3-VL (4B and 32B) and Qwen3.5-9B on generated and live pages, we compare the lenses with one another and with scale, the 32B model with no lens.

## Findings

- The text lens separates the personas strongly but is not robust to profile changes that should not move gaze.
- The pixel lens separates the personas less but is unaffected by attributes unrelated to gaze.
- At 4B and 9B, the weight lens separates the personas on interests held out from training, with no extra step on a new page.
- The 32B model separates the personas with the base prompt alone.

The choice of a lens therefore depends on cost and model size.

## Code and data

This repository holds only this page for now. The code, the preregistered protocol files, the per-trial logs and the generated pages will be released later. Screenshots of live pages are copyrighted and will not be redistributed, so the release will give their URLs, capture dates and the capture script instead.

## Citation

```bibtex
@misc{shin2026personalensesmakesvisionlanguage,
  title={Persona Lenses: What Makes a Vision-Language Model See Through Its Persona's Eyes?},
  author={Yoonho Shin},
  year={2026},
  eprint={2611.25508},
  archivePrefix={arXiv},
  primaryClass={cs.CV},
  url={https://arxiv.org/abs/2611.25508},
}
```
