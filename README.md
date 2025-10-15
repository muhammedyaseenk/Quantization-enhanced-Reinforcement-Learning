# Quantization-enhanced-Reinforcement-Learning
QeRL is a Quantization-enhanced RL framework for large language models. It combines NVFP4 quantization with LoRA, introduces Adaptive Quantization Noise (AQN) to boost exploration, speeds up rollouts by 1.5×, and enables RL training of 32B models on a single 80GB GPU, matching full fine-tuning on GSM8K and MATH.

#### QeRL introduces an Adaptive Quantization Noise (AQN) mechanism :
In RL, when we quantize the model (reduce precision), it naturally adds small random noise to its predictions. The RL algorithm then controls this randomness (entropy) to balance exploration and accuracy during training.

![rank speed](assets/rank_speed.png)
##### Quantization noise brings higher initialized entropy, which encourages exploration in RL training, accelerating the increase of reward.

![alt text](assets/qerl.png)
![alt text](assets/performance.png)
![alt text](assets/lora.png)
##### The framework of QeRL. QeRL utilize NVFP4 for low-cost and fast LoRA training with injected adaptive quantization noise.

![alt text](assets/image.png)
![alt text](assets/da_gr.png)
##### In GRPO, quantized model delivers better converged reward score and faster reward growth.

![alt text](assets/curve.png)
##### Training reward of Qwen2.5-32B-Instruct model.

### Installation
Requirements: my repo on the following setup:  Nvidia GPU supports NVFP4 weight format with triton (e.g. RTX 5090, H100, B100...). Linux operating system. 64 GB RAM.

Environment: Create a conda environment and install dependencies:
