# Bag of Tricks for Learning with Noisy Labels

This project is a collection of common tricks for learning with noisy labels in the field of machine learning. Noisy labels refer to labels that contain errors or inaccuracies, which can significantly affect the performance of machine learning models. The tricks included in this project aim to mitigate the negative impact of noisy labels and improve the robustness of machine learning models.

In this repo:

- We provide code for constructing noisy data, including symmetric, asymmetric, instance, and real noise.

- All experiments are conducted on the CIFAR dataset. The CIFAR dataset has 50,000 images, and the image size is 32x32, so it can be run on a single GPU.


The following is a brief introduction to the tricks used in this project:

- `EMA`: a technique for updating the weights of a teacher model by taking an exponential moving average of the current student's weights and the teacher's previous weights.
- `Mix-up`: a technique for combining two training examples and their labels to create a convex combination of the two examples and labels.
- `Label smoothing`: a regularization technique that replaces the hard 0/1 targets with soft targets.
- `RandAugment`: a data augmentation method that applies a series of random image transformations with different intensities.
- `AutoAugment`: a data augmentation method that uses a reinforcement learning algorithm to learn the best data augmentation policy for a given dataset.
- `Regularization`: include class balance regularization.


## Experiment

The project uses ResNet + cross-entropy as baseline, and all tricks are evaluated on top of this baseline. This section provides a brief introduction, and detailed descriptions and experimental results can be found in the trick-gallery.md file in the Document directory.

We conducted extensive experiments on the CIFAR dataset, which is a popular benchmark dataset for image classification. The results were the mean and standard deviation after three repetitions and the noise types and corresponding noise rates of the constructed dataset can be found in the table below. 

<table class="tg">
<thead>
  <tr>
    <th  align="center" class="tg-baqh">Dataset</th>
    <th  align="center" class="tg-baqh" colspan="8">CIFAR-10</th>
    <th  align="center" class="tg-baqh" colspan="7">CIFAR-100</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td  align="center" class="tg-baqh">Noise type</td>
    <td  align="center" class="tg-baqh" colspan="3">Symmetric</td>
    <td  align="center" class="tg-baqh">Asym.</td>
    <td  align="center" class="tg-baqh" colspan="2">Instance</td>
    <td  align="center" class="tg-baqh" colspan="2">Real</td>
    <td  align="center" class="tg-baqh" colspan="3">Symmetric</td>
    <td  align="center" class="tg-baqh">Asym.</td>
    <td  align="center" class="tg-baqh" colspan="2">Instance</td>
    <td  align="center" class="tg-baqh">Real</td>
  </tr>
  <tr>
    <td  align="center" class="tg-baqh">Noise rate</td>
    <td  align="center" class="tg-baqh">0.2</td>
    <td  align="center" class="tg-baqh">0.4</td>
    <td  align="center" class="tg-baqh">0.6</td>
    <td  align="center" class="tg-baqh">0.4</td>
    <td  align="center" class="tg-baqh">0.2</td>
    <td  align="center" class="tg-baqh">0.4</td>
    <td  align="center" class="tg-baqh">aggre</td>
    <td  align="center" class="tg-baqh">worst</td>
    <td  align="center" class="tg-baqh">0.2</td>
    <td  align="center" class="tg-baqh">0.4</td>
    <td  align="center" class="tg-baqh">0.6</td>
    <td  align="center" class="tg-baqh">0.4</td>
    <td  align="center" class="tg-baqh">0.2</td>
    <td  align="center" class="tg-baqh">0.4</td>
    <td  align="center" class="tg-baqh">noisy100</td>
  </tr>
</tbody>
</table>



<font size=2> -  `Symmetric Noise` is generated by uniformly flipping labels for a percentage of the training dataset for all classes, as well as `Asymmetric Noise` by flipping labels for
particular pairs of classes</font>

<font size=2> -  `Instance-dependent Noise` is generated by image features. For more infomation, please refer to [Part-dependent Label Noise: Towards Instance-dependent Label Noise](https://proceedings.neurips.cc/paper/2020/hash/5607fe8879e4fd269e88387e8cb30b7e-Abstract.html)</font>

<font size=2> -  `Real Noise` is a re-annotation of CIFAR-10/CIFAR-100 with human workers. For more infomation, please refer to [Learning with Noisy Labels Revisited: A Study Using Real-World Human Annotations](https://arxiv.org/abs/2110.12088)</font>

<font size=2> -  `Noise Rate` is defined as $\alpha = \frac{\text{Noise Samples}}{\text{Total Samples}}$.</font>


## Usage

If you want to run the code and reproduce the results, please refer to the trick-gallery.md file in the Document directory. It provides detailed instructions on how to use each trick.

## Related link

[Noisy Labels Competition](http://competition.noisylabels.com/)

[Bag of Tricks for LongTailed Image Classification](https://github.com/zhangyongshun/BagofTricks-LT)

[Bag of Tricks for Image Classification with Convolutional Neural Networks](https://github.com/weiaicunzai/Bag_of_Tricks_for_Image_Classification_with_Convolutional_Neural_Networks)

## Contribution

We welcome contributions and suggestions for new tricks to be added to this project. Please feel free to submit a pull request or open an issue to discuss your ideas.
