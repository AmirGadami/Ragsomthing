# 🛡️ TAVo: Tor Application Detection with Voting Critic

**Published at**: 36th Canadian Conference on Artificial Intelligence (Canadian AI 2023)  
**Authors**: Gautam Vira, Samik Pal, Behdad Mansouri, Amirhossein Ghadami, Paula Branco  
**Conference Date**: June 5, 2023  
**DOI/URL**: [caiac.pubpub.org/pub/5grrmohq](https://caiac.pubpub.org/pub/5grrmohq)  
**License**: [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)

---

## 📄 Abstract

With increasing use and traffic in **The Onion Router (TOR)** network, it's essential to identify and monitor traffic types for performance and security. **TAVo** (Tor Application detection with a Voting-classifier Critic) is a novel two-layer classification framework that:

- Detects whether network traffic uses TOR.
- Identifies the **type of application** generating TOR traffic.
- Uses a **Voting Critic** to handle low-confidence predictions, improving classification performance without compromising efficiency.

---

## 🧠 Methodology

TAVo consists of a **two-stage classification architecture**:

1. **Stage 1**: Classifies traffic as **TOR vs. Non-TOR**.
2. **Stage 2**: Further classifies TOR traffic by **application type** (e.g., browsers, messaging apps, file-sharing services).
3. **Voting-Classifier Critic**:
   - Activates only when the second layer outputs low-confidence predictions.
   - Confirms or corrects predictions by combining multiple classifiers.
   - Ensures high precision on difficult samples without heavy computational load.

---

## 📊 Results

| Metric          | Without Critic | With Critic |
|-----------------|----------------|-------------|
| **F1 Score**    | 84%            | **91%**     |
| **Efficiency**  | High           | High (Critic only used when needed) |

TAVo demonstrates strong generalization across diverse traffic patterns while maintaining lightweight inference performance.

---

## 🏗️ Architecture Summary

     ┌────────────────┐
     │ Packet Capture │
     └──────┬─────────┘
            │
    ┌───────▼────────┐
    │   Layer 1      │
    │ TOR / Non-TOR  │
    └───────┬────────┘
            │
    ┌───────▼────────┐
    │   Layer 2      │
    │  App Detection │
    └───────┬────────┘
            │  (Low confidence?)
       ┌────▼────┐
       │ Critic  │ <── Voting Ensemble (Meta-classifier)
       └─────────┘


---

## 🌐 Citation

```bibtex
@inproceedings{ghadami2023tavo,
  title={TAVo: Tor Application Detection with Voting Critic},
  author={Vira, Gautam and Pal, Samik and Mansouri, Behdad and Ghadami, Amirhossein and Branco, Paula},
  booktitle={Proceedings of the 36th Canadian Conference on Artificial Intelligence},
  year={2023},
  url={https://caiac.pubpub.org/pub/5grrmohq}
}