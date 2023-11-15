import firebase from 'firebase/app';
import 'firebase/auth';
// Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
    apiKey: "AIzaSyCBH7nQrvUV0imDxg6EGUIrddvoxJwjhN4",
    authDomain: "e-shop-3931a.firebaseapp.com",
    databaseURL: "https://e-shop-3931a-default-rtdb.firebaseio.com",
    projectId: "e-shop-3931a",
    storageBucket: "e-shop-3931a.appspot.com",
    messagingSenderId: "1054682549402",
    appId: "1:1054682549402:web:042bd1184c044ba4a0a323",
    measurementId: "G-MXJSG4V3DW"
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);
  //get input fields
let emailInput = document.getElementById('Email');
let passwordInput = document.getElementById('Password');
let confirmpasswordInput = document.getElementById('confirm-Password');

//register with google account
document.getElementById('google-btn').addEventListener('click',(e)=>{
    signInWithRedirect(auth, provider);

    getRedirectResult(auth)
  .then((result) => {
    // This gives you a Google Access Token. You can use it to access Google APIs.
    const credential = GoogleAuthProvider.credentialFromResult(result);
    const token = credential.accessToken;

    // The signed-in user info.
    const user = result.user;
    // IdP data available using getAdditionalUserInfo(result)
    // name

    alert(user.displayName);
  }).catch((error) => {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;
    // The email of the user's account used.
    const email = error.customData.email;
    // The AuthCredential type that was used.
    const credential = GoogleAuthProvider.credentialFromError(error);
    // ...
  });
})


// Register User
document.getElementById('register-btn').addEventListener('click', function () {
    const email = document.getElementById('Email').value;
    const password = document.getElementById('Password').value;
    const confirmPassword = document.getElementById('confirm-Password').value;

    if (password !== confirmPassword) {
        alert('Passwords do not match.');
        return;
    }

    auth.createUserWithEmailAndPassword(email, password)
      
            // Store user information in the database
            // Replace the following code with your database logic
            const userRef = firebase.database().ref('users/' + user.uid);
            userRef.set({
              
                email: email
            });

            console.log('Registration successful for user: ', user);
            // Redirect to another page or perform other actions
        })
        .catch((error) => {
            const errorCode = error.code;
            const errorMessage = error.message;
            console.error('Registration error:', errorCode, errorMessage);
        });


// Login User
document.getElementById('login-btn').addEventListener('click', function () {
    const email = document.getElementById('Email').value;
    const password = document.getElementById('Password').value;

    auth.signInWithEmailAndPassword(email, password)
        .then((userCredential) => {
            const user = userCredential.user;
            console.log('Login successful for user: ', user);
            // Redirect to another page or perform other actions
        })
        .catch((error) => {
            const errorCode = error.code;
            const errorMessage = error.message;
            console.error('Login error:', errorCode, errorMessage);
        });
});
  