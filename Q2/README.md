# Urdu Poetry Generation - Project Report

## Contents

This folder contains the complete LaTeX report for the "Comparative Analysis of Sequence-to-Sequence Models and Optimization Algorithms for Urdu Poetry Text Generation" project.

### Files

- **urdu_poetry_report.tex** - Main LaTeX report file
- **All PNG files** - Visualizations and training curves used in the report

### Report Structure

The report includes the following sections:

1. **Abstract** - Summary of the project and key findings
2. **Problem Statement** - Background, problem definition, and objectives
3. **Methodology** - Dataset, preprocessing, model architectures, and training configuration
4. **Experiments and Results**
   - Main comparison experiments (9 model-optimizer combinations)
   - Visualization of results (heatmaps, loss curves, time analysis)
   - Training curves for all models
   - Hyperparameter tuning experiments
   - Text generation results
   - Qualitative evaluation
5. **Discussion**
   - Answers to all research questions
   - Interpretation of findings
   - Analysis of failure cases
6. **Conclusion**
   - Summary of findings
   - Best configuration recommendation
   - Contributions
   - Future work

### Key Findings

- **Best Model:** Transformer + SGD (Qualitative Score: 3.66/5, Perplexity: 357.99)
- **Best Sample:** "دل سے زندگی کا نام ہے" (Life's name is from the heart) - Score: 4.8/5
- **Worst Model:** RNN + RMSprop (Qualitative Score: 1.50/5, Perplexity: 1075.96)

### Compilation Instructions

To compile the LaTeX report:

#### Prerequisites
1. Install a LaTeX distribution:
   - **Windows:** MiKTeX or TeX Live
   - **Mac:** MacTeX
   - **Linux:** TeX Live

2. Install required packages:
   - polyglossia (for Urdu text support)
   - Noto Nastaliq Urdu font

#### Compilation

**Using pdflatex:**
```bash
cd report
pdflatex urdu_poetry_report.tex
pdflatex urdu_poetry_report.tex  # Run twice for references
```

**Using XeLaTeX (recommended for Urdu text):**
```bash
cd report
xelatex urdu_poetry_report.tex
xelatex urdu_poetry_report.tex  # Run twice for references
```

**Using Overleaf:**
1. Upload all files to Overleaf
2. Set compiler to XeLaTeX
3. Compile

### Images Included

1. **perplexity_heatmap.png** - Heatmap showing perplexity across all model-optimizer combinations
2. **test_loss_comparison.png** - Bar chart comparing test loss
3. **training_time_comparison.png** - Bar chart comparing training times
4. **tradeoff_analysis.png** - Scatter plot showing time vs performance tradeoff
5. **RNN_Adam_curves.png** - Training/validation curves for RNN + Adam
6. **RNN_RMSprop_curves.png** - Training/validation curves for RNN + RMSprop
7. **RNN_SGD_curves.png** - Training/validation curves for RNN + SGD
8. **LSTM_Adam_curves.png** - Training/validation curves for LSTM + Adam
9. **LSTM_RMSprop_curves.png** - Training/validation curves for LSTM + RMSprop
10. **LSTM_SGD_curves.png** - Training/validation curves for LSTM + SGD
11. **Transformer_Adam_curves.png** - Training/validation curves for Transformer + Adam
12. **Transformer_RMSprop_curves.png** - Training/validation curves for Transformer + RMSprop
13. **Transformer_SGD_curves.png** - Training/validation curves for Transformer + SGD

### Report Statistics

- **Total Pages:** ~30-35 pages (when compiled)
- **Total Figures:** 13 figures
- **Total Tables:** 6 tables
- **Samples Evaluated:** 136 generated poetry samples
- **Model Combinations:** 9 (3 architectures × 3 optimizers)

### Citation

If you use this work, please cite:

```
Comparative Analysis of Sequence-to-Sequence Models and Optimization Algorithms 
for Urdu Poetry Text Generation
Deep Learning Project - Part 2
December 2025
```

### Contact

For questions or issues with the report, please refer to:
- Main project folder: `../`
- Evaluation file: `../generation_evaluation.txt`
- Results folder: `../results/`
- Notebook: `../q11.ipynb`

---

**Note:** The report follows all requirements specified including:
- Complete methodology description
- All 9 model-optimizer combinations
- Quantitative and qualitative evaluation
- Hyperparameter tuning results
- Generation samples with evaluation
- Answers to all research questions
- Failure mode analysis
- Visualizations and tables
