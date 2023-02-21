---
layout: default
---

# Projects
### Video Search
**Collaborators:** <a href="https://www.linkedin.com/in/atsushi-shimizu/">Atsushi Shimizu</a>, <a href="https://www.linkedin.com/in/karthikudhay/">Karthik Udhayakumar</a> 
**What is it?**  
Given a text query, the system returns the videos that are most relevant to the query in the database.

**The magic behind it:**  
Dual encoders! We trained dual encoders of image and text to generate embeddings that locate image and text data close to each other when they're related. We trained the dual encoder using image-captioning dataset. We then perform the video search by sampling images form the videos and generating embeddings of these images and store them in milvus vector database. We then generate an embedding of the text query and find the closest matches and fetch the videos to with these images belong to.

**Use it here:** <a href="https://ansidd.github.io/video_search.html">Video Search</a>  

**Code Repository:** <a href="https://github.com/arjunnyu/video-search-dl"><img src="assets/bin/github.png" width="30" /></a>

---
### Face Mask Detection
**Collaborators:** <a href="https://www.linkedin.com/in/atsushi-shimizu/">Atsushi Shimizu</a>
**What is it?**  
Detects and labels faces in a video feed as "with mask" or "without mask".

**The magic behind it:**
We performed transfer learning on yoloface model to detect the two different categories. yolo is an object detection model. yoloface is a variant of yolo that was trained to identify faces. We used the learning of this model by freezing the upstream layers and training the downstream layers to learn to detect the classes "with mask" or "without mask".

**Code Repository:** <a href="https://github.com/satsushi0/CSGY6923-ML"><img src="assets/bin/github.png" width="30" /></a>


---
### Olympics - A Small Study
**Collaborators:** <a href="https://www.linkedin.com/in/atsushi-shimizu/">Atsushi Shimizu</a>

**View it here:** <a href="https://observablehq.com/@satsushi0/the-olympic-games-a-small-study">Olympics - A Small Study</a>
---
### Drug Response
**Collaborators:** <a href="https://www.linkedin.com/in/arundhati-g/">Arundhati Gorkhe</a>, <a href="https://www.linkedin.com/in/meghana-murthy-26a947150/">Meghana S Murthy</a>
---
### Sign Language Recognizer
**Collaborators:** <a href="https://www.linkedin.com/in/bhavya-97/">Bhavya Jain</a>,
---

