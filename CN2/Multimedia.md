multimedia means different types of media like audio video text images animation etc. 
## Digitizing audio and video
- **Digitizing Audio:-** 
	- when sound is fed into microphone an electronic signal is generated which is of analog nature 
	- this then has to be digitized according to nyquist theorem that is it is sampled at 2f times per second for a frequency f
- **Digitizing video**
	- video refers to the moving pictures accompanied by sound such as a picture in television A video consist of sequence of frames
	- if frames are displayed on the screen fast enough we get impression of motion 
	- there is no standard frames per second however 25 frames per second is common 
	- each frame is divided into small grids called picture element or pixels 
	- for a black and white each 8-bit pixel represent of 256 different gray levels 
	- for a color tv each pixel is 24bits with 8 bits for each primary color

## Audio and video compression
- in order to save storage space and efficient transfer it is necessary to compress the digital data 
- Compression is a reduction in the number of bits needed to represent data the data in the form of text audio video images and animation and so on
- lossy compression involves loss of information and the data that can be compressed using lossy compression cannot be recovered or restored to its original form
- lossless compression however involves no loss of information it the data have been losslessly compressed the original data can be recovered or restored 

	- **Audio compression-**
		- Uncompressed audio is bulky and not appropriate for transmission over network 
		- Audio compression can be used for speech or music for speech we need to compress a 64Khz signal for music we need to compress 1.411Mhz signal
		- two categories of techniques are used for audio compression:
			- **Predictive encoding**: In this encoding the differences between the samples are encoded instead of encoding all the sampled values Predictive encoding compression is normally used for speech 
			- **Perceptual encoding**: it is the most common compression technique used to create CD- quality audio this type of audio needs ate least 1.411 Mbps. This cannot be sent over the internet without compression MP3 also uses this encoding. the idea is based on some flaws in our auditory system. some sounds can mask other sounds masking can happen in frequency and time . In frequency masking a loud sound in frequency range can particularly mask a softer sound. In temporal masking a loud sound can numb our ears for a short time even after the sound has stopped MP3 uses both to compress audio
	 - Video Compression:-
		 - Video compression is done by compressing its individual frames two most common methods are JPEG (Joint photographic experts group) and MPEG ( moving pictures experts group) used to compress video
		 - Image compression (JPEG):
			 - Image compression is the process of encoding or converting an image file in such a way that it consumes less storage space than the original file 
			 - If a picture is not in color each pixel can be represented by 8-bit integer if the picture is in color each picture is represented by 24 bits with each 8 bit representing red blue or green 
			 - the whole picture is divided into blocks of 8x8 pixels and passed through 3 phases
				 - phase 1 :discrete cosine transform (DCT):
					 - In DCT each block of 64 pixels goes through a transformation the transformation changes the values so that the relative relationship between pixels are kept but the redundancies are revealed. 
				- phase 2 :quantization
					- it is lossy compression technique in which the values are quantized to reduce the number of bits needed for encoding
					- here we divide the number by a constant and then drop the fraction this reduces the required number of bits even more 
				- phase 3 : Compression:
					- after quantization the values are read form the table and redundant 0's are removed the table is read in a zig zag order this is the reason that the picture changes smoothly
		- Video compression (MPEG)
			- it is the process of reducing total number of bits needed to represent a given image 
			- the mpeg is used to compress video in principal a motion picture is a rapid flow of set of frames
			- this means compressing each frame individually 
			- the spatial compression of each frame is done with JPEG and each frame is individually compressed 
			- in temporal compression redundant frames are removed that is similar frames are dropped

## Streaming audio and Video
- in stored audio and video streaming the files are stored on a server and a client download the files through the internet 
- there are three approaches to this each with a different complexity
	- 1st approach (Using a web server):
		- a compressed audio or video file can be downloaded as a text file 
		- the web server can send compressed file to the browser the browser can then use a help application to play the file
		- this is a simple method but has drawbacks like an audio / video file is large even after compression in this approach the file needs to be downloaded completely before it can be played
		- this takes a long time to play the media and also uses unnecessary space
		- ![[1stapproach to stream.png]]
	- 2nd approach (using a web server with metafile)
		- in this approach the media player is directly connected to the Web Server for downloading the audio/video file
		- the web server stores two files namely the actual file and a metadata file that holds information about the audio/video file
		- this approach is very slow as media player uses http which uses TCP
		- ![[2nd approach.png]]
	- 3rd approach (using a media server):
		- In this method we use TCP to retrieve metafile but uses UDP to retrieve the audio / video file 
		- this is not directly possible since web server is designed for TCP only hence we use a separate media server which holds the audio /video file 
		- this file is accessed using UDP for a much faster download 
		- ![[3rd approach.png]]
	- fourth approach (using a media server and RTSP):
		- The RTSP (Real time streaming protocol) is designed to add functionalities to the streaming process
		- using RTSP we can control the playing of audio / video. RTSP is an out-of-band connection protocol that is similar to the second connection in FTP
		- ![[4th approach.png]]

## Streaming live audio and video
In Streaming live audio and video the user receives the file in real time as its being created example includes live television etc
live streaming is better suited to protocols like UDP and RTP (Real-time transport protocol )

## Real time interactive audio and video
in real-time interactive audio/video people use internet to achieve communication with each other 
some characteristic of it are 
1. Time relationship 
	1. real time data on a packet switched network require preservation of the time relationship between the packets of a session
	2. for eg imagine there are 3 packets the first packet start at 0s the second at 10s and the third at 20s 
	3. also imagine that it takes 1s to reach the receiver (equal delay)
	4. then at the receiver can play the packet at 1s , 11s, and 21s respectively
2. Timestamp 
	1. it is a solution of jitter. here each packet has a timestamp different from its arrival time 
	2. the timestamp shows the time the packet was produced relative to the first packet then the receiver can add this time to the time at which it starts the playback
	3. for eg if packets are timestamped as 0s 10s and 20s and at the receiver the first packet reaches at 8s then the second packet will be played at 18s and the third at 28s hence there are no gaps 
3. Playback buffer
	1. the playback buffer is used to store the packets received until they are ready to be played 
	2. the receiver delays playing data until a threshold is reached 
4. Ordering
	1. we need to number packets so that the receiver knows if a particular packet has been lost
	2. suppose the timestamps are 0, 10 and 20 if second packet start the receiver assumes that the second packet is the packet with timestamp 20
5. multicasting
	1. real time traffic needs to support multicasting for communication can be between multiple sources and receivers
6. translation
	1. sometimes we need to translate high bandwidth data to low bandwidth data for better transmission  
7. Mixing
	1. if there are more than one sources transmitting then we need to converge data from multiple sources 