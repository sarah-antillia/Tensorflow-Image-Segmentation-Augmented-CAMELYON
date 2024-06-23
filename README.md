<h2>Tensorflow-Image-Segmentation-Augmented-CAMELYON (2024/06/23)</h2>

This is the first experiment of Image Segmentation for CAMELYON (CAncer MEtastases in LYmph nOdes)
 Images based on
the <a href="https://github.com/sarah-antillia/Tensorflow-Image-Segmentation-API">Tensorflow-Image-Segmentation-API</a>, and
Camelyon-ImageMask-Dataset 
<a href="https://drive.google.com/file/d/1X7Qx2hCBnXdM7-eh0t6YnyUYmnK2Wbj-/view?usp=sharing">Camelyon-ImageMask-Dataset-512x512-JPG-V1.zip</a>
, which was derived by us from <a href="https://www.kaggle.com/datasets/osmanf/camelyon-preprocessed">
Camelyon_preprocessed</a> in kaggle.com website.
<br><br>
<!--
On <b>Non-Tiled-Camelyon-ImageMask-Dataset</b>, please refer to <a href="https://github.com/sarah-antillia/Tiled-ImageMask-Dataset-Camelyon">
Tiled-ImageMask-Dataset-Camelyon</a><br>
 -->
<br>
<hr>
<b>Actual Image Segmentation for 512x512 images.</b><br>
As shown below, compared to the predicted masks, the original ground truth masks look quite square and angular.<br>
<table>
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images/10674.jpg" width="320" height="auto"></td>

<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/masks/10674.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test_output/10674.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images/10691.jpg" width="320" height="auto"></td>

<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/masks/10691.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test_output/10691.jpg" width="320" height="auto"></td>
</tr>
</table>

<hr>
<br>
In this experiment, we used the simple UNet Model 
<a href="./src/TensorflowUNet.py">TensorflowSlightlyFlexibleUNet</a> for this Camelyon Segmentation.<br>
As shown in <a href="https://github.com/sarah-antillia/Tensorflow-Image-Segmentation-API">Tensorflow-Image-Segmentation-API</a>.
you may try other Tensorflow UNet Models:<br>

<li><a href="./src/TensorflowSwinUNet.py">TensorflowSwinUNet.py</a></li>
<li><a href="./src/TensorflowMultiResUNet.py">TensorflowMultiResUNet.py</a></li>
<li><a href="./src/TensorflowAttentionUNet.py">TensorflowAttentionUNet.py</a></li>
<li><a href="./src/TensorflowEfficientUNet.py">TensorflowEfficientUNet.py</a></li>
<li><a href="./src/TensorflowUNet3Plus.py">TensorflowUNet3Plus.py</a></li>
<li><a href="./src/TensorflowDeepLabV3Plus.py">TensorflowDeepLabV3Plus.py</a></li>

<br>


<h3>1. Dataset Citation</h3>
The original dataset used here has been taken from <a href="https://www.kaggle.com/datasets/osmanf/camelyon-preprocessed">
Camelyon_preprocessed</a> in kaggle.com website.
<br>
<br>
<b>About Dataset</b>
No description available<br>
<br>
On CAMELYON dataset, please refer to the following link <br>
<li><a href="https://camelyon16.grand-challenge.org/Data/">The CAMELYON16 challenge has ended in November 2016</a></li>
<li><a href="https://camelyon17.grand-challenge.org/"> CAMELYON17 </a></li>
<br>
Please see alo;<br>
<a href="https://registry.opendata.aws/camelyon/">CAncer MEtastases in LYmph nOdes challeNge (CAMELYON) Dataset</a><br>
<br>
<b>Description</b>:<br>
"This dataset contains the all data for the CAncer MEtastases in LYmph nOdes challeNge or CAMELYON. CAMELYON was the first challenge using whole-slide images in computational pathology and aimed to help pathologists identify breast cancer metastases in sentinel lymph nodes. Lymph node metastases are extremely important to find, as they indicate that the cancer is no longer localized and systemic treatment might be warranted. Searching for these metastases in H&E-stained tissue is difficult and time-consuming and AI algorithms can play a role in helping make this faster and more accurate.
<br>
<b>License</b>: CC0 <br>
<br>
<b>Documentation</b>: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6007545/<br>
<br>

