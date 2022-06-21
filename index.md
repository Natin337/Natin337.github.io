<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="../css/fittingstyle.css">
</head>
<body>
    <div class="main">
        <header>
            <div class = "wrapper">
                <img src="./image/피팅 로고.png" alt="로고">
                <nav>
                    <ul class="menu">
                        <li><a href="https://www.instagram.com/fitting.official/"><img src="./image/인스타.png" alt="로고"></a></li>
                        <li><a href="https://www.youtube.com/channel/UCKYAqPJT6SibgZUm4uF1v_A"><img src="./image/유튜브.png" alt="로고"></a></li>
                    </ul>
                </nav>
            </div>
        </header>
        
        <div class="section" id="content1">
            <div class="text">
                <div>
                    <h1>화장품 신상체험<br>집에서 피팅으로 만나보세요</h1>
                </div>
                <div class="button">
                    <a href="https://itunes.apple.com/app/id1518586200"><button type="button" class="button1"></button></a>
                    <a href="http://play.google.com/store/apps/details?id=com.jjang.bangpan2"><button type="button" class="button2" onclick="window.location.href=''"></button></a>
                </div>
            </div>
        </div>

        <div class="section" style="background-color: rgb(108, 21, 223);">
            <div class = "content2">
                <div class = "section1text">
                    <h2>피부 타입에 맞는<br>
                        화장품을           <br>
                        무료체험 하세요!
                    </h2>
                    <p>내 피부에 맞는지 고민되어 주저되던 화장품<br>
                        이제 체험해보고 구매하세요!
                    </p>
                 </div>
                <img src="./image/피팅 휴대폰 그림자.png" alt="피팅 휴대폰" class = "phone1">
            </div>
        </div>
        <div class="section" style="background-color: pink;">3</div>
        <div class="section" style="background-color: palegoldenrod;">4</div>
        <div class="section" style="background-color: violet;">5</div>
        
    </div>

    <script>
        window.onload = function(){
          const elm = document.querySelectorAll('.section');
          const elmCount = elm.length;
          elm.forEach(function(item, index){
            item.addEventListener('mousewheel', function(event){
              event.preventDefault();
              let delta = 0;
    
              if (!event) event = window.event;
              if (event.wheelDelta) {
                  delta = event.wheelDelta / 120;
                  if (window.opera) delta = -delta;
              } 
              else if (event.detail)
                  delta = -event.detail / 3;
    
              let moveTop = window.scrollY;
              let elmSelector = elm[index];
    
              // wheel down : move to next section
              if (delta < 0){
                if (elmSelector !== elmCount-1){
                  try{
                    moveTop = window.pageYOffset + elmSelector.nextElementSibling.getBoundingClientRect().top;
                  }catch(e){}
                }
              }
              
              // wheel up : move to previous section
              else{
                if (elmSelector !== 0){
                  try{
                    moveTop = window.pageYOffset + elmSelector.previousElementSibling.getBoundingClientRect().top;
                  }catch(e){}
                }
              }
    
              const body = document.querySelector('html');
              window.scrollTo({top:moveTop, left:0, behavior:'smooth'});
            });
          });
        }
      </script>
</body>
</html>
