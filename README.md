<!DOCTYPE html>
<html lang="my">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>For You </title>

  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family: Arial, sans-serif;
    }

    body{
      height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      background: linear-gradient(135deg,#ff9ecf,#ffd6e7);
      overflow:hidden;
    }

    .card{
      width:350px;
      padding:30px;
      border-radius:25px;
      background:white;
      text-align:center;
      box-shadow:0 10px 30px rgba(0,0,0,0.2);
      animation:fadeIn 1.5s ease;
      position:relative;
      z-index:2;
    }

    h1{
      color:#ff4f8b;
      margin-bottom:15px;
      font-size:32px;
    }

    p{
      color:#444;
      line-height:1.7;
      margin-bottom:20px;
    }

    .heart{
      font-size:70px;
      animation:beat 1s infinite;
    }

    button{
      padding:12px 25px;
      border:none;
      border-radius:30px;
      background:#ff4f8b;
      color:white;
      font-size:16px;
      cursor:pointer;
      transition:0.3s;
    }

    button:hover{
      transform:scale(1.08);
      background:#ff2f74;
    }

    .hidden{
      display:none;
      margin-top:20px;
      color:#ff2f74;
      font-size:20px;
      font-weight:bold;
    }

    @keyframes beat{
      0%{transform:scale(1);}
      50%{transform:scale(1.2);}
      100%{transform:scale(1);}
    }

    @keyframes fadeIn{
      from{
        opacity:0;
        transform:translateY(30px);
      }
      to{
        opacity:1;
        transform:translateY(0);
      }
    }

    .floating-heart{
      position:absolute;
      color:white;
      font-size:20px;
      animation:float 6s linear infinite;
      opacity:0.7;
    }

    @keyframes float{
      0%{
        transform:translateY(100vh) scale(0);
      }
      100%{
        transform:translateY(-10vh) scale(1.5);
      }
    }
  </style>
</head>
<body>

  <div class="card">
    <div class="heart"></div>

    <h1>Hey Beautiful</h1>

    <p>
      နေ့တိုင်းပြုံးနိုင်အောင်လုပ်ပေးချင်တဲ့သူက<br>
      မောင်ပါ <br><br>

      မ နဲ့စကားပြောရတဲ့အချိန်တိုင်းက<br>
      မောင်အတွက် special ဖြစ်နေတယ် 
    </p>

    <button onclick="showMessage()">
      Click Me 
    </button>

    <div class="hidden" id="msg">
      I Like You So Much 
    </div>
  </div>

  <script>
    function showMessage(){
      document.getElementById("msg").style.display = "block";
    }

    // Floating Hearts
    function createHeart(){
      const heart = document.createElement("div");
      heart.classList.add("floating-heart");
      heart.innerHTML = "";

      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = Math.random() * 20 + 15 + "px";
      heart.style.animationDuration = Math.random() * 3 + 3 + "s";

      document.body.appendChild(heart);

      setTimeout(()=>{
        heart.remove();
      },6000);
    }

    setInterval(createHeart,300);
  </script>

</body>
</html>
