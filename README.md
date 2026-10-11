# Reinforcement Learning for Risk-Based Information Security Contract Review

**Author:** A Powers  
**Course:** PhDAI 830 – Reinforcement Learning Project, Part 2

## Project Overview

This project explores how reinforcement learning can support information security contract reviews. I developed a Proximal Policy Optimization (PPO) agent that reviews simulated vendor scenarios and recommends security controls, determines whether a Vendor Security Assessment (VSA) is required, and assigns a risk classification.

The goal is to evaluate whether reinforcement learning can make these decisions more consistent while keeping human reviewers responsible for final decisions.

## Methodology

The project uses Python, Gymnasium, Stable-Baselines3, and PyTorch.

The environment includes six vendor characteristics and 12 sequential decisions:

- 10 security control recommendations
- 1 Vendor Security Assessment decision
- 1 risk classification (Low, Medium, or High)

I generated 240 simulated scenarios, using 192 for training and 48 for held-out testing. The PPO agent was trained for 150,000 timesteps.

## Results

The trained PPO agent achieved the following results on the 48 held-out simulated scenarios:

| Evaluation Metric | PPO Result |
|---|---|
| Security control accuracy | 91.46% |
| VSA decision accuracy | 100% |
| Risk classification accuracy | 100% |
| Missed required controls | 0 |
| Unnecessary controls | 41 |
| Invalid control actions | 0 |

The results show that the agent learned to follow the experimental review rules. However, the results do not establish that the model would perform equally well with actual vendor contracts.

## Repository Files

- `A_Powers_RL_ContractReview_Part2.ipynb` – Complete Google Colab notebook
- `a_powers_rl_contractreview_part2.py` – Python source code
- `ppo_contract_review.zip` – Trained PPO model
- `evaluation_summary.csv` – Evaluation metrics
- `held_out_scenario_results.csv` – Individual scenario results
- `held_out_accuracy.png` – Accuracy comparison chart
- `training_reward_curve.png` – Training performance chart
- `training_rewards.csv` – Training reward data
- `experiment_metadata.json` – Experiment configuration
- `requirements.txt` – Required Python packages

## How to Run the Project

### Google Colab

1. Download the `.ipynb` notebook from this repository.
2. Open Google Colab.
3. Upload the notebook.
4. Select **Runtime → Run all**.
5. Allow training and evaluation to complete.
6. Review the generated results and demonstration.

### Local Python

Install the dependencies:

`pip install -r requirements.txt`

Then run:

`python a_powers_rl_contractreview_part2.py`

Training may take several minutes depending on the computer.

## Limitations and Ethical Considerations

This project uses simulated scenarios and experimental security rules rather than actual vendor contracts or confidential company information. The agent learns decisions based on a predefined baseline, not independently verified security standards.

A real-world implementation would require additional testing, validated security policies, and human oversight.

## Future Improvements

Future development could include more realistic vendor scenarios, additional contract characteristics, comparisons with other reinforcement learning algorithms, and testing against expert-reviewed decisions.
