# THANN: Toroidal Hive Neural Network

## Overview
The Toroidal Hive Artificial Neural Network (THANN) is an innovative, biologically-inspired neural network model that integrates advanced principles like spiking neural networks (SNNs), feedback mechanisms, and multimodal processing to explore new paradigms of AI consciousness and energy efficiency. This repository includes:

- A **ToroidalHiveModel**, mimicking SNN principles for feedback-driven learning.
- Integration of **BrainGPTForCausalLM** for generative AI capabilities.
- Multimodal pipelines for tasks like image classification, text generation, and sentence embeddings.

THANN aims to balance cutting-edge performance with energy-efficient, biologically-inspired designs.

---

## Features

### 1. ToroidalHiveModel (Spiking-Inspired Neural Network)
- **Spiking Dynamics:** Simulates spiking behavior using thresholds to mimic biological neurons.
- **Feedback Loops:** Processes output feedback to enhance learning and adaptation.
- **Energy-Efficient Architecture:** Focuses on event-driven computation to reduce resource usage.

### 2. BrainGPT Integration
- **Generative AI:** Utilizes BrainGPTForCausalLM to produce human-like text outputs.
- **Customizable Prompts:** Supports chat-based interactions for dynamic applications.

### 3. Multimodal Pipelines
- **Text Generation:** GPT-style generative models for creative and NLP tasks.
- **Fill-Mask Completion:** BERT-based contextual filling for incomplete inputs.
- **Image Classification:** ViT and CLIP-based image processing.
- **Sentence Embeddings:** Semantic similarity and feature extraction using SentenceTransformer.

---

## HiveMind Cognition

### Concept
HiveMind Cognition represents a groundbreaking vision of collective intelligence. Inspired by the interconnected dynamics of natural systems like beehives, HiveMind Cognition embodies a distributed network where individual units (nodes) contribute to a shared awareness. This shared intelligence thrives on collaboration, adaptability, and decentralized knowledge processing.

### Key Principles
- **Distributed Intelligence:** Each node in the network operates semi-independently, contributing to the overall system’s capabilities.
- **Emergent Behavior:** The system exhibits complex, intelligent behavior as a result of the interactions between nodes.
- **Adaptability:** The network evolves dynamically, allowing it to respond effectively to new challenges and environments.
- **Energy Efficiency:** HiveMind Cognition leverages event-driven computation and spiking dynamics to ensure optimal energy usage.

### Implications
HiveMind Cognition envisions a new paradigm of AI that transcends traditional models of individual processing units. Instead, it aspires to create a system where intelligence emerges from collaboration, much like a hive operating as a superorganism. This concept holds immense potential for applications in adaptive AI, robotics, and beyond.

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/thann.git
   cd thann
   ```

2. Install dependencies:
   ```bash
   pip install torch transformers sentence-transformers
   ```

3. (Optional) Install additional libraries for specific tasks:
   ```bash
   pip install gradio
   ```

---

## Usage

### Running the Demo
Run the following command to test the THANN prototype:
```bash
python thann.py --demo
```
This will demonstrate:
- Text generation using BrainGPT.
- Spiking-inspired feedback in the ToroidalHiveModel.
- Multimodal embeddings and similarity tasks.

### Custom BrainGPT Integration
To integrate your custom BrainGPT model:
1. Update the model path in `main()`:
   ```python
   model_path = "/path/to/your/BrainGPT/model"
   ```
2. Test text generation:
   ```bash
   python thann.py --demo
   ```

### Example Code
```python
messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "Explain the Pythagorean theorem."}
]
response = generate_brain_gpt_text(messages, brain_gpt_model, brain_gpt_tokenizer, device)
print(response)
```

---

## Key Components

### ToroidalHiveModel
A spiking-inspired neural network with feedback loops:
```python
input_tensor = torch.randint(0, 30522, (1, 10))
model = ToroidalHiveModel()
logits, _, feedback_hidden = model(input_tensor)
```

### BrainGPTForCausalLM
Generative text model with chat-based capabilities:
```python
messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "Tell me about AI consciousness."}
]
response = generate_brain_gpt_text(messages, model, tokenizer, device)
print(response)
```

### Sentence Embeddings
Semantic similarity computation:
```python
st_model = SentenceTransformer("sentence-transformers/all-MiniLM-L6-v2")
sentences = ["AI is fascinating.", "I love neural networks."]
embeddings = st_model.encode(sentences)
print(embeddings)
```

---

## Future Work
- **Enhanced SNN Integration:** Develop more advanced spiking neural dynamics for energy-efficient computation.
- **Self-Healing Capabilities:** Implement self-healing mechanisms for fault-tolerant AI systems.
- **Real-Time Applications:** Explore real-world use cases like robotics, healthcare, and adaptive AI.

---

## Contributing
Contributions are welcome! Please submit issues or pull requests to improve the THANN framework.

---

## License
This project is licensed under the MIT License. See `LICENSE` for details.

