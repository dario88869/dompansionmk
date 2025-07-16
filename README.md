<!DOCTYPE html>
<html lang="mk">
<head>
  <meta charset="UTF-8">
  <title>Дом Пансион – Резервации</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      margin: 0;
      padding: 0;
    }

    header {
      background: #ffcc70;
      text-align: center;
      padding: 20px;
    }

    header h1 {
      margin: 0;
      font-size: 2em;
    }

    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      padding: 20px;
      background: #fff;
    }

    .gallery img {
      width: 250px;
      height: 200px;
      object-fit: cover;
      border-radius: 10px;
    }

    .main-content {
      padding: 30px;
      max-width: 600px;
      margin: auto;
      background: white;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      border-radius: 10px;
    }

    .main-content input, select {
      display: block;
      width: 100%;
      margin-top: 10px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .main-content button {
      margin-top: 15px;
      padding: 10px;
      background: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    .hidden {
      display: none;
    }

    .success-message {
      text-align: center;
      color: green;
      font-weight: bold;
      margin-top: 20px;
    }
  </style>
</head>
<body>

<header>
  <h1>🐶🐱 Дом Пансион - Резервации за миленичиња</h1>
</header>

<div class="gallery">
  <img src="https://placedog.net/500/400?id=1" alt="куче">
  <img src="https://placekitten.com/500/400" alt="маче">
  <img src="https://placedog.net/500/400?id=2" alt="куче">
  <img src="https://placekitten.com/501/400" alt="маче">
</div>

<div class="main-content">
  <label for="date">Внеси го твојот датум:</label>
  <input type="date" id="date">
  <button onclick="checkAvailability()">Провери достапност</button>

  <div id="availability" class="hidden">
    ✅ Слободен термин! Пополнете ги деталите подолу:
    <form action="https://formspree.io/f/xqalkgbg" method="POST">
      <select name="petType" required>
        <option value="">Избери миленик</option>
        <option>Куче</option>
        <option>Маче</option>
      </select>

      <select name="size" required>
        <option value="">Големина</option>
        <option>Мал раст</option>
        <option>Среден раст</option>
        <option>Голем раст</option>
      </select>

      <input type="number" name="age" placeholder="Години на миленикот" required>
      <input type="text" name="petName" placeholder="Име на миленикот" required>
      <input type="text" name="ownerName" placeholder="Име на сопственикот" required>
      <input type="tel" name="phone" placeholder="Телефонски број" required>

      <button type="submit">Резервирај</button>
    </form>
  </div>

  <div id="thanks" class="success-message hidden">
    ✅ Ви благодариме за довербата! Ќе ве контактираме наскоро.
  </div>
</div>

<script>
  function checkAvailability() {
    const date = document.getElementById("date").value;
    if (!date) {
      alert("Ве молиме внесете датум.");
      return;
    }

    // Тука можеш да ставиш правила ако има зафатени датуми
    document.getElementById("availability").classList.remove("hidden");
  }

  function submitForm(event) {
    event.preventDefault();
    document.getElementById("reservationForm").classList.add("hidden");
    document.getElementById("thanks").classList.remove("hidden");

    // Ова е пример: тука може да вклучиш интеграција со EmailJS/Formspree
    console.log("Form submitted. Може да се прати со EmailJS тука.");
  }
</script>

</body>
</html># dompansionmk
