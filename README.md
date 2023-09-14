# Auto Save Textarea
## Step 1: Html file
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Auto Text</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>Auto Save Textarea</h1>
        <textarea id="myTextarea" rows="10" cols="10" placeholder="Start typing here..."></textarea>
    </div>
    <script src="script.js"></script>
</body>
</html>
```
## Step 2: Css file
```
body {
    margin: 0;
    padding: 0;
}

.container {
    height: 90vh;
    padding: 20px;
    background-color: #fff;
    text-align: center;
}

h1 {
    color: #333;
    font-size: 28px;
    margin-bottom: 20px;
}

textarea {
    width: 100%;
   
    font-size: 15px;
    border: 2px solid #d4cbcb;
    min-height:180px;
}

textarea:focus {
    border-color: #2fbfb3;
    box-shadow: 0px 0px 5px rgba(29, 126, 96, 0.5);
}
```
## Step 3 :Javascript file
```
const textarea = document.getElementById("myTextarea");

function saveToLocalStorage(){
    localStorage.setItem("savedText",textarea.value);
}
if(localStorage.getItem("savedText")){
    textarea.value = localStorage.getItem("savedText")
}
textarea.addEventListener("input",saveToLocalStorage);
```
