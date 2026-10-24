
# 🎬 Manim Animation Studio

A notebook-based animation studio for creating educational, mathematical, and concept-based animations using Python, Manim Community Edition, and Gradio.

Generate Manim code with your preferred AI assistant, paste it into the studio, render the animation, preview the result, and export it as an MP4 video.

## ✨ Features

🎬 **Manim CE Rendering**  
Create mathematical, educational, and concept-based animations using Python.

🖥️ **Gradio Interface**  
Write or paste Manim code and manage rendering through a simple interface.

📐 **Multiple Aspect Ratios**  
Choose from landscape (16:9), portrait (9:16), square (1:1), and 4:3 formats, depending on the available configuration.

⚡ **Rendering Quality Options**  
Select draft, preview, or final quality depending on your requirements.

👀 **Video Preview**  
Preview generated animations directly in the interface.

📥 **MP4 Export**  
Download rendered animations for YouTube videos, Shorts, presentations, and educational content.

🛠️ **Render Logs**  
View rendering output and error messages to troubleshoot failed renders.

🤖 **AI-Assisted Code Generation**  
Use an AI assistant to generate Manim code from a topic, script, or visual direction.

📓 **Notebook Support**  
Run the studio in Kaggle, Google Colab, Jupyter, or another compatible notebook environment, provided the required dependencies are available.

## 📁 Project Structure

```text
.
├── Manim_Animation_Studio_Complete.ipynb
├── claude prompt tech.mp4
└── README.md
```

The notebook contains the animation studio, while the MP4 file demonstrates the workflow.

## 🚀 Where to Run the Notebook

This project uses a Jupyter Notebook (`.ipynb`), which can be opened in several compatible environments.

### ☁️ Option 1: Kaggle Notebooks

