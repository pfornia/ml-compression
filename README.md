# Machine Learnable Compression via "Alternating Transfer Learning"

By Paul Fornia, 2019

As part of a final project for my advanced machine learning course at Johns Hopkins, I undertook this small, non-published research project. 

In it, I exploring machine learnable image compression techniques by sharing initial layers of deep neural network. In other words, the motivation is to create a 
compressed image file, on which one can perform classification ML without first decompressing the image. 

For more details on the techniques and background, please see the accompanying paper `paper/alternating_transfer_learning_FORNIA.pdf`.

All corresponding code is contained in the notebook `code/alternating_transfers_pytorch`, and uses the pytorch framework. 

Very briefly, the concept of this approach is to create a hybrid network of a CNN classifier (to classify images), and and Autoencoder (to compress images).
The initial layers feed both these tasks. Then two sets of layers perform the last steps in each task. The network is trained by using transfer learning back and forth
between the tasks, until sufficient performance is simultaneously seen in both tasks. 

This approach is successful when the initial layers are already trained on data similar to the validation data (but still tested strictly on out-of-sample data). 
The approach is also tried while training initial layers on one domain of data (e.g., numbers), 
and latter layers on another domain (e.g., images of clothing), but success in this experiment is more limited.