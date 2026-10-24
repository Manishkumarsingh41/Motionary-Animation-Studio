
# Manim Animation Studio 🎬

A Kaggle-based animation studio built with **Manim Community Edition (CE)** and **Gradio**. Paste Python animation code, choose your aspect ratio and render quality, generate videos, preview the result, and download the final MP4.

## 🎥 Demo Video

A sample animation is included in this repository:

**[▶ Watch Claude Prompting Techniques Demo](./claude%20prompt%20tech.mp4)**

The demo video is stored in the same folder as the notebook. You can open or download it directly from GitHub.



## ✨ Features

🎬 **Manim CE Rendering**  
Create mathematical, educational, and concept-based animations using Python.

🖥️ **Gradio Interface**  
Write or paste Manim code and manage the rendering process through a simple interface.

📐 **Multiple Aspect Ratios**  
Choose from landscape (16:9), portrait (9:16), square (1:1), and 4:3 formats.

⚡ **Rendering Quality Options**  
Select draft, preview, or final quality depending on your requirements.

👀 **Video Preview**  
Preview your generated animations directly in the interface.

📥 **MP4 Export**  
Download rendered animations as MP4 videos.

🛠️ **Render Logs and Error Handling**  
View rendering logs and error messages to troubleshoot failed renders.

📓 **Kaggle Notebook Support**  
Set up and run the animation studio directly inside a Kaggle notebook.



## 📁 Repository Structure

```text
manim-animation-studio/
│
├── Manim_Animation_Studio_Complete.ipynb
├── claude prompt tech.mp4
└── README.md
```

> Make sure the notebook filename matches the actual filename in your repository.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Animation scripting |
| Manim Community Edition | Animation engine |
| Gradio | Interactive web interface |
| FFmpeg | Video encoding |
| Cairo and Pango | Rendering dependencies |
| LaTeX | Mathematical typesetting |
| Kaggle Notebooks | Cloud execution environment |

## 🚀 Getting Started

### 1. Open the notebook

Open `Manim_Animation_Studio_Complete.ipynb` in Kaggle, or download it from this repository and import it into your Kaggle environment.

### 2. Set up dependencies

Run the notebook cells from top to bottom. The setup cells install the required system packages and Python dependencies.

### 3. Launch the studio

Run the final cell and open the Gradio public URL printed in the notebook output.

### 4. Generate an animation

1. Paste your Manim Python code into the code editor.
2. Ensure your code contains a valid `Scene` subclass.
3. Select the desired aspect ratio.
4. Choose the rendering quality.
5. Click **Render**.
6. Preview the output and inspect the logs if anything fails.
7. Download the generated MP4.

**Tip:** Start with draft quality while testing. Switch to final quality after the animation renders correctly.

## 💻 Example Manim Code

Try this small example to test your setup:

```python
from manim import *

class QuickTest(Scene):
    def construct(self):
        self.camera.background_color = BLACK

        title = Text(
            "Hello, Manim!",
            color=WHITE,
            font_size=48
        )

        circle = Circle(color=BLUE)
        circle.next_to(title, DOWN, buff=0.5)

        self.play(Write(title), run_time=1.5)
        self.play(Create(circle), run_time=1.5)
        self.wait(1)
```

Run it from a terminal with:

```bash
manim -pql quick_test.py QuickTest
```

## ⚙️ Environment and Compatibility

The notebook is designed for a Kaggle environment. The exact package versions depend on the installed runtime and the versions selected by the setup cells.

For reliable code generation, target the installed **Manim Community Edition** version rather than APIs from other animation libraries.

Before rendering, check that:

- Every color constant and variable is defined.
- All required imports are present.
- Animation functions receive valid Manim objects.
- No unsupported arguments or undefined helper functions are used.
- Text fits within the frame and does not overlap other elements.
- The scene class name matches the class you intend to render.

## 🐛 Troubleshooting

### `NameError: name 'CYAN' is not defined`

Define the color explicitly:

```python
CYAN = "#45D7F5"
```

### `TypeError: Animation only works on Mobjects`

A plain Python list may have been passed directly to an animation. Animate the list elements individually:

```python
self.play(*[FadeOut(item) for item in items])
```

Each item must be a valid Manim `Mobject`.

### LaTeX or `MathTex` errors

Check that the notebook's LaTeX dependencies installed successfully. For ordinary text, use `Text` instead of `MathTex`.

### Rendering takes too long

- Use draft quality first.
- Reduce unnecessary objects and effects.
- Simplify complex scenes.
- Render at high quality only after a successful preview.

### Gradio link is unavailable

Check the final cell's output and rerun the launch cell if necessary. Public share links are temporary and may stop working after the Kaggle session ends.

## ⚠️ Important Notes

- The studio executes Python code that you provide. Run only code you trust.
- Download important videos before your Kaggle session ends.
- Rendering depends on code correctness, installed dependencies, and available resources.
- The notebook cannot guarantee that every generated animation will render without errors.
- Package versions and hosted notebook environments may change over time.

## 🤝 Contributing

Suggestions, bug reports, and improvements are welcome.

When reporting an issue, include:

- The relevant Manim code.
- The Python and Manim CE versions.
- The selected aspect ratio and quality.
- The complete render traceback.

## 📄 License

No license has been specified yet. Add a `LICENSE` file before distributing this project as open source. Make sure you have permission to distribute the included demo video and any third-party assets.

---

**Built with Python, Manim Community Edition, and Gradio.**
