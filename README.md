<!DOCTYPE html>
<html>
  <head>
    <title>Hitung Indeks Prestasi</title>
    <style>
        /* Reset default margin and padding */
body, h2, form, p {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  /* Body styling */
  body {
    font-family: 'Arial', sans-serif;
    background: linear-gradient(120deg, #a1c4fd, #c2e9fb);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
  }
  
  /* Form container */
  form {
    background-color: white;
    padding: 20px 25px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    max-width: 400px;
    width: 100%;
  }
  
  h2 {
    text-align: center;
    color: #444;
    margin-bottom: 20px;
  }
  
  div {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    font-weight: bold;
    color: #555;
    margin-bottom: 5px;
  }
  
  input[type="number"] {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 16px;
    color: #333;
  }
  
  input[type="number"]:focus {
    outline: none;
    border-color: #4a90e2;
    box-shadow: 0 0 5px rgba(74, 144, 226, 0.5);
  }
  
  /* Button styling */
  button {
    display: block;
    width: 100%;
    padding: 10px;
    background: #4a90e2;
    color: white;
    font-size: 16px;
    font-weight: bold;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s ease;
  }
  
  button:hover {
    background: #357ABD;
  }
  
  /* Result paragraph styling */
  #result {
    margin-top: 20px;
    text-align: center;
    font-size: 18px;
    color: #333;
    font-weight: bold;
  }
  
    </style>
  </head>
  <body>
    <h2>Hitung Indeks Prestasi</h2>
    <form>
      <div>
        <label for="quis">Quis (10%):</label>
        <input type="number" id="quis" min="0" max="100" required>
      </div>
      <div>
        <label for="tugas">Tugas (20%):</label>
        <input type="number" id="tugas" min="0" max="100" required>
      </div>
      <div>
        <label for="uts">UTS (30%):</label>
        <input type="number" id="uts" min="0" max="100" required>
      </div>
      <div>
        <label for="uas">UAS (40%):</label>
        <input type="number" id="uas" min="0" max="100" required>
      </div>
      <button type="button" onclick="calculateIndeks()">Hitung</button>
    </form>

    <p id="result"></p>

    <script>
      function calculateIndeks() {
        const quis = parseFloat(document.getElementById("quis").value);
        const tugas = parseFloat(document.getElementById("tugas").value);
        const uts = parseFloat(document.getElementById("uts").value);
        const uas = parseFloat(document.getElementById("uas").value);

        const totalScore = (quis * 0.1) + (tugas * 0.2) + (uts * 0.3) + (uas * 0.4);
        let indeks;
        let keterangan;

        if (totalScore >= 80 && totalScore <= 100) {
          indeks = "A";
          keterangan = "Lulus dengan Sangat Baik";
        } else if (totalScore >= 68 && totalScore < 80) {
          indeks = "B";
          keterangan = "Lulus dengan Baik";
        } else if (totalScore >= 55 && totalScore < 68) {
          indeks = "C";
          keterangan = "Lulus dengan Cukup";
        } else if (totalScore >= 38 && totalScore < 55) {
          indeks = "D";
          keterangan = "Lulus dengan Kurang";
        } else {
          indeks = "E";
          keterangan = "Tidak Lulus";
        }

        document.getElementById("result").textContent = `Indeks Prestasi: ${indeks}, Keterangan: ${keterangan}`;
      }
    </script>
  </body>
</html>
