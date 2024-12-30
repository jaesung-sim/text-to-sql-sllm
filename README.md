# Text-to-SQL Project Using Spider Benchmark

This project aims to evaluate and enhance the text-to-SQL capabilities of open-source large language models (LLMs) by leveraging the **Spider Benchmark**, a standard for assessing the performance of text-to-SQL systems.

The implementation is based on the source code of **DIN-SQL: Decomposed In-Context Learning of Text-to-SQL with Self-Correction**, one of the top-ranking models on the Spider Benchmark. We modified the original code to optimize performance and adapt it to our specific requirements.

---

## **Project Environment**

### **Operating System**
- **Distributor ID**: Ubuntu  
- **Description**: Ubuntu 22.04.5 LTS  
- **Release**: 22.04

### **Hardware Specifications**
- **Architecture**: x86_64
- **CPU**: Intel(R) Core(TM) i9-14900KF  
  - CPU Mode(s): 32-bit, 64-bit  
  - Address Sizes: 39 bits (physical), 48 bits (virtual)  
  - Cores: 32 (On-line CPU(s): 0-31)

- **GPU**: NVIDIA GeForce RTX 4090  
  - **Memory**: 24,564 MiB  
  - **Driver Version**: 535.183.01  
  - **CUDA Version**: 12.2

### **LLM Framework**
The project predominantly utilizes LLMs powered by **Ollama**, ensuring seamless integration and advanced model capabilities.

---

## **Model Implementation**
We leveraged the **DIN-SQL** architecture, a state-of-the-art approach for decomposed in-context learning with self-correction. Our modifications include:
- **Code Optimization**: Enhancements for improved computational efficiency.
- **Adaptation for Spider Benchmark**: Custom tweaks to align with benchmark requirements.

---

## **Highlights**
- **Advanced LLM Capabilities**: Explored and enhanced text-to-SQL performance using cutting-edge LLMs.
- **High-Performance Environment**: Leveraged top-tier hardware, including the Intel i9-14900KF and NVIDIA RTX 4090.
- **Spider Benchmark**: Evaluated model performance against industry-standard benchmarks for SQL generation tasks.

---

## **Usage**
To replicate our results or explore the modified DIN-SQL implementation, ensure the following:
1. Install the required dependencies (refer to the `requirements.txt`).
2. Set up the environment as described in the installation guide.
3. Run the model using the provided scripts to benchmark against the Spider dataset.

---

## **Acknowledgments**
Special thanks to the developers of **DIN-SQL** for their groundbreaking work and the maintainers of the **Spider Benchmark** for providing a robust evaluation framework.

---

For any inquiries or contributions, feel free to open an issue or submit a pull request. Together, let's push the boundaries of LLM capabilities in text-to-SQL tasks!

