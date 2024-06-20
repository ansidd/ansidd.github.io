---
layout: default
---

## Video Search System

---


<html>
<head>
    <script>
        
        var video_list = null

    function displayData(data) {
        const dataContainer = document.getElementById('dataContainer');
        dataContainer.textContent = JSON.stringify(data, null, 2);
    }


        function send_request(){
            var query = document.getElementById('vid_search_query').value
               fetch('https://ansidd.eastus.cloudapp.azure.com:8000/rag/?query='+query,{
                method : 'GET',
                headers : {
                    'Content-Type': 'application/json; charset=UTF-8'
                }
            }
        )
        .then(response => response.json())
        .then(function(response){
            console.log(response);

            displayData(data);

        })};

    </script>
</head>
<body>

<center>

<input type='text' id='vid_search_query' value='Driving car on the highway'>
<button id='submit' onClick="send_request()">Search</button>
<br>
<br>
<div id="dataContainer">Loading data...</div>
</center>
</body>
</html>