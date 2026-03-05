# ML Inverse Pulse Design for Quantum Control in SiC Qubits

This repository contains a machine learning and quantum control codebase developed to optimize microwave pulses for Silicon Carbide (SiC) spin-defect qubits. The software addresses signal distortion in a SiC + Amplifier system by applying both Neural Network surrogates and Gradient Ascent Pulse Engineering (GRAPE).

This work was conducted as part of the Future Scientist Exchange Program (FuSEP) 2025 at the Key Laboratory of Quantum Information, University of Science and Technology of China (USTC).

## 🚀 Key Features

* **Neural Network Surrogate (`NN_Output_Gaussian_Pi_Pulses.ipynb`):** A PyTorch deep learning pipeline that solves the inverse design problem. It maps target output envelopes (ideal Gaussians) back to their required pre-distorted input waveforms.
* **Custom Loss Optimization:** The training loop utilizes custom weighted Mean Squared Error (MSE) loss functions and dynamic learning rate scheduling (`ReduceLROnPlateau`) to strictly penalize waveform deviations.
* **Quantum Control with GRAPE (`GRAPE_Pulse_Design_SiC_defect_Qubits.ipynb`):** Implementation of Gradient Ascent Pulse Engineering using `qutip` (Quantum Toolbox in Python) to design robust control pulses that maximize spin-defect coherence times within a two-level Hamiltonian system.

## 📊 Results

The ML inverse-designed pulses achieved a **40% lower average error** compared to standard Gaussian inputs, successfully mitigating amplifier distortion and improving control fidelity.

## 🛠️ Installation & Requirements

To run the notebooks locally, ensure you have the following dependencies installed:

```bash
pip install torch numpy scipy scikit-learn matplotlib qutip pandas
