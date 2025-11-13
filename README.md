<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalkulator Perencanaan Biaya Pendidikan</title>
    <!-- Memuat Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Menggunakan font Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-gray-100 min-h-screen flex items-center justify-center p-4">

    <div class="max-w-4xl w-full bg-white p-6 md:p-8 rounded-xl shadow-2xl">
        
        <h1 class="text-2xl md:text-3xl font-bold text-center text-blue-700 mb-2">
            Kalkulator Perencanaan Biaya Pendidikan
        </h1>
        <p class="text-center text-gray-600 mb-8">
            Proyeksikan total biaya pendidikan tinggi Anda, termasuk biaya pokok dan biaya pendukung.
        </p>

        <!-- Bagian Input Data -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
            <!-- Kolom Biaya Saat Ini -->
            <div class="space-y-4 p-4 bg-gray-50 rounded-lg border border-gray-200">
                <h2 class="text-lg font-semibold text-gray-800 border-b pb-2">Biaya Saat Ini (Perkiraan)</h2>
                
                <div>
                    <label for="uangPangkal" class="block text-sm font-medium text-gray-700">Uang Pangkal / Biaya Masuk</label>
                    <input type="text" id="uangPangkal" placeholder="Rp. 15.000.000" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 rupiah-input">
                </div>
                
                <div>
                    <label for="ukt" class="block text-sm font-medium text-gray-700">UKT / SPP (Per Semester)</label>
                    <input type="text" id="ukt" placeholder="Rp. 5.000.000" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 rupiah-input">
                </div>

                <div>
                    <label for="kost" class="block text-sm font-medium text-gray-700">Biaya Akomodasi / Kost (Per Bulan)</label>
                    <input type="text" id="kost" placeholder="Rp. 1.000.000" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 rupiah-input">
                </div>

                <div>
                    <label for="hidup" class="block text-sm font-medium text-gray-700">Biaya Hidup / Uang Saku (Per Bulan)</label>
                    <input type="text" id="hidup" placeholder="Rp. 1.500.000" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 rupiah-input">
                </div>

                <div>
                    <label for="buku" class="block text-sm font-medium text-gray-700">Biaya Buku & Alat (Per Semester)</label>
                    <input type="text" id="buku" placeholder="Rp. 500.000" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 rupiah-input">
                </div>

                <div>
                    <label for="transportasi" class="block text-sm font-medium text-gray-700">Biaya Transportasi (Per Semester)</label>
                    <input type="text" id="transportasi" placeholder="Rp. 300.000" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 rupiah-input">
                </div>
            </div>

            <!-- Kolom Parameter Proyeksi -->
            <div class="space-y-4 p-4 bg-gray-50 rounded-lg border border-gray-200">
                <h2 class="text-lg font-semibold text-gray-800 border-b pb-2">Parameter Proyeksi</h2>
                
                <div>
                    <label for="bulanLagi" class="block text-sm font-medium text-gray-700">Berapa bulan lagi akan masuk kuliah?</label>
                    <input type="number" id="bulanLagi" value="12" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500">
                </div>

                <div>
                    <label for="inflasi" class="block text-sm font-medium text-gray-700">Estimasi Inflasi Biaya Pendidikan (per Tahun)</label>
                    <div class="flex">
                        <input type="number" id="inflasi" value="8" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-l-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500">
                        <span class="inline-flex items-center px-3 mt-1 text-gray-500 bg-gray-200 border border-l-0 border-gray-300 rounded-r-md">%</span>
                    </div>
                </div>

                <div>
                    <label for="jumlahSemester" class="block text-sm font-medium text-gray-700">Total Durasi Kuliah (Jumlah Semester)</label>
                    <input type="number" id="jumlahSemester" value="8" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500">
                </div>
            </div>
        </div>

        <!-- Tombol Aksi -->
        <div class="text-center mb-8">
            <div class="flex flex-col md:flex-row justify-center gap-4">
                <button id="hitungBtn" class="w-full md:w-auto bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-10 rounded-lg shadow-lg transition duration-300 ease-in-out">
                    Hitung Estimasi Biaya
                </button>
                <button id="resetBtn" type="button" class="w-full md:w-auto bg-gray-500 hover:bg-gray-600 text-white font-bold py-3 px-10 rounded-lg shadow-lg transition duration-300 ease-in-out">
                    Reset
                </button>
            </div>
        </div>

        <!-- Bagian Hasil (Default tersembunyi) -->
        <div id="hasil" class="hidden mt-8">
            <h2 class="text-2xl font-bold text-gray-900 mb-4 text-center">Hasil Proyeksi Biaya</h2>

            <!-- Total Biaya -->
            <div class="bg-blue-100 border-l-4 border-blue-500 text-blue-900 p-6 rounded-lg mb-6 shadow-md">
                <p class="text-lg">Total Estimasi Biaya Pendidikan Anda (selama <span id="totalSemesterHasil"></span> semester) adalah:</p>
                <p id="totalBiaya" class="text-3xl md:text-4xl font-extrabold mt-2">Rp 0</p>
            </div>

            <!-- Rincian Biaya per Semester -->
            <h3 class="text-xl font-semibold text-gray-800 mb-4">Rincian Proyeksi per Semester</h3>
            <div class="overflow-x-auto rounded-lg shadow-md border border-gray-200">
                <table class="min-w-full divide-y divide-gray-200">
                    <thead class="bg-gray-100">
                        <tr>
                            <th scope="col" class="px-6 py-3 text-left text-xs font-bold text-gray-600 uppercase tracking-wider">Tahun / Semester</th>
                            <th scope="col" class="px-6 py-3 text-left text-xs font-bold text-gray-600 uppercase tracking-wider">Biaya Kuliah (UKT/SPP)</th>
                            <th scope="col" class="px-6 py-3 text-left text-xs font-bold text-gray-600 uppercase tracking-wider">Biaya Pendukung (Kost, Hidup, Buku)</th>
                            <th scope="col" class="px-6 py-3 text-left text-xs font-bold text-gray-600 uppercase tracking-wider">Total Biaya di Periode Ini</th>
                        </tr>
                    </thead>
                    <tbody id="rincianTabel" class="bg-white divide-y divide-gray-200">
                        <!-- Data akan diisi oleh JavaScript -->
                    </tbody>
                </table>
            </div>
        </div>

    </div>

    <script>
        // Helper function to format numbers as Indonesian Rupiah (for display)
        function formatRupiahDisplay(angka) {
            if (isNaN(angka)) return "Rp 0";
            return new Intl.NumberFormat('id-ID', {
                style: 'currency',
                currency: 'IDR',
                minimumFractionDigits: 0,
                maximumFractionDigits: 0
            }).format(angka);
        }

        // Fungsi baru untuk mem-format input saat diketik
        function formatKeRupiah(inputElem) {
            let value = inputElem.value;
            // 1. Hapus semua karakter non-digit
            let numberString = value.replace(/[^,\d]/g, '').toString();
            
            // Pengecualian khusus untuk "0"
            if (numberString === "0") {
                inputElem.value = "Rp. 0";
                return; // Selesai
            }

            // 2. Hapus awalan nol (jika ada), tapi jangan hapus jika itu satu-satunya angka "0"
            numberString = numberString.replace(/^0+/, '');

            // 3. Format dengan titik sebagai pemisah ribuan
            let formatted = numberString.replace(/\B(?=(\d{3})+(?!\d))/g, '.');
            
            // 4. Set nilainya
            if (formatted) {
                inputElem.value = "Rp. " + formatted;
            } else {
                inputElem.value = ""; // Kosongkan jika tidak ada angka
            }
        }

        // Fungsi baru untuk mengubah format Rupiah kembali ke angka
        function parseRupiah(value) {
            if (typeof value !== 'string') {
                return 0;
            }
            // Hapus "Rp. " dan semua titik
            const numericString = value.replace(/Rp\.\s*|\./g, '');
            return parseFloat(numericString) || 0;
        }


        // Get elements
        const hitungBtn = document.getElementById('hitungBtn');
        const resetBtn = document.getElementById('resetBtn'); // Tombol reset baru
        const hasilSection = document.getElementById('hasil');
        const cardContainer = document.querySelector('.max-w-4xl'); // Untuk scroll

        // Menambahkan listener ke semua input dengan kelas 'rupiah-input'
        const inputRupiah = document.querySelectorAll('.rupiah-input');
        inputRupiah.forEach(function(input) {
            input.addEventListener('input', function(e) {
                formatKeRupiah(e.target);
            });
            // Format juga saat fokus hilang, untuk membersihkan input
            input.addEventListener('blur', function(e) {
                formatKeRupiah(e.target);
            });
        });
        
        // Listen for button click
        hitungBtn.addEventListener('click', function() {
            // 1. Get all input values - Gunakan fungsi parseRupiah
            const uangPangkal = parseRupiah(document.getElementById('uangPangkal').value);
            const ukt = parseRupiah(document.getElementById('ukt').value);
            const kostBulanan = parseRupiah(document.getElementById('kost').value);
            const hidupBulanan = parseRupiah(document.getElementById('hidup').value);
            const bukuSemester = parseRupiah(document.getElementById('buku').value);
            const transportasiSemester = parseRupiah(document.getElementById('transportasi').value); // Input baru

            const bulanLagi = parseInt(document.getElementById('bulanLagi').value) || 0;
            const inflasiRate = (parseFloat(document.getElementById('inflasi').value) || 0) / 100;
            const jumlahSemester = parseInt(document.getElementById('jumlahSemester').value) || 8;

            // 2. Calculate initial costs at the start of college (after inflation)
            // Konversi bulan ke tahun (bisa fraksional) untuk perhitungan pangkat
            const tahunLagi = bulanLagi / 12.0;
            const inflasiAwal = Math.pow(1 + inflasiRate, tahunLagi);

            let currentUangPangkal = uangPangkal * inflasiAwal;
            let currentUkt = ukt * inflasiAwal;
            let currentKostBulanan = kostBulanan * inflasiAwal;
            let currentHidupBulanan = hidupBulanan * inflasiAwal;
            let currentBukuSemester = bukuSemester * inflasiAwal;
            let currentTransportasiSemester = transportasiSemester * inflasiAwal; // Inflasi untuk transportasi
            
            let totalKeseluruhan = 0;
            let tableHtml = "";

            // 3. Add one-time Uang Pangkal
            if (currentUangPangkal > 0) {
                totalKeseluruhan += currentUangPangkal;
                tableHtml += `
                    <tr class="bg-blue-50 font-medium">
                        <td class="px-6 py-4 whitespace-nowrap">Biaya Masuk (Tahun 1)</td>
                        <td class="px-6 py-4 whitespace-nowrap">${formatRupiahDisplay(0)}</td>
                        <td class="px-6 py-4 whitespace-nowrap">Uang Pangkal</td>
                        <td class="px-6 py-4 whitespace-nowrap">${formatRupiahDisplay(currentUangPangkal)}</td>
                    </tr>
                `;
            }

            // 4. Loop through each semester
            for (let semester = 1; semester <= jumlahSemester; semester++) {
                // Calculate costs for this semester
                // Biaya pendukung = (kost * 6 bulan) + (hidup * 6 bulan) + (buku * 1 semester) + (transportasi * 1 semester)
                const biayaPendukungSemester = (currentKostBulanan * 6) + (currentHidupBulanan * 6) + currentBukuSemester + currentTransportasiSemester;
                const totalSemesterIni = currentUkt + biayaPendukungSemester;

                // Add to table HTML
                tableHtml += `
                    <tr>
                        <td class="px-6 py-4 whitespace-nowrap">Semester ${semester}</td>
                        <td class="px-6 py-4 whitespace-nowrap">${formatRupiahDisplay(currentUkt)}</td>
                        <td class="px-6 py-4 whitespace-nowrap">${formatRupiahDisplay(biayaPendukungSemester)}</td>
                        <td class="px-6 py-4 whitespace-nowrap font-semibold">${formatRupiahDisplay(totalSemesterIni)}</td>
                    </tr>
                `;

                // Add to grand total
                totalKeseluruhan += totalSemesterIni;

                // Apply annual inflation after every 2 semesters (end of the year)
                if (semester % 2 === 0 && semester < jumlahSemester) {
                    currentUkt *= (1 + inflasiRate);
                    currentKostBulanan *= (1 + inflasiRate);
                    currentHidupBulanan *= (1 + inflasiRate);
                    currentBukuSemester *= (1 + inflasiRate);
                    currentTransportasiSemester *= (1 + inflasiRate); // Inflasi untuk transportasi
                }
            }

            // 5. Display the results
            document.getElementById('totalBiaya').innerText = formatRupiahDisplay(totalKeseluruhan);
            document.getElementById('totalSemesterHasil').innerText = jumlahSemester;
            document.getElementById('rincianTabel').innerHTML = tableHtml;
            
            // Show the hidden results section
            hasilSection.classList.remove('hidden');
            // Scroll to results
            hasilSection.scrollIntoView({ behavior: 'smooth' });
        });

        // Listener untuk tombol Reset baru
        resetBtn.addEventListener('click', function() {
            // 1. Kosongkan semua input Rupiah
            document.getElementById('uangPangkal').value = "";
            document.getElementById('ukt').value = "";
            document.getElementById('kost').value = "";
            document.getElementById('hidup').value = "";
            document.getElementById('buku').value = "";
            document.getElementById('transportasi').value = ""; // Reset input baru

            // 2. Kembalikan input parameter ke nilai default
            document.getElementById('bulanLagi').value = "12"; // Diubah ke 12 bulan
            document.getElementById('inflasi').value = "8";
            document.getElementById('jumlahSemester').value = "8";

            // 3. Sembunyikan bagian hasil
            hasilSection.classList.add('hidden');

            // 4. Scroll kembali ke atas card
            cardContainer.scrollIntoView({ behavior: 'smooth' });
        });
    </script>

</body>
</html>
