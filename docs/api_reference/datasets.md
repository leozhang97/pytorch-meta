## Omniglot

The Omniglot dataset [1]. A dataset of 1623 handwritten characters from 50 different alphabets.

```python
torchmeta.datasets.Omniglot(root, num_classes_per_task=None, meta_train=False,
    meta_val=False, meta_test=False, meta_split=None, use_vinyals_split=True,
    transform=None, target_transform=None, dataset_transform=None,
    class_augmentations=None, download=False)
```

**Parameters**

 - **root**: *string*
 Root directory where the dataset folder `omniglot` exists.

 - **num_classes_per_task**: *int*
 Number of classes per tasks. This corresponds to "N" in "N-way" classification.

 - **meta_train**: *bool (default: `False`)*
 Use the meta-train split of the dataset. If set to `True`, then the arguments `meta_val` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_val**: *bool (default: `False`)*
 Use the meta-validation split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_test**: *bool (default: `False`)*
 Use the meta-test split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_val` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_split**: *string in {'train', 'val', 'test'}, optional*
 Name of the split to use. This overrides the arguments `meta_train`, `meta_val` and `meta_test` if all three are set to `False`.

 - **use_vinyals_split**: *bool (default: `True`)*
 If set to `True`, the dataset uses the splits defined in [3]. If `False`, then the meta-train split corresponds to `images_background`, and the meta-test split corresponds to `images_evaluation` (raises an error when calling the meta-validation split).

 - **transform**: *callable, optional*
 A function/transform that takes a `PIL` image, and returns a transformed version. See also `torchvision.transforms`.

 - **target_transform**: *callable, optional*
 A function/transform that takes a target, and returns a transformed version. See also `torchvision.transforms`.

 - **dataset_transform**: *callable, optional*
 A function/transform that takes a dataset (ie. a task), and returns a transformed version of it. E.g. `torchmeta.transforms.ClassSplitter()`.

 - **class_augmentations**: *list of callable, optional*
 A list of functions that augment the dataset with new classes. These classes are transformations of existing classes. E.g. `torchmeta.transforms.HorizontalFlip()`.

 - **download**: *bool (default: `False`)*
 If `True`, downloads the zip files and processes the dataset in the root directory (under the `omniglot` folder). If the dataset is already available, this does not download/process the dataset again.

!!! note "Notes"
    The dataset is downloaded from the original [Omniglot repository](https://github.com/brendenlake/omniglot). The meta train/validation/test splits used in [3] are taken from [this repository](https://github.com/jakesnell/prototypical-networks). These splits are over 1028/172/423 classes (characters).

!!! attention "References"
    - **[1]** Lake, B. M., Salakhutdinov, R., and Tenenbaum, J. B. (2015). Human-level concept learning through probabilistic program induction. Science, 350(6266), 1332-1338 (http://www.sciencemag.org/content/350/6266/1332.short)
    - **[2]** Lake, B. M., Salakhutdinov, R., and Tenenbaum, J. B. (2019). The Omniglot Challenge: A 3-Year Progress Report (https://arxiv.org/abs/1902.03477)
    - **[3]** Vinyals, O., Blundell, C., Lillicrap, T. and Wierstra, D. (2016). Matching Networks for One Shot Learning. In Advances in Neural Information Processing Systems (pp. 3630-3638) (https://arxiv.org/abs/1606.04080)

## MiniImagenet

The Mini-Imagenet dataset, introduced in [1]. This dataset contains images of 100 different classes from the ILSVRC-12 dataset (Imagenet challenge). The meta train/validation/test splits are taken from [2] for reproducibility.

```python
torchmeta.datasets.MiniImagenet(root, num_classes_per_task=None,
    meta_train=False, meta_val=False, meta_test=False, meta_split=None,
    transform=None, target_transform=None, dataset_transform=None,
    class_augmentations=None, download=False)
```

**Parameters**

 - **root**: *string*
 Root directory where the dataset folder `miniimagenet` exists.

 - **num_classes_per_task**: *int*
 Number of classes per tasks. This corresponds to "N" in "N-way" classification.

 - **meta_train**: *bool (default: `False`)*
 Use the meta-train split of the dataset. If set to `True`, then the arguments `meta_val` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_val**: *bool (default: `False`)*
 Use the meta-validation split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_test**: *bool (default: `False`)*
 Use the meta-test split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_val` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_split**: *string in {'train', 'val', 'test'}, optional*
 Name of the split to use. This overrides the arguments `meta_train`, `meta_val` and `meta_test` if all three are set to `False`.

 - **transform**: *callable, optional*
 A function/transform that takes a `PIL` image, and returns a transformed version. See also `torchvision.transforms`.

 - **target_transform**: *callable, optional*
 A function/transform that takes a target, and returns a transformed version. See also `torchvision.transforms`.

 - **dataset_transform**: *callable, optional*
 A function/transform that takes a dataset (ie. a task), and returns a transformed version of it. E.g. `torchmeta.transforms.ClassSplitter()`.

 - **class_augmentations**: *list of callable, optional*
 A list of functions that augment the dataset with new classes. These classes are transformations of existing classes. E.g. `torchmeta.transforms.HorizontalFlip()`.

 - **download**: *bool (default: `False`)*
 If `True`, downloads the pickle files and processes the dataset in the root directory (under the `miniimagenet` folder). If the dataset is already available, this does not download/process the dataset again.

