# 👗 Style Finder — Multimodal Fashion Analysis with RAG

**Style Finder** is an end-to-end **multimodal Retrieval-Augmented Generation (RAG)** application that analyzes fashion images and generates professional, catalog-style fashion insights.

The system combines **computer vision**, **vector similarity search**, and a **vision-capable large language model (LLM)** to identify garments, analyze style elements, and surface similar items with pricing and links.

Users interact with the system through an **interactive Gradio web application**, uploading an image and receiving AI-generated fashion analysis in real time.

---

## 🚀 Why This Project Matters

This project demonstrates how modern AI systems go beyond simple image recognition or text generation by **augmenting LLMs with retrieved visual and structured context**.

From a recruiter’s perspective, this project shows:
- Practical **multimodal RAG implementation**
- Vision embedding + similarity search
- Context-aware LLM prompting
- Clean, modular AI system design
- Real-world application of GenAI in retail / fashion tech

---

## 🧠 What Is Multimodal RAG?

**Multimodal Retrieval-Augmented Generation (RAG)** enhances LLM outputs by retrieving relevant information before generation.

In this project:
- **Images** and **text** are both first-class inputs
- Image embeddings retrieve relevant fashion metadata
- Retrieved context is injected into the LLM prompt
- The LLM produces richer, more accurate responses

This approach significantly improves reliability compared to using a vision model alone.

---

## 🧩 System Architecture

### End-to-End Pipeline

1. **User Uploads Image (Gradio UI)**
2. **Image Encoding**
   - ResNet50 extracts dense visual embeddings
   - Image is also encoded to Base64 for LLM input
3. **Vector Similarity Search**
   - Cosine similarity against precomputed dataset embeddings
   - Closest fashion match identified
4. **Context Retrieval**
   - Item metadata (name, price, links) retrieved
5. **Context-Augmented Generation**
   - Retrieved data injected into LLM prompt
   - Llama 3.2 Vision Instruct generates analysis
6. **Formatted Output**
   - Professional fashion catalog-style response

---

## 🖼️ Application Screenshots

### 🔹 Project Structure
*(Shows modular design and separation of concerns)*

![Style Finder Output](Output/style-finder%20output.png)

### 🔹 Gradio Web Interface

The interactive Gradio-based user interface allows users to:

- **Upload a fashion image** for analysis  
- **Analyze garments and style elements**, including colors, patterns, materials, and fit  
- **View similar fashion items** along with pricing information and direct purchase links  

The interface is designed to be simple and intuitive, enabling real-time interaction with the multimodal RAG pipeline while clearly presenting the AI-generated fashion insights.


## 📊 Example Output (What the AI Produces)

For a sample fashion image, the system generates:

- **Professional Fashion Analysis**
  - Garment identification
  - Colors, patterns, and materials
  - Fit and styling details

- **Key Elements Summary**

- **Similar Items**
  - Item names
  - Prices
  - Purchase links

- **Confidence Handling**
  - Differentiates exact vs similar matches using similarity thresholds

This output is intentionally designed to resemble **retail catalog or professional stylist notes**, rather than casual or conversational descriptions.

---

## 🧰 Tech Stack

### AI & Machine Learning
- **Meta Llama 3.2 Vision Instruct**
- **Multimodal Retrieval-Augmented Generation (RAG)**
- **ResNet50** for image embeddings
- **Cosine similarity** for vector-based retrieval

### Backend
- Python
- Modular service-oriented architecture
- IBM watsonx.ai SDK

### Frontend
- **Gradio** (interactive web interface)

### Data
- Precomputed image embeddings
- Structured fashion metadata (items, prices, links)

---

## 📁 Project Structure

style-finder/ <br>
│<br>
├── app.py                         # Main Gradio application<br>
├── config.py                      # Configuration and constants<br>
├── requirements.txt               # Dependencies<br>
├── swift-style-embeddings.pkl     # Precomputed image embeddings<br>
│<br>
├── models/<br>
│   ├── image_processor.py         # Image encoding & similarity search<br>
│   └── llm_service.py             # LLM interaction & prompting<br>
│<br>
├── utils/<br>
│   └── helpers.py                 # Retrieval & response formatting<br>
│<br>
├── examples/                      # Sample input images<br>
├── Output/<br>
│   └── style-finder-output.png    # UI + output screenshot<br>
└── README.md<br>

## 📌 Key Engineering Highlights

- Vision embeddings decoupled from LLM inference
- Retrieval-first design improves factual grounding
- Similarity threshold controls confidence handling
- Modular, testable architecture
- Clear separation of computer vision, retrieval, and generation layers

---

## ⚠️ Disclaimer

This project is intended for educational and demonstrative purposes.  
Fashion item matches are based on visual similarity and may not represent exact products.

---


## ⭐ What This Project Demonstrates

- Real-world **multimodal RAG system** implementation
- Strong understanding of **Generative AI pipelines**
- Vision, retrieval, and LLM integration
- Production-style AI application design

This project is part of my portfolio showcasing applied AI, computer vision, and generative AI system design.

