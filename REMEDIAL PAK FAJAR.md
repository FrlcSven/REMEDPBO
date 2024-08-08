void main() {

  // Kumpulan data: daftar nilai siswa

  List<int> nilaiSiswa = [85, 90, 78, 92, 88, 76, 95, 60, 70, 100];

  

  // Menggunakan set untuk menyimpan nilai unik

  Set<int> nilaiUnik = Set.from(nilaiSiswa);

  

  // Menghitung statistik

  Map<String, dynamic> statistik = hitungStatistik(nilaiUnik);

  

  // Menampilkan hasil

  print('Nilai Unik: $nilaiUnik');

  print('Jumlah bilangan genap: ${statistik['genap']}');

  print('Jumlah bilangan ganjil: ${statistik['ganjil']}');

  print('Nilai maksimum: ${statistik['maksimum']}');

  print('Nilai minimum: ${statistik['minimum']}');

}

  

// Fungsi untuk menghitung jumlah bilangan genap, ganjil, maksimum, dan minimum

Map<String, dynamic> hitungStatistik(Set<int> nilai) {

  int jumlahGenap = nilai.where((angka) => angka % 2 == 0).length; // Menghitung jumlah bilangan genap

  int jumlahGanjil = nilai.where((angka) => angka % 2 != 0).length; // Menghitung jumlah bilangan ganjil

  int min = nilai.reduce((a, b) => a < b ? a : b); // Menghitung nilai minimum

  int max = nilai.reduce((a, b) => a > b ? a : b); // Menghitung nilai maksimum

  

  // Mengembalikan map dengan hasil

  return {

    'genap': jumlahGenap,

    'ganjil': jumlahGanjil,

    'maksimum': max,

    'minimum': min,

  };

}