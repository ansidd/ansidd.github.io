---
layout: default
---

## Video Search System

---


<html>
<head>
    <script>
        
        var video_list = null

        function send_request(){
            var query = document.getElementById('vid_search_query').value
               fetch('https://ansidd.eastus.cloudapp.azure.com:8000/search/?query='+query,{
                method : 'GET',
                headers : {
                    'Content-Type': 'application/json; charset=UTF-8'
                }
            }
        )
        .then(response => response.json())
        .then(function(response){
            console.log(response);
            textarea = document.getElementById('result')
            video_list = response['result'].split(";")

            vid_table = document.getElementById('vid_table')
            vid_table.removeAttribute('hidden')


            var i=1,l=video_list.length
            var count = 1
            var error = false

            for(i=1; ;i++){
                vid_element = document.getElementById('video'+count)
                vid_source_element = document.getElementById('vid_source_'+count)

                if(i<=l){

                    vid_element.removeAttribute('hidden')
                    vid_element.src= "https://videodatabasearjun.blob.core.windows.net/videos/"+video_list[i-1]+".mp4"
                    //vid_element.src= "https://videodatabasearjun.blob.core.windows.net/videos/video0.mp4"
                    vid_element.addEventListener("error", () => {
                        error = true
                        console.error(`Error loading: ${"https://videodatabasearjun.blob.core.windows.net/videos/"+video_list[i-1]+".mp4"}`);
                    });

                    if(error==true){
                        error = false;
                    }else{
                        count+=1;
                    }



                }else{
                    vid_element.setAttribute('hidden', 'hidden')
                }

                if(count==11){
                    break;
                }

            }

        })
    }
    (document).ready(function () {
   document.getElementById("submit").click();
    });

    </script>
</head>
<body>

<center>

<input type='text' id='vid_search_query' value='Driving car on the highway'>
<button id='submit' onClick="send_request()">Search</button>
<br>
<br>
<table border="0" hidden="hidden" id="vid_table">
    <tr>
        <td>
            <video width="320" height="240" controls id="video1" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_1">
            </video>
        </td>
        <td>
            <video width="320" height="240" controls id="video2" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_2">
            </video>
        </td>
    </tr>
    <tr>
        <td>
            <video width="320" height="240" controls id="video3" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_3">
            </video>
        </td>
        <td>
            <video width="320" height="240" controls id="video4" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_4">
            </video>
        </td>
    </tr>
    <tr>
        <td>
            <video width="320" height="240" controls id="video5" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_5">
            </video>
        </td>
        <td>
            <video width="320" height="240" controls id="video6" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_6">
            </video>
        </td>
    </tr>
    <tr>
        <td>
            <video width="320" height="240" controls id="video7" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_7">
            </video>
        </td>
        <td>
            <video width="320" height="240" controls id="video8" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_8">
            </video>
        </td>
    </tr>
    <tr>
        <td>
            <video width="320" height="240" controls id="video9" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_9">
            </video>
        </td>
        <td>
            <video width="320" height="240" controls id="video10" hidden="hidden">
            <source src="assets/bin/movie.mp4" type="video/mp4" id="'vid_source_10">
            </video>
        </td>
    </tr>
</table>
</center>
</body>
</html>