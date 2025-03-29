# CycleGAN-W-Domain-Adaptation
using CycleGAN to address domain shift and fine-tuning a classifier on the adapted dataset is a highly effective method for bridging gaps between source and target domains


Why?

reduce the domain gap

Artistic Style to Photographic Images

Goal - Reduce the Domain Shift enough to be able to classificy the target domain images with just fine-tunning a model

CycleGAN

It consists of two generators (G and F) and two discriminators (D_X and D_Y).
The goal is to learn mappings between two domains, X → Y and Y → X, without needing paired examples

Models

need new definations

The generator translates images from one domain to another.
The discriminator classifies whether an image is real or generated.

CycleGAN Training Loop

The training loop for CycleGAN consists of alternating updates between two generator networks and two discriminator networks.

Epoch 1/10 - Loss_G: 6.5575, Loss_F: 6.3069, Loss_D_A: 0.0754, Loss_D_B: 0.2460
Epoch 2/10 - Loss_G: 7.1973, Loss_F: 6.9931, Loss_D_A: 0.2243, Loss_D_B: 0.3103
Epoch 3/10 - Loss_G: 8.0973, Loss_F: 7.7318, Loss_D_A: 0.1714, Loss_D_B: 0.2557
Epoch 4/10 - Loss_G: 8.9121, Loss_F: 8.6646, Loss_D_A: 0.2167, Loss_D_B: 0.2153
Epoch 5/10 - Loss_G: 8.0969, Loss_F: 7.7281, Loss_D_A: 0.0644, Loss_D_B: 0.2283
Epoch 6/10 - Loss_G: 10.6232, Loss_F: 10.4350, Loss_D_A: 0.0238, Loss_D_B: 0.2547
Epoch 7/10 - Loss_G: 11.3655, Loss_F: 10.8175, Loss_D_A: 0.0340, Loss_D_B: 0.3024
Epoch 8/10 - Loss_G: 9.3688, Loss_F: 8.8938, Loss_D_A: 0.0866, Loss_D_B: 0.2154
Epoch 9/10 - Loss_G: 9.2278, Loss_F: 8.6637, Loss_D_A: 0.0244, Loss_D_B: 0.3427
Epoch 10/10 - Loss_G: 7.6658, Loss_F: 7.4510, Loss_D_A: 0.0197, Loss_D_B: 0.2439


Translate Source Domain Images

Utilize the trained generators to convert all source domain images into the style of the target domain. The resulting adapted dataset will then serve as a foundation for downstream tasks such as classification.


Fine-Tune for Classification

Once the source domain images have been adapted to match the target domain's distribution, fine-tune a classification model using the new source domain images


Epoch [1/10], Loss: 3.6808
Epoch [2/10], Loss: 2.6575
Epoch [3/10], Loss: 1.6770
Epoch [4/10], Loss: 1.1055
Epoch [5/10], Loss: 0.5429
Epoch [6/10], Loss: 0.1904
Epoch [7/10], Loss: 0.1130
Epoch [8/10], Loss: 0.0803
Epoch [9/10], Loss: 0.0517
Epoch [10/10], Loss: 0.0544


Conclusion

The steady decline in training loss indicates strong model convergence with the adapted dataset loader, and with proper validation, this workflow can achieve excellent generalization on the target domain. By tackling domain shift creatively and efficiently, you're enhancing model robustness for real-world computer vision applications.
