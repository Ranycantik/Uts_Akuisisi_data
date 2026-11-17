# Data Ethics Checklist (9 butir)

| No | Butir | Status | Bukti |
|----|-------|--------|-------|
| 1 | Sumber data jelas dan resmi | Ya | BPS (https://www.bps.go.id/id/statistics-table/2/MjIwMSMy/jumlah-perjalanan-wisatawan-nusantara-menurut-provinsi-tujuan-perjalanan.html); Open-Meteo (open-meteo.com); Wikipedia id (halaman statis). Rinci di docs/provenance.csv |
| 2 | Lisensi dataset diperiksa | Ya | BPS: Ketentuan Penggunaan (gratis, komersial/nonkomersial, wajib kutip) di docs/bukti/lisensi_bps.txt; Open-Meteo: CC BY 4.0, API gratis non-komersial di docs/bukti/lisensi_openmeteo.txt; Wikipedia: CC BY-SA 4.0 di docs/bukti/lisensi_wikipedia.txt |
| 3 | Ketentuan layanan portal dibaca | Ya | bps.go.id/assets/term-of-use dan open-meteo.com/en/terms, dibaca 2026-11-12 |
| 4 | Tidak ada PII | Ya | Pemindaian kolom (Soal 2): tidak ada kolom PII/quasi-identifier |
| 5 | Risiko quasi-identifier dinilai | Ya (rendah) | Data agregat provinsi x bulan; unit analisis wilayah, bukan individu |
| 6 | robots.txt diperiksa dan dipatuhi | Ya | docs/bukti/robots_id_wikipedia.txt; can_fetch=True untuk halaman https://id.wikipedia.org/wiki/Daftar_ibu_kota_provinsi_di_Indonesia pada 2026-11-17T11:44:40 |
| 7 | Timeout, User-Agent berisi email kampus, jeda antar-request | Ya | Fungsi polite_get: timeout 20 dtk, jeda 2 dtk, retry untuk 429/5xx; User-Agent: UTS-DataAcq-INSTIKI/1.0 (mahasiswa Informatika; humas@instiki.ac.id) |
| 8 | Tidak memakai situs terlarang; tidak ada API key/token di notebook | Ya | Domain terlarang ditemukan: tidak ada; Open-Meteo tanpa key; email dibaca dari .env |
| 9 | Provenance lengkap, data mentah tidak diubah | Ya | 10 baris provenance (URL, tanggal akses, lisensi, MD5); MD5 berkas mentah cocok: True |
