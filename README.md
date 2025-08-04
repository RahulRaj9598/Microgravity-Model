# Microgravity Model - APAP Pharmacokinetic Analysis

This repository contains pharmacokinetic models for analyzing acetaminophen (APAP) behavior under microgravity conditions. The models incorporate gene expression data and physiologically-based pharmacokinetic (PBPK) modeling to understand drug metabolism and transport in space environments.

## 📁 Repository Contents

### Core Files
- **`APAPKineticModel.py`** - Main Python class implementing the acetaminophen PBPK model
- **`Acetominophen.ipynb`** - Primary Jupyter notebook for acetaminophen analysis
- **`APAP_model.ipynb`** - Additional Jupyter notebook with APAP model implementations
- **`Gene_expression_APAP_processed.csv`** - Gene expression data for APAP-related transporters and enzymes

### Model Features
- **Compartmental modeling**: Lumen, Liver, Plasma, Urine, Metabolites
- **Gene knockout analysis**: Simulate effects of reduced gene expression
- **Microgravity simulation**: Model drug behavior in space conditions
- **Transporter modeling**: MRP2, MRP3, OATP1B1, OATP1B3 transporters
- **Metabolism simulation**: CYP2E1, CYP1A2, CYP3A4 enzyme pathways

## 🚀 Getting Started

### Prerequisites

Make sure you have Python 3.7+ installed on your system. You can download it from [python.org](https://www.python.org/downloads/).

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/RahulRaj9598/Microgravity-Model.git
   cd Microgravity-Model
   ```

2. **Install required dependencies:**
   ```bash
   pip install numpy pandas matplotlib scipy jupyter
   ```

   Or install all dependencies at once:
   ```bash
   pip install -r requirements.txt
   ```
   *(Note: Create requirements.txt file if needed)*

### Alternative Installation using Conda

If you prefer using Conda:
```bash
conda install numpy pandas matplotlib scipy jupyter
```

## 📊 Usage

### Running Jupyter Notebooks

1. **Start Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

2. **Open the main analysis notebooks:**
   - `Acetominophen.ipynb` - Primary analysis notebook
   - `APAP_model.ipynb` - Model implementation and examples

### Using the Python Module

You can also import and use the model directly in Python:

```python
from APAPKineticModel import AcetaminophenPBPKModel

# Initialize the model
model = AcetaminophenPBPKModel()

# Load gene expression data for microgravity simulation
model.simulate_microgravity('Gene_expression_APAP_processed.csv', n_samples=1000)

# Run knockout analysis
model.knockout(rates=[0, 1, 2])  # Knockout specific genes

# Plot model results
model.plot_model(comp_no=2, title='APAP Concentration in Plasma')
```

### Example Analyses

1. **Basic Model Simulation:**
   ```python
   # Run basic pharmacokinetic simulation
   model.plot_model(comp_no=2)  # Plot plasma concentration
   ```

2. **Gene Knockout Analysis:**
   ```python
   # Analyze effect of gene knockouts
   model.plot_all_knockouts_analysis()
   ```

3. **Microgravity Simulation:**
   ```python
   # Simulate microgravity effects on drug metabolism
   model.simulate_microgravity('Gene_expression_APAP_processed.csv')
   ```

## 🔬 Model Components

### Compartments
- **Lumen**: Gastrointestinal tract
- **Liver**: Primary metabolism site
- **Plasma**: Systemic circulation
- **Urine**: Renal elimination
- **Metabolites**: Drug metabolites

### Transporters & Enzymes
- **MRP2/MRP3**: Efflux transporters (Liver → Lumen)
- **OATP1B1/OATP1B3**: Uptake transporters (Lumen → Liver)
- **CYP2E1/CYP1A2/CYP3A4**: Metabolic enzymes (Liver → Metabolites)
- **Renal clearance**: Elimination pathway (Plasma → Urine)

## 📈 Data Requirements

The model uses gene expression data in CSV format with the following structure:
- Gene expression levels for APAP-related transporters and enzymes
- Normalized expression values for microgravity conditions
- Compatible with the provided `Gene_expression_APAP_processed.csv`

## 🛠️ Troubleshooting

### Common Issues

1. **ImportError: No module named 'scipy'**
   ```bash
   pip install scipy
   ```

2. **Jupyter notebook not starting:**
   ```bash
   pip install --upgrade jupyter
   ```

3. **Matplotlib display issues:**
   ```bash
   pip install --upgrade matplotlib
   ```

### System Requirements
- **Python**: 3.7+
- **RAM**: 4GB minimum (8GB recommended for large simulations)
- **Storage**: 100MB for repository and dependencies

## 📚 Scientific Background

This model is designed for pharmacokinetic research in microgravity environments, specifically focusing on:
- Drug absorption and distribution changes in space
- Gene expression alterations affecting drug metabolism
- Transporter function modifications under microgravity
- Predictive modeling for astronaut medication protocols


## 📄 License

This project is available for research and educational purposes. Please cite appropriately if used in scientific publications.

---

**Note**: This model is for research purposes. Clinical applications require additional validation and regulatory approval.
