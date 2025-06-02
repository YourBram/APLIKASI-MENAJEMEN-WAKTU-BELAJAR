data_belajar = []

def tambah_sesi(tanggal, mata_pelajaran, durasi, fokus):
    sesi = {
        'tanggal': tanggal,
        'mata_pelajaran': mata_pelajaran,
        'durasi': durasi,  
        'fokus': fokus     
    }
    data_belajar.append(sesi)

def tampilkan_semua_sesi():
    print("\nDaftar Sesi Belajar:")
    for sesi in data_belajar:
        print(f"{sesi['tanggal']} - {sesi['mata_pelajaran']} - {sesi['durasi']} menit - Fokus: {sesi['fokus']}")

def total_durasi():
    total = sum([sesi['durasi'] for sesi in data_belajar])
    print(f"\nTotal durasi belajar: {total} menit")

def sesi_fokus_tertinggi():
    if data_belajar:
        tertinggi = max(data_belajar, key=lambda x: x['fokus'])
        print("\nSesi dengan fokus tertinggi:")
        print(f"{tertinggi['tanggal']} - {tertinggi['mata_pelajaran']} - Fokus: {tertinggi['fokus']}")
    else:
        print("\nBelum ada data.")

def urutkan_durasi():
    urut = sorted(data_belajar, key=lambda x: x['durasi'], reverse=True)
    print("\nSesi belajar diurutkan berdasarkan durasi:")
    for sesi in urut:
        print(f"{sesi['mata_pelajaran']} - {sesi['durasi']} menit")

tambah_sesi('2025-06-01', 'Matematika', 90, 4)
tambah_sesi('2025-06-01', 'Bahasa inggris', 60, 3)
tambah_sesi('2025-06-02', 'Fisika', 120, 5)
tambah_sesi('2025-06-03', 'Biologi', 30, 2)

tampilkan_semua_sesi()
total_durasi()
sesi_fokus_tertinggi()
urutkan_durasi()
