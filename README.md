# latihan-repo-pertama
Belajar repository
// ==========================================
// PROGRAM SIMULASI KERANJANG BELANJA SEDERHANA
// ==========================================

// 1. Data produk yang tersedia di toko
const produkToko = [
    { id: 1, nama: "Kemeja Katun UNIQLO", harga: 299000 },
    { id: 2, nama: "Kaos AIRism Polos", harga: 149000 },
    { id: 3, nama: "Masker Wajah Skintific", harga: 89000 }
];

// 2. Wadah keranjang belanja pengguna (awalnya kosong)
let keranjangSaya = [];

// 3. Fungsi untuk menambahkan produk ke dalam keranjang
function tambahKeKeranjang(idProduk, jumlah) {
    const produk = produkToko.find(p => p.id === idProduk);
    
    if (produk) {
        keranjangSaya.push({
            ...produk,
            jumlahBelanja: jumlah
        });
        console.log(`✅ Berhasil menambahkan ${jumlah}x ${produk.nama} ke keranjang.`);
    } else {
        console.log("❌ Produk tidak ditemukan!");
    }
}

// 4. Fungsi untuk menghitung total belanjaan
function hitungTotalBelanja() {
    let total = 0;
    console.log("\n--- ISI KERANJANG BELANJA ANDA ---");
    
    keranjangSaya.forEach((item, index) => {
        const subTotal = item.harga * item.jumlahBelanja;
        total += subTotal;
        console.log(`${index + 1}. ${item.nama} (${item.jumlahBelanja}x) : Rp ${subTotal.toLocaleString('id-ID')}`);
    });
    
    console.log("---------------------------------");
    console.log(`TOTAL PEMBAYARAN: Rp ${total.toLocaleString('id-ID')}\n`);
}

// ==========================================
// SIMULASI JALANNYA PROGRAM (PROSES BELANJA)
// ==========================================

console.log("Memulai simulasi belanja...");

// Pengguna memilih barang (Contoh: Beli 1 Kemeja dan 2 Kaos AIRism)
tambahKeKeranjang(1, 1); 
tambahKeKeranjang(2, 2); 

// Menghitung total akhir yang harus dibayar
hitungTotalBelanja();
