# GA DSIF 11 Capstone Project:

#  Dance Move Classifier (Originality Never Dies)


## Lua Yeow Wen
---

## Overview

### Background
---
Breaking or bboying is a form of dance that has evolved from the battling at the streets of the Bronx into global stage ([source](https://www.redbull.com/sg-en/pushing-progression-breakdance-evolution#1-a-way-out:-from-the-bronx-to-the-world)).

Nowadays, winners in dance competitions or events can receive rewards and incentives such as cash prizes, invitations to events, inclusion in an all-star team, or even representation of a country in the 2024 Paris Olympics.

These are the prizes for some of the competitions:

### Overseas Competitions
**World Breaking Classic 2 vs 2 2024 ([source](https://worldbreakingclassic.com/tournament)):**
* Top 16: €200
* Top 8: €400
* Top 4: €1000
* 2nd Place: €1500
* 1st Place: €5000

**Silverback Open Championships 3 vs 3 ([source](https://silverbackbboyevents.com/championships2018/)):**
* Top 32: USD \$50
* Top 16: USD \$250
* Top 8: USD \$500
* Top 4: USD \$1,000
* 2nd Place: USD \$5000 + silver Silverback medal
* 1st Place: USD \$15,000 + gold Silverback medal


### Local Competitions
**Lion City Dance Convention 4 vs 4 ([source](https://www.activesgcircle.gov.sg/academies-clubs/active-groove)):**
* 3rd Place: SGD \$800
* 2nd Place: SGD \$1,200
* 1st Place: SGD \$3,200


**Lion City Dance Convention 1 vs 1 ([source](https://www.activesgcircle.gov.sg/academies-clubs/active-groove)):**
* 1st Place: SGD \$800




**These are some of the incentives:**

* Being Part of Red Bull BC All Star Team ([source](https://www.bboycity.com/bc1allstarbios-taisuke.html))

* Multiple Bboy sponsorships such as Samsung, Toyota, Alibaba and etc ([source](https://www.paris2024.org/en/sport/breaking/)) for Paris 2024 Games 

* Sponsorships like Rimowa,Sony Xperia, G-Shock, and Red Bull ([source](https://mythnewyork.com/blogs/magazine/shigekix))

* Featured in movie documentary ([source](https://www.bboycity.com/bc1allstarbios-taisuke.html))

* The WDSF Breaking For Gold series, which is a crucial event where breakers earn points that are essential for qualifying for the 2024 Paris Games ([source](https://www.redbull.com/int-en/b-boy-issin-need-to-know)).



The bboy dance scene significantly benefits from corporate involvement, with numerous companies sponsoring dancers and funding events, thereby playing a pivotal role in the culture and growth of the scene.



In breaking contests, judges typically evaluate competitors based on eight key criteria: musicality, foundation, the difficulty of movement, character, style, execution, originality, and the composition of the rounds ([source](https://www.redbull.com/sg-en/judges-criteria-breaking-competitions#7-originality-and-creativity)).



In the scoring system of The WDSF Breaking For Gold series, originality is a crucial aspect, accounting for 20% of the final score. This element plays a key role in determining a bboy's edge over another in a battle. Additionally, each instance of a 'bite' results in a penalty of 2.34% off the score ([source](https://dancesport.app.box.com/s/fowfqyiedh1z3vryqa0a963acptv1vhv)).


Originality in breaking is evaluated by how well a dancer demonstrates improvisation, innovation, spontaneity, and their unique personality in their performance. Dancers who can creatively adapt basic movements into their own distinctive style and react spontaneously to the music, particularly in recovering from any slips, score higher in originality.


### Estimated Revenue Made in Events
---
* \$825,000 for Breakin tournament that at the world finals
* \$207,000 for Breakin Festival held in a city

These are rough estimations were made by a veteran bboy([source](https://www.dyzeediaries.com/breakin-aka-break-dancing-is-lucrative-but-not-for-the-breakers/)).




### Problem Statement
---

Over the years, instances have arisen where a bboy's performance closely resembles that of others , leading to an appearance of imitation, a phenomenon known as "Biting" ([source](https://www.redbull.com/us-en/breaking-terminology-basics#8-bite-biter-or-biting)) in the breaking community. Given the extensive array of moves within the bboy scene, judges may occasionally overlook instances of "Biting," especially in the fast-paced environment of a bboy battle.

This oversight can consequently lead to potential misjudgment in scoring and decision-making.



### Why should we be concern
---

* It is important to ensure that sponsors support the right Bboy or athlete to maintain the integrity of the sponsorship process.

* Addressing potential backlash from the public is essential, as it could become more challenging to attract corporate funding for Bboy events in the future.


* Misjudgment could potentially discourage new dancers from participating in dance events or competitions, leading to the deterioration of the Bboy dance scene. Thus, hurting revenues made for such events.



### Who am I
---
* An advocate bboy data scientist

### Stakeholders
---
* Dance event organizers

### Secondary Stakeholders
---
* Corporate Sponsors

### Goal
---

* Develop a multi-class classifier that accurately identifies moves, assisting bboy judges in detecting instances of biting.
* Encourage breakers to create more original moves.
* Assisting corporations in selecting the appropriate bboy or bgirl for sponsorship.

### Approach
---


* Identify bodylandmarks AKA features.

* Extract data from the the 24 video attempts and save as csv and numpy arrays with MediaPipe library.

* Process the videos and connect body landmarks with lines and include details of the video with MediaPipes.

* Train the model find its best parameters with hyperparameter optimizer.

* Use the best parameters to retrain the model and evaluate to identify the best suitable model.

* The chosen model shall be implemented to for multi-class classification. Its output shall include the name of the move and the probability score of how confident the model identifies the move correctly.










### Dataset
---

* The dance moves that the model will be indentifying are "cc" , "jackhammer" and "handhop"

* The dataset is obtained by extracting body landmark values in x,y,z,coordinates and visibility from the video attempts of the dance moves. Mediapipe library is ultilized for this process.

**Selections of Body Landmarks:**

These are the 15 body landmark numbers for x,y,z coordinates and visibility that are extracted:


* p0 : nose
* p9 : mouth_left
* p10 : mouth_right
* p12 : right_shoulder
* p14 : right_elbow
* p16 : right_wrist
* p11 : left_shoulder
* p13 : left_elbow
* p15 : left_wrist
* p24 : right_hip
* p26 : right_knee
* p28 : right_ankle
* p23 : left_hip
* p25 : left_knee
* p27 : left_ankle

<img src="images/pose_landmarks_index.png" width="80%">

source: https://github.com/google/mediapipe/blob/master/docs/solutions/pose.md



* These 15 body landmarks are essential in capturing the movements that breakers showcase, which often involve spinning their whole body on hands, elbows, back, head, or shoulders. Each body part plays a crucial role in executing these moves, making it important to accurately track and analyze these landmarks to fully understand and appreciate the skill and artistry involved in breaking ([source](https://olympics.com/en/news/breaking-breakdancing-rules-format-moves)).

* The body landmark values in x,y,z coordinates are essential as the dance movement involves spinning across x and z axis (for jackhammer) and hopping in the y axis (for handhop).


* Datasets were saved as csv and in numpy array.


* The videos of the various attempts of different dance moves were self recorded with Samsung Galaxy S22 (settings: UHD, 30 fps). There are 3 different dance moves with 8 attempts each for modelling (7 each for training and 1 each for validation) and 1 attempt each for prediction.

* 2 seconds of each video attempt were extracted and processed. There are 60 frames of data extracted for each attempt in each moves as the camera setting is set to 30 frames per second which is suffice for this project.


**Rows:**
* Each row represents a frame of a 2 sec video (total 60 frames for a video)
* There are 8 videos attempts for each move
* There are 3 moves in total
* Total rows: 8 x 3 x 60 = 1440

**Columns**
* There are 15 landmark columns
* Each landmark consist of x,y,z coordinate and visibility
* There are also 7 no. of columns that consist information of the extracted video file
* Total columns: (15 x 4) + 7 = 67



**These are the columns that stores the information of the videos:**

* videolandmarks_path : Folder location of the video attempts with landmarks for the specific move
* videolandmarks_name : File name of the video with landmark
* video_name : File name of the video attempts that will be processed
* bboy_name : Name of the bboy
* move_name : Name of the move
* frame : Frame number
* video_num : Video attempt number



The shape of the dataset should be **(1440,67)**.


### Retrieving Dataset and Notebook
---
**Google Drive link is also available to retrieve data and notebook:**

https://drive.google.com/drive/folders/1XVi1OqjL-KfIfnygQ7LH19N_DpVQZcYc?usp=sharing

**Main Folder:**
* capstone

**Sub Folders:**
* images: landmark referrence in PNG format
* archive_video: Contain all the video attempts for extraction and processing
* video_landmarks: Contain all the proccessed video attempts with landmarks
* dataset_csv: Contain folders for the extracted data in csv format
* dataset_numpy: Contain folders for the extracted data in numpy format
* models: Contains the trained models in keras format
* my_dir: Contains the trials run with different models
* predict_video: Contains the video to use for prediction in mp4 format
* predict_result: Contains the predicted result in GIF format


**Jupyter Notebooks located within Main Folder:**
* 01_data_extraction.ipynb
* 02_data_eda.ipynb
* 03_data_process_modelling.ipynb
* 04_data_demo.ipynb
* README.md

**Presenation Slide**
* capstone_presentation.pdf



### Metric of Success
---
* Model with highest Categorical Accuracy and least model training time.


### Non built-in Python library
---

**Versions:**
* The version of the notebook server is: 6.5.4
* Python: ver 3.11.3 
* tensorflow: ver 2.14.0
* keras-tuner: ver 1.4.6
* imageio: ver 2.26.0
* mediapipe: ver 0.10.7
* cv2: ver 4.8.1


## Data Modelling
---
Two types of recurrent neural network (RNN) architecture will be used for the data modelling, Gated Recurrent Unit (GRU) and Long Short-Term Memory (LSTM) network. Variations such as different regularization techniques were applied to the two RNNs subsequently.

These two RNN architectures are designed to handle sequential data and can be applied to temporal/ time-series data.

**Sequential GRU Model (base model)** is chosen as the baseline model. The GRU has a simpler architecture compared to LSTM. It is adept at capturing less intricate patterns in data, outperforms with smaller datasets, and offers quicker training times on larger datasets ([source](https://medium.com/@prudhviraju.srivatsavaya/lstm-vs-gru-c1209b8ecb5a#:~:text=LSTM%3A%20LSTM%20typically%20has%20more,it%20lacks%20the%20forget%20gate.)). Additionally, GRUs are tailored for maintaining information across relatively shorter sequences than LSTMs.




### Models
---

#### GRU

* Model 1 - Sequential GRU Model **(base model)**
* Model 3 - Sequential GRU Model with Dropout Regularization
* Model 5 - Sequential GRU Model with EarlyStopping Regularization
* Model 7 - Sequential GRU Model with Dropout and EarlyStopping Regularization


#### LSTM

* Model 2 - Sequential LSTM Model
* Model 4 - Sequential LSTM Model with Dropout Regularization
* Model 6 - Sequential LSTM Model with EarlyStopping Regularization
* Model 8 - Sequential LSTM Model with Dropout and EarlyStopping Regularization


### Model Results
---



| Index |                model | accuracy score |     run time |                saved model |
|------:|---------------------:|---------------:|-------------:|---------------------------:|
| **2** |     **GRU Model DO** |   **1.000000** | **00:02:53** |     **GRU Model DO.keras** |
|     7 | LSTM Model DO and ES |       1.000000 |     00:03:17 | LSTM Model DO and ES.keras |
|     6 |  GRU Model DO and ES |       1.000000 |     00:03:19 |  GRU Model DO and ES.keras |
|     0 |            GRU Model |       1.000000 |     00:03:40 |            GRU Model.keras |
|     4 |         GRU Model ES |       1.000000 |     00:04:00 |         GRU Model ES.keras |
|     3 |        LSTM Model DO |       0.666667 |     00:03:03 |        LSTM Model DO.keras |
|     5 |        LSTM Model ES |       0.666667 |     00:04:17 |        LSTM Model ES.keras |
|     1 |           LSTM Model |       0.333333 |     00:03:35 |           LSTM Model.keras |


* **GRU Model DO (Sequential GRU Model with Dropout Regularization)** is chosen for identifies moves, assisting bboy judges in detecting instances of biting.

* Although it has the same accuracy as the base model (GRU Model AKA Sequential GRU Model) and might slightly overfit, but it still fits within the threshold of 10%. 

* The model trained almost a minute faster than the base model, providing it with a significant edge over the base model.

* All 3 classes of confusion matrix shows perfect accuracy results with 2 true negatives and 1 true positive.



## Conclusion
----

The project has successfully achieved its goals:

* The model accurately identifying moves to help bboy judges detect instances of biting. 

* This will assist corporations in selecting the right bboy or bgirl for potential sponsorship. 

* The fairness and rewarding incentives will encourage bboys and bgirls to create more original moves.




## Recomendation
----

* The marketing team of a company can utilize this model to identify dancers with exceptional originality for potential sponsorship opportunities.
* Dance competitions and events can utilize this model to provide judges with valuable insights, helping them assess the originality of performances. Just like VAR system in soccer matches to detect fouls.



## Further Improvements
----

* Incorporate videos captured from various angles.
* Diversify move durations during execution.
* Extend the dance moves database to encompass various hip-hop styles, including popping and locking.
* Develop a user-friendly app for bboys and bgirls, encouraging the creation of original dance moves.