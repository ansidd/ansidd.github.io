---
layout: default
---

## Retrieval Augmented Generation - BMS

---

<html>
<head>
    <style>
        div.with-breaks {
        white-space: pre-wrap;
        }   
    </style>
    <script>
        
        var video_list = null

    function displayData(data) {
        const dataContainer = document.getElementById('dataContainer');
        dataContainer.textContent = data;
    }


        function send_request(){
            displayData("Processing Request... It takes a bit of time for the first query, it picks up speed afterwards!")

            var query = document.getElementById('search_query').value
               fetch('https://ansidd.eastus.cloudapp.azure.com:8000/rag_bms/?query='+query,{
                method : 'GET',
                headers : {
                    'Content-Type': 'application/json; charset=UTF-8'
                }
            }
        )
        .then(response => response.json())
        .then(function(response){
            response = response.split("\n")
            response = response.join("") 
            console.log(response);
            displayData(response);

        })};

    </script>
</head>
<body>

<center>

<input type='text' id='search_query' value='Enter your query' style="width: 200px">
<button id='submit' onClick="send_request()">Search</button>
<br>
<br>
<div>Example queries to get you started:   
What is the mission of Bristol Myers Squibb? ; What is the culture at BMS like?; Where is the headquarters of BMS?
</div>
<div>-------</div>
<div class="with-breaks" id="dataContainer">
Please enter a query!</div>
</center>
</body>
</html>