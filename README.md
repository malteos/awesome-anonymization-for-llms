# Awesome Anonymization for LLMs

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A comprehensive collection of resources for PII detection, anonymization, privacy-preserving techniques, and GDPR compliance in Large Language Model applications.

## Research Papers

### PII Detection and Recognition in Text

**Adaptive PII Mitigation Framework for Large Language Models** (2025)
- Context-aware PII detection with regulation-specific remediation strategies (GDPR, CCPA, PIPEDA)
- Achieves F1 score of 0.95 for passport numbers, outperforming Microsoft Presidio and Amazon Comprehend
- [arXiv Paper](https://arxiv.org/html/2501.12465v1)

**PIIvot: A Lightweight NLP Anonymization Framework for Question-Anchored Tutoring Dialogues** (2024)
- Novel approach reframing PII detection as potential-PII labeling with LLM-generated contextual replacements
- Preserves data integrity in educational settings while ensuring privacy
- [arXiv Paper](https://arxiv.org/html/2505.16931)

**The Text Anonymization Benchmark (TAB): A Dedicated Corpus and Evaluation Framework** (2022)
- Seminal benchmark comprising 1,268 ECHR court cases with comprehensive PII annotations
- Introduces novel evaluation metrics for privacy protection and utility preservation
- [Paper](https://aclanthology.org/2022.cl-4.19/) | [Dataset](https://huggingface.co/datasets/mattmdjaga/text-anonymization-benchmark-train)

**Can Large Language Models Really Recognize Your Name?** (2024)
- Demonstrates LLM recall drops 20-40% for ambiguous names vs recognizable ones
- Creates AmBench benchmark showing LLMs confuse human names with non-human entities
- [arXiv Paper](https://arxiv.org/html/2505.14549)

### Anonymization Methods and Techniques

**Unlocking the Potential of Large Language Models for Clinical Text Anonymization** (2024)
- Proposes six evaluation metrics for generative anonymization with LLMs in clinical settings
- Establishes LLM-based models as reliable alternatives to traditional approaches
- [Paper](https://aclanthology.org/2024.privatenlp-1.8/)

**Bootstrapping Text Anonymization Models with Distant Supervision** (2022)
- Uses knowledge graphs and distant supervision to automatically generate training data
- Eliminates manual annotation while following privacy-first k-anonymity principles
- [Paper](https://aclanthology.org/2022.lrec-1.476.pdf)

**Large Language Models are Advanced Anonymizers** (2024)
- Demonstrates LLMs' superior anonymization capabilities compared to commercial tools
- Introduces adversarial anonymization framework with privacy-utility trade-offs
- [arXiv Paper](https://arxiv.org/abs/2402.13846)

### Differential Privacy for LLMs

**Fine-tuning LLMs with user-level differential privacy** (2024)
- Google Research's technical implementation of user-level differential privacy for LLM fine-tuning
- Novel optimization techniques including Example-Level and User-Level Sampling
- [Google Research Blog](https://research.google/blog/fine-tuning-llms-with-user-level-differential-privacy/)

**VaultGemma: The world's most capable differentially private LLM** (2024)
- Technical deep-dive into training LLMs with differential privacy from scratch
- Includes scaling laws and compute-privacy-utility trade-offs
- [Google Research Blog](https://research.google/blog/vaultgemma-the-worlds-most-capable-differentially-private-llm/)

**Differential Privacy in Natural Language Processing: The Story So Far** (2022)
- Comprehensive survey of DP vulnerabilities and methodologies in NLP
- Essential reading for understanding DP applications to text data
- [arXiv Paper](https://arxiv.org/abs/2208.08140)

**Does Differential Privacy Impact Bias in Pretrained NLP Models?** (2024)
- First study examining how DP training affects bias in LLMs
- Shows DP can increase model bias against protected groups
- [arXiv Paper](https://arxiv.org/abs/2410.18749)

### Privacy-Preserving Training and Federated Learning

**FedNLP: Benchmarking Federated Learning Methods for Natural Language Processing Tasks** (2022)
- First comprehensive benchmarking framework for federated learning in NLP
- Universal interface between Transformer models and FL methods
- [Paper](https://aclanthology.org/2022.findings-naacl.13/)

**Privacy-Preserving Instructions for Aligning Large Language Models** (2024)
- First work analyzing privacy risks in LLM alignment annotation process
- Studies over 12,000 real-world user instructions for sensitive content
- [arXiv Paper](https://arxiv.org/html/2402.13659v2)

### Membership Inference Attacks

**Do Membership Inference Attacks Work on Large Language Models?** (2024)
- Large-scale evaluation showing MIAs on LLMs barely outperform random guessing
- Analyzes 160M to 12B parameter models with comprehensive attack evaluation
- [arXiv Paper](https://arxiv.org/abs/2402.07841)

**User Inference Attacks on Large Language Models** (2023)
- Introduces efficient user inference attack scaling to LLMs
- Demonstrates user-level privacy risks in fine-tuning scenarios
- [arXiv Paper](https://arxiv.org/html/2310.09266v2)

## Tools & Libraries

### PII Detection Frameworks

**Microsoft Presidio**
- Most comprehensive open-source framework for detecting, redacting, and anonymizing sensitive data
- Context-aware detection using spaCy, 50+ predefined entity types, multi-language support
- [GitHub](https://github.com/microsoft/presidio) | [Documentation](https://microsoft.github.io/presidio/)

**DataFog Python**
- Lightning-fast PII detection with 190x performance advantage (2.4ms for 10KB text)
- Multiple engines: Regex, spaCy, GLiNER with smart cascading
- [GitHub](https://github.com/DataFog/datafog-python)

**PII Masker (HydroXai)**
- Advanced AI-powered detection using fine-tuned DeBERTa-v3 with 1024 token support
- High-precision detection with ~4% performance improvement over base models
- [GitHub](https://github.com/HydroXai/pii-masker)

**PII Codex**
- Research-focused package for PII detection, categorization, and severity assessment
- Built on Microsoft Presidio with NIST/DHS categorizations and risk scoring

**DarkMoon Privacy Gateway**
- Self-hosted proxy that tokenizes sensitive values (IPs, hostnames, credentials, PII) into deterministic, reversible placeholders before prompts reach the LLM
- The model never sees real data; placeholders are restored in the response, backed by an anti-exfiltration command gateway (open-source, GPL-3.0)
- [GitHub](https://github.com/ASCIT31/Dark-Moon)
- [GitHub](https://github.com/EdyVision/pii-codex)

### Privacy-Preserving ML Frameworks

**PySyft**
- Comprehensive library for secure, private Deep Learning using federated learning and differential privacy
- Multi-Party Computation (MPC), homomorphic encryption, remote data science
- [GitHub](https://github.com/OpenMined/PySyft)

**TensorFlow Privacy**
- Google's library for training ML models with differential privacy
- DP-SGD optimizers, privacy accounting, membership inference attack defenses
- [GitHub](https://github.com/tensorflow/privacy)

**OpenDP Library & SmartNoise**
- Microsoft-Harvard partnership providing comprehensive differential privacy toolkit
- SmartNoise SQL for DP queries, synthetic data generation, Rust core with Python bindings
- [GitHub Core](https://github.com/opendp/smartnoise-core) | [SDK](https://github.com/opendp/smartnoise-sdk)

**Opacus (PyTorch Differential Privacy)**
- Meta AI's library for training PyTorch models with differential privacy
- Drop-in replacement for PyTorch optimizers with minimal code changes
- [GitHub](https://github.com/pytorch/opacus)

**IBM Differential Privacy Library (diffprivlib)**
- General-purpose differential privacy library with scikit-learn compatible API
- Multiple DP mechanisms with easy integration for existing workflows
- [GitHub](https://github.com/IBM/differential-privacy-library)

### Synthetic Data Generation

**Faker**
- Most popular library for generating fake data with 150+ providers
- Localization support for 50+ countries, extensible provider system
- [GitHub](https://github.com/joke2k/faker)

**SDV (Synthetic Data Vault)**
- Comprehensive synthetic data generation ecosystem for single-table, multi-table, time-series
- Privacy controls, evaluation metrics, production-ready implementations
- [GitHub](https://github.com/sdv-dev/SDV)

**Gretel Synthetics**
- Neural network-based synthetic data generation with differential privacy support
- High utility synthetic data with privacy guarantees for production use
- [GitHub](https://github.com/gretelai/gretel-synthetics)

## Models & Datasets (HuggingFace)

### PII Detection Models

**iiiorg/piiranha-v1-detect-personal-information**
- State-of-the-art multilingual PII detection (99.44% accuracy) across 17 PII types and 6 languages
- Fine-tuned microsoft/mdeberta-v3-base with exceptional precision (98.48%) and recall (98.27%)
- [HuggingFace Model](https://huggingface.co/iiiorg/piiranha-v1-detect-personal-information)

**beki/flair-pii-distilbert**
- 5-class NER model trained on protocol trace data (F1-Score: 0.9522)
- Specialized for detecting PER, LOC, ORG, DATE_TIME, NRP entities in network traces
- [HuggingFace Model](https://huggingface.co/beki/flair-pii-distilbert)

**betterdataai/PII_DETECTION_MODEL**
- Lightweight multilingual PII detection covering 29 classes across 7 languages
- Built on Qwen2-0.5B for low latency with long document support
- [HuggingFace Model](https://huggingface.co/betterdataai/PII_DETECTION_MODEL)

### Datasets

**Text Anonymization Benchmark (TAB)**
- Gold standard benchmark with European Court Documents and multiple annotator labels
- Comprehensive framework for evaluating anonymization techniques
- [HuggingFace Dataset](https://huggingface.co/datasets/mattmdjaga/text-anonymization-benchmark-train)

**beki/privy**
- Synthetic PII dataset with 60+ PII types in protocol trace formats (JSON, SQL, HTML, XML)
- Generated using Privy tool from OpenAPI specifications for comprehensive training
- [HuggingFace Dataset](https://huggingface.co/datasets/beki/privy)

**allenai/WildChat-4.8M**
- Large conversation dataset with PII detection and anonymization features
- Includes redaction indicators and anonymized content for conversational AI training
- [HuggingFace Dataset](https://huggingface.co/datasets/allenai/WildChat-4.8M)

### Demo Applications

**beki/pii-anonymizer**
- Interactive Streamlit app using Presidio framework with custom PII models
- Real-time PII detection and anonymization demonstration
- [HuggingFace Space](https://huggingface.co/spaces/beki/pii-anonymizer)

**haakohu/deep_privacy2**
- Advanced computer vision anonymization for faces and full-body anonymization
- Comprehensive human anonymization using multiple detection networks
- [HuggingFace Space](https://huggingface.co/spaces/haakohu/deep_privacy2)

## Tutorials & Implementation Guides

### Getting Started

**Microsoft Presidio Framework Tutorial**
- Comprehensive guide for building PII detection systems with Python API documentation
- Custom recognizer creation, multi-language support, context-aware enhancement
- [Documentation](https://microsoft.github.io/presidio/analyzer/)

**Building a Customized PII Anonymizer with Microsoft Presidio**
- Step-by-step tutorial for implementing custom multi-language PII anonymizer
- Practical code examples with Norwegian National ID detection case study
- [Towards Data Science](https://towardsdatascience.com/building-a-customized-pii-anonymizer-with-microsoft-presidio-b5c2ddfe523b/)

**Detecting and Masking PII with Piiranha**
- Tutorial for using state-of-the-art Piiranha model with 99.44% accuracy
- Python implementation examples covering 17 PII entity types
- [Medium Tutorial](https://medium.com/@danushidk507/detecting-and-masking-personally-identifiable-information-pii-with-piiranha-6938c2629b64)

### Advanced Privacy Techniques

**Data Anonymization Techniques for Secure LLM Utilization**
- Comprehensive guide covering k-anonymity, differential privacy, synthetic data generation
- Specific techniques for LLM deployments with GDPR compliance considerations
- [Protecto AI Guide](https://www.protecto.ai/blog/data-anonymization-techniques-for-secure-llm-utilization)

**Using Local LLMs to Anonymize Data for Remote LLMs**
- Innovative approach using smaller local LLMs (llama 3.1 8B) for pre-anonymization
- Detailed prompt engineering for entity replacement and de-anonymization workflows
- [Medium Guide](https://medium.com/@scmstorz/using-a-small-local-llm-llama-3-1-1d13223b2bbe)

### Cloud Platform Implementation

**Google Cloud PII De-identification Pipeline**
- Enterprise-grade implementation using Google Cloud DLP for automated data transformation
- Dataflow pipelines, format-preserving encryption, streaming data processing
- [Google Cloud Architecture](https://cloud.google.com/architecture/de-identification-re-identification-pii-using-cloud-dlp)

**Azure AI PII Detection Service**
- Official documentation for Azure's cloud-based PII detection with API references
- Conversation PII detection, multi-language support, batch processing capabilities
- [Microsoft Learn](https://learn.microsoft.com/en-us/azure/ai-services/language-service/personally-identifiable-information/overview)

**AWS PII Detection with Comprehend and Macie**
- HIPAA-compliant PII/PHI detection using AWS services with S3 Object Lambda integration
- Healthcare data protection patterns and compliance best practices
- [AWS Industries Blog](https://aws.amazon.com/blogs/industries/common-techniques-to-detect-phi-and-pii-data-using-aws-services/)

### Case Studies

**Real-World LLM Project Anonymization**
- AI-powered document processing system achieving 95% processing time reduction
- Modular anonymization architecture with AWS deployment and business impact metrics
- [The Software House Case Study](https://tsh.io/blog/pii-anonymization-in-llm-projects/)

**Medical Text Anonymization with Local LLMs**
- Comprehensive anonymization tool for medical text using locally deployed LLMs
- HIPAA vs GDPR compliance with quantitative evaluation and precision metrics
- [NEJM AI Paper](https://ai.nejm.org/doi/full/10.1056/AIdbp2400537)

## Frameworks & Standards

### Regulatory Guidance

**European Data Protection Board (EDPB) Opinion 28/2024 on AI Models**
- Comprehensive 35-page guidance on when AI models can be considered anonymous
- Three-step anonymity test and mitigating measures for GDPR compliance
- [Official Document](https://www.edpb.europa.eu/system/files/2024-12/edpb_opinion_202428_ai-models_en.pdf)

**UK ICO AI and Data Protection Guidance**
- Updated guidance restructured around GDPR principles for AI systems
- AI Risk Toolkit for practical privacy risk assessment during development
- [ICO Guidance](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/)

**CNIL AI Development Recommendations (2025)**
- Latest French recommendations on AI system development and individual rights facilitation
- PANAME project for privacy auditing of AI models with sector-specific guidance
- [CNIL Guidance](https://www.cnil.fr/en/ai-cnil-finalises-its-recommendations-development-artificial-intelligence-systems)

### Technical Standards

**ISO/IEC 29100:2024 - Privacy Framework**
- Updated international privacy framework with common terminology and principles
- Technology-neutral approach applicable to all AI systems processing PII
- [ISO Standard](https://www.iso.org/standard/85938.html)

**ISO/IEC 27559:2022 - Privacy Enhancing Data De-identification**
- Framework for identifying and mitigating re-identification risks in de-identified data
- Critical for AI model training data anonymization and attack prevention
- [ISO Standard](https://www.iso.org/standard/80392.html)

### Risk Management Frameworks

**NIST AI Risk Management Framework (AI RMF 1.0)**
- Comprehensive framework with four core functions: GOVERN, MAP, MEASURE, MANAGE
- Seven trustworthy AI characteristics including "privacy enhanced" considerations
- [NIST Framework](https://www.nist.gov/itl/ai-risk-management-framework)

**Google Secure AI Framework (SAIF)**
- Six core elements for securing AI systems with integrated privacy protections
- Security-by-default approach for ML and generative AI applications
- [Google SAIF](https://safety.google/cybersecurity-advancements/saif/)

### Privacy by Design Implementation

**Privacy by Design Seven Foundational Principles**
- Essential framework for embedding privacy into AI system architecture from design phase
- Proactive approach with privacy as default setting throughout development lifecycle

**DPIA Templates for AI Systems**
- EDPB, ICO, and CNIL templates specifically adapted for AI system risk assessment
- Step-by-step processes for identifying and mitigating privacy risks in LLM development

## Industry Resources

### Privacy Engineering Tools

**Privacy Meter - ML Privacy Auditing**
- Open-source library for quantitative privacy risk assessment through inference attacks
- Membership inference, range membership inference, and attribute inference testing
- [GitHub](https://github.com/privacytrustlab/ml_privacy_meter)

**OWASP AI Security and Privacy Guide**
- Practical privacy engineering guidance throughout the AI/ML system lifecycle
- Data minimization principles and privacy-enhancing technology implementations
- [OWASP Project](https://owasp.org/www-project-ai-security-and-privacy-guide/)

### Compliance Checklists

**GDPR Article 25 Implementation for AI**
- Data protection by design and by default requirements with technical measures
- Lifecycle approach to privacy protection in AI system development

**Legitimate Interest Assessment for AI Training**
- Three-step framework for using legitimate interest as legal basis for LLM training
- AI-specific considerations and mitigating measures per EDPB guidelines

## Getting Started

For organizations new to privacy-preserving LLM development, we recommend this implementation order:

1. **Start with PII Detection**: Deploy Microsoft Presidio or DataFog for immediate PII identification
2. **Implement Privacy by Design**: Follow NIST AI RMF and EDPB guidelines for system architecture  
3. **Conduct DPIAs**: Use regulatory templates to assess privacy risks in your AI development
4. **Explore Differential Privacy**: Begin with TensorFlow Privacy or Opacus for training privacy
5. **Consider Synthetic Data**: Evaluate SDV or Gretel Synthetics for privacy-safe training data

## Contributing

This awesome list focuses on practical, implementable resources alongside theoretical foundations. We prioritize recent developments (2022-2024) while including seminal works that remain relevant. Resources are selected based on:

- **Practical utility** for developers and researchers
- **Technical rigor** and peer review quality  
- **Active maintenance** and community support
- **GDPR compliance** relevance and regulatory alignment
- **Open source availability** when possible

---

*This resource collection is maintained for educational and research purposes. Always consult with legal experts for specific GDPR compliance requirements in your jurisdiction and use case.*


## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
