## Automobile Security at IEEE Hackathon

<img src="https://miro.medium.com/max/6000/1*bkgDXYXDzWqwjgQYhesgkg.jpeg" alt=".hack() by IEEE MACE">


My 27th hackathon .hack() organized by IEEE MACE at KSUM(Kerala Startup Mission) was overflowing with ideas and innovation. Young devs, mentors, volunteers and the amazing participants took the excitement to the next level with their mind-blowing ideas.

The event was an Open Hackathon which allowed the teams to develop projects of their interest. Devs playing with Arduino, Pi, Jetson nano, beacon cards and boards attracted curiosity. While the hardware devs exhibited models from ‘Intelligent Navigation System for Blind People' to ‘The Road that Charges your Electric Car' the software devs touted projects from ‘blockchain chat tracking app' to ‘high-end automobile security’.

I packed my bag and set off to the venue in search of innovative ideas, geeky vibe and free food! Thankfully I met two inspiring teammates and we started working on our project ‘ How to defend your autonomous cars against cyber attacks ? ’.

<img src="https://miro.medium.com/max/6000/1*hw172H_TWf4vLdT41isI0A.jpeg" alt=".hack() by IEEE MACE">
I had an epiphany as I came across the article: how to hack a car. I started my research about the latest developments and advancements in that area and came across this blog. Since I have a background in InfoSec, I dived into the project to defend automobiles from cyber attacks. The possibility of cars getting hacked is increasing day by day as connected cars and V2X communication are the upcoming trends in market.

My Automobile Security for dummies approach focuses on Log Analysis and Incident Response which is the current industry standard for protecting organizational assets. The use of SIEM and SOAR is the backbone for the development of the AutoSec model. Around the globe, various organizational assets ranging from PCs to routers(End point devices) and the Network they’re operating on are being secured by Security Tools like CarbonBlack, Fidelis and Splunk.

So when these devices can be protected WHY NOT AUTONOMOUS CARS? This question intrigued me towards the project I’m currently working on.

Where to get these logs from ? I tried figuring out the working of a car(not from a mechanical engineering perspective) by using CAN Bus simulators and studying the ECUs and finally, figured out the way(**secret**). The next major decision was to move with Cloud Computing with communications over the network or go to with Edge Computing. After hours of brainstorming the 'EDGE' is what I went for.

I collected data sets and started working on Python scripts which can identify an anomaly using LSTM Autoencoders. I’ve used Spark to process the big data efficiently and created a dashboard for visualizing the summary of log analysis using D3 Graphs.

Finally at the 23rd hour of hackathon, the prototype was ready for evaluation. We had a considerably long discussion with the judges regarding the pros and cons of the model. During the conversation we got another idea of adding UEBA feature to the same model. We used Travis-CI, Codecov, Better Code Hub and Deepsource while writing the code and won the special-prize sponsored by Github. The hackathon project was just a beginning, the awesome product is on its way.
Kudos and cheers to every single dev out there who helped us with ideas and kept us motivated !!
