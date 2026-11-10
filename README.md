CFIN Reproducibility Package
This package contains the Python implementation of the Contextual Feature Interaction Network (CFIN) and the supporting code for student dropout prediction. It includes model and dataset configurations, training and evaluation scripts, analysis utilities, tests, and documentation.
Package contents
Path	Contents
[`src/cfin_repro/models/`](src/cfin_repro/models/)	CFIN with separate feature-group encoders and an inter-group context encoder, plus MLP and FT-Transformer implementations, tokenization, and loss functions.
[`src/cfin_repro/`](src/cfin_repro/)	Baseline adapters for logistic regression, random forest, XGBoost, MLP, TabNet, and FT-Transformer. Also includes dataset loading and splitting, preprocessing, training, Optuna tuning, out-of-fold threshold selection, evaluation metrics, statistical tests, and run provenance.
[`configs/`](configs/)	YAML configurations for dataset schemas, CFIN and baseline hyperparameters, the main experiment, and additional analyses.
[`scripts/`](scripts/)	Command-line entry points for data preparation, experiments, analyses, and package validation.
[`data/`](data/)	Dataset placement instructions and placeholder directories for raw and processed files. The dataset configurations cover StudentDropIndia (inels in the code) and UCI Predict Students’ Dropout and Academic Success (uci). Raw datasets must be obtained separately.
[`tests/`](tests/)	Tests for dataset splits, model behavior, metrics, threshold selection, statistical routines, and simulated reference files.
logs/simulated_reference/, results/simulated_reference/	Simulated examples of the log, CSV, and JSONL formats used by the package.
logs/real/, results/real/	Placeholder directories for files generated when the scripts are run.


Scripts
Script	Purpose
[`prepare_data.py`](scripts/prepare_data.py)	Validates dataset inputs and prepares processed files and split indices.
[`run_experiment.py`](scripts/run_experiment.py)	Runs configured model training, tuning, and evaluation.
[`run_analysis.py`](scripts/run_analysis.py)	Runs predictor-horizon analyses, school-grouped evaluations, component ablations, and feature-grouping comparisons.
[`run_shap.py`](scripts/run_shap.py)	Computes SHAP attributions at the feature and feature-group levels.
[`run_efficiency.py`](scripts/run_efficiency.py)	Profiles training time, inference latency, and model size.
[`run_statistics.py`](scripts/run_statistics.py)	Computes paired statistical comparisons from prediction files.
[`summarize_results.py`](scripts/summarize_results.py)	Aggregates per-seed evaluation records.
[`generate_reference_logs.py`](scripts/generate_reference_logs.py)	Generates simulated reference logs and example output files.
[`validate_package.py`](scripts/validate_package.py)	Checks package structure, anonymity, and output provenance.
[`build_manifest.py`](scripts/build_manifest.py)	Generates the package’s SHA-256 file manifest.


Environment and documentation
- [`pyproject.toml`](pyproject.toml) defines Python packaging metadata, optional dependencies, and test settings. [`requirements.txt`](requirements.txt) and [`environment.yml`](environment.yml) list dependencies for pip and Conda environments.
- [`REPRODUCIBILITY.md`](REPRODUCIBILITY.md) documents the experiment protocol, and [`data/README.md`](data/README.md) documents the expected input file locations.
- [`ANONYMITY_CHECKLIST.md`](ANONYMITY_CHECKLIST.md) lists checks for anonymous distribution. [`SIMULATED_LOGS_NOTICE.md`](SIMULATED_LOGS_NOTICE.md) describes the simulated reference files.
- MANIFEST.sha256 records package file checksums. .gitignore specifies local files and generated artifacts excluded from version control.
