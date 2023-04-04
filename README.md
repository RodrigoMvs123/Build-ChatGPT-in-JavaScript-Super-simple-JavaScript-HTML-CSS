# Build-ChatGPT-in-JavaScript-Super-simple-JavaScript-HTML-CSS

https://www.youtube.com/watch?v=05ssqx-SZT0



index.html
<!DOCTYPE html>
<html lang=”en”>
<head>
          <meta charset=”UTF-8”>
          <meta http-equiv=”X-UA-Compatible” content=”IE=edge”>
          <meta name=”viewport” content=”width=device-width, initial-scale=1.0””>
          <title>Javascript ChatGPT Clone</title>
          <link rel=”stylesheet” href=”styles.css”>
</head>
<body>


<section class=”side-bar”>
          <button>New chat</button>
          <div class=”history”></div>
          <nav>
          <p>Made by Ania</p>
          <nav>
</div>
</section>
<section class=”main”>
          <h1>AniaGPT</h1>
          <p id=”output”></p>
          <div class=”bottom-section”>
          <div class=”input-container”>
          <input/>
          <div id=”submit”>//https://www.compart.com/en/unicode/U+27A2</div>
</div>
          
</div>
<p class=”info”>Chat GPT Mar 14 Version. Free Research Preview. Our goal is to make AI systems more natural and safe to interact with. Your feedback will help us improve. </p>
 </section>

<script src=”app.js”></script>
</body>
</html>


app.js 
const API_KEY = ‘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’
const submitButton = document.querySelector(‘#submit’)
const outPutElement = document.querySelector (‘#output’)
const inputElement = document.querySelector(‘input’)
const historyElement = document.querySelector(‘.history’)
const buttonElement = document.querySelector (‘button’) 

function changeInput(value) {
       const inputElement = document.querySelector (‘input’)
       inputElement.value = value
}

async function getMessage () {
       const.log (‘clicked’)
       const options = {
           method: ‘POST’, 
           headers: {
                  ‘Authorization’: ‘Bearer $ {API_KEY}’,
                  ‘Content-Type’: ‘application/json’

},
body: JSON.stringify ({

        model: "gpt-3.5-turbo",
        messages: [{role: "user", content: inputElement.value }],
        max_tokens: 100
)} 

}

       try {
          const response = await fetch(‘https://api.openai.com/vi/chat/completions’, options)  
          const data = await response. json () 
          console.log (data)
          outPutElement.textContent = data.choises [0]. message.content
          if (data.choises [0]. message.content && inputElement.value) {
               const pElement = document.createElement (‘p’)   
               pElement.textContent = inputElement.value 
               pElement.addEventListener(‘click’, () => changeInput (pElement.textContent))       
               historyElement.append( pElement)   
               
}
 } catch (error) {
       console.error (error) 
   }

}

submitButton.addEventListener (‘click’, getMessage)

function clearIput() {
        inputElement.value = ‘’
}  

buttonElement.addEventListener(‘click’, clearInput)


styles.css
@import url (@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;800&display=swap')

*{
     color: #fff;
     font-family: ‘Open Sans’, sans-serif;
}

body {
      margin:0;
      padding:0;
      background-color: #343541;
      display: flex;
}
      h1 {
      font-size: 33px;
      font-weight: 600;
      padding: 200px 0;
}

.side-bar {
       back-ground-color: #202123;
       width: 244px;
       height: 100vh;
       display: flex;
       flex-direction: column;
       justify-content: space-between;

}

.main {
       display-flex;
       flex-direction: column;
       align-items: center;
       text-align: center;
       justify-content: space-between;
       height: 100vh;
       width: 100%;
}      

.bottom-section {
       width: 100%;
       display-flex;
       flex-direction: column;
       justify-content: center;
       align–items: center;
}

.info {
       color: rgba (255, 255, 255, 0.5);
       font-size: 11px;
       padding: 10px;

}

input {
       border: none;
       background-color: rgba (255,255,255,0.05);
       width: 100%;
       font-size: 20px;
        padding: 12px 15px;
        border-radius: 5px;
        box-shadow: rgba(0,0,0,0,0.5) 0 54px 55px, 
        rgba(0,0,0,0,0.5) 0 -12px 30px, 
        rgba(0,0,0,0,0.5) 0 -4px 6px,
        rgba(0,0,0,0,0.5) 0 -12px 3px,
        rgba(0,0,0,0,0.09) 0 –3px 5px   
}

input:focus {
        outline: none;
        
}

.input-container {
        position: relative;
        width: 100%;
        max-width: 650px;
 }

.input-container # submit {
        position-absolute;
        right: 0;
        bottom: 15px;
        cursor: pointer; 
}

button {
        border: solid 0.5px rgba (255,255,255,0.5);
        background-color: transparent;
        border-radius: 5px;
        padding: 10px;
        margin: 10px;
}

nav {
       border-top: solid 0.5.px rgba (255,255,255,0.5);
       padding: 10px;
       margin: 10px;
}

.history {
        padding: 10px;
        margin: 10px;
        display: flex;
        flex-direction: column;
        height: 100%;
}

.history p {
         cursor: pointer;
}

https://fonts.google.com/specimen/Open+Sans?query=Open+sans
https://www.compart.com/en/unicode/U+27A2
https://platform.openai.com/account/api-keys 
