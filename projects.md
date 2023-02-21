---
layout: default
---

# Projects
#### Video Search
What is it?
Basically youtube. Given a text query, the system returns the videos that are most relevant to the query in the database.

The magic behind it:
Dual encoders! We used trained dual encoders of image and text to generate embeddings that locate image and text data close to each other when they're related. We trained the dual encoder using image-captioning dataset. We then perform the video search by sampling images form the videos and generating embeddings of these images and store them in milvus vector database. We then generate an embedding of the text query and find the closest matches and fetch the videos to with these images belong to.

Use it here: <a href="https://ansidd.github.io/video_search.html">Video Search</a>
<a href="https://github.com/arjunnyu/video-search-dl"><img src="assets/bin/github.png" width="30" /></a>
---
#### Face Mask Detection
---
#### Olympics 
---
#### Drug Response
---
#### Sign Language Recognizer
---

