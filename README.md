# uas

# index.php

<?php
include "koneksi.php";
?>

<!DOCTYPE html>
<html>
<head>

<title>Project UAS</title>

<style>

body{

font-family:Arial;
margin:30px;

}

table{

border-collapse:collapse;
width:100%;

}

table,th,td{

border:1px solid black;
padding:8px;

}

</style>

</head>

<body>

<h2>Tambah Data Penjualan</h2>

<form action="simpan.php" method="POST">

Barang

<select name="id_barang">

<?php

$data=mysqli_query($conn,"SELECT * FROM barang");

while($d=mysqli_fetch_array($data)){

?>

<option value="<?= $d['id_barang']; ?>">

<?= $d['nama_barang']; ?>

</option>

<?php } ?>

</select>

<br><br>

Jumlah

<input type="number" name="jumlah">

<br><br>

Tanggal

<input type="date" name="tanggal">

<br><br>

<button>Simpan</button>

</form>

<hr>

<h2>Data Master Barang</h2>

<table>

<tr>

<th>ID</th>

<th>Nama Barang</th>

<th>Harga</th>

<th>Stok</th>

</tr>

<?php

$data=mysqli_query($conn,"SELECT * FROM barang");

while($d=mysqli_fetch_array($data)){

?>

<tr>

<td><?= $d['id_barang']; ?></td>

<td><?= $d['nama_barang']; ?></td>

<td>Rp <?= number_format($d['harga']); ?></td>

<td><?= $d['stok']; ?></td>

</tr>

<?php } ?>

</table>

</body>

</html>
