# Introduction
<div style="text-align: justify; text-indent: 30px;">
<p>
This project originates from automated game evaluation.
A fisheye camera is used to capture a room where
people are playing a newly designed social game.
In the gram, two teams compete with each other and
the team dancing in higher sync win the game.
</p>
</div>

<div style="text-align: justify; text-indent: 30px;">
<p>
In the previous work, people are detected and marked with a bounding
box as in Fig. 1. In the work, we track and clustering people
into groups. People in each group should have similar behavior
and group is the minimal study unit in the following game evaluation.
</p>
</div>

<center>
<img width="300" height="300"  src="assets/images/detected_people.png?raw=true" >
</center>
<div style="text-align: justify; text-align:center;" >
<p>Fig. 1 Detected people are marked with a boundary box.</p>
</div>

# Tracking
<div style="text-align: justify; text-indent: 30px;">
<p>
The basic idea of tracking is searching for the most similar boundary
box in the coming frame. However, in fisheye video, as people move,
the bounding boxes undergo significant deformation and it needs to be
taken into consideration when comparing box contents. We handle it by
reconstructing the real scene from the fisheye video based on fisheye
imaging model and using persisting physical constants as the clues
to predict the box deformation. Of course, it is really possible
to reconstruct the real scene from a single fisheye camera. Strong
assumption about the real scene is used which is enough for the
tracking task.
</p>
</div>

<center>
<img src="assets/images/tracking_1.gif?raw=true" >
</center>
<div style="text-align: justify; text-align:center;" >
<p>Fig. 2 People tracking showcase 1.</p>
</div>

<br>
<center>
<img src="assets/images/tracking_2.gif?raw=true" >
</center>
<div style="text-align: justify; text-align:center;" >
<p>Fig. 3 People tracking showcase 2.</p>
</div>

<br>
<center>
<img src="assets/images/tracking_3.gif?raw=true" >
</center>
<div style="text-align: justify; text-align:center;" >
<p>Fig. 4 People tracking showcase 3.</p>
</div>


# Clustering
<div style="text-align: justify; text-indent: 30px;">
<p>
After tracking, the trajectory of each people is obtained.
Meanshift is then used for clustering, using people location and
motion energy spectrum as features.
</p>
</div>

<center>
<img width="270" height="234" src="assets/images/clustering_1_1.gif?raw=true" >
<img width="270" height="234" src="assets/images/clustering_1_2.jpeg?raw=true" >
<img width="270" height="234" src="assets/images/clustering_1_3.jpeg?raw=true" >
</center>
<div style="text-align: justify; text-align:center;" >
<p>Fig. 5 People clustering showcase 1.</p>
</div>

<br>
<center>
<img width="270" height="234" src="assets/images/clustering_2_1.gif?raw=true" >
<img width="270" height="234" src="assets/images/clustering_2_2.jpeg?raw=true" >
<img width="270" height="234" src="assets/images/clustering_2_3.jpeg?raw=true" >
</center>
<div style="text-align: justify; text-align:center;" >
<p>Fig. 6 People clustering showcase 2.</p>
</div>

#### <a href="https://yuanwangonward.github.io/">Back to Yuan's homepage</a>

