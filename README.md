<style>      /* Gaya untuk tombol */
    .button {
        background: #45a049;
        color: #fff;
        padding: 10px 15px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        text-align: center;
        width: 48%;
        font-size: 14px;
    }

    .button:hover {
        background: #1A3C5E;
    }

    /* Gaya untuk tombol panjang */
    .button-long {
        background: #45a049;
        color: #fff;
        padding: 10px 15px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        text-align: center;
        width: 100%;
        font-size: 14px;
        margin-top: 10px;
    }

    .button-long:hover {
        background: #1A3C5E;
    }</style>


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DAFTAR PRODUK</title>
    <style>
        .container {
            max-width: 800px;
            margin: 40px auto;
            padding: 20px;
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        
        #produk-select {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
        }
        
        #deskripsi-produk {
            padding: 20px;
            background-color: #f7f7f7;
            border: 1px solid #ddd;
        }

        #deskripsi-produk {
    padding: 20px;
    background-color: #f7f7f7;
    border: 1px solid #ddd;
    line-height: 1.5; /* tambahkan spasi antara baris */
}


    </style>
</head>
<body>
    <div class="container">
        <h1>Daftar Produk</h1>
        <select id="produk-select"></select>
        <div id="deskripsi-produk"></div>
    </div>

    <script>
        const produkSelect = document.getElementById('produk-select');
        const deskripsiProduk = document.getElementById('deskripsi-produk');

        fetch('https://api.sheetbest.com/sheets/94fe5133-fb31-4d45-b025-da7b9efb6130')
        .then(response => response.json())
        .then(data => {
            const produkOptions = data.map(produk => {
                return `
                    <option value="${produk.nama_produk}">${produk.nama_produk}</option>
                `;
            }).join('');

            produkSelect.innerHTML = produkOptions;

            produkSelect.addEventListener('change', (e) => {
                const selectedProduk = e.target.value;
                const selectedProdukData = data.find(produk => produk.nama_produk === selectedProduk);

                deskripsiProduk.innerHTML = selectedProdukData.deskripsi_produk;
            });
        })
        .catch(error => console.error(error));

        namaSelect.addEventListener('change', (e) => {
    const selectedNama = e.target.value;
    const selectedProdukData = data.find(produk => produk.NAMA === selectedNama);

    const deskripsi = selectedProdukData.DESKRIPSI;
    const deskripsiWithLineBreak = deskripsi.replace(/([.!?])\s+/g, '$1<br><br>'); // tambahkan <br> setelah titik, tanda tanya, dan tanda seru

    deskripsiProduk.innerHTML = deskripsiWithLineBreak;
});



    </script>
</body>
</html>


<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CEK STOK TERSEDIA</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f7f7f7;
    }
    .container {
      width: 100%;
      max-width: 95%;
      margin: 40px auto;
      padding: 20px;
      background-color: #fff;
      border: 1px solid #ddd;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    #cek-stok-btn {
      background-color: #4CAF50;
      color: #fff;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    #result {
      margin-top: 20px;
    }
    table {
      border-collapse: collapse;
      width: 100%;
    }
    th, td {
      border: 1px solid #ddd;
      padding: 10px;
      text-align: left;
    }
    th {
      background-color: #f2f2f2;
      font-weight: bold;
    }
    .stok-hijau {
      color: #008000;
    }
  </style>
</head>
<body>

      <head>
        <title>Title of the document</title>
        <style>
          .button {
            background-color: #1c87c9;
            border: none;
            color: white;
            padding: 10px 4px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 15px;
            margin: 4px 2px;
            cursor: pointer;
          }
        </style>
      </head>
      <center>
      <body>
        <a href="https://cekareaxl.vercel.app/" class="button">CEK AREA</a>
        <a href="https://akrab.nfime.xyz/" class="button">UNREG AKRAB</a>
      </body>
      <body>
        <a href="https://nomorxlku.my.id/?sc=e28d1cade0900dee5b1ce07034258d5b" class="button">DAFTAR OTP V1</a>
        <a href="https://xlotp.my.id/" class="button">DAFTAR OTP V2</a>
        <a href="https://myxl.nfime.xyz/" class="button">DAFTAR OTP V3</a>
        <a href="https://chat.whatsapp.com/F1ddFA7kVNTBLT7ZD6XRvZ" class="button">JOIN GRUP WA</a>
      </body></center>
    </html>


    <CENTER>
  <div class="container">
    <h1>CEK STOK TERSEDIA</h1>
   

<style>
    #cek-stok-btn {
        background-color: #1ba11f;
        color: #dfe676;
        padding: 15px 30px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        font-size: 18px;
        font-weight: bold;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        transition: background-color 0.3s ease;
    }
    
    #cek-stok-btn:hover {
        background-color: #3e8e41;
    }
    
    </style>

    <button id="cek-stok-btn">Cek Stok</button>

    <div id="result"></div> </CENTER>
  </div>

  <script>
    const cekStokBtn = document.getElementById('cek-stok-btn');
    const resultDiv = document.getElementById('result');

    cekStokBtn.addEventListener('click', () => {
      fetch('https://panel.khfy-store.com/api/api-xl-v7/cek_stock_akrab', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded',
          'Accept': 'application/json'
        }
      })
      .then(response => response.json())
      .then(data => {
        const stok = data.message.split('\n');
        const table = document.createElement('table');
        const thead = document.createElement('thead');
        const tbody = document.createElement('tbody');
        table.appendChild(thead);
        table.appendChild(tbody);
        resultDiv.innerHTML = '';
        resultDiv.appendChild(table);

        const row = document.createElement('tr');
        thead.appendChild(row);
        const th1 = document.createElement('th');
        th1.innerHTML = 'Produk';
        row.appendChild(th1);
        const th2 = document.createElement('th');
        th2.innerHTML = 'Stok';
        row.appendChild(th2);

        stok.forEach(item => {
          const [produk, stoknya] = item.split(': ');
          const row = document.createElement('tr');
          tbody.appendChild(row);
          const td1 = document.createElement('td');
          td1.innerHTML = produk;
          row.appendChild(td1);
          const td2 = document.createElement('td');
          td2.innerHTML = stoknya;
          td2.classList.add('stok-hijau');
          row.appendChild(td2);
        });
      })
      .catch(error => {
        resultDiv.innerHTML = 'Error: ' + error.message;
      });
    });
  </script>




</body>
</html>
