<p align="justify">
In this post, we show the demo of the Digestive Metabolic Network for TTS
</p>

### Overview
<p align="justify">
The current typical text-to-speech (TTS) technology can hardly differentiate the timbre information of each speaker from the multi-speaker speech dataset. If the target speaker just takes a small proportion of the data set compared with other speakers, other speakers will have a severe influence on the timbre and pitch of the generated voice. Inspired by the digestive process and metabolic activity of animals, we propose a general bionic architecture, functional Digestive Metabolic Network (DMN), which could exploit the traditional TTS model. The DMN consists of the digestive network containing pre-net and decomposition-net, and metabolic network including self-interest classifier and label classifier. It can ignore the timbre information of non-target speakers and then absorb the benefit phoneme information to generate the voice sounding like the target speaker. Simultaneously, we introduce the functional digestive enzyme concept to enhance the timbre similarity towards the target speaker. We embed the original Tacotron2 into the DMN framework, where the $x\text{-}vector$ is regarded as the digestive enzyme. Ablation experiment on multi-speaker speech dataset shows that the proposed functional DMN outperforms other models on Mean Opinion Score (MOS) and Voice Similarity Score (VSS), which demonstrates that the bionic framework could separate the timbre information from speech.
</p>

![Model Architecture ](https://raw.githubusercontent.com/AImusic-zhangxulong/FDMN-TTS/master/assets/image/fig1.png)
<p align="center">Figure.1 The architecture of the general digestive metabolic network.</p>

### Functional Digestive Metabolic Network

![Spectrograms](https://raw.githubusercontent.com/AImusic-zhangxulong/FDMN-TTS/master/assets/image/fig2.png)
<p align="center">Figure.2 The architecture of the functional digestive metabolic network.</p>

### Results

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
    <tr>
        <th> ID </th>
        <th> DMN</th>
        <th> FDMN </th>
        <th> Tacotron2 </th>
        <th> Tacotron2 X-vector </th>
    </tr>
    <tr>
        <th> 1 </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/0.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/0.mp3" type="audio/mpeg"></audio> </th>
    </tr>
    <tr>
        <th> 2</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/1.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/1.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/1.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/1.mp3" type="audio/mpeg"></audio> </th>
    </tr>

      <tr>
        <th> 3 </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/2.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/2.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/2.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/2.mp3" type="audio/mpeg"></audio> </th>
    </tr>


​    
​      <tr>
​        <th> 4 </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/3.mp3" type="audio/mpeg"></audio> </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/3.mp3" type="audio/mpeg"></audio> </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/3.mp3" type="audio/mpeg"></audio> </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/3.mp3" type="audio/mpeg"></audio> </th>
​    </tr>


​    
​    
​      <tr>
​        <th> 5 </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/DMN/30/4.mp3" type="audio/mpeg"></audio> </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/FDMN/30/4.mp3" type="audio/mpeg"></audio> </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2/30/4.mp3" type="audio/mpeg"></audio> </th>
​        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/Tacotron2_x-vec/30/4.mp3" type="audio/mpeg"></audio> </th>
​    </tr>

</table>
