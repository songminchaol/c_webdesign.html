# c_webdesign.html

<!DOCTYPE html>
    <html lang="ko-KR">
    <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="../css/common/reset.css">
      <link rel="stylesheet" href="../css/common/common.css">
      <link rel="stylesheet" href="../css/src/c_02_web.css">
      <script src="../js/common/modernizr-custom.js"></script>
      <title>Document</title>
    </head>
<style>
/* c_02_web.css */
/* * { margin: 0; padding: 0; border: 0;
box-sizing: border-box;} */

/* --------------------------- */
/*  디스플레이논도좋음
#wrap
워렙의 가로값은 1200을기준으로
가로가운데 배치해야한다.

이때,내부에 존재하는 헤드박스가
상단에 픽스드로배치했다.

-그로인해 헤드박스뒤에오는 뷰박스가 상단으로올라갔다.

-왜?
헤드박스가 포지션픽스드로되어서,

형제요소개념이 아닌 별도의 위치로배치하는 (브라우저기준)
내용이 되었기떄문.

-그래서, 뷰박스에 내용을 화면에
온전히 보이게 만들기위해

-조건: 헤드박스 배경색이
불투명
-wrap
강제로 하위 내용이 배치하루있도록
밀어내자!!
(padding-top:100px;)이다.*/
#wrap {
  width: 1200px; height:auto; min-height:700px;
  margin:auto; 
  /* padding-top: 100px; */

/* *{margin:0;
padding:0;
border:0;
boxsizing:border_box} */

/* #headBox */
/* 내가 코드쓸거를정리해사 써보고 께획을 쓰고 
아웃풋해라 행동해라 실행해라*/

/* #headBox */
/* #headBox를 상단에 고정: position:fixed
    1. top 0, 가로 가운데 배치 (전체 가로 꽉차게):width100%
      - width100% 는? #wrap에 꽉찬거 아닌가?
      - 왜 아니지? fixed는 브라우저를 기준으로 처리
    2. 다른요소들보다 앞에 배치 :
    3. fixed를 처리함으로 인해 다른 요소(형제)들은? 
    4. 내부 요소는 가로 1200크기일때 가운데 배치?
내가하고자하는걸 쓰자!! 적용중요*/


 #headBox{
  position: fixed; top:0; left:0;  z-index: 1500;
  width:100%; height:100px; 
  padding:0 20px; padding-top: 60px; box-sizing: border-box;
  background-color: rgba(200,200,200,0.5);
}

  .head_wrapper {
    width: 1200px; height:40px;
    margin:auto; 
  }
/* 부모가어디있느지알아야자식도 위치잡는다*/






