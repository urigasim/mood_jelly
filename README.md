<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>MOOD JELLY</title>
  <style>
    body {
      margin: 0;
      font-family: 'Helvetica Neue', sans-serif;
      background: #fffafc;
      color: #333;
    }

    header {
      background: #ffe4ec;
      padding: 2rem 1rem;
      text-align: center;
      box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    }

    header h1 {
      font-size: 3rem;
      color: #ff69b4;
      margin-bottom: 1rem;
    }

    .mood-buttons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
    }

    .mood-buttons button {
      border: none;
      background: #fff0f5;
      cursor: pointer;
      border-radius: 10px;
      padding: 0.8rem;
      text-align: center;
      font-size: 0.9rem;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      transition: 0.3s;
    }

    .mood-buttons img {
      width: 60px;
      height: 60px;
      border-radius: 50%;
      display: block;
      margin: 0 auto 0.3rem;
    }

    section {
      max-width: 800px;
      margin: 2rem auto;
      padding: 0 1rem;
    }

    details {
      background: #fff;
      border: 1px solid #ffdae5;
      border-radius: 10px;
      margin-bottom: 1rem;
      padding: 1rem;
      box-shadow: 0 0 5px rgba(0,0,0,0.03);
    }

    summary {
      font-weight: bold;
      font-size: 1.2rem;
      color: #d63384;
      cursor: pointer;
      outline: none;
    }

    summary:hover {
      color: #c2185b;
    }

    details[open] summary {
      margin-bottom: 1rem;
    }
  </style>
