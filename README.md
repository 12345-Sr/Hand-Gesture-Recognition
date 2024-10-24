<div align= >

# 👋 Hand Gesture Recognition


</div>
<div align="center">
   <br>

   ### ”Hello, Let us help you easily recognize hand gestures 🖐️“
</div>

<p align="center"> 
    <br> 
</p>



## 📙 Overview

<ul>
<li> Hand Gesture Recognition is a machine learning project that aims to recognize hand signs from 0 => 5</li>
<li> This project ranked <strong>1st place</strong> among 21 teams with 81% accuracy, tested on unseen dataset.</li>

<li> Built using <a href="https://docs.python.org/3/">Python</a>.</li>
<li> Using Libraries</li>
<ul>
<li>opencv</li>
<li>numpy</li>
<li>matplotlib</li>
<li>pandas</li>
<li>scikit_image</li>
<li>scikit_learn</li>
<li>seaborn</li>
<li>joblib</li>
</ul>
<li>You can view
<a href="https://www.kaggle.com/datasets/evernext10/hand-gesture-of-the-colombian-sign-language">Data Set</a> which was used to train the model</li>
</ul>
<hr style="background-color: #4b4c60"></hr>
<a id = "Started"></a>

## 🚀 How To Run

- First install the  <a href="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/blob/main/requirements.txt">needed packages</a>.</li> 

```sh
pip install -r requirements.txt
```

- Add the needed data to test the model in the `data` folder next to the `src` folder

```sh
├───data
├───src
│   ├───main.py
│   └───predict.py
...
```

- Navigate to the src directory

```sh
cd src
```

- Run the `main.py` file

```python
python main.py
```
- Output 2 files <a href="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/blob/main/src/result.txt">"result.txt"</a> & <a href="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/blob/main/src/time.txt">"time.txt"</a>
<table>
<tr>
<th>File</th>
<th>Description</th>
</tr>
<tr>
<td>Result</td>
<td>Classification result of every image by order</td>
</tr>
<tr>
<td>Time</td>
<td>Time taken for classifying the images</td>
</tr>
</table>

- Features are saved in `./output.csv `
<hr style="background-color: #4b4c60"></hr>

<a id = "Pipeline"></a>

## 🧱 Project Pipeline
<ol>
<li>📷 Read images</li>
<li>🔁 Preprocessing</li>
<li>💪 Get features</li>
<li>🪓 Split Training and Test Data</li>
<li>✅ Calculate accuracy</li>
<li>📈 Performance analysis</li>

</ol>

<hr style="background-color: #4b4c60"></hr>
<a id = "Modules"></a>

## 🤖 Modules
<a id = "Preprocessing"></a>

### <img align= center width=50px src="https://media0.giphy.com/media/321AaGDATXT8dq4MDC/giphy.gif?cid=ecf05e47r2eazdcsf8tqp6diz0z2o24gcho6yy4kj4lu6ctb&ep=v1_stickers_search&rid=giphy.gif&ct=s">Preprocessing Module
<ol>
<li>Resize image for faster preprocessing</li>
<li>Apply gamma correction to adjust lighting</li>
<li>Convert image to YCbCr color space</li>
<li>Apply segmentation on the skin color</li>
<li>Skin masking</li>
<li>Convert the segmented & original image to grayscale</li>
<li>Erosion using a 5x5 elliptic kernel</li>
<li>Dilation using a 17x17 elliptic kernel</li>
<li>Region Filling using Contours</li>
<li>Erosion again to clean the image from outside</li>
<li>Masking the eroded image with the original one</li>
<li>Crop image to fit the hand exactly</li>
</ol>
<table>
<thead>
<th>Input</th>
<th>Output</th>
</thead>
<tr>
<td  align="center" width="15%"><img src="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/assets/71986226/8f4e3133-bf46-479a-8299-0c4b14c177a3"></td>
<td  align="center" width="15%"><img  height="250px" 
src="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/assets/71986226/2dfd3cdf-b66c-4c7f-af2d-68fbe2bf9ddd"></td>
</tr>
<tr>
<td width="15%"><img src="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/assets/71986226/35d6a4a4-b84f-4743-b1cf-0b363f459db8"></td>
<td  align="center" width="15%"><img height="250px"src="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/assets/71986226/6114c5d5-9d2d-40b3-bfe5-1b037f5d467a"></td>
</tr>
</table>
<a id = "Feature"></a>

### <img align= center height=60px src="https://media0.giphy.com/media/fw9KH5k7W2BVb78Wkq/200w.webp?cid=ecf05e472gayvziprwm50vr429mjzkk6lic31u4tegu821k7&ep=v1_stickers_search&rid=200w.webp&ct=s">Feature Extraction Module
<ol>
<li>Apply data augmentation on each image to enhance accuracy </li>
<li>Input each image to the Histogram of Oriented Gradients (HOG)</li>
<ol>
<li>Resizing</li>
<li>Gradient Computation</li>
<li>Cell Division</li>
<li>Orientation Binning</li>
<li>Histogram Calculations</li>
<li>Block Normalization</li>
<li>Feature Vector</li>
</ol>
<li>Append array of features of each image in a list</li>
</ol>
<a id = "Selection"></a>

### <img align= center height=60px src="https://media0.giphy.com/media/YqJxBFX7cOPQSFO6gv/200w.webp?cid=ecf05e47q2pctv46mon3iqculvvgg8k8bruy7d5or1kf1jh8&ep=v1_stickers_search&rid=200w.webp&ct=s">Model Selection
<ol>
<li>Fitting training data and labels into an <strong>SVM model</strong></li>
<li>Dumping model</li>
<li>Getting classified data</li>
</ol>


### ✅ Performance Module
<strong>Compute Confusion Matrix</strong>
<br>
<div align="center">
<img  width="75%" src="https://github.com/AbdelrahmanHamdyy/Hand-Gesture-Recognition/assets/71986226/c68e7987-7dc3-48d1-bb2b-4414316b3fce">
</div>
<hr style="background-color: #4b4c60"></hr>

<a id ="Contributors"></a>





