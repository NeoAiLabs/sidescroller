# One-Shot Side-Scroller

A small benchmark for comparing how different AI models handle the same one-shot game-development prompt.

Each model receives the prompt in [`sidescroller prompt.txt`](./sidescroller%20prompt.txt) and returns one self-contained HTML file. The result should run directly in a desktop browser without a build step, server, external library, or downloaded asset.

## Results

| Model | Game |
| --- | --- |
| GPT-5.6Sol | [`GPT-5.6Sol.html`](./GPT-5.6Sol.html) |
| Ling-3.0-Flash | [`Ling-3.0-Flash.html`](./Ling-3.0-Flash.html) |
| Deepseekv4-Flash | [`Deepseekv4-Flash.html`](./Deepseekv4-Flash.html) |
| Grok-4.5 | [`Grok-4.5.html`](./Grok-4.5.html) |
| North-Mini | [`North-Mini.html`](./North-Mini.html) |

## Run a game

1. Download or clone this repository.
2. Open a model's `.html` file in a modern desktop browser.
3. Play using:
   - **Move:** Arrow keys or `WASD`
   - **Jump:** `Space`
   - **Shoot:** `J` or left mouse button
   - **Restart after win/game over:** `R`

No installation or build command is required.

## Benchmark method

To keep comparisons meaningful:

1. Start a fresh model conversation with no project context or follow-up instructions.
2. Send the contents of [`sidescroller prompt.txt`](./sidescroller%20prompt.txt) as a single prompt.
3. Save the model's first complete response as `<model-name>.html`.
4. Do not hand-edit the generated game.
5. Confirm that the saved file opens and is playable, then add it to the results table above.

Model filenames should be short, filesystem-safe, and identify the exact model variant used.

## Repository layout

```text
.
├── README.md                  # Project overview and benchmark method
├── sidescroller prompt.txt    # Canonical prompt sent to every model
└── <model-name>.html          # One-shot result from a tested model
```

## Prompt goal

The prompt asks for a colorful, retro-tech HTML5 side-scroller starring a tiny Hermes Agent. The game must include platforming, enemies, collectibles, checkpoints, a boss fight against a cyber-lobster, and complete start/win/game-over states—all inside one HTML file using canvas and vanilla JavaScript.
