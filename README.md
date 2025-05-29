<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <title>اختبار بريد الجزائر</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      direction: rtl;
      background-color: #f4f4f4;
      padding: 20px;
    }
    .container {
      background: white;
      padding: 20px;
      border-radius: 10px;
      max-width: 800px;
      margin: auto;
      box-shadow: 0 0 10px #ccc;
    }
    h1 {
      text-align: center;
      color: #006400;
    }
    .question {
      margin-bottom: 15px;
      padding: 10px;
      background: #f9f9f9;
      border-radius: 8px;
    }
    .question p {
      margin: 0 0 10px;
      font-weight: bold;
    }
    .result {
      text-align: center;
      font-size: 20px;
      margin-top: 20px;
      font-weight: bold;
    }
    .btn {
      display: block;
      margin: 20px auto;
      padding: 10px 25px;
      font-size: 18px;
      background: #28a745;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div class="container">
  <h1>اختبار بريد الجزائر</h1>

  <form id="quizForm">
    <div class="question">
      <p>1. ما هي العملة الوطنية في الجزائر؟</p>
      <label><input type="radio" name="q1" value="أ"> الدولار</label><br>
      <label><input type="radio" name="q1" value="ب"> اليورو</label><br>
      <label><input type="radio" name="q1" value="ج"> الدينار</label>
    </div>

    <div class="question">
      <p>2. ما هو دور البنك المركزي؟</p>
      <label><input type="radio" name="q2" value="أ"> جمع الضرائب</label><br>
      <label><input type="radio" name="q2" value="ب"> طبع النقود</label><br>
      <label><input type="radio" name="q2" value="ج"> تقديم القروض العقارية</label>
    </div>

    <!-- أضف المزيد من الأسئلة هنا بنفس النمط -->

    <button type="button" class="btn" onclick="showResult()">عرض النتيجة</button>
  </form>

  <div id="result" class="result"></div>
</div>

<script>
  const answers = {
    q1: "ج",
    q2: "ب",
    // أضف باقي الإجابات هنا
  };

  function showResult() {
    let score = 0;
    let total = Object.keys(answers).length;

    for (let q in answers) {
      const selected = document.querySelector(`input[name="${q}"]:checked`);
      if (selected && selected.value === answers[q]) {
        score++;
      }
    }

    const result = document.getElementById("result");
    result.innerHTML = `✔️ نتيجتك: ${score} / ${total} - ${score >= total / 2 ? "ناجح" : "راسب"}`;
    result.style.color = score >= total / 2 ? "green" : "red";
  }
</script>

</body>
</html>
