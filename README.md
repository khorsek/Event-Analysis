# Event-Analysis Project

# This is the lab writeup of the time I had to analyze a PCAP file that was recorded while a home network was "experiencing significant events". I'll try to answer a few questions and determine what could have happened during this session. 

# This lab was done a few months ago and I'm just importing this info to document on GitHub.

# The first thing I do is open up my Windows virtual machine that I have for training purposes and look for my PCAP file. Once I find it on the desktop, I open it up in Network Miner, an open source application for exploratory analysis and visualization of large network data. 

# Once it loads, I get my first view of all the information for me to parse through.
<img src="images\1.PNG">

# Looking at the image, it has about 1695 parameters, 83 hosts, 62 files, 16 images, and so on.

# The first thing that I think to check is to see how long exactly, the entire session capture lasted. So I open up the sessions tab and compare the start time of the first entry to the very last one:
<img src="images\2.PNG">

# So the session began capturing at about 9:30 PM in 12 hour time and lasted until 9:37 PM, a total of 7 minutes worth of captured data.Now that I’ve determined how long the session capture lasted, I try to determine how many packets were “captured” or received as it’s known in Network Miner. To get the number of packet’s captured, I moved back to the “hosts” tab and sorted each host by the number of received packets(descending). As seen in the figure 3 below, I circled the area where it’s shown how many packets are captured and this way, I went down each host and calculated the sum of all these packets until I got the total amount of packets captured.
<img src="images\3.PNG">
<img src="images\4.PNG">

# After going down each of the highlighted hosts and calculating the total amount of packets received, the number comes out to ~2325 packets and ~768,933 bytes captured over the entire 7 minute session which is surely a handful. Now that I’ve determined exactly how many packets and bytes were captured, I move on to try to see which protocols(or application layers) were observed during the entire 7 minute capture. To do this, I move on over to the “Sessions” tab and immediately, you can see each of the Sessions showing which protocol was observed for them. If I sort by Protocol, I can see a number of different protocols that were observed, those being: FTPControl, HTTP, Oscar, and SSL. You can see a glimpse in the figure below:
<img src="images\5.PNG">

