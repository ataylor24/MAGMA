# MAGMA: Multistep AlGorithMic ReAsoning Benchmark

🎉🎉PLEASE SEE THE UPDATED VERSION HERE🎉🎉: https://github.com/ataylor24/MAGMA_v2

## Paper
Are Large-Language Models Graph Algorithmic Reasoners? [[pdf](https://arxiv.org/pdf/2410.22597)]

## Summary

The MAGMA Benchmark is designed to evaluate the performance of large language models (LLMs) on classical graph algorithms using intermediate steps. Despite advances in LLMs, they exhibit significant limitations in structured, multistep reasoning tasks, particularly those involving explicit graph structures. Our benchmark addresses this gap by evaluating state-of-the-art LLMs on five fundamental algorithms: BFS, DFS, Dijkstra's, Floyd-Warshall, and Prim's MST.

We are actively updating this benchmark! Please reach out to the contact email below with any update requests/bug fixes.

## Features

- **Comprehensive Benchmark:** Evaluates LLM performance on classical graph algorithms.
- **Intermediate Steps Evaluation:** Focuses on the accuracy of intermediate reasoning steps.
- **Multiple Algorithms:** Includes BFS, DFS, Dijkstra's, Floyd-Warshall, and Prim's MST.
- **Advanced Prompting Techniques:** Explores advanced prompting techniques and algorithmic instructions.

## Installation Process

### Prerequisites

- Python 3.10 or higher

### Clone the Repository

```bash
git clone https://github.com/yourusername/LLM-CLRS-Graph-Reasoning-Benchmark.git
cd LLM-CLRS-Graph-Reasoning-Benchmark
```

### Create a Conda Environment

To create a Conda environment with the required dependencies, run the following command:

```bash
conda env create --file environment.yml
```

This will create a new Conda environment with all the dependencies specified in the `environment.yml` file.

### Activate the Conda Environment

Activate the newly created environment using:

```bash
conda activate nar2
```

### Training baseline models

An example of a script used to run the benchmark on the included algorithms is included in `run_scripts`.

```bash
bash run_scripts/bfs_CoT.sh
```
### Running inference with trained models 

An example of a script used to run the benchmark on a selected algorithm is included in `inference_scripts`.

```bash
bash inference_scripts/bfs_CoT.sh
```

### Configuration

You can customize the model training settings using the configuration file `configuration_example/config_qlora.yaml`.

## Performance Metrics

The benchmark uses the following metrics:
- **Exact Match Accuracy:** Measures the correctness of the final output. (Primary metric used in the paper)
- **F1 Score** Measures the partial correcness of the final output.
Note: We also include 'partial' accuracies that provide credit for outputs that are similar to the desired output but lack the full response template.

For both the Exact Match Accuracy and F1 score metrics, we provide the following variants:
- **Intermediate Steps Accuracy:** Evaluates the performance of models on intermediate steps.
- **Final Step Accuracy** Evaluates the performance of models on only the final step.
- **Trajectory Accuracy** Evaluates the performance of models on the full trajectory (i.e. intermediate steps & final step)
- **Independent Accuracy** Evaluates the performance of models on each independent inference (trajectory agnostic).

## Contributing

We welcome contributions to improve this benchmark. Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

See `data_generation` for further details.

## Reproducibility

Seed used = 100898

BFS Llama3 _r_ & _alpha_: 8

Otherwise, baseline data generation and model training follow default settings for parameters.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

Data used in the benchmark is translated from the CLRS benchmark, which can be found here: https://github.com/google-deepmind/clrs

Model training adapted from the Huggingface Alignment Handbook: https://github.com/huggingface/alignment-handbook.git

## Contact Information

For questions or feedback, please open an issue or contact us at `ataylor2@cs.ucla.edu`.

---

Thank you for using the LLM-CLRS Graph Reasoning Benchmark! We hope this benchmark helps advance the understanding and capabilities of large language models in structured reasoning tasks.