<h3>
<a id="2">
2 Camelyon ImageMask Dataset
</a>
</h3>
 If you would like to train this Camelyon Segmentation model by yourself,
 please download the dataset from the google drive  
<a href="https://drive.google.com/file/d/1X7Qx2hCBnXdM7-eh0t6YnyUYmnK2Wbj-/view?usp=sharing">Camelyon-ImageMask-Dataset-512x512-JPG-V1.zip</a>
<br>
<br>
Please expand the downloaded ImageMaskDataset and place them under <b>./dataset</b> folder to be
<pre>
./dataset
└─Camelyon
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
        ├─images
        └─masks
</pre>
<br>

<b>Camelyon Dataset Statistics</b><br>
<img src ="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/Camelyon-ImageMask-Dataset-512x512-JPG-V1_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images of train and valid dataset is not necessarily large. Therefore, probably an online augmentation strategy to
train this model may be effective to improve segmentation accuracy.
<br>

<br>
<b>Train_images_sample</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_masks_sample</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/train_masks_sample.png" width="1024" height="auto">
<br>

<h3>
4 Train TensorflowUNet Model
</h3>
 We have trained Camelyon TensorflowUNet Model by using the following
<a href="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/Camelyon and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
, which simply runs the following command.<br>
<pre>
>python ../../../src/TensorflowUNetTrainer.py ./train_eval_infer.config
</pre>
<pre>
; train_eval_infer.config
; 2024/06/22 (C) antillia.com

[model]
model          = "TensorflowUNet"
generator      = True
image_width    = 512
image_height   = 512
image_channels = 3
input_normalize = False
normalization  = False
num_classes    = 1
base_filters   = 16
base_kernels   = (5,5)
num_layers     = 8
dropout_rate   = 0.05
learning_rate  = 0.00006
clipvalue      = 0.5
dilation       = (2,2)
;loss           = "bce_iou_loss"
loss           = "bce_dice_loss"
metrics        = ["binary_accuracy"]
show_summary   = False

[train]
epochs        = 100
batch_size    = 2
steps_per_epoch  = 400
validation_steps = 80
patience      = 10

;metrics       = ["iou_coef", "val_iou_coef"]
metrics       = ["binary_accuracy", "val_binary_accuracy"]
model_dir     = "./models"
eval_dir      = "./eval"
image_datapath = "../../../dataset/Camelyon/train/images/"
mask_datapath  = "../../../dataset/Camelyon/train/masks/"

;Inference execution flag on epoch_changed
epoch_change_infer     = True

; Output dir to save the inferred masks on epoch_changed
epoch_change_infer_dir =  "./epoch_change_infer"

;Tiled-inference execution flag on epoch_changed
epoch_change_tiledinfer     = False

; Output dir to save the tiled-inferred masks on epoch_changed
epoch_change_tiledinfer_dir =  "./epoch_change_tiledinfer"

; The number of the images to be inferred on epoch_changed.
num_infer_images       = 1
create_backup  = False

learning_rate_reducer = True
reducer_factor     = 0.2
reducer_patience   = 4
save_weights_only  = True

[eval]
image_datapath = "../../../dataset/Camelyon/valid/images/"
mask_datapath  = "../../../dataset/Camelyon/valid/masks/"

[test] 
image_datapath = "./mini_test/images/"
mask_datapath  = "./mini_test/masks/"

[infer] 
images_dir    = "./mini_test/images"
output_dir    = "./mini_test_output"
merged_dir    = "./mini_test_output_merged"
;blur          = True

[tiledinfer] 
overlapping   = 128
images_dir    = "./mini_test/Metaplastic/images"
output_dir    = "./tiled_mini_test_output"
merged_dir    = "./tiled_mini_test_output_merged"
bitwise_blending = False
;binarize      = True
mask_colorize = True

[segmentation]
colorize      = False
black         = "black"
white         = "green"
blursize      = None

[mask]
blur      = False
blur_size = (3,3)
binarize  = False
;threshold = 128
threshold = 80

[generator]
debug        = False
augmentation = True

[augmentor]
vflip    = True
hflip    = True
rotation = True
angles   = [60, 120, 180, 240, 300]
shrinks  = [0.6, 0.8]
shears   = [0.1]

