# Firebase Realtime Database

> ## [Video here](https://www.youtube.com/watch?v=kM-7AWOKTLI)

### This project is ONLY for learning!

©Xchuangc 2021

Source code

```html
<!DOCTYPE html>
<html lang="en">

<head>
  
    <!---import jquery--->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
    
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase Test</title>
  
    <!---Style--->
    <style>
        input {
            height: 50px;
            width: 100px;
            margin-top: 15px;
            font-size: 30px;
            outline: none;
            border: 1px solid black !important;
            transition: 0.5s;
            margin-left: 40%;
        }
        
        input:focus {
            width: 250px;
        }
        
        input:hover {
            width: 250px;
        }
        
        button {
            height: 50px;
            width: 50px;
            margin-top: 15px;
            font-size: 30px;
            outline: none;
            border: 1px solid black !important;
            transition: 0.5s;
            margin-left: 40%;
            background: transparent !important;
            border-radius: 50%;
        }
        
        #get {
            margin-left: 5%;
        }
        
        * {
            user-select: none;
        }
        
        span {
            transition: 1s;
        }
        
        button:hover span {
            transform: rotate(360deg);
        }
        
        button:active span {
            transition: 0.3s;
            transform: translateX(5px);
        }
        
        #text {
            position: absolute;
            resize: none;
            height: 200px;
            margin-top: -180px;
            margin-left: 180px;
            font-size: 30px;
            outline: none;
            border: 1px solid black !important;
            transition: 0.5s;
            background: transparent !important;
        }
    </style>
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Outlined" rel="stylesheet" />
</head>

<body>
  <!---From--->
    <from class="f"><br><br><br><br><br><br><br><br>
        <input type="text" id="name" placeholder="Name" /><br>
        <input type="number" id="year" placeholder="Year" /><br>
        <input type="text" id="school" placeholder="School" /><br>
        <button type="submit" id="submit"> <span class="material-icons-outlined"> send </span> </button>
        <button type="submit" id="get"> <span class="material-icons-outlined"> search </span> </button>
        <textarea id="text" readonly></textarea>
    </from>

    <script type="module">

        // Import the functions you need from the SDKs you need
        import { initializeApp } from "https://www.gstatic.com/firebasejs/9.1.1/firebase-app.js";
        import { getDatabase, ref, set} from "https://www.gstatic.com/firebasejs/9.1.1/firebase-database.js";
        // TODO: Add SDKs for Firebase products that you want to use
        // https://firebase.google.com/docs/web/setup#available-libraries
      
        // Your web app's Firebase configuration
        const firebaseConfig = {
          apiKey: "AIzaSyAO89L5yildOYV8B_kvGpwZ8481gqK4SD8",
          authDomain: "database-test-javascript-xcc.firebaseapp.com",
          projectId: "database-test-javascript-xcc",
          storageBucket: "database-test-javascript-xcc.appspot.com",
          messagingSenderId: "728413118455",
          appId: "1:728413118455:web:66565d9eafd470e47ed8f2",
          databaseURL: "https://database-test-javascript-xcc-default-rtdb.asia-southeast1.firebasedatabase.app/"
        };

        
        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const db = getDatabase();

        // Set data
        function setdata(){
            set(ref(db, name.value), {
                Name: name.value,
                School: school.value,
                Year: year.value,
            });
        }

        // Get data
        function getdata(){
            $.getJSON( "https://database-test-javascript-xcc-default-rtdb.asia-southeast1.firebasedatabase.app/.json", function(data) {
                if(data.hasOwnProperty(name.value)) {
                    console.log(data[name.value]['Name'])
                    console.log(data[name.value]['School'])
                    console.log(data[name.value]['Year'])
                    text.value = `Name: ${data[name.value]['Name']}\nSchool: ${data[name.value]['School']}\nYear: ${data[name.value]['Year']}`
                }

        })}

        // Variables and click events
        const name = document.getElementById('name')
        const school = document.getElementById('school')
        const year = document.getElementById('year')
        const submit = document.getElementById('submit')
        const getd = document.getElementById('get')
        const text = document.getElementById('text')
        submit.addEventListener('click', setdata)
        getd.addEventListener('click', getdata)

      </script>
      
</body>

</html>
```

We use Javascript Css Html to make this file.