h1{
      float:left; width: 200px; height: 40px;
      background-color: #afa;
    }
    .navigation {
      float:right; width: 600px; height: 30px; 
      margin-top: 10px;
      background-color: #aff;
    }
    .navigation > ul {
      width: 100%; height: auto;
      background-color: #999;
    }
    .navigation > ul > li {
      float:left;
      width: 25%; height:auto;
      padding:0 5px;
    }

    .nav_title { width: 100%; height:30px; }
    .nav_title a {
      display: block;
      width: 100%; height: 100%; 
      text-align: center; line-height:30px;}

    .nav_list { 
      display: none;
      width: 100%; height: auto;
      color:#fff;
      background-color: #333;}
    .nav_list li{ width: 100%; height: 40px; margin-bottom:10px;}
    .nav_list a{
    display: block; width: 100%; height:100%;
    text-align: center; line-height: 40px;
    }



  /* 마우스커버 코드 전체커버, 개인커버 */
  .navigation:hover .nav_list {display: block;}
  .nav_title:hover {background-color: #171717; color:#fff; }

/*.navigation li:hover > .nav_list{display:block}*/

/* .nav_title :hover + .nav_list{display: block;} */




/* 클릭이안됨 */
/* csss는안되지만 자바스크립가능
 */
/* 마우스호버
1.mousrenter
2.mouseleave 
자바스크립 코드줄많음
순서대로생각
많이써야함
할거많음*/


/* #viewBox */
/* 왜? headBox뒤에 붙을까? 해결방법은?
    - headBox 가 fixed처리되어있으니 headBox는 공중에 떠있어서 해당부분이 비어있다. 그래서 headBox자리에 viewBox가 자리를 차지한다.
    - 높이값이 300이지만 우리에겐 200만큼만 보이더라 ㅜㅜ
    - 우린 300을 원한다구.!
    - 그럼 실제로는 400만큼의 크기를 가져야 300이 보이는데 어케???
    - 상단에 100을 추가하자 ( 선택: margin/padding )
    - 그래!! padding-top이야! 
    - 그런데? 왜 안으로 들어가지?
    - reset에 box-sizing:border-box가 있어!!!
    - ???? 언제? 시른데? -> box-sizing:content-box

    /*---------------- */

/* #viewBox */
#viewBox{
    width:100%; height:300px; background-color: #aaa;
  }
  
/* #contentbox */
#contentbox{ width:100%; height:200px; }
  #contentbox > .con_area {
    float:left; width:400px; height:200px;
    padding:10px 30px; box-sizing: border-box;
  }
  .notice_area { background-color: #afd;}

.con_part { width: 100%; height: 150px; border:1px solid #777; }
.con_part ul { width: 100%; height:auto;  }
/* .con_part ul:after {content:""; display: block; clear:both;} */


.notice_area ul { 
    list-style:decimal; 
    padding:10px; padding-left:30px; box-sizing: border-box;}
  .notice_area li { width: 100%; height:25px; margin-bottom:10px; }

  .gallery_area {counter-reset:gal_li; background-color: #daf;}
  .gallery_area li:before { counter-increment:gal_li; content:counter(gal_li) ". "; }

 
  .notice_area ul { 
    list-style:decimal; 
    padding:10px; padding-left:30px; box-sizing: border-box;}
  .notice_area li { width: 100%; height:25px; margin-bottom:10px; }



/* 신기술 속성 */
/* 검색결과 기술 */
.gallery_area {counter-reset:gal_li; background-color: #daf;}
  .gallery_area li:before { counter-increment:gal_li; content:counter(gal_li) ". "; }



    .gallery_area li:before{counter-increment: gal_li ;
    content: counter(gal_li)".";}

/* 플렉스 부모요소컨트롤 */
.gallery_area ul {display:flex; justify-content: space-between;}
  .gallery_area li {
    /* float:left;  */
    width:100px; height:150px;
    /* margin-right:19px;  */
    background-color: #fff;}  
  .gallery_area li:last-child {margin: 0;}

  .commercial_area { background-color: #afd;}




  /* 탭메뉴설정가이드 */
.con_part{display: block;}
.con_area>h3:hover+.con_part{display: block;}



/* #otherBox */
#otherBox { 
  width: 900px; height:800px;
  margin:30px auto;
  background-image:linear-gradient(#aaf , #faa);
}

/* #footBox */
#footBox{
  width:100%; height:100px; 
  padding:30px 20px; padding-bottom:50px;
  background-color: #999;
}
  #footBox > h2 {
    float:left; width:200px; height:40px;
    background-color: #faa;
  }
  address {
    float:left; width:600px; height:30px; 
    margin-top:10px; margin-left:100px;
    background-color: #afa;
  }
  .family {
    float:right; width:200px; height:30px;
    margin-top:10px;
    background-color: #aaf;
  }






</style>




</head>

    <body><div id="wrap">
        <header id="headBox">
          <div class="head_wrapper">
            <h1>사이트</h1>
            <nav class="navigation">
              <h2 class="blind">네비게이션</h2>
              <ul>
                <li>
                  <div class="nav_title"><a href="#">재단소개</a></div>
                  <ul class="nav_list">
                    <li><a href="#">설립취지</a></li>
                    <li><a href="#">연혁</a></li>
                    <li><a href="#">찾아오시는길</a></li>
                  </ul>
                </li>
                <li>
                  <div class="nav_title"><a href="#">후원하기</a></div>
                  <ul class="nav_list">
                    <li><a href="#">국내후원</a></li>
                    <li><a href="#">국외후원</a></li>
                    <li><a href="#">맞춤후원</a></li>
                  </ul>
                </li>
                <li>
                  <div class="nav_title"><a href="#">자료실</a></div>
                  <ul class="nav_list">
                    <li><a href="#">서식자료실</a></li>
                    <li><a href="#">사진자료실</a></li>
                    <li><a href="#">후원양식</a></li>
                  </ul>
                </li>
                <li>
                  <div class="nav_title"><a href="#">스토리</a></div>
                  <ul class="nav_list">
                    <li><a href="#">웹진</a></li>
                    <li><a href="#">보고서</a></li>
                    <li><a href="#">나의 후원</a></li>
                  </ul>
                </li>
              </ul>
            </nav>
          </div>
        </header>
    
        <section id="viewBox">
          <h2 class="blind">광고</h2>
        </section>
    
        <article id="contentbox">
          <h2 class="blind">본문내용</h2>
          <section class="con_area notice_area">
            <h3>공지사항</h3>
            <div class="con_part">
              <ul>
                <li>공지사항: Lorem ipsum dolor sit.</li>
                <li>공지사항: Lorem ipsum dolor sit.</li>
                <li>공지사항: Lorem ipsum dolor sit.</li>
                <li>공지사항: Lorem ipsum dolor sit.</li>
              </ul>
            </div>
          </section>
    
          <section class="con_area gallery_area">
            <h3>갤러리</h3>
            <div class="con_part">
              <ul>
                <li>gallery_01</li>
                <li>gallery_02</li>
                <li>gallery_03</li>
              </ul>
            </div>
          </section>
    
          <section class="con_area commercial_area">
            <h3 class="blind">commercial</h3>
          </section>
        </article>
    
        <aside id="otherBox"></aside>
    
        <footer id="footBox">
          <h2>사이트이름</h2>
          <address>copyright</address>
          <div class="family"></div>
        </footer>
      </div>
    </body>
    </html>
    <!-- 
      시멘틱구조에서 :
      웹페이지의 본문의 성격을 띄는 article/section의 형식은
      내부에 다시 header/article/section/nav/aside/footer...을 가질 수 있다.
      하지만 header/aside/footer/nav의 특정위치나, 기능의 성향을 가지고있는 요소는 내부에 section/article을 사용할 수 없다.
      header의 경우는 내부에 nav요소를 가질 수 있다.
    -->
