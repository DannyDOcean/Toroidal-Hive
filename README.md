# THANN Prototype – README

## Overview
This repository contains a conceptual **Toroidal Hive Artificial Neural Network (THANN)** prototype showcasing:
1. **A simple neural network class** (`ToroidalHiveModel`) that demonstrates a toroidal feedback loop.
2. **Hugging Face Transformer pipelines** for text and image tasks (text generation, fill-mask, image classification, zero-shot image classification, and text-to-text generation).
3. **Sentence embeddings** using [Sentence Transformers](https://www.sbert.net/).
4. **ResNet image classification** (`microsoft/resnet-50`).
5. **Gradio UI** to easily interact with text generation and image classification features.

While the code includes basic components inspired by the THANN concept (like a feedback loop and modular design), it is primarily a **proof of concept** rather than a fully functional, self-healing or quantum-powered system.

---

## Features
1. **ToroidalHiveModel**:  
   - A simple LSTM-based model illustrating how a toroidal feedback loop might be implemented.
   - Shows how to pass output “feedback” back into an additional transformation layer.

2. **Multimodal Pipelines**:  
   - **Text Generation** (DistilGPT2)  
   - **Fill-Mask** (BERT base)  
   - **Image Classification** (ViT base)  
   - **Zero-Shot Image Classification** (CLIP base)  
   - **Text2Text Generation** (FLAN-T5-Small)  
   - **ResNet Classification** (microsoft/resnet-50)

3. **Sentence Embeddings**:  
   - Uses [Sentence Transformers](https://github.com/UKPLab/sentence-transformers) to compute embeddings and produce a dot-product similarity matrix.

4. **Gradio UI**:  
   - User-friendly interface that allows you to:
     - Enter custom text and get auto-generated responses.
     - Upload images for classification using ResNet-50.

---

## Installation

1. **Clone This Repository**

   ```bash
   git clone https://github.com/YOUR_USERNAME/THANN.git
   cd THANN
   ```

2. **Install Dependencies**

   ```bash
   pip install torch transformers sentence-transformers gradio
   ```

   - **PyTorch**: Deep learning library  
   - **Transformers**: Hugging Face library for state-of-the-art NLP models  
   - **Sentence Transformers**: Easy computation of sentence and text embeddings  
   - **Gradio**: Quick creation of easy-to-use web interfaces

---

## Usage

### 1. Demo Mode
**Runs pipeline demonstrations** (text generation, fill-mask, image classification, etc.) and the sentence embedding example.

```bash
python thann.py --demo
```

- Prints out:
  - Loaded pipeline names  
  - Sentence similarity matrix  
  - Example text generation from DistilGPT2 (if loaded)

### 2. Gradio UI
**Launches the Gradio web interface** to:
- Type in a prompt for text generation using DistilGPT2  
- Upload an image for classification using ResNet-50

```bash
python thann.py --ui
```

- This opens a local Gradio interface in your browser (usually at `http://127.0.0.1:7860`).
- In the “Text Generation” tab, enter your prompt to get a generated response.  
- In the “ResNet Image Classification” tab, upload an image to see classification labels.

### 3. Additional Arguments
To see all available command-line arguments:
```bash
python thann.py --help
```

---

## File Structure

```plaintext
.
├── thann.py           # Main script containing the THANN prototype & pipelines
├── requirements.txt   # (optional) Dependencies if you want a pinned environment
├── README.md          # Project documentation (this file)
└── ...                # Any additional files or directories
```

- **`thann.py`** includes:
  - `ToroidalHiveModel`: Illustrates the concept of a toroidal feedback loop.
  - `create_multimodal_pipelines()`: Loads all Hugging Face pipelines.
  - `example_sentence_embeddings()`: Demonstrates sentence embeddings.
  - `run_gradio_ui()`: Launches the Gradio interface.

---

## Technical Details

1. **ToroidalHiveModel (Conceptual)**  
   - Uses a simple LSTM to process tokenised input.  
   - After classification, the output logits are passed through a softmax and then averaged to create a feedback signal.  
   - Demonstrates how feedback could be reinjected into the network for error correction or further processing.

2. **Multimodal Pipelines**  
   - Each pipeline uses a different Hugging Face model.  
   - The script attempts to load them in sequence; if any model fails to load, it displays a warning.

3. **Sentence Embeddings**  
   - Uses the [all-MiniLM-L6-v2](https://www.sbert.net/docs/pretrained_models.html) model from Sentence Transformers.  
   - Shows how to compute embeddings and a similarity matrix for a list of example sentences.

4. **Gradio UI**  
   - Built with `gradio.Blocks()` to create two separate tabs:
     - **Text Generation**: DistilGPT2  
     - **Image Classification**: ResNet-50  
   - Easily extendable to include other pipelines (e.g., fill-mask, zero-shot classification) with minimal code changes.

---

## Future Improvements

- **Self-Healing Mechanisms**: Implement layers that detect and correct errors during runtime.
- **Adaptive Learning Rates/Emotional Inputs**: Adjust learning parameters based on “emotional signals” or reinforcement cues.
- **Quantum Modules**: Integrate quantum computing libraries (e.g., Qiskit) for advanced features like quantum-enhanced search.
- **Swarm-Based Logic**: Expand the single `ToroidalHiveModel` into multiple agents exchanging parameters or experiences.

---

## Contributing

1. **Fork the Repository**  
   - Make a personal copy to experiment and add features.

2. **Create a Feature Branch**  
   ```bash
   git checkout -b feature-new-idea
   ```

3. **Commit Your Changes**  
   ```bash
   git commit -m "Add new feature"
   ```

4. **Push and Submit a Pull Request**  
   ```bash
   git push origin feature-new-idea
   ```
   - Open a Pull Request in GitHub, describing your changes.

---

## License

This project is provided “as is” for educational and illustrative purposes. Please consult the repository’s [LICENSE](LICENSE) file (if available) or consider adding your preferred license (e.g., MIT, Apache-2.0) to clarify usage rights and limitations.

---

## Contact

For questions or suggestions, open an [issue](../../issues) in this repository or reach out via your preferred method (e.g., LinkedIn, Twitter, or email if provided).

Enjoy experimenting with the **THANN Prototype** and exploring cutting-edge ideas in neural network design!