</head>
<body>

  <header>
    <h1>MOOD JELLY</h1>
    <div class="mood-buttons">
      <button onclick="showJoyMessage()"><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fshop1.phinf.naver.net%2F20240413_191%2F1712936627434GYqYq_JPEG%2F114072526137161227_368206349.jpg&type=sc960_832" alt="기쁨"/><div>기쁨</div></button>
      <button><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAxODA0MjVfMjYg%2FMDAxNTI0NjM1NzYxNjk4.MHesKk68ZTSE_YIB7fMpFpbPC7DS-zqqoNcrQ3H60iMg.CA-CmYNprUu_GBjrFoGPjPkpzQQwqn2qZ3Pv8Cy8jrcg.JPEG.su20981%2Foutput_251131031.jpg&type=a340" alt="슬픔"/><div>슬픔</div></button>
      <button><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMDA0MDVfMTgg%2FMDAxNTg2MDY2MjIzMjgx.s7K-cTHlMCdv9gK1DOaGXY7emhjCCtTSXBnRg5n6NqMg.JEh8VfhGB7apoU4IZaDPiqWpe2wM24Ahg24WRT52yGUg.JPEG.liscjs%2F20200404_124449.jpg&type=a340" alt="짜증"/><div>짜증</div></button>
      <button><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMjAxMTRfMjc1%2FMDAxNjQyMTUzMDY1NjY2.gDqxRQnGoNXK3cVjCCkCaiu__Qo70IDuMfF5x9Z68qYg.2FT3ydXEk2ArGQF_5KyZqb3YzTwPv5vW72CxLsn_9qsg.JPEG.dnel0123%2F20220114_183002.jpg&type=a340" alt="화남"/><div>화남</div></button>
      <button><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAxODAzMjlfNTIg%2FMDAxNTIyMzI5MzczNzk2.prlIp4WtITUGrNYg6L8mivay0-nR9QKkd41ZWojbWnQg.OrB647uMOZnv5XQfsK5Rd_S-FNJcE4boLXmlsStaz10g.JPEG.eos660%2F20180328_172436.jpg&type=a340" alt="평온"/><div>평온</div></button>
      <button><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMzA2MDlfNDMg%2FMDAxNjg2Mjc3NTM1MTI2.BgDL1twzoS2fa1jymH6otJ4NJhdZ8AIAV-XflOvJgaYg._P94IyE52uG79rurDVjzF9sGVveu5qBtfctEmQyaawEg.JPEG.ryu0200%2F20230604_140951.jpg&type=a340" alt="피곤"/><div>피곤</div></button>
      <button><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fshop1.phinf.naver.net%2F20231228_44%2F1703694145961pTyIC_JPEG%2F104829988670259886_1816887481.jpeg&type=a340" alt="설렘"/><div>설렘</div></button>
      <button><img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyNDA0MDFfMTk1%2FMDAxNzExOTY3NDEwODA0.P4--cfvil82xlDyKVGP6vhPfGCsp-fu0Hgwctq1gWDAg._fZxwQwjWLvI48EmKhqk89VoxnC2xY7T58RAzqLirwIg.JPEG%2F%25BB%25E7%25BF%25F6%25C1%25A9%25B8%25AE_13.jpg&type=a340" alt="불안"/><div>불안</div></button>
    </div>
  </header>

  <section>
    <details>
      <summary>1. 젤리 추천 미리보기 🍬</summary>
      <p>감정에 따라 추천되는 젤리 조합을 미리 확인해보세요!<br>🍋기쁠 땐 망고젤리🍋 🍇슬플 땐 포도젤리🍇 🍊짜증날 땐 오렌지 젤리🍊 
        🍍화가 날 땐 파인젤리🍍 <br>🍒평온할 땐 체리 젤리🍒 🥃피곤할 땐 에너지 젤리🥃 🧡설렐 때는 하트 젤리🧡 🌈불안할 땐 무지개 젤리🌈</p>
    </details>

    <details>
      <summary>2. 서비스 소개 📦</summary>
      <p>3단계로 간단히 즐기세요!<br>① 기분 입력 → ② 젤리 추천 → ③ 배송 또는 선물!</p>
    </details>

    <details>
      <summary>3. 구독 안내 및 혜택 💌</summary>
      <p>1.💐 기분 한 스푼 요금제 (Light Plan)💐
        <br>구성: 감정별 맞춤 젤리 1팩 + 메시지 카드
        <br>주기: 월 1회 배송
        <br>가격: 9,900원 / 월
        <br>추천 대상: 가볍게 기분을 표현하고 싶은 분
        <br>특징: 깜짝 선물처럼 소소하게 전할 수 있는 미니 플랜
        <br><br>2.🌈 무드 테라피 요금제 (Standard Plan)🌈
        <br>구성: 감정 맞춤 젤리 3팩 + 기분별 음료 샘플 + 메시지 카드
        <br>주기: 월 2회 배송 (감정 입력 기반 자동 추천)
        <br>가격: 18,900원 / 월
        <br>추천 대상: 스트레스 해소나 감정 관리가 필요한 직장인, 학생
        <br>특징: 기분 케어 + 테라피 효과를 함께 누릴 수 있는 실속형
        <br><br>첫 구독 시 10% 할인 혜택 제공!<br><br>기분에 맞춘 배송일 선택도 가능해요.</p>
    </details>

    <details>
      <summary>4. 선물하기 🎁</summary>
      <p>감정에 어울리는 젤리와 메시지 카드로 감성을 선물하세요!<br>디자인 카드와 맞춤 메시지 포함 💖</p>
    </details>

    <details>
      <summary>5. 고객 후기/리뷰 💬</summary>
      <p>진심이 담긴 후기들로 신뢰도 UP!<br>1."하루 종일 스트레스 받았는데, 상큼한 레몬 젤리를 먹고 나니 기분이 훨씬 나아졌어요 🍋 다음에도 또 주문할게요!"
      <br>2."설레는 하루에 딱 어울리는 딸기 젤리였어요. 포장도 너무 예뻐서 기분까지 좋아졌어요!"
      <br>3."일 끝나고 지친 몸에 딱이었어요. 젤리 하나에 에너지가 느껴져요 ⚡ 재구매 의사 100%입니다."
      <br>4."좋은 일이 있어서 주문했는데, 포도 젤리랑 기분이 찰떡이었어요! 친구한테도 추천했어요."
      <br>5."중요한 발표 전에 너무 긴장됐는데, 말랑한 구미 젤리를 천천히 씹으면서 마음이 좀 가라앉았어요. 의외로 효과 있었어요!"</p>
    </details>
  </section>

  <script>
    function showJoyMessage() {
      alert("런칭 기념 10000원 이상 구매 시 배송비 무료!!");
    }
  </script>
</body>
</html>
