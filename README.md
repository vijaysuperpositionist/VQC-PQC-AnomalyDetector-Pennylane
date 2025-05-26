├── data/
│ ├── grover_anomaly_subset.csv # Subset of dataset with labeled anomalies (used in Grover)
│ └── original_dataset.csv # Full PQC feature dataset (optional)
├── grover_anomaly_search.ipynb # Grover's Algorithm implementation using PennyLane
├── pennylane_vqc_anomaly_classifier.ipynb # VQC model with feature embedding and training
├── README.md

yaml
Always show details

Copy

---


## 🔍 Grover’s Algorithm Overview

- **Qubits**: 5 (for 32 search states)
- **Oracle**: Marks anomaly indices (label = 1)
- **Amplification**: Grover iterations amplify the anomalous state
- **Output**: Identified most probable anomalous row

> Grover detected anomaly at state `|10100⟩` (index 20).

---


## 🧠 VQC Model Overview

- **Qubits**: 4
- **Embedding**: `AngleEmbedding` with PCA-reduced features
- **Ansatz**: `StronglyEntanglingLayers`
- **Loss Function**: Square loss on `PauliZ(0)` expectation value
- **Performance**: Perfect classification on the test set

> Loss reduced from 0.1053 → 0.0293 over 50 training steps.

---


## 📈 Results Summary

| Component      | Result                                    |
|----------------|--------------------------------------------|
| Grover Output  | State `|10100⟩` → Index 20 (0.2583 prob)   |
| VQC Accuracy   | 100% on test batch (class 0 only)          |
| Dataset        | 10 PQC metrics + anomaly label (0 or 1)    |

---


## 🛠️ Dependencies

- `pennylane`
- `matplotlib`
- `numpy`
- `scikit-learn`

Install via:

```bash
pip install pennylane matplotlib numpy scikit-learn
🧪 How to Run
Run grover_anomaly_search.ipynb to identify probable anomaly locations.

Run pennylane_vqc_anomaly_classifier.ipynb to classify using trained VQC.

📚 References
PennyLane Documentation

Grover’s Algorithm (Textbook)

Quantum Machine Learning papers (QML + VQC)

MIT License © 2025 VijaySuperPositionist
"""

readme_path = Path("/mnt/data/README.md")
readme_path.write_text(readme_text)
readme_path.as_posix()
