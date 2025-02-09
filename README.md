

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Order Langsung</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f7f7f7;
            margin: 0;
            padding: 0;
        }
        
        .container {
            width: 100%;
            max-width: 500px;
            margin: 40px auto;
            padding: 20px;
            background-color: #fff;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .header {
            text-align: center;
            margin-bottom: 20px;
        }

        marquee {
            font-size: 18px;
            color: #333;
        }

        h2 {
            font-size: 24px;
            margin-top: 0;
            color: #333;
        }
        
        .button-container {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }
        
        .button {
            background-color: #2F4F7F;
            color: #fff;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            text-align: center;
            width: 48%;
        }
        
        .button:hover {
            background-color: #1A3C5E;
        }
        
        .order-container {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 30px;
        }

        .order-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .order-item select, .order-item input {
            width: 65%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .order-item label {
            width: 30%;
            font-weight: bold;
            text-align: left;
        }

        .order-item button {
            background-color: #4CAF50;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
        }

        .order-item button:hover {
            background-color: #45a049;
        }

        .result {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: #f9f9f9;
            overflow-x: auto;
        }

        /* Styling for the table */
        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 10px;
            text-align: left;
            border: 1px solid #ddd;
        }

        th {
            background-color: #f2f2f2;
            font-weight: bold;
        }

        td {
            text-align: center;
        }

        .product-details {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: #f9f9f9;
            font-size: 14px;
            display: none;
        }

    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <marquee><h2>Selamat Datang Di MWSSTORE   Silahkan Digunakan:)</h2></marquee>
        </div>

        <!-- Buttons -->
        <div class="button-container">
            <button class="button" onclick="cekStock()">Cek Stock</button>
            <button class="button" onclick="refreshData()">Refresh</button>
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
        </div>


        <!-- Action Buttons -->
        <div class="button-container">
            <button class="button" onclick="window.location.href='https://cekareaxl.vercel.app/'">Cek Area</button>
            <button class="button" onclick="window.location.href='https://akrab.nfime.xyz/'">Unreg Akrab</button>

        </div>

        <!-- Action Buttons -->
        <div class="button-container">
            <button class="button" onclick="window.location.href='https://nomorxlku.my.id/?sc=e28d1cade0900dee5b1ce07034258d5b'">Daftar Otp 1</button>
            <br>
            <button class="button" onclick="window.location.href='https://xlotp.my.id/'">Daftar Otp 2</button>
            <br>
            <button class="button" onclick="window.location.href='https://myxl.nfime.xyz/'">Daftar Otp 3</button>
            <br>
        </div>


        <!-- Result Section -->
        <div class="result" id="result"></div>

        <!-- Order Section -->
        <h2>Order Langsung</h2>
        <div class="order-container">
            <div class="order-item">
                <label for="produk">Produk:</label>
                <select id="produk" onchange="showProductDetails()">
                    <option value="jumbo">Jumbo</option>
                    <option value="jumbo_v2">Jumbo V2</option>
                    <option value="big">Big</option>
                    <option value="mini">Mini</option>
                    <option value="superbig">SuperBig</option>
                    <option value="supermini">SuperMini</option>
                    <option value="sepesialjumbo">SepesialJumbo</option>
                </select>
            </div>

            <div class="order-item">
                <label for="nomor">Nomor Telepon:</label>
                <input type="text" id="nomor" placeholder="Nomor Telepon">
            </div>
            <p style="font-size: 12px; color: #666; text-align: center;">Penulisan Nomor Harus Seperti Ini Contoh: 087748842242</p>

            <div class="order-item">
                <button id="beli">Beli Paket</button>
            </div>
        </div>

        <!-- Product Details Section -->
        <div class="product-details" id="productDetails"></div>

    </div>

    <script>
        const nomor = '6287748842242'; 

        // Pesan untuk setiap produk
        const pesanProduk = {
            'jumbo': 'JUMBO : ',
            'jumbo_v2': 'JUMBO V2 : ',
            'big': 'BIG : ',
            'mini': 'MINI : ',
            'superbig': 'SUPERBIG : ',
            'supermini': 'SUPERMINI : ',
            'sepesialjumbo': 'SPESIALJUMBO : '
        };

        // Detail produk
        const produkDetails = {
            'jumbo': {

                kuota: '<br> Area 1 = 67GB <br> Area 2 = 72GB <br> Area 3 = 85GB <br> Area 4 = 125GB <br>',
                noted: '<br> * rewards tidak masuk, tunggu 1 x 24 jam, baru komplen. <br>  * official, resmi, bergaransi.'
            },
            'jumbo_v2': {
   
                kuota: '<br> Area 1 = 50-52GB <br> Area 2 = 52-54GB <br> Area 3 = 57-59GB <br> Area 4 = 67-69GB <br>',
                noted: '<br> * rewards tidak masuk, tunggu 1 x 24 jam, baru komplen. <br>  * official, resmi, bergaransi.'
            },
            'big': {
         
                kuota: '<br> Area 1 = 38-40GB <br> Area 2 = 49-42GB <br> Area 3 = 45-47GB <br> Area 4 = 55-57GB <br>',
                noted: '<br> * rewards tidak masuk, tunggu 1 x 24 jam, baru komplen. <br>  * official, resmi, bergaransi.'
            },
            'mini': {
 
                 kuota: '<br> Area 1 = 31-33GB <br> Area 2 = 33-35GB <br> Area 3 = 38-40GB <br> Area 4 = 48-50GB <br>',
                noted: '<br> * rewards tidak masuk, tunggu 1 x 24 jam, baru komplen. <br>  * official, resmi, bergaransi.'
            },
            'superbig': {
           
                 kuota: '<br> Area 1 = 25-27GB <br> Area 2 = 30-32GB <br> Area 3 = 43-45GB <br> Area 4 = 83-85GB <br>',
                noted: '<br> * rewards tidak masuk, tunggu 1 x 24 jam, baru komplen. <br>  * official, resmi, bergaransi.'
            },
            'supermini': {
                kuota: '<br> Area 1 = 13-15GB <br> Area 2 = 15-17GB <br> Area 3 = 20-22GB <br> Area 4 = 30-32GB <br>',
                noted: '<br> * rewards tidak masuk, tunggu 1 x 24 jam, baru komplen. <br>  * official, resmi, bergaransi.'
            },
            'sepesialjumbo': {
                kuota: '<br> Area 1 = 88-90GB <br> Area 2 = 90-92GB <br> Area 3 = 95-97GB <br> Area 4 = 105-107GB <br>',
                noted: '<br> * rewards tidak masuk, tunggu 1 x 24 jam, baru komplen. <br>  * official, resmi, bergaransi.'
            }
        };

        // Menampilkan detail produk saat dipilih
        function showProductDetails() {
            const produk = document.getElementById('produk').value;
            const productDetailDiv = document.getElementById('productDetails');
            const details = produkDetails[produk];

            productDetailDiv.innerHTML = `
                <strong>Details Kuota:</strong> ${details.kuota} <br>
                <strong>Noted:</strong> ${details.noted}
            `;

            productDetailDiv.style.display = 'block';
        }

 
        // Fungsi Order
        document.getElementById('beli').addEventListener('click', function() {
            const produk = document.getElementById('produk').value;
            const nomorTelepon = document.getElementById('nomor').value;
            const url = `https://wa.me/${nomor}?text=${pesanProduk[produk]}${nomorTelepon}`;
            window.open(url, '_blank');
        });
    </script>
</body>
</html>