1. Download `Manim_Animation_Studio_Complete.ipynb` from this repository.
2. Open [Kaggle Notebooks](https://www.kaggle.com/code).
3. Create a notebook or use the available import/upload workflow to add the downloaded file.
4. Enable internet access if package installation requires it.
5. Run the notebook cells in order.
6. Open the Gradio link displayed by the launch cell.

**Good for:** Running the project in a hosted notebook environment.

### 🔵 Option 2: Google Colab

1. Download `Manim_Animation_Studio_Complete.ipynb` from this repository.
2. Open [Google Colab](https://colab.research.google.com/).
3. Select **File → Upload notebook** and upload the `.ipynb` file.
4. Choose a suitable runtime and enable internet access if needed.
5. Run the setup cells first, followed by the remaining cells.
6. Open the Gradio link displayed by the notebook.

**Good for:** Getting started without setting up a local Python environment.

### 💻 Option 3: Jupyter Notebook or JupyterLab

1. Install Python on your computer.
2. Install Jupyter Notebook or JupyterLab.
3. Download or clone this repository.
4. Install the required dependencies, including Manim CE, Gradio, and FFmpeg.
5. Open `Manim_Animation_Studio_Complete.ipynb`.
6. Run the cells in order and launch the Gradio interface.

**Good for:** Local development and customization.

### 🧑‍💻 Option 4: VS Code or Another Compatible Environment

You can also open the notebook in VS Code with the Jupyter extension or another environment that supports `.ipynb` files.

Make sure your environment supports the required Python version, Manim Community Edition, FFmpeg, Gradio, and other dependencies used by the notebook.

### ⚠️ Environment Notes

Setup requirements can differ between Kaggle, Colab, and local systems. Python versions, package compatibility, internet access, available compute, FFmpeg installation, and Gradio networking settings can affect whether the notebook runs without changes.

Follow the setup instructions in the notebook and check the error output if a cell fails.

## 🤖 How to Use the AI Master Prompt

The master prompt helps an AI assistant generate a complete Manim Community Edition Python script for your animation.

### Step 1: Open an AI Assistant

Open ChatGPT, Claude, or another AI assistant capable of generating Python code.

### Step 2: Copy the Complete Master Prompt

Copy the full Manim code-generation prompt used in your workflow. Keep its technical requirements and compatibility instructions intact.

If the prompt contains a placeholder for the topic, script, or visual direction, replace it with your own content.

### Step 3: Describe Your Animation

Give the AI a clear topic and, if possible, a short script or scene-by-scene plan.

You can specify the audience, duration, visual style, equations, examples, and aspect ratio.

**Example:**

```text
TOPIC: How a Large Language Model Works

STYLE:
Minimal, professional educational animation.

VISUAL DIRECTION:
Show text entering a model, passing through transformer
blocks, and producing the next predicted token.

DURATION:
Approximately 60 seconds.

OUTPUT:
Complete, runnable Manim CE Python code.
```

### Step 4: Generate the Code

Ask the AI to return the complete Python script, including imports, a scene class, a `construct()` method, and the required animation logic.

Your master prompt should instruct the AI to:

- Use APIs compatible with the installed Manim version.
- Define every referenced variable and color.
- Use valid Manim objects in animation functions.
- Avoid unsupported methods and incorrect function arguments.
- Return complete, runnable code rather than partial snippets.

### Step 5: Review the Generated Script

Before rendering, check that all imports and variables are defined, the scene class is present, and the code uses APIs compatible with your environment.

AI-generated code may still need debugging, so review it before running it.

## 🎨 How to Render an Animation

### Step 1: Launch the Studio

Run the notebook setup cells in order, then execute the cell that launches Gradio. Open the link shown in the output.

### Step 2: Paste the Code

Copy the complete Python script from your AI assistant and paste it into the Manim code editor.

### Step 3: Choose an Aspect Ratio

Select the format that suits your content.

| Format | Suitable For |
| --- | --- |
| 16:9 | YouTube videos and presentations |
| 9:16 | YouTube Shorts and Reels |
| 1:1 | Square social media videos |
| 4:3 | Traditional presentation formats |

The exact options depend on the notebook configuration.

### Step 4: Choose Rendering Quality

**Draft:** For quick checks while developing the animation.

**Preview:** For reviewing timing, layout, and transitions.

**Final:** For the finished animation.

Higher-quality renders generally take longer.

### Step 5: Render the Scene

Click the render button and wait for the process to finish.

Rendering time depends on scene complexity, resolution, frame rate, and available computing resources.

### Step 6: Preview the Video

Watch the result in the interface. Check for clipped text, overlapping objects, incorrect equations, abrupt transitions, and timing issues.

### Step 7: Fix and Render Again

If the output is incorrect, update the code and render again.

If an error appears, copy the relevant error message into your AI assistant and request a targeted fix.

### Step 8: Download the MP4

When rendering succeeds, use the interface's download option to save the MP4 video.

You can then import it into your video editor or use it in your content workflow.

## 🛠️ Troubleshooting

### Undefined Color or Variable

Example:

```python
NameError: name 'CYAN' is not defined
```

**Why it happens:** The script uses a name that has not been defined or imported.

**Possible fix:** Define the color before using it, or use a valid Manim color constant.

```python
from manim import *

CYAN = "#00FFFF"
```

### Animation Only Works on Mobjects

Example:

```text
TypeError: Animation only works on Mobjects
```

**Why it happens:** A list or another unsupported object may have been passed to an animation such as `FadeOut`.

**Possible fix:** Animate individual Manim objects, or group compatible objects with `VGroup`.

```python
# Animate individual objects
self.play(FadeOut(circle), FadeOut(square))

# Or group compatible objects
group = VGroup(circle, square)
self.play(FadeOut(group))
```

### Rendering Fails

1. Read the error message in the render logs.
2. Check for missing imports and undefined variables.
3. Verify that animation functions receive valid Manim objects.
4. Confirm that the scene class name matches the scene selected for rendering.
5. Check that the installed dependencies and APIs are compatible.
6. Ask your AI assistant to fix the specific error without rewriting the entire script unnecessarily.

### Gradio Does Not Open

Check whether the launch cell completed successfully.

Use the link printed by the notebook. If the launch failed, inspect the output for errors and review the environment's networking requirements.

## 💡 Tips for Better Results

- Keep each scene focused on one main idea.
- Use readable text and consistent colors.
- Prefer visual explanations over long paragraphs on screen.
- Add pauses after important equations or concepts.
- Use draft renders to catch layout issues early.
- Give the AI precise instructions about what should appear and when.
- Ask for targeted fixes when an error occurs.

## 🎥 Demo

Watch the included demonstration video:

[▶️ View the output generated video](./claude%20prompt%20tech.mp4)

If GitHub does not play the video inline, open the MP4 file in the repository or download it.

## 🧰 Technology Stack

- Python
- Manim Community Edition
- Gradio
- FFmpeg
- Jupyter Notebook
- Kaggle or Google Colab
- AI assistants for code generation

## ⚠️ Notes

This project is intended for educational and creative animation workflows.

AI-generated code is not guaranteed to work on the first attempt. Review the script, inspect render logs, and test the output in your chosen environment.

Rendering performance and available options depend on the notebook configuration and the resources provided by the platform.

## 🤝 Contributing

Suggestions, bug reports, and improvements are welcome. When reporting an issue, include the relevant error message and steps to reproduce it.

## 📄 License

No license has been specified in this README. Check the repository for licensing information before redistributing or reusing this project.
