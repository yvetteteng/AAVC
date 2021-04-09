<p align="justify">
In this post, we show the demo of the functional Digestive Metabolic Network for TTS
</p>

## Overview
<p align="justify">
The current typical text-to-speech (TTS) techniques fail to perform well on differentiating each speaker's timbre information from the multi-speaker speech dataset. Specially, when the target speaker takes a small proportion of the dataset compared with other speakers, other speakers will severely influence the timbre and pitch of generated speech. This is a difficult problem in TTS. Inspired by animals' digestive process and metabolic activity after taking intake, we propose firstly a general bionic architecture, functional Digestive Metabolic Network (DMN), which could exploit the traditional TTS model. The DMN consists of a digestive network containing pre-net and decomposition-net, and a metabolic network including self-interest classifier and supervised generator. It can ignore the dregs and then absorb the benefits of intake to generate target compound. Simultaneously, we introduce the functional digestive enzyme concept to enhance the performance. Considering the above problem of TTS, we embed the Tacotron2 into the DMN framework, as well as adding the timbre feature as the digestive enzyme. Ablation experiment on the multi-speaker speech dataset shows that the proposed DMN has improved greatly the performance of Tacotron2 on Mean Opinion Score (MOS) and Voice Similarity Score (VSS).
</p>

## Model Architecture
<!-- <center class="half">
    <img src="assets/image/fig1.jpg" width="300"/>
    <img src="assets/image/fig2.jpg" width="300"/>
</center>       <p>&nbsp;</p> 
<p align="center">Figure.1 The architecture of the functional digestive metabolic network,</p> -->

<table>
    <tr>
        <td ><center><img src="assets/image/fig1.jpg"/> </center></td>
        <td ><center><img src="assets/image/fig2.jpg"/> </center></td>
    </tr>
	<tr>
		<th> (A) DMN </th>
		<th> (B) FDMN </th>
<!--         <td>(A) DMN </center></td>
        <td >(B) FDMN </center> </td> -->
    </tr>

​	
</table>
<p align="center">Figure.1 (A) The architecture of the functional digestive metabolic network (DMN). (B) The architecture of the functional digestive metabolic network (FDMN).</p>


<!-- ### General Digestive Metabolic Network

![Model Architecture ](assets/image/fig1.jpg)
<p align="center">Figure.1 The architecture of the general digestive metabolic network.</p>

### Functional Digestive Metabolic Network

![Spectrograms](assets/image/fig2.jpg)
<p align="center">Figure.2 The architecture of the functional digestive metabolic network.</p> -->

## Experiment
### Dataset
We carry out the experiments on a private commercial datasetcollected in Chinese. This dataset contains three speakers, speaker1, speaker2, speaker3, of which there are 4019, 20257,
8915 records, respectively. The total length of the dataset is 30 hours approximately. We randomly split 24000 records of speaker1 and speaker2 for training and 276 records for validation. We randomly select 30, 100, 300, 500 records from speaker3 as training data respectively. Furthermore, the corresponding validation set has 100 records and the corresponding test set has 100 records. To understand in detail the comparision, we count the duration of target speaker's speech in four conditions. The duration of 30, 100, 300, 500 records are about one minute, four minutes, ten minutes, and twenty minutes respectively.


### Results
In order to evaluate the performance of our model, we use the text transcripts in test set as the input of the model, and obtain the synthetic audios, which are rated together with the ground truth audio by speaker3. Here, to describe the superiority of the functional DMN framework, we list the four Tables such as Table1, Table2, Table3 and Table4. Among them, the six texts are in the test set of speaker3. 


<p>&nbsp;</p> 

<script>
function pauseOthers(ele) {
    $("audio").not(ele).each(function (index, audio) {audio.pause();});
}
</script>

<style>
.main-content table {
    display: inline-table;
}
table {
    table-layout:fixed;
    width: 100%;
    overflow: hidden;
}
#player{
    width: 100%;
}
</style>


