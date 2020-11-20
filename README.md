<!DOCTYPE html>
<html lang="fi">
    <head>
        <title>Etusivu</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        
          <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
    <link href="https://fonts.googleapis.com/css?family=Montserrat" rel="stylesheet">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>

   

    <!-- jQuery -->
      <script src="https://code.jquery.com/jquery-3.5.0.js"></script>
   <!-- Popper JS -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"> </script>
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet">
     
    </head>
    <body>
  
         <!-- The core Firebase JS SDK is always required and must be listed first -->
    <!-- The core Firebase JS SDK is always required and must be listed first -->
    <script src="https://www.gstatic.com/firebasejs/8.0.2/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.0.2/firebase-database.js"></script>

    <!-- TODO: Add SDKs for Firebase products that you want to use
     https://firebase.google.com/docs/web/setup#available-libraries -->
    <script src="https://www.gstatic.com/firebasejs/8.0.2/firebase-analytics.js"></script>
        
          <script>
        // Your web app's Firebase configuration
        // For Firebase JS SDK v7.20.0 and later, measurementId is optional
        var firebaseConfig = {
            apiKey: "AIzaSyAZTue9hrIIvkyCDmsvx71NsbYzsxNMUzM",
            authDomain: "mina-ff47d.firebaseapp.com",
            databaseURL: "https://mina-ff47d.firebaseio.com",
            projectId: "mina-ff47d",
            storageBucket: "mina-ff47d.appspot.com",
            messagingSenderId: "183690180617",
            appId: "1:183690180617:web:d9ce585a7e96ff7bb3a0d8",
            measurementId: "G-VQXKK12KJQ"
        };
        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        firebase.analytics();

        function laheta() {
           

           
            var name = document.getElementById("nimi").value;
            var firebaseRef = firebase.database().ref();
            firebaseRef.child("Viesti").push().set({
         
                "nimi2": name
            });
        }





        //Lisää firebasen viestien lukemis-scripti scriptielementtiin koodin loppuosaan:
        var rootRef = firebase.database().ref().child('Viesti');
        rootRef.on('child_added', snap => {
    
            var name2 = snap.child("nimi2").val();







            $("#nimi").append("<p>" +name2 + "</p>");
           
        })

        </script>


        <div class="header">
            <h1>Tervetuloa!</h1>
            <h2>Tällä sivulla voit tarkastella ja muokata omia tietojasi.</h2>
        </div>
        
        <section>
            
            <div class="flex_container wrapper">
                
                <div class="flex_item">
                    <h2>Henkilötiedot</h2>
                        <label for="nimi">Nimi</label><br>
                        <input class="luku" type="text" id="nimi" name="nimi" value="Erkki Ernest Esimerkki" ><br>
                   
                        <button  onclick="laheta()" class="submit" id="submit">Tallenna muutokset</button>
                </div>
                
              
                
            </div>
            <div id=viestiketju> </div>
            
        </section>
        
      
  
    

    </body>
</html>
