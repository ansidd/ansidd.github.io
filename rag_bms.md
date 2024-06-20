---
layout: default
---

## Retrieval Augmented Generation - BMS

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
               fetch('https://ansidd.eastus.cloudapp.azure.com:8000/rag_bms/?query='+query,{
                method : 'GET',
                headers : {
                    'Content-Type': 'application/json; charset=UTF-8'
                }
            }
        )
        .then(response => response.json())
        .then(function(response){
            console.log(response);
            response = (response.split(";")[:2]).join("\n")
            response = response.replace("\n", "<br>")
            displayData(response);

        })};

    </script>
</head>
<body>

<center>

<input type='text' id='vid_search_query' value='What is the mission of Bristol Myers Squibb?' style="width: 200px">
<button id='submit' onClick="send_request()">Search</button>
<br>
<br>
<div id="dataContainer">Loading data...</div>
</center>
</body>
</html>