!!! note "Notes"
    The dataset is downloaded from [this repository](https://github.com/renmengye/few-shot-ssl-public/). The meta train/validation/test splits are over 64/16/20 classes.

!!! attention "References"
    - **[1]** Vinyals, O., Blundell, C., Lillicrap, T. and Wierstra, D. (2016). Matching Networks for One Shot Learning. In Advances in Neural Information Processing Systems (pp. 3630-3638) (https://arxiv.org/abs/1606.04080)
    - **[2]** Ravi, S. and Larochelle, H. (2016). Optimization as a Model for Few-Shot Learning. (https://openreview.net/forum?id=rJY0-Kcll)

## TieredImagenet

The Tiered-Imagenet dataset, introduced in [1]. This dataset contains images of 608 different classes from the ILSVRC-12 dataset (Imagenet challenge).

```python
torchmeta.datasets.TieredImagenet(root, num_classes_per_task=None,
    meta_train=False, meta_val=False, meta_test=False, meta_split=None,
    transform=None, target_transform=None, dataset_transform=None,
    class_augmentations=None, download=False)
```

**Parameters**

 - **root**: *string*
 Root directory where the dataset folder `tieredimagenet` exists.

 - **num_classes_per_task**: *int*
 Number of classes per tasks. This corresponds to "N" in "N-way" classification.

 - **meta_train**: *bool (default: `False`)*
 Use the meta-train split of the dataset. If set to `True`, then the arguments `meta_val` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_val**: *bool (default: `False`)*
 Use the meta-validation split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_test**: *bool (default: `False`)*
 Use the meta-test split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_val` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_split**: *string in {'train', 'val', 'test'}, optional*
 Name of the split to use. This overrides the arguments `meta_train`, `meta_val` and `meta_test` if all three are set to `False`.

 - **transform**: *callable, optional*
 A function/transform that takes a `PIL` image, and returns a transformed version. See also `torchvision.transforms`.

 - **target_transform**: *callable, optional*
 A function/transform that takes a target, and returns a transformed version. See also `torchvision.transforms`.

 - **dataset_transform**: *callable, optional*
 A function/transform that takes a dataset (ie. a task), and returns a transformed version of it. E.g. `torchmeta.transforms.ClassSplitter()`.

 - **class_augmentations**: *list of callable, optional*
 A list of functions that augment the dataset with new classes. These classes are transformations of existing classes. E.g. `torchmeta.transforms.HorizontalFlip()`.

 - **download**: *bool (default: `False`)*
 If `True`, downloads the pickle files and processes the dataset in the root directory (under the `tieredimagenet` folder). If the dataset is already available, this does not download/process the dataset again.

!!! note "Notes"
    The dataset is downloaded from [this repository](https://github.com/renmengye/few-shot-ssl-public/). The dataset contains images from 34 categories. The meta train/validation/test splits are over 20/6/8 categories. Each category contains between 10 and 30 classes. The splits over categories (instead of over classes) ensures that all the training classes are sufficiently distinct from the test classes (unlike Mini-Imagenet).

!!! attention "References"
    - **[1]** Ren, M., Triantafillou, E., Ravi, S., Snell, J., Swersky, K., Tenenbaum, J.B., Larochelle, H. and Zemel, R.S. (2018). Meta-learning for semi-supervised few-shot classification. International Conference on Learning Representations. (https://arxiv.org/abs/1803.00676)

## FC100

The Fewshot-CIFAR100 dataset, introduced in [1]. This dataset contains images of 100 different classes from the CIFAR100 dataset [2].

```python
torchmeta.datasets.FC100(root, num_classes_per_task=None, meta_train=False,
    meta_val=False, meta_test=False, meta_split=None, transform=None,
    target_transform=None, dataset_transform=None, class_augmentations=None,
    download=False)
```

**Parameters**

 - **root**: *string*
 Root directory where the dataset folder `cifar100` exists.

 - **num_classes_per_task**: *int*
 Number of classes per tasks. This corresponds to `N` in `N-way` classification.

 - **meta_train**: *bool (default: `False`)*
 Use the meta-train split of the dataset. If set to `True`, then the arguments `meta_val` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_val**: *bool (default: `False`)*
 Use the meta-validation split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_test**: *bool (default: `False`)*
 Use the meta-test split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_val` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_split**: *string in {'train', 'val', 'test'}, optional*
 Name of the split to use. This overrides the arguments `meta_train`, `meta_val` and `meta_test` if all three are set to `False`.

 - **transform**: *callable, optional*
 A function/transform that takes a `PIL` image, and returns a transformed version. See also `torchvision.transforms`.

 - **target_transform**: *callable, optional*
 A function/transform that takes a target, and returns a transformed version. See also `torchvision.transforms`.

 - **dataset_transform**: *callable, optional*
 A function/transform that takes a dataset (ie. a task), and returns a transformed version of it. E.g. `transforms.ClassSplitter()`.

 - **class_augmentations**: *list of callable, optional*
 A list of functions that augment the dataset with new classes. These classes are transformations of existing classes. E.g. `transforms.HorizontalFlip()`.

 - **download**: *bool (default: `False`)*
 If `True`, downloads the pickle files and processes the dataset in the root directory (under the `cifar100` folder). If the dataset is already available, this does not download/process the dataset again.

!!! note "Notes"
    The meta train/validation/test splits are over 12/4/4 superclasses from the CIFAR100 dataset. The meta train/validation/test splits contain 60/20/20 classes.

!!! attention "References"
    - **[1]** Oreshkin B. N., Rodriguez P., Lacoste A. (2018). TADAM: Task dependent adaptive metric for improved few-shot learning. In Advances in Neural Information Processing Systems (https://arxiv.org/abs/1805.10123)
    - **[2]** Krizhevsky A. (2009). Learning Multiple Layers of Features from Tiny Images. (https://www.cs.toronto.edu/~kriz/learning-features-2009-TR.pdf)

## CIFARFS

The CIFAR-FS dataset, introduced in [1]. This dataset contains images of 100 different classes from the CIFAR100 dataset [2].

```python
torchmeta.datasets.CIFARFS(root, num_classes_per_task=None, meta_train=False,
    meta_val=False, meta_test=False, meta_split=None, transform=None,
    target_transform=None, dataset_transform=None, class_augmentations=None,
    download=False)
```

**Parameters**

 - **root**: *string*
 Root directory where the dataset folder `cifar100` exists.

 - **num_classes_per_task**: *int*
 Number of classes per tasks. This corresponds to `N` in `N-way` classification.

 - **meta_train**: *bool (default: `False`)*
 Use the meta-train split of the dataset. If set to `True`, then the arguments `meta_val` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_val**: *bool (default: `False`)*
 Use the meta-validation split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_test` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_test**: *bool (default: `False`)*
 Use the meta-test split of the dataset. If set to `True`, then the arguments `meta_train` and `meta_val` must be set to `False`. Exactly one of these three arguments must be set to `True`.

 - **meta_split**: *string in {'train', 'val', 'test'}, optional*
 Name of the split to use. This overrides the arguments `meta_train`, `meta_val` and `meta_test` if all three are set to `False`.

 - **transform**: *callable, optional*
 A function/transform that takes a `PIL` image, and returns a transformed version. See also `torchvision.transforms`.

 - **target_transform**: *callable, optional*
 A function/transform that takes a target, and returns a transformed version. See also `torchvision.transforms`.

 - **dataset_transform**: *callable, optional*
 A function/transform that takes a dataset (ie. a task), and returns a transformed version of it. E.g. `transforms.ClassSplitter()`.

 - **class_augmentations**: *list of callable, optional*
 A list of functions that augment the dataset with new classes. These classes are transformations of existing classes. E.g. `transforms.HorizontalFlip()`.

 - **download**: *bool (default: `False`)*
 If `True`, downloads the pickle files and processes the dataset in the root directory (under the `cifar100` folder). If the dataset is already available, this does not download/process the dataset again.

!!! note "Notes"
    The meta train/validation/test splits are over 64/16/20 classes from the CIFAR100 dataset.

!!! attention "References"
    - **[1]** Bertinetto L., Henriques J. F., Torr P. H.S., Vedaldi A. (2019). Meta-learning with differentiable closed-form solvers. In International Conference on Learning Representations (https://arxiv.org/abs/1805.08136)
    - **[2]** Krizhevsky A. (2009). Learning Multiple Layers of Features from Tiny Images. (https://www.cs.toronto.edu/~kriz/learning-features-2009-TR.pdf)