<table>
	<CAPTION>Table.1 The comparision between the functional DMN (FDMN) and other models when the number of target speaker's speech is 30</CAPTION>
    <tr>
        <th> ID </th>
		<th> Ground Truth</th>
        <th> Tacotron2 </th>
        <th> Tacotron2+x-vector </th>
		<th> DMN</th>
        <th> FDMN </th>
    </tr>
    <tr>
        <th> text1 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/30/0.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/0.mp3" type="audio/mpeg"></audio> </th>
    </tr>

	<tr>
	    <th> text2 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/30/1.wav" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/1.mp3" type="audio/mpeg"></audio> </th>
	</tr>


​	
​	<tr>
​	    <th> text3 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/30/2.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/2.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text4 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/30/3.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/3.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text5 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/30/4.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/4.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text6 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/30/5.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/5.mp3" type="audio/mpeg"></audio> </th>
​	</tr>	
</table>


<p>&nbsp;</p> 


<table>
	<CAPTION>Table.2 The comparision between the functional DMN (FDMN) and other models when the number of target speaker's speech is 100</CAPTION>
    <tr>
        <th> ID </th>
		<th> Ground Truth</th>
        <th> Tacotron2 </th>
        <th> Tacotron2+x-vector </th>
		<th> DMN</th>
        <th> FDMN </th>
    </tr>
    <tr>
        <th> text1 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/0.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/0.mp3" type="audio/mpeg"></audio> </th>
    </tr>

	<tr>
	    <th> text2 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/1.wav" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/1.mp3" type="audio/mpeg"></audio> </th>
	</tr>


​	
​	<tr>
​	    <th> text3 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/2.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/2.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text4 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/3.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/3.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text5 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/4.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/4.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text6 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/5.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/5.mp3" type="audio/mpeg"></audio> </th>
​	</tr>	
</table>

<p>&nbsp;</p> 


<table>
	<CAPTION>Table.3 The comparision between the functional DMN (FDMN) and other models when the number of target speaker's speech is 300</CAPTION>
    <tr>
        <th> ID </th>
		<th> Ground Truth</th>
        <th> Tacotron2 </th>
        <th> Tacotron2+x-vector </th>
		<th> DMN</th>
        <th> FDMN </th>
    </tr>
    <tr>
        <th> text1 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/300/0.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/300/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/300/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/300/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/300/0.mp3" type="audio/mpeg"></audio> </th>
    </tr>

	<tr>
	    <th> text2 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/300/1.wav" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/300/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/300/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/300/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/300/1.mp3" type="audio/mpeg"></audio> </th>
	</tr>


​	
​	<tr>
​	    <th> text3 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/300/2.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/300/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/300/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/300/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/300/2.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text4 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/300/3.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/300/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/300/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/300/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/300/3.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text5 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/300/4.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/300/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/300/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/300/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/300/4.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text6 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/300/5.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/300/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/300/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/300/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/300/5.mp3" type="audio/mpeg"></audio> </th>
​	</tr>	
</table>


<p>&nbsp;</p> 


<table>
	<CAPTION>Table.4 The comparision between the functional DMN (FDMN) and other models when the number of target speaker's speech is 500</CAPTION>
    <tr>
        <th> ID </th>
		<th> Ground Truth</th>
        <th> Tacotron2 </th>
        <th> Tacotron2+x-vector </th>
		<th> DMN</th>
        <th> FDMN </th>
    </tr>
    <tr>
        <th> text1 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/0.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/0.mp3" type="audio/mpeg"></audio> </th>
    </tr>

	<tr>
	    <th> text2 </th>
		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/1.wav" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/1.mp3" type="audio/mpeg"></audio> </th>
	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/1.mp3" type="audio/mpeg"></audio> </th>
	</tr>


​	
​	<tr>
​	    <th> text3 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/2.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/2.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/2.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text4 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/3.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/3.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/3.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text5 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/4.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/4.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/4.mp3" type="audio/mpeg"></audio> </th>
​	</tr>


​	
​	<tr>
​	    <th> text6 </th>
​		<th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Ground_Truth/100/5.wav" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/100/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/100/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/100/5.mp3" type="audio/mpeg"></audio> </th>
​	    <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/100/5.mp3" type="audio/mpeg"></audio> </th>
​	</tr>	
</table>


