# text-to-sql-sllm | 스파이더 벤치마크 기반 소형 LLM Text-to-SQL

**text-to-sql-sllm**은 **임베디드 적용을 염두에 둔 소형 LLM**의 Text-to-SQL 성능 향상을 목표로 합니다. 표준 평가셋인 **Spider Benchmark**를 활용해, 경량 모델 환경에서 **정확도와 효율**을 함께 개선하는 데 초점을 맞추었습니다.

본 구현은 Spider 상위권 접근법인 **DIN-SQL: Decomposed In-Context Learning of Text-to-SQL with Self-Correction**의 공개 소스를 기반으로 하며, 프로젝트 요구에 맞춘 **성능 최적화** 및 **벤치마크 적합화**를 적용했습니다.
실제 배포 타깃은 임베디드/엣지 환경이며, 재현성과 분석 편의상 아래 환경에서 실험을 수행했습니다. 이 사양은 설계 시 **상한(upper-bound) 제약**으로 간주했습니다.

<img src="https://github.com/user-attachments/assets/6bba25a8-7b0d-41b1-84df-8cd3bb097780" width="400" height="400"/> <img src="https://github.com/user-attachments/assets/1c8a1a62-56bc-4c30-8edf-639f88e0573f" width="500" height="400"/>

## 프로젝트 환경 (상한 제약)

### 운영체제

* **Distributor ID**: Ubuntu
* **Description**: Ubuntu 22.04.5 LTS
* **Release**: 22.04

### 하드웨어 사양

* **아키텍처**: x86_64
* **CPU**: Intel(R) Core(TM) i9-14900KF

  * 동작 모드: 32-bit, 64-bit
  * 주소 크기: 39 bits(physical), 48 bits(virtual)
  * 코어 수: 32 (On-line CPU(s): 0-31)
* **GPU**: NVIDIA GeForce RTX 4090

  * 메모리: 24,564 MiB
  * 드라이버 버전: 535.183.01
  * CUDA 버전: 12.2

> 위 사양은 개발·평가 시 **상한 제약**으로 사용했습니다. 실제 목표는 **소형 LLM/임베디드 환경에서의 저지연·저메모리 추론**입니다. 이를 위해 프롬프트/컨텍스트 길이 단축, 예시 수 제한, 후보 생성/재랭킹 경량화 등을 적용했습니다.

### LLM 프레임워크

* **Ollama** 기반 LLM을 주로 사용하여 간편한 통합과 일관된 실행 환경을 제공합니다.

## 모델 구현

* **기반 아키텍처**: **DIN-SQL**(분해형 In-Context 학습 + Self-Correction)
* **주요 수정 사항**

  * **코드 최적화**: 불필요 오버헤드 제거 및 연산 효율 개선
  * **Spider 적합화**: 스키마/질의 복잡도 기반 프롬프트 구성 조정
  * **소형 LLM 지향 설정**: 컨텍스트 길이·예시 수·후처리 단계를 임베디드 제약(지연/메모리) 관점에서 튜닝

## 하이라이트

* **소형 LLM 초점**: 임베디드/엣지 적용을 위해 **품질–효율 균형**을 중점적으로 탐색
* **제약 기반 설계**: 상기 환경을 **상한 제약**으로 가정하고 추론 비용 체계적 관리
* **표준 평가**: **Spider Benchmark**로 다양한 스키마·질의 유형에 대한 일반화 성능 검증
* **재현성**: 제시한 워크스테이션에서 손쉽게 재현 가능하며 결과를 임베디드 관점에서 해석

## 사용 방법

1. 의존성을 설치합니다. (`requirements.txt` 참고)
2. 설치 가이드를 따라 환경을 설정합니다. (Ollama 및 필요한 모델 포함)
3. 제공 스크립트로 **Spider** 데이터셋 벤치마크를 실행합니다.

## 고지 및 감사의 말

* 본 프로젝트는 **DIN-SQL**의 소스를 참고·수정했습니다. 훌륭한 연구를 공개해 주신 개발진께 감사드립니다.
* **Spider Benchmark** 유지보수 팀의 노고에도 감사드립니다.

문의/기여는 언제든지 이슈 등록 또는 Pull Request로 부탁드립니다. 함께 **text-to-sql-sllm**을 발전시켜 주세요.

---

# text-to-sql-sllm | Text-to-SQL with Small LLMs on Spider (Embedded-Oriented)

**text-to-sql-sllm** targets **improving text-to-SQL with small LLMs** for embedded use. Using the **Spider Benchmark**, we focus on **accuracy and efficiency** under lightweight settings.

We build upon **DIN-SQL: Decomposed In-Context Learning of Text-to-SQL with Self-Correction**, applying **performance optimizations** and **benchmark adaptations**.
While the deployment target is embedded/edge, experiments were run on the environment below for reproducibility and treated as an **upper-bound constraint** during design and validation.

<img src="https://github.com/user-attachments/assets/6bba25a8-7b0d-41b1-84df-8cd3bb097780" width="400" height="400"/> <img src="https://github.com/user-attachments/assets/1c8a1a62-56bc-4c30-8edf-639f88e0573f" width="500" height="400"/>

## Environment (Upper-Bound Constraints)

### Operating System

* **Distributor ID**: Ubuntu
* **Description**: Ubuntu 22.04.5 LTS
* **Release**: 22.04

### Hardware Specifications

* **Architecture**: x86_64
* **CPU**: Intel(R) Core(TM) i9-14900KF

  * Modes: 32-bit, 64-bit
  * Address Sizes: 39 bits (physical), 48 bits (virtual)
  * Cores: 32 (On-line CPU(s): 0-31)
* **GPU**: NVIDIA GeForce RTX 4090

  * Memory: 24,564 MiB
  * Driver Version: 535.183.01
  * CUDA Version: 12.2

> We treat the above specs as **upper bounds** for development/evaluation, while optimizing for **small-LLM, embedded scenarios** (lower latency/memory). The pipeline reduces prompt/context length, limits example counts, and streamlines candidate generation/reranking.

### LLM Framework

* Primarily uses **Ollama** for consistent packaging and straightforward integration.

## Model Implementation

* **Base Architecture**: **DIN-SQL** (decomposed in-context learning with self-correction)
* **Key Modifications**

  * **Code Optimization** for computational efficiency
  * **Spider Adaptation** based on schema/query complexity
  * **Small-LLM Oriented Settings** for context length, example count, and post-processing under embedded constraints

## Highlights

* **Small-LLM Focus**: Balance **quality vs efficiency** for embedded/edge
* **Constraint-Driven Design**: Use the listed environment as **upper bounds** and manage inference cost
* **Standardized Evaluation**: Validate generalization on the **Spider Benchmark**
* **Reproducibility**: Easy to reproduce on the given workstation; interpret results for embedded targets

## Usage

1. Install dependencies (`requirements.txt`).
2. Set up the environment per the installation guide (including Ollama and required models).
3. Run the provided scripts to benchmark on the **Spider** dataset.

## Acknowledgments

* Thanks to the authors of **DIN-SQL** for releasing their pioneering work.
* Appreciation to the maintainers of the **Spider Benchmark** for a robust evaluation framework.

Issues and PRs are welcome—let’s keep improving **text-to-sql-sllm** together.
