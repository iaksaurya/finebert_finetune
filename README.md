# FinBERT Fine-Tuning Report (Sentiment Classification)

## Overview
This project fine-tunes **FinBERT** for **3-class financial sentiment classification** (labels: 0, 1, 2).  
Goal: improve model performance on domain-specific financial/news text compared to the baseline (pre-trained) model.

---

## Baseline (Before Fine-Tuning)
**Accuracy:** 0.7118

**Classification Report:**
- Class 0: Precision **0.50**, Recall **0.76**, F1 **0.60** (Support: 1431)
- Class 1: Precision **0.58**, Recall **0.59**, F1 **0.58** (Support: 1918)
- Class 2: Precision **0.85**, Recall **0.74**, F1 **0.79** (Support: 6195)

**Macro Avg:** Precision **0.64**, Recall **0.70**, F1 **0.66**  
**Weighted Avg:** Precision **0.74**, Recall **0.71**, F1 **0.72**

Observation: strong bias toward Class 2 (majority class), with weaker precision/recall balance on minority classes.

---

## Fine-Tuned Results (After Fine-Tuning)
**Eval Loss:** 0.4395  
**Eval Accuracy:** 0.8618  
**Eval Precision:** 0.8625  
**Eval Recall:** 0.8618  
**Eval F1:** 0.8619  
**Epochs:** 3

**Runtime:** 7.54s  
**Throughput:** ~158.3 samples/sec

---

## Key Improvement
- Accuracy improved from **71.2% → 86.2%** (**+15.0 percentage points**).
- F1 improved to **~0.862**, indicating substantially better overall classification performance.

---

## Conclusion
Fine-tuning significantly improved FinBERT’s performance on the target dataset, reducing loss and increasing accuracy/F1 to production-usable levels. The model also supports efficient evaluation/inference throughput (~158 samples/sec).

---

## Next Steps (Optional)
- Add confusion matrix + per-class error analysis
- Try class-weighted loss / focal loss to further improve minority-class performance
- Run k-fold validation or test on a time-split dataset for robustness
