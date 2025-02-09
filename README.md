
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cek Stock XL Akrab</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f7f7f7;
        }
        
        .container {
            max-width: 400px;
            margin: 40px auto;
            padding: 20px;
            background-color: #fff;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        
        .button {
            background-color: #4CAF50;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        
        .button:hover {
            background-color: #3e8e41;
        }
        
        .result {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: #f9f9f9;
        }
        
        .result table {
            width: 100%;
            border-collapse: collapse;
        }
        
        .result th, .result td {
            border: 1px solid #ddd;
            padding: 10px;
            text-align: left;
        }
        
        .result th {
            background-color: #f0f0f0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Cek Stock XL Akrab</h2>
        <button class="button" onclick="cekStock()">Cek Stock</button>
        <button class="button" onclick="refreshData()">Refresh</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function cekStock() {
            const url = "https://panel.khfy-store.com/api/api-xl-v7/cek_stock_akrab";
            fetch(url, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/x-www-form-urlencoded',
                    'Accept': 'application/json'
                }
            })
            .then(response => response.json())
            .then(data => {
                const result = document.getElementById('result');
                result.innerHTML = '';
                const table = document.createElement('table');
                const thead = document.createElement('thead');
                const tbody = document.createElement('tbody');
                table.appendChild(thead);
                table.appendChild(tbody);
                result.appendChild(table);
                const row = document.createElement('tr');
                thead.appendChild(row);
                const th1 = document.createElement('th');
                th1.innerHTML = 'Produk';
                row.appendChild(th1);
                const th2 = document.createElement('th');
                th2.innerHTML = 'Stok';
                row.appendChild(th2);
                const produkList = {
                    'xxl_rw': 'Jumbo',
                    'xxl_rw_v2': 'Jumbo V2',
                    'xl_rw': 'Big',
                    'xl_no_rw': 'Mini',
                    'xxl_only': 'SuperBig',
                    'xl_only': 'SuperMini'
                };
                for (const key in produkList) {
                    const row = document.createElement('tr');
                    tbody.appendChild(row);
                    const td1 = document.createElement('td');
                    td1.innerHTML = produkList[key];
                    row.appendChild(td1);
                    const td2 = document.createElement('td');
                    td2.innerHTML = data.data[key];
                    row.appendChild(td2);
                }
            })
            .catch(error => {
                const result = document.getElementById('result');
                result.innerHTML = 'Error: ' + error.message;
            });
        }

        function refreshData() {
            cekStock();
        }
    </script>
</body>
</html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Order Langsung</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f7f7f7;
        }
        
        .container {
            max-width: 400px;
            margin: 40px auto;
            padding: 20px;
            background-color: #fff;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        
        .kolom {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }
        
        .judul {
            width: 100px;
            font-weight: bold;
            margin-right: 10px;
        }
        
        .text-area {
            width: 150px;
            height: 30px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-right: 10px;
        }
        
        .button {
            background-color: #2F4F7F; /* Biru Tua */
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        
        .button:hover {
            background-color: #1A3C5E; /* Biru Tua Gelap */
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Order Langsung</h2>
        <div class="kolom">
            <span class="judul">Mini:</span>
            <input type="text" id="nomor1" class="text-area" placeholder="Nomor Telepon">
            <a href="#" id="beli-paket1" class="button">Beli Paket</a>
        </div>
        <div class="kolom">
            <span class="judul">Big:</span>
            <input type="text" id="nomor2" class="text-area" placeholder="Nomor Telepon">
            <a href="#" id="beli-paket2" class="button">Beli Paket</a>
        </div>
        <div class="kolom">
            <span class="judul">Jumbo:</span>
            <input type="text" id="nomor3" class="text-area" placeholder="Nomor Telepon">
            <a href="#" id="beli-paket3" class="button">Beli Paket</a>
        </div>
    </div>

    <script>
        const nomor = '6287847526737'; 
        const pesan = 'MAS MAU ORDER DI NOMOR TUJUAN : '; 

        document.getElementById('beli-paket1').addEventListener('click', function() {
            const nomorTelepon = document.getElementById('nomor1').value;
            const url = `https://wa.me/${nomor}?text=${pesan}${nomorTelepon}`;
            window.open(url, '_blank');
        });

        document.getElementById('beli-paket2').addEventListener('click', function() {
            const nomorTelepon = document.getElementById('nomor2').value;
            const url = `https://wa.me/${nomor}?text=${pesan}${nomorTelepon}`;
            window.open(url, '_blank');
        });

        document.getElementById('beli-paket3').addEventListener('click', function() {
            const nomorTelepon = document.getElementById('nomor3').value;
            const url = `https://wa.me/${nomor}?text=${pesan}${nomorTelepon}`;
            window.open(url, '_blank');
        });
    </script>
</body>
</html>
