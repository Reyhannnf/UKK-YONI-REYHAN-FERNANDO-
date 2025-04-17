<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Web Kasir Suparman</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f1ee;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #7c6e65;
      color: #fff;
      padding: 1em;
      text-align: center;
    }
    main {
      padding: 20px;
    }
    section {
      margin-bottom: 30px;
      background-color: #fff;
      padding: 15px;
      border-radius: 5px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    h2 {
      color: #5b4d47;
    }
    label {
      display: block;
      margin-top: 10px;
    }
    input, select {
      padding: 8px;
      width: 100%;
      margin-top: 5px;
      box-sizing: border-box;
    }
    button {
      margin-top: 15px;
      background-color: #9d7e6d;
      color: white;
      padding: 10px;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background-color: #7c6e65;
    }
  </style>
</head>
<body>

<header>
  <h1>Sistem Web Kasir Toko yoni</h1>
</header>

<main>
  <!-- Form Pelanggan -->
  <section>
    <h2>Data Pelanggan</h2>
    <label for="nama_pelanggan">Nama Pelanggan:</label>
    <input type="text" id="nama_pelanggan">

    <label for="alamat">Alamat:</label>
    <input type="text" id="alamat">

    <label for="telepon">No. Telepon:</label>
    <input type="text" id="telepon">
  </section>

  <!-- Form Produk -->
  <section>
    <h2>Data Produk</h2>
    <label for="produk">Pilih Produk:</label>
    <select id="produk">
      <option value="produk1">Produk A - Rp10.000</option>
      <option value="produk2">Produk B - Rp20.000</option>
      <!-- Tambah produk dinamis nanti dari database -->
    </select>

    <label for="jumlah">Jumlah:</label>
    <input type="number" id="jumlah" min="1" value="1">
  </section>

  <!-- Form Penjualan -->
  <section>
    <h2>Detail Penjualan</h2>
    <p><strong>Subtotal:</strong> Rp<span id="subtotal">0</span></p>
    <p><strong>PPN (11%):</strong> Rp<span id="ppn">0</span></p>
    <p><strong>Total Bayar:</strong> Rp<span id="total_bayar">0</span></p>
    <button onclick="hitungTotal()">Hitung Total</button>
  </section>
</main>

<script>
  function hitungTotal() {
    let hargaProduk = {
      produk1: 10000,
      produk2: 20000
    };

    const produk = document.getElementById("produk").value;
    const jumlah = parseInt(document.getElementById("jumlah").value);

    const subtotal = hargaProduk[produk] * jumlah;
    const ppn = subtotal * 0.11;
    const total = subtotal + ppn;

    document.getElementById("subtotal").textContent = subtotal.toLocaleString();
    document.getElementById("ppn").textContent = ppn.toLocaleString();
    document.getElementById("total_bayar").textContent = total.toLocaleString();
  }
</script>

</body>
</html>