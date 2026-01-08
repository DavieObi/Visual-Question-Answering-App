---

# Visual Question Answering App

A simple web app that allows you to **ask questions about images** using a multimodal AI model. Upload an image, type a question, and the app will provide an answer based on the visual content of the image.

This app leverages **ViLT (Vision-and-Language Transformer)** fine-tuned for Visual Question Answering.

---

## Features

* Upload any image and ask questions about it.
* Get real-time answers from a pre-trained ViLT model.
* Easy-to-use web interface powered by **Gradio**.
* Handles errors gracefully for unsupported inputs or ambiguous queries.

---

## Technologies Used

* **Python 3.x**
* **[Transformers](https://huggingface.co/docs/transformers/index)** – for the ViLT model and processor.
* **[PyTorch](https://pytorch.org/)** – deep learning framework.
* **[Pillow](https://python-pillow.org/)** – image processing.
* **[Gradio](https://gradio.app/)** – to build the web interface.

**Model Used:** `dandelin/vilt-b32-finetuned-vqa` from Hugging Face.

---

## Installation

1. Clone this repository:

```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

2. Install the dependencies:

```bash
pip install gradio transformers torch Pillow
```

---

## How to Run

1. Run the app:

```bash
python app.py
```

2. A web interface will open (usually at `http://127.0.0.1:7860`).
3. Upload an image, type a question about the image, and click **Submit**.
4. The model will return an answer below the input box.

---

## How It Works

1. **Processor**: The `ViltProcessor` prepares both the image and the text question into a format the model understands.
2. **Model Prediction**: `ViltForQuestionAnswering` predicts the answer using the combined image and text features.
3. **Decoding**: The model output logits are converted into readable text using the model’s label mapping.
4. **Interface**: Gradio handles user inputs and displays the predicted answers in real time.

---

## Example

Upload an image of a dog and ask:

```
What is the dog doing?
```

The model may answer:

```
Sitting
```

---

## Notes

* The model works best with **clear images** and **direct questions**.
* If the app fails to process an image or question, try using a different image or rephrasing your question.
* Currently supports a single image at a time.

---

## Future Improvements

* Support for **batch image questions**.
* Improve **error handling and logging** for unsupported file types.
* Deploy as a public web app with a persistent URL.

---

## References

* [ViLT: Vision-and-Language Transformer](https://huggingface.co/dandelin/vilt-b32-finetuned-vqa)
* [Gradio Documentation](https://gradio.app/docs/)
* [Hugging Face Transformers](https://huggingface.co/docs/transformers/)

---
