# Text-to-SQL Project Using Spider Benchmark | 스파이더 벤치마크 기반 Text-to-SQL 프로젝트

**EN:**
This project aims to evaluate and enhance the text-to-SQL capabilities of open-source large language models (LLMs) by leveraging the **Spider Benchmark**, a standard for assessing the performance of text-to-SQL systems.

The implementation is based on the source code of **DIN-SQL: Decomposed In-Context Learning of Text-to-SQL with Self-Correction**, one of the top-ranking models on the Spider Benchmark. We modified the original code to optimize performance and adapt it to our specific requirements.

**KR:**
본 프로젝트는 **Spider 벤치마크**를 활용하여 오픈소스 대규모 언어모델(LLM)의 Text-to-SQL 성능을 평가하고 향상하는 것을 목표로 합니다.

구현은 Spider 벤치마크 상위권 모델인 **DIN-SQL: Decomposed In-Context Learning of Text-to-SQL with Self-Correction**의 소스 코드를 기반으로 하며, 성능 최적화와 프로젝트 요구사항 반영을 위해 원본 코드를 일부 수정하였습니다.

<img src="https://github.com/user-attachments/assets/6bba25a8-7b0d-41b1-84df-8cd3bb097780" width="400" height="400"/>
<img src="https://github.com/user-attachments/assets/1c8a1a62-56bc-4c30-8edf-639f88e0573f" width="500" height="400"/>

---

## Project Environment | 프로젝트 환경

### Operating System | 운영체제

* **Distributor ID / 배포판 식별자**: Ubuntu
* **Description / 설명**: Ubuntu 22.04.5 LTS
* **Release / 릴리스**: 22.04

### Hardware Specifications | 하드웨어 사양

* **Architecture / 아키텍처**: x86_64

* **CPU**: Intel(R) Core(TM) i9-14900KF

  * **CPU Mode(s) / 동작 모드**: 32-bit, 64-bit
  * **Address Sizes / 주소 크기**: 39 bits (physical), 48 bits (virtual)
  * **Cores / 코어 수**: 32 (On-line CPU(s): 0-31)

* **GPU**: NVIDIA GeForce RTX 4090

  * **Memory / 메모리**: 24,564 MiB
  * **Driver Version / 드라이버 버전**: 535.183.01
  * **CUDA Version / CUDA 버전**: 12.2

### LLM Framework | LLM 프레임워크

* **EN:** The project predominantly utilizes LLMs powered by **Ollama**, ensuring seamless integration and advanced model capabilities.
* **KR:** 본 프로젝트는 주로 **Ollama** 기반 LLM을 사용하여 손쉬운 통합과 향상된 모델 기능을 제공합니다.

---

## Model Implementation | 모델 구현

**EN:**
We leveraged the **DIN-SQL** architecture, a state-of-the-art approach for decomposed in-context learning with self-correction. Our modifications include:

* **Code Optimization**: Enhancements for improved computational efficiency.
* **Adaptation for Spider Benchmark**: Custom tweaks to align with benchmark requirements.

**KR:**
본 프로젝트는 자기 수정(self-correction)을 포함한 분해형 인컨텍스트 학습을 적용한 **DIN-SQL** 아키텍처를 활용하였습니다. 주요 수정 사항은 다음과 같습니다.

* **코드 최적화**: 연산 효율 향상을 위한 개선.
* **Spider 벤치마크 적합화**: 벤치마크 요구사항에 맞춘 커스텀 조정.

---

## Highlights | 하이라이트

* **EN:** Advanced LLM capabilities: Explored and enhanced text-to-SQL performance using cutting-edge LLMs.
* **EN:** High-performance environment: Leveraged top-tier hardware, including the Intel i9-14900KF and NVIDIA RTX 4090.
* **EN:** Spider Benchmark: Evaluated model performance against industry-standard benchmarks for SQL generation tasks.
* **KR:** 최첨단 LLM을 활용하여 Text-to-SQL 성능을 분석하고 향상하였습니다.
* **KR:** Intel i9-14900KF와 NVIDIA RTX 4090 등 고성능 하드웨어 환경을 활용하였습니다.
* **KR:** 산업 표준인 Spider 벤치마크로 SQL 생성 성능을 체계적으로 평가하였습니다.

---

## Usage | 사용 방법

**EN:**
To replicate our results or explore the modified DIN-SQL implementation, ensure the following:

1. Install the required dependencies (refer to the `requirements.txt`).
2. Set up the environment as described in the installation guide.
3. Run the model using the provided scripts to benchmark against the Spider dataset.

**KR:**
결과 재현 또는 수정된 DIN-SQL 구현을 실험하시려면 아래 절차를 따라 주십시오.

1. 필요한 의존성을 설치합니다(`requirements.txt` 참고).
2. 설치 가이드에 따라 실행 환경을 구성합니다.
3. 제공된 스크립트를 사용하여 Spider 데이터셋 기준으로 벤치마크를 실행합니다.

---

## Acknowledgments | 감사의 말

* **EN:** Special thanks to the developers of **DIN-SQL** for their groundbreaking work and the maintainers of the **Spider Benchmark** for providing a robust evaluation framework.
* **KR:** 혁신적인 연구를 공개해 주신 **DIN-SQL** 개발진과, 탄탄한 평가 프레임워크를 제공해 주신 **Spider 벤치마크** 유지보수 팀께 감사드립니다.

---

**EN:** For any inquiries or contributions, feel free to open an issue or submit a pull request. Together, let’s push the boundaries of LLM capabilities in text-to-SQL tasks!
**KR:** 문의 및 기여는 언제든지 이슈 등록 또는 Pull Request로 부탁드립니다. 함께 Text-to-SQL 분야에서 LLM의 한계를 넓혀가면 좋겠습니다.
