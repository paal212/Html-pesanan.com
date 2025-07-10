<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Pecel Lele Lezat</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #fffbea;
    }
    header {
      background-color: #f57c00;
      color: white;
      padding: 20px;
      text-align: center;
    }
    .container {
      padding: 20px;
    }
    .menu-item, .info, .form-section {
      background-color: #fff;
      padding: 15px;
      margin-bottom: 20px;
      border-left: 5px solid #f57c00;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    h2 {
      margin-top: 0;
    }
    label {
      display: block;
      margin: 10px 0 5px;
    }
    input, select, textarea {
      width: 100%;
      padding: 8px;
      margin-bottom: 10px;
      box-sizing: border-box;
    }
    button {
      background-color: #f57c00;
      color: white;
      border: none;
      padding: 10px 20px;
      cursor: pointer;
      width: 100%;
    }
    button:hover {
      background-color: #e65100;
    }
    footer {
      background-color: #eeeeee;
      text-align: center;
      padding: 15px;
      font-size: 14px;
    }
  </style>
</head>
<body>

  <header>
    <h1>Pecel Lele Lezat</h1>
    <p>Menu Lezat, Bahan Fresh, Sistem PO</p>
  </header>

  <div class="container">
    <section class="menu-item">
      <h2>Menu Hari Ini</h2>
      <ul>
        <li><strong>Lele Goreng</strong> (Lele + Nasi + Lalapan) - Rp.15.000</li>
        <li><strong>Ayam Goreng</strong> (Ayam + Nasi + Lalapan) - Rp.20.000</li>
        <li><strong>Ayam Ketumbar</strong> (Ayam + Nasi Jeruk + Lalapan) - Rp.25.000</li>
      </ul>
    </section>

    <section class="info">
      <h2>Sistem Pemesanan</h2>
      <p>Pemesanan menggunakan sistem <strong>PO H-1</strong> untuk menjaga kualitas dan kesegaran bahan.</p>
      <p>Alamat: Krangean, Kertanegara, Purbalingga</p>
      <p>No HP: <a href="https://wa.me/6285283453531">0852-8345-3531</a></p>
    </section>

    <section class="form-section">
      <h2>Form Pemesanan</h2>
      <form id="orderForm">
        <label for="nama">Nama Pemesan:</label>
        <input type="text" id="nama" name="nama" required />

        <label for="menu">Pilih Menu:</label>
        <select id="menu" name="menu" required>
          <option value="Lele Goreng">Lele Goreng - Rp15.000</option>
          <option value="Ayam Goreng">Ayam Goreng - Rp20.000</option>
          <option value="Ayam Ketumbar">Ayam Ketumbar - Rp25.000</option>
        </select>

        <label for="jumlah">Jumlah Porsi:</label>
        <input type="number" id="jumlah" name="jumlah" min="1" required />

        <label for="catatan">Catatan Tambahan:</label>
        <textarea id="catatan" name="catatan" rows="3"></textarea>

        <button type="submit">Kirim Pesanan via WhatsApp</button>
      </form>
    </section>
  </div>

  <footer>
    &copy; 2025 Pecel Lele Lezat - Dibuat dengan â¤ï¸ di Purbalingga
  </footer>

  <script>
    document.getElementById("orderForm").addEventListener("submit", function(e) {
      e.preventDefault();

      const nama = document.getElementById("nama").value;
      const menu = document.getElementById("menu").value;
      const jumlah = document.getElementById("jumlah").value;
      const catatan = document.getElementById("catatan").value;
      const nomor = "6285283453531"; // nomor WA tujuan

      const pesan = `Halo! Saya ingin pesan:\n\nNama: ${nama}\nMenu: ${menu}\nJumlah: ${jumlah} porsi\nCatatan: ${catatan}\n\nPemesanan PO H-1 ya. Terima kasih!`;
      const encodedPesan = encodeURIComponent(pesan);

      const link = `https://wa.me/${nomor}?text=${encodedPesan}`;
      window.open(link, "_blank");
    });
  </script>
</body>
</html>