deformation = True
distortion  = True
sharpening  = False
brightening = False

barrdistortion = False

[deformation]
alpah    = 1300
sigmoids  = [8.0]

[distortion]
gaussian_filter_rsigma= 40
gaussian_filter_sigma = 0.5
distortions           = [0.02, 0.03]

[barrdistortion]
radius = 0.3
amount = 0.3
centers =  [(0.3, 0.3), (0.5, 0.5), (0.7, 0.7)]

[sharpening]
k        = 1.0

[brightening]
alpha  = 1.2
beta   = 10  
</pre>
In this configuration file above, we added the following parameters to enable <b>epoch_change_infer</b> callback in [train] section.<br>
<pre>
[train]
;Inference execution flag on epoch_changed
epoch_change_infer     = True
; Output dir to save the inferred masks on epoch_changed
epoch_change_infer_dir =  "./epoch_change_infer"

; The number of the images to be inferred on epoch_changed.
num_infer_images       = 1
</pre>

By using this callback, on every epoch_change, the inference procedures can be called
 for an image in <b>mini_test</b> folder.<br><br>
<b>Epoch_change_inference output</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/epoch_change_infer.png" width="1024" height="auto"><br>
<br>
<br>
The training process has just been stopped at epoch 36 by an early-stopping callback as shown below.<br><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/train_console_output_at_epoch_36.png" width="720" height="auto"><br>
<br>
<br>
<a href="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/eval/train_metrics.png" width="520" height="auto"><br>

<br>
<a href="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/eval/train_losses.png" width="520" height="auto"><br>
<br>

<h3>
5 Evaluation
</h3>
Please move to a <b>./projects/TensorflowSlightlyFlexibleUNet/Camelyon</b> folder,<br>
and run the following bat file to evaluate TensorflowUNet model for Camelyon.<br>
<pre>
./2.evaluate.bat
</pre>
<pre>
python ../../../src/TensorflowUNetEvaluator.py ./train_eval_infer_aug.config
</pre>
Evaluation console output:<br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/evaluate_console_output_at_epoch_36.png" width="720" height="auto">
<br><br>
<a href="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/evaluation.csv">evaluation.csv</a><br>
The loss (bce_dice_loss) and binary_accuracy for this mini_test dataset were very bad as shown below.<br>
<pre>
loss,0.7485
binary_accuracy,0.6296
</pre>
<br>
<h3>
6 Inference
</h3>
Please move to a <b>./projects/TensorflowSlightlyFlexibleUNet/Camelyon</b> folder
, and run the following bat file to infer segmentation regions for the images 
in <a href="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images"><b>mini_test/images</b></a> by the Trained-TensorflowUNet model for Camelyon.<br>
<pre>
./3.infer.bat
</pre>
<pre>
python ../../../src/TensorflowUNetInferencer.py ./train_eval_infer_aug.config
</pre>
The <a href="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/"><b>mini_test</b></a>
folder contains some large image and mask files taken from the original BCSS dataset.<br><br>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/mini_test_images.png" width="1024" height="auto"><br>
<br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/mini_test_masks.png" width="1024" height="auto"><br>

<hr>
<b>inferred test masks</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>


<hr>
<b>Enlarged Masks Comparison</b><br>

<table>
<tr>
<th>Image</th>
<th>Mask (ground_truth)</th>
<th>Inferred-mask</th>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images/10072.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/masks/10072.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test_output/10072.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images/10671.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/masks/10671.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test_output/10671.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images/10674.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/masks/10674.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test_output/10674.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images/10679.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/masks/10679.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test_output/10679.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/images/10692.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test/masks/10692.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Camelyon/mini_test_output/10692.jpg" width="320" height="auto"></td>
</tr>
</table>
<br>

<h3>
References
</h3>
<b>1. Accurate diagnostic tissue segmentation and concurrent disease subtyping with small datasets</b><br>
https://doi.org/10.1016/j.jpi.2022.100174<br>
Steven J. Frank<br>
<pre>
https://www.sciencedirect.com/science/article/pii/S215335392200774X
</pre>
<br>
<b>2. Deep Learning Pipeline for Camelyon 2016 dataset</b><br>
Weizhe Li <br>
<pre>
https://github.com/3dimaging/DeepLearningCamelyon
</pre>

