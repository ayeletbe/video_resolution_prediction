# Video_Resolution_Prediction
Identifying video resolution of encrypted videos

The purpose is to measure the quality of a cellular network out of the customers video's streeming events. 
High video resolutions should indicate high quality, however low video resolutions should indicate poor quality. 

### Dataset 
The dataset contains information about ~250 videos.  
Every row in the data corresponds to packet, there is a label for each packet which determines the video resolution of this packet. The labels are collected every second, each packet within that second receives the sampled label. 

### Features 
1. Time_epoch – The time epoch as captured by wireshark. 
2. Conn_id – Unique identifier for every connection. 
3. Is_inbound – The direction of the packet, inbound or outbound. 
4. Payload_size – The number of bytes of the tcp/udp payload, basically this is the size of the video in this packet.
5. Ip_proto – L4 protocol, 6=TCP, 17=UDP/QUIC 6. Sni – if client hello packet, this column contains the SNI. 
7. Quic_user_agent – ignore 
### Identifiers 
1. url_id – Unique identifier for each video. Note that the data may contain the same video more than once, different resolutions for example. In this case the url_id is the same.
2. Video_id – Unique identifier for each video playing. In the example above of same video different resolutions, the identifier is different unlike url_id. Note you cannot use the video_id as a feature. Finally, you should generate a prediction per video_id. 

### Labels 
1. Resolution – The video resolution: 0=360p, 1=480p, 2=720p, 3=180p 
