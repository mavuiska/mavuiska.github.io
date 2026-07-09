<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Informasi Logistik & Akuntansi Internasional</title>
    <style>
        :root {
            --primary: #1e40af;
            --primary-light: #3b82f6;
            --secondary: #0f172a;
            --success: #16a34a;
            --warning: #ca8a04;
            --danger: #dc2626;
            --bg-main: #f8fafc;
            --sidebar-width: 270px;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background-color: var(--bg-main); color: #334155; min-height: 100vh; display: flex; }

        /* Utility Classes */
        .hidden { display: none !important; }
        .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
        .grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; }
        .card { background: white; padding: 20px; border-radius: 8px; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05); margin-bottom: 20px; border: 1px solid #e2e8f0; }
        .btn { padding: 8px 16px; border: none; border-radius: 6px; cursor: pointer; font-weight: 600; font-size: 14px; display: inline-flex; align-items: center; gap: 8px; }
        .btn-primary { background: var(--primary); color: white; }
        .btn-success { background: var(--success); color: white; }
        .btn-danger { background: var(--danger); color: white; }
        .btn-warning { background: var(--warning); color: white; }
        .badge { padding: 4px 8px; border-radius: 4px; font-size: 12px; color: white; font-weight: bold; }
        
        /* Auth Page */
        .auth-container { width: 100vw; height: 100vh; display: flex; justify-content: center; align-items: center; background: linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%); }
        .auth-card { background: white; padding: 40px; border-radius: 12px; width: 100%; max-width: 400px; box-shadow: 0 20px 25px -5px rgba(0,0,0,0.3); }
        .form-group { margin-bottom: 15px; }
        .form-group label { display: block; margin-bottom: 6px; font-weight: 500; font-size: 14px; }
        .form-group input, .form-group select, .form-group textarea { width: 100%; padding: 10px; border: 1px solid #cbd5e1; border-radius: 6px; font-size: 14px; }

        /* Layout Utama */
        #app-layout { display: flex; width: 100%; min-height: 100vh; }
        
        /* Sidebar Navigation */
        .sidebar { width: var(--sidebar-width); background: var(--secondary); color: white; padding: 20px; display: flex; flex-direction: column; }
        .sidebar h3 { font-size: 14px; color: #64748b; text-transform: uppercase; letter-spacing: 1px; margin: 20px 0 10px 0; border-bottom: 1px solid #334155; padding-bottom: 5px; }
        .nav-item { padding: 12px 15px; color: #cbd5e1; cursor: pointer; border-radius: 6px; display: flex; align-items: center; font-size: 14px; font-weight: 500; margin-bottom: 4px; }
        .nav-item:hover, .nav-item.active { background: var(--primary); color: white; }
        .logout-btn { margin-top: auto; background: var(--danger); }

        /* Logo Brand Style */
        .brand-container { display: flex; align-items: center; gap: 12px; margin-bottom: 10px; border-bottom: 1px solid #334155; padding-bottom: 15px; }
        .brand-text h2 { font-size: 18px; font-weight: bold; color: white; line-height: 1.2; }
        .brand-text span { font-size: 11px; color: #3b82f6; font-weight: bold; letter-spacing: 1.5px; text-transform: uppercase; }

        /* Main Content Area */
        .main-content { flex: 1; padding: 30px; overflow-y: auto; height: 100vh; }
        .content-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 25px; border-bottom: 2px solid #e2e8f0; padding-bottom: 15px; }
        
        /* Tables */
        table { width: 100%; border-collapse: collapse; margin-top: 10px; }
        th, td { padding: 12px; text-align: left; border-bottom: 1px solid #e2e8f0; font-size: 14px; }
        th { background-color: #f1f5f9; font-weight: 600; color: #475569; }

        /* Report Widgets */
        .widget { background: #f8fafc; border: 1px solid #e2e8f0; padding: 15px; border-radius: 8px; text-align: center; }
        .widget h4 { font-size: 14px; color: #64748b; margin-bottom: 5px; }
        .widget p { font-size: 20px; font-weight: bold; color: var(--secondary); }
    </style>
</head>
<body>

    <div id="auth-page" class="auth-container">
        <div class="auth-card">
            <h2 style="margin-bottom: 10px; text-align: center; color: var(--secondary);">Global System Login</h2>
            <p style="text-align: center; color: #64748b; font-size: 13px; margin-bottom: 25px;">Masukkan kredensial terdaftar untuk mengelola logistik</p>
            <div class="form-group">
                <label>Username</label>
                <input type="text" id="login-username" placeholder="Masukkan username (ex: seller / buyer)">
            </div>
            <div class="form-group">
                <label>Password</label>
                <input type="password" id="login-password" placeholder="Masukkan password (admin123)">
            </div>
            <button class="btn btn-primary" style="width: 100%; justify-content: center; margin-top: 10px;" onclick="handleLogin()">Masuk ke Sistem</button>
        </div>
    </div>

    <div id="app-layout" class="hidden">
        <nav class="sidebar">
            
            <div class="brand-container">
                <svg width="42" height="42" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <circle cx="12" cy="12" r="9" stroke="#3b82f6" stroke-width="1.2" stroke-dasharray="3 1.5"/>
                    <path d="M12 3C14.5 5.5 15 8.5 15 12C15 15.5 14.5 18.5 12 21" stroke="#1e40af" stroke-width="1"/>
                    <path d="M12 3C9.5 5.5 9 8.5 9 12C9 15.5 9.5 18.5 12 21" stroke="#1e40af" stroke-width="1"/>
                    <path d="M3 12H21" stroke="#1e40af" stroke-width="1"/>
                    <path d="M6 8L10 11.5M10 11.5L15 7.5M10 11.5V16.5" stroke="#10b981" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                    <circle cx="6" cy="8" r="1" fill="#10b981"/>
                    <circle cx="15" cy="7.5" r="1" fill="#10b981"/>
                    <circle cx="10" cy="16.5" r="1.2" fill="#3b82f6"/>
                    <circle cx="10" cy="11.5" r="1.5" fill="#f59e0b" stroke="#0f172a" stroke-width="0.5"/>
                </svg>
                <div class="brand-text">
                    <h2>Global</h2>
                    <span>LogisTech</span>
                </div>
            </div>

            <p style="font-size: 12px; color: #94a3b8; margin-bottom: 20px; padding-left: 5px;">User Aktif: <span id="span-username" style="color: var(--primary-light); font-weight: bold;"></span></p>
            
            <h3>Input Interface</h3>
            <div class="nav-item active" onclick="switchMenu('menu-terima-pesanan', this)">📥 Terima Pesanan</div>
            <div class="nav-item" onclick="switchMenu('menu-kelola-pesanan', this)">📦 Kelola Pesanan</div>
            <div class="nav-item" onclick="switchMenu('menu-klausal-fob', this)">🗺️ Rute & Tracking Negara</div>
            <div class="nav-item" onclick="switchMenu('menu-konfirmasi-pembayaran', this)">💳 Konfirmasi Pembayaran</div>
            <div class="nav-item" onclick="switchMenu('menu-kelola-pengiriman', this)">🚚 Kelola Pengiriman</div>
            <div class="nav-item" onclick="switchMenu('menu-konfirmasi-serah', this)">🏁 Konfirmasi Serah Terima</div>

            <h3>Output Interface</h3>
            <div class="nav-item" onclick="switchMenu('menu-executive-report', this)">📊 Executive Report</div>
            <div class="nav-item" onclick="switchMenu('menu-summary-report', this)">📈 Summary Report</div>
            <div class="nav-item" onclick="switchMenu('menu-detail-report', this)">📋 Detail Report</div>
            <div class="nav-item" onclick="switchMenu('menu-exception-report', this)">🚨 Exception Report</div>

            <div class="nav-item logout-btn" onclick="handleLogout()">🚪 Logout User</div>
        </nav>

        <main class="main-content">
            
            <div id="menu-terima-pesanan" class="menu-content">
                <div class="content-header"><h2>Terima Pesanan</h2></div>
                <div class="card">
                    <h3>Daftar Pesanan Masuk (Menunggu Validasi Seller)</h3>
                    <table>
                        <thead>
                            <tr><th>No Pesanan</th><th>Pelanggan</th><th>Barang</th><th>Jumlah</th><th>Aksi</th></tr>
                        </thead>
                        <tbody id="table-terima-pesanan"></tbody>
                    </table>
                </div>
            </div>

            <div id="menu-kelola-pesanan" class="menu-content hidden">
                <div class="content-header"><h2>Kelola Pesanan</h2></div>
                <div class="grid-2">
                    <div class="card">
                        <h3>Tambah / Edit Pesanan</h3>
                        <div class="form-group"><label>Nomor Pesanan</label><input type="text" id="kp-id" readonly placeholder="Otomatis"></div>
                        <div class="form-group"><label>Nama Pelanggan</label><input type="text" id="kp-customer"></div>
                        <div class="form-group"><label>Nama Barang</label><input type="text" id="kp-barang"></div>
                        <div class="form-group"><label>Jumlah / Kuantitas</label><input type="number" id="kp-qty"></div>
                        <div class="form-group"><label>Total Harga (Rp)</label><input type="number" id="kp-harga"></div>
                        <button class="btn btn-primary" onclick="simpanPesanan()">Simpan Data Pesanan</button>
                    </div>
                    <div class="card">
                        <h3>Daftar Master Pesanan</h3>
                        <table>
                            <thead><tr><th>ID</th><th>Pelanggan</th><th>Status</th><th>Aksi</th></tr></thead>
                            <tbody id="table-master-pesanan"></tbody>
                        </table>
                    </div>
                </div>
            </div>

            <div id="menu-klausal-fob" class="menu-content hidden">
                <div class="content-header"><h2>Rute & Tracking Negara</h2></div>
                <div class="grid-2">
                    <div class="card">
                        <h3>Konfigurasi Tujuan Internasional & Aktivasi Rute</h3>
                        <div class="form-group">
                            <label>Pilih Transaksi Terkonfirmasi</label>
                            <select id="fob-select-pesanan" onchange="loadRiwayatRute()"></select>
                        </div>
                        <div class="form-group">
                            <label>Tentukan Negara / Kota Tujuan Akhir</label>
                            <select id="fob-tujuan">
                                <option value="Singapore">Singapore (SG)</option>
                                <option value="Tokyo, Japan">Tokyo, Japan (JP)</option>
                                <option value="Rotterdam, Netherlands">Rotterdam, Netherlands (NL)</option>
                                <option value="Los Angeles, USA">Los Angeles, USA (US)</option>
                            </select>
                        </div>
                        <button class="btn btn-success" onclick="prosesPembuatanRute()">Bentuk Rute & Aktifkan Tracking</button>

                        <hr style="margin:20px 0; border:1px dashed #e2e8f0;">
                        
                        <h3>Perbarui Lokasi & Status Terkini (Oleh Pihak Berwenang)</h3>
                        <div class="form-group">
                            <label>Pilih Lokasi Cekpoin Saat Ini</label>
                            <select id="update-lokasi-checkpoint">
                                <option value="Gudang Asal (Indonesia)">Gudang Asal (Indonesia)</option>
                                <option value="Customs Pelabuhan Transit">Customs Pelabuhan Transit</option>
                                <option value="Laut Internasional Zona 1">Laut Internasional Zona 1</option>
                                <option value="Pelabuhan Bongkar Tujuan">Pelabuhan Bongkar Tujuan</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>Status Logistik Terbaru</label>
                            <input type="text" id="update-status-text" placeholder="Contoh: Lolos Bea Cukai / Berlayar">
                        </div>
                        <button class="btn btn-primary" onclick="simpanPerubahanStatusNegara()">Update Status & Lokasi</button>
                    </div>

                    <div class="card">
                        <h3>Riwayat Perjalanan & Estimasi Logistik</h3>
                        <div id="rute-info-box" style="margin-bottom:15px; padding:10px; background:#eff6ff; border-radius:6px; font-size:14px;">
                            Pilih transaksi untuk menampilkan riwayat pelacakan lintas negara.
                        </div>
                        <h4>Papan Log Perjalanan:</h4>
                        <div id="rute-logs-area" style="background:#0f172a; color:#38bdf8; padding:15px; border-radius:8px; height:200px; overflow-y:auto; font-family:monospace; margin-top:10px; font-size:13px;">
                            [-] Menunggu aktivasi rute transaksi...
                        </div>
                    </div>
                </div>
            </div>

            <div id="menu-konfirmasi-pembayaran" class="menu-content hidden">
                <div class="content-header"><h2>Konfirmasi Pembayaran</h2></div>
                <div class="card">
                    <h3>Daftar Verifikasi Invoice Keuangan</h3>
                    <table>
                        <thead><tr><th>No Pesanan</th><th>Pelanggan</th><th>Total Tagihan</th><th>Status Bayar</th><th>Aksi</th></tr></thead>
                        <tbody id="table-pembayaran"></tbody>
                    </table>
                </div>
            </div>

            <div id="menu-kelola-pengiriman" class="menu-content hidden">
                <div class="content-header"><h2>Kelola Pengiriman</h2></div>
                <div class="grid-2">
                    <div class="card">
                        <h3>Input Informasi Logistik Ekspeditur</h3>
                        <div class="form-group"><label>Pilih Pesanan Lunas</label><select id="ship-select-pesanan" onchange="renderTrackingTimeline()"></select></div>
                        <div class="form-group"><label>Nomor Resi Kelautan / Cargo</label><input type="text" id="ship-resi" value="BL-2026-9901"></div>
                        <div class="form-group"><label>Jasa Ekspedisi / Armada</label><input type="text" id="ship-kurir" value="Maersk Line Cargo"></div>
                        <button class="btn btn-primary" onclick="mulaiSimulasiPengiriman()">Simulasikan Pengiriman Real-Time 🚢</button>
                    </div>
                    <div class="card">
                        <h3>Monitor Posisi & Alokasi Risiko Geografis</h3>
                        <div id="tracking-visual-box" style="padding:15px; background:#f1f5f9; border-radius:8px; min-height:100px; font-weight:bold; text-align:center;">
                            Silakan pilih pesanan lunas untuk melacak posisi logistik jarak jauh.
                        </div>
                    </div>
                </div>
            </div>

            <div id="menu-konfirmasi-serah" class="menu-content hidden">
                <div class="content-header"><h2>Konfirmasi Serah Terima</h2></div>
                <div class="card">
                    <h3>Penerimaan Barang Akhir</h3>
                    <table>
                        <thead><tr><th>No Pesanan</th><th>Tujuan Akhir</th><th>Status Lokasi</th><th>Aksi Konfirmasi</th></tr></thead>
                        <tbody id="table-serah-terima"></tbody>
                    </table>
                </div>
            </div>

            <div id="menu-executive-report" class="menu-content hidden">
                <div class="content-header"><h2>Executive Report</h2></div>
                <div class="card">
                    <h3 style="color:var(--primary)">Executive Report - A: Ringkasan Rute Finansial Kontrak</h3>
                    <div class="grid-3" style="margin-top:15px;">
                        <div class="widget"><h4>Total Nilai Kontrak</h4><p id="rep-exec-nilai">Rp 0</p></div>
                        <div class="widget"><h4>Rute Terkonfigurasi</h4><p id="rep-exec-rute-aktif">0 Transaksi</p></div>
                        <div class="widget"><h4>Tujuan Paling Sering</h4><p id="rep-exec-top-dest">-</p></div>
                    </div>
                    <blockquote style="margin-top:15px; font-style:italic; font-size:13px; color:#64748b;">
                        <b>Kegunaan Keputusan:</b> Mengevaluasi sebaran distribusi geografis pesanan global serta memetakan alokasi armada ke negara tujuan dengan biaya paling efisien.
                    </blockquote>
                </div>
                <div class="card">
                    <h3 style="color:var(--primary)">Executive Report - B: Status Perjalanan Kargo</h3>
                    <div class="grid-3" style="margin-top:15px;">
                        <div class="widget"><h4>Pengiriman Berhasil</h4><p id="rep-exec-sukses">0</p></div>
                        <div class="widget"><h4>Dalam Proses Transit</h4><p id="rep-exec-transit">0</p></div>
                        <div class="widget"><h4>Terlambat / Bermasalah</h4><p id="rep-exec-delay">1</p></div>
                    </div>
                </div>
            </div>

            <div id="menu-summary-report" class="menu-content hidden">
                <div class="content-header"><h2>Summary Report</h2></div>
                <div class="card">
                    <h3>Summary Report - A: Ringkasan Pesanan</h3>
                    <div class="grid-3" style="margin-top:15px;">
                        <div class="widget"><h4>Total Pesanan Masuk</h4><p id="rep-sum-total">0</p></div>
                        <div class="widget"><h4>Pesanan Selesai</h4><p id="rep-sum-done">0</p></div>
                    </div>
                </div>
                <div class="card">
                    <h3>Summary Report - B: Ringkasan Piutang dan Pembayaran</h3>
                    <div class="grid-3" style="margin-top:15px;">
                        <div class="widget"><h4>Total Pembayaran Diterima</h4><p id="rep-sum-kas">Rp 0</p></div>
                        <div class="widget"><h4>Saldo Piutang Belum Lunas</h4><p id="rep-sum-piutang">Rp 0</p></div>
                    </div>
                </div>
            </div>

            <div id="menu-detail-report" class="menu-content hidden">
                <div class="content-header"><h2>Detail Report</h2></div>
                <div class="card">
                    <h3>Detail Report - A: Detail Pesanan & Lokasi Saat Ini</h3>
                    <table>
                        <thead><tr><th>ID Pesanan</th><th>Pelanggan</th><th>Barang</th><th>Negara/Kota Tujuan</th><th>Status Perjalanan</th></tr></thead>
                        <tbody id="table-detail-pesanan"></tbody>
                    </table>
                </div>
                <div class="card">
                    <h3>Detail Report - B: Detail Jurnal Akuntansi Pengiriman</h3>
                    <table>
                        <thead><tr><th>Tanggal</th><th>Keterangan Akun</th><th>Debit (Rp)</th><th>Kredit (Rp)</th><th>Rute Logistik</th></tr></thead>
                        <tbody id="table-detail-jurnal"></tbody>
                    </table>
                </div>
            </div>

            <div id="menu-exception-report" class="menu-content hidden">
                <div class="content-header"><h2>Exception Report</h2></div>
                <div class="card" style="border-left: 5px solid var(--danger);">
                    <h3 style="color:var(--danger)">Exception Report - A: Pengiriman Bermasalah</h3>
                    <table>
                        <thead><tr><th>No Resi</th><th>Armada</th><th>Kendala Penundaan</th><th>Status Tindakan</th></tr></thead>
                        <tbody>
                            <tr style="background:#fef2f2"><td>BL-2026-X88</td><td>Pacific Cargo</td><td><span style="color:var(--danger)">⚠️ Terjebak Cuaca Ekstrim Selat Malaka (>48 Jam)</span></td><td><button class="btn btn-warning" onclick="alert('Rute dialihkan!')">Alihkan Rute</button></td></tr>
                        </tbody>
                    </table>
                </div>
                <div class="card" style="border-left: 5px solid var(--danger);">
                    <h3 style="color:var(--danger)">Exception Report - B: Piutang Jatuh Tempo</h3>
                    <table>
                        <thead><tr><th>Pelanggan</th><th>Jumlah Piutang</th><th>Batas Waktu Kredit</th><th>Prioritas Penagihan</th></tr></thead>
                        <tbody>
                            <tr style="background:#fef2f2"><td>PT. Global Buyer Mandiri</td><td>Rp 45.000.000</td><td>Sudah Lewat 14 Hari</td><td><span class="badge" style="background:var(--danger)">HIGH PRIORITY</span></td></tr>
                        </tbody>
                    </table>
                </div>
            </div>

        </main>
    </div>

    <script>
        let dataPesanan = [
            { id: "ORD-001", customer: "PT. Krakatau Buyer", barang: "Biji Besi Baja", qty: 150, harga: 75000000, status: "Menunggu Penerimaan Seller", bayar: "Belum Lunas", transitStage: 0, negaraTujuan: "-", riwayatRute: [] },
            { id: "ORD-002", customer: "CV. Samudera Trading", barang: "Komponen Mesin", qty: 40, harga: 24000000, status: "Diterima", bayar: "Belum Lunas", transitStage: 0, negaraTujuan: "-", riwayatRute: [] }
        ];

        let jurnalAkuntansi = [];

        function handleLogin() {
            const user = document.getElementById("login-username").value;
            const pass = document.getElementById("login-password").value;

            if (user.trim() === "") { alert("Masukkan Username terlebih dahulu!"); return; }
            if (pass === "admin123") {
                localStorage.setItem("sessionUser", user);
                initDashboard();
            } else {
                alert("Password Salah! Gunakan password dev: admin123");
            }
        }

        function handleLogout() {
            localStorage.removeItem("sessionUser");
            document.getElementById("auth-page").classList.remove("hidden");
            document.getElementById("app-layout").classList.add("hidden");
        }

        function initDashboard() {
            const session = localStorage.getItem("sessionUser");
            if(session) {
                document.getElementById("auth-page").classList.add("hidden");
                document.getElementById("app-layout").classList.remove("hidden");
                document.getElementById("span-username").innerText = session;
                renderAllData();
            }
        }

        function switchMenu(menuId, element) {
            document.querySelectorAll('.menu-content').forEach(el => el.classList.add('hidden'));
            document.getElementById(menuId).classList.remove('hidden');
            document.querySelectorAll('.nav-item').forEach(el => el.classList.remove('active'));
            element.classList.add('active');
            renderAllData();
        }

        function renderAllData() {
            renderTerimaPesanan();
            renderMasterPesanan();
            renderFobDropdown();
            renderPembayaran();
            renderShipDropdown();
            renderSerahTerima();
            hitungLaporan();
        }

        function renderTerimaPesanan() {
            const tbody = document.getElementById("table-terima-pesanan");
            tbody.innerHTML = "";
            dataPesanan.filter(p => p.status === "Menunggu Penerimaan Seller").forEach(p => {
                tbody.innerHTML += `<tr>
                    <td><b>${p.id}</b></td><td>${p.customer}</td><td>${p.barang}</td><td>${p.qty} Pcs</td>
                    <td><button class="btn btn-success" onclick="aksiTerima('${p.id}')">✔️ Terima Pesanan</button></td>
                </tr>`;
            });
        }
        function aksiTerima(id) {
            let p = dataPesanan.find(x => x.id === id);
            p.status = "Diterima";
            alert(`Pesanan ${id} Berhasil Diterima oleh Seller!`);
            renderAllData();
        }

        function renderMasterPesanan() {
            const tbody = document.getElementById("table-master-pesanan");
            tbody.innerHTML = "";
            dataPesanan.forEach(p => {
                tbody.innerHTML += `<tr>
                    <td>${p.id}</td><td>${p.customer}</td>
                    <td><span class="badge" style="background:var(--primary)">${p.status}</span></td>
                    <td><button class="btn btn-danger" onclick="hapusPesanan('${p.id}')">Hapus</button></td>
                </tr>`;
            });
        }
        function simpanPesanan() {
            const cust = document.getElementById("kp-customer").value;
            const brg = document.getElementById("kp-barang").value;
            const q = document.getElementById("kp-qty").value;
            const hg = document.getElementById("kp-harga").value;
            if(!cust || !brg) { alert("Data tidak boleh kosong!"); return; }
            
            const newId = "ORD-00" + (dataPesanan.length + 1);
            dataPesanan.push({
                id: newId, customer: cust, barang: brg, qty: parseInt(q), harga: parseInt(hg),
                status: "Menunggu Penerimaan Seller", bayar: "Belum Lunas", transitStage: 0, negaraTujuan: "-", riwayatRute: []
            });
            alert("Pesanan Baru Berhasil Ditambahkan ke Sistem!");
            renderAllData();
        }
        function hapusPesanan(id) {
            dataPesanan = dataPesanan.filter(x => x.id !== id);
            renderAllData();
        }

        function renderFobDropdown() {
            const select = document.getElementById("fob-select-pesanan");
            select.innerHTML = "";
            dataPesanan.filter(p => p.status === "Diterima" || p.status === "Rute Aktif (Tracking Terikat)").forEach(p => {
                select.innerHTML += `<option value="${p.id}">${p.id} - ${p.customer}</option>`;
            });
            loadRiwayatRute();
        }

        function prosesPembuatanRute() {
            const id = document.getElementById("fob-select-pesanan").value;
            const tujuan = document.getElementById("fob-tujuan").value;
            if(!id) { alert("Tidak ada transaksi terpilih!"); return; }
            
            let p = dataPesanan.find(x => x.id === id);
            p.negaraTujuan = tujuan;
            p.status = "Rute Aktif (Tracking Terikat)";
            
            let waktu = new Date().toLocaleTimeString();
            p.riwayatRute = [
                { jam: waktu, lokasi: "Gudang Asal (Indonesia)", ket: "Rute dibentuk, fitur tracking telah diaktifkan secara otomatis menuju " + tujuan }
            ];
            
            alert(`Sistem sukses membentuk rute pengiriman baru ke ${tujuan} untuk transaksi ${id}!`);
            loadRiwayatRute();
        }

        function loadRiwayatRute() {
            const id = document.getElementById("fob-select-pesanan").value;
            const infoBox = document.getElementById("rute-info-box");
            const logsArea = document.getElementById("rute-logs-area");
            
            if(!id) {
                infoBox.innerHTML = "Pilih transaksi untuk menampilkan riwayat pelacakan lintas negara.";
                logsArea.innerHTML = "[-] Menunggu aktivasi rute transaksi...";
                return;
            }
            
            let p = dataPesanan.find(x => x.id === id);
            infoBox.innerHTML = `
                <b>Transaksi:</b> ${p.id}<br>
                <b>Negara/Kota Tujuan Akhir:</b> <span style="color:var(--primary); font-weight:bold;">${p.negaraTujuan}</span><br>
                <b>Estimasi Tujuan Berikutnya:</b> ${p.status === "Tiba Di Lokasi" || p.status === "Transaksi Selesai (Selesai)" ? "Sampai Tujuan" : p.negaraTujuan}
            `;
            
            if(p.riwayatRute.length === 0) {
                logsArea.innerHTML = "[-] Rute belum dibuat untuk transaksi ini. Silakan tentukan negara tujuan di sebelah kiri.";
            } else {
                logsArea.innerHTML = "";
                p.riwayatRute.forEach(r => {
                    logsArea.innerHTML += `<div>[${r.jam}] Lokasi: ${r.lokasi} | Status: ${r.ket}</div>`;
                });
            }
        }

        function simpanPerubahanStatusNegara() {
            const id = document.getElementById("fob-select-pesanan").value;
            const checkpoint = document.getElementById("update-lokasi-checkpoint").value;
            const statusKeterangan = document.getElementById("update-status-text").value;
            
            if(!id) { alert("Pilih transaksi terlebih dahulu!"); return; }
            if(!statusKeterangan.trim()) { alert("Isi deskripsi status terbaru!"); return; }
            
            let p = dataPesanan.find(x => x.id === id);
            if(p.riwayatRute.length === 0) { alert("Bentuk rute pengiriman terlebih dahulu!"); return; }
            
            let waktu = new Date().toLocaleTimeString();
            p.riwayatRute.push({ jam: waktu, lokasi: checkpoint, ket: statusKeterangan });
            
            alert(`Status dan koordinat lokasi berhasil disimpan ke dalam riwayat perjalanan!`);
            document.getElementById("update-status-text").value = "";
            loadRiwayatRute();
        }

        function renderPembayaran() {
            const tbody = document.getElementById("table-pembayaran");
            tbody.innerHTML = "";
            dataPesanan.filter(p => p.status === "Rute Aktif (Tracking Terikat)").forEach(p => {
                tbody.innerHTML += `<tr>
                    <td>${p.id}</td><td>${p.customer}</td><td>Rp ${p.harga.toLocaleString()}</td>
                    <td><span class="badge" style="background:var(--warning)">${p.bayar}</span></td>
                    <td><button class="btn btn-success" onclick="konfirmasiBayar('${p.id}')">💰 Nyatakan Lunas</button></td>
                </tr>`;
            });
        }
        function konfirmasiBayar(id) {
            let p = dataPesanan.find(x => x.id === id);
            p.bayar = "Lunas";
            p.status = "Lunas & Siap Kirim";
            
            let hariIni = new Date().toLocaleDateString('id-ID');
            jurnalAkuntansi.push({ tgl: hariIni, akun: "Kas di Bank (Debit)", deb: p.harga, kre: 0, ref: "Tujuan: " + p.negaraTujuan });
            jurnalAkuntansi.push({ tgl: hariIni, akun: "Pendapatan Penjualan (Kredit)", deb: 0, kre: p.harga, ref: "Tujuan: " + p.negaraTujuan });

            alert(`Pembayaran Invoice ${id} Dinyatakan Lunas.`);
            renderAllData();
        }

        function renderShipDropdown() {
            const select = document.getElementById("ship-select-pesanan");
            select.innerHTML = "";
            dataPesanan.filter(p => p.status === "Lunas & Siap Kirim" || p.status === "Dalam Perjalanan Laut").forEach(p => {
                select.innerHTML += `<option value="${p.id}">${p.id} [Ke: ${p.negaraTujuan}]</option>`;
            });
        }

        function renderTrackingTimeline() {
            const id = document.getElementById("ship-select-pesanan").value;
            const box = document.getElementById("tracking-visual-box");
            if(!id) return;
            let p = dataPesanan.find(x => x.id === id);

            let tahapan = ["Gudang Seller (ID)", "Pelabuhan Transit", "Laut Internasional", p.negaraTujuan];
            box.innerHTML = `
                <p style='color:var(--primary)'>📍 Posisi Sekarang: ${tahapan[p.transitStage]}</p>
                <progress value="${p.transitStage}" max="3" style="width:100%; margin:10px 0;"></progress>
                <div style='font-size:12px; background:white; padding:8px; border-radius:4px;'>
                    🌐 <b>Target Akhir:</b> <span style="color:var(--success)">${p.negaraTujuan}</span>
                </div>
            `;
        }

        function mulaiSimulasiPengiriman() {
            const id = document.getElementById("ship-select-pesanan").value;
            if(!id) { alert("Pilih pesanan terlebih dahulu!"); return; }
            let p = dataPesanan.find(x => x.id === id);
            p.status = "Dalam Perjalanan Laut";

            let timer = setInterval(() => {
                if(p.transitStage < 3) {
                    p.transitStage++;
                    renderTrackingTimeline();
                    let waktu = new Date().toLocaleTimeString();
                    let tahapan = ["Gudang Seller (ID)", "Pelabuhan Transit", "Laut Internasional", p.negaraTujuan];
                    p.riwayatRute.push({ jam: waktu, lokasi: tahapan[p.transitStage], ket: "Sistem: Barang terdeteksi berpindah lokasi." });
                } else {
                    clearInterval(timer);
                    p.status = "Tiba Di Lokasi";
                    alert(`Simulasi Selesai! Kargo telah sampai di wilayah otoritas ${p.negaraTujuan}.`);
                    renderAllData();
                }
            }, 3000);
        }

        function renderSerahTerima() {
            const tbody = document.getElementById("table-serah-terima");
            tbody.innerHTML = "";
            dataPesanan.filter(p => p.status === "Tiba Di Lokasi").forEach(p => {
                tbody.innerHTML += `<tr>
                    <td><b>${p.id}</b></td><td>${p.negaraTujuan}</td><td>Tiba di Kota Tujuan</td>
                    <td><button class="btn btn-primary" onclick="aksiSelesai('${p.id}')">🏁 Konfirmasi Terima Barang</button></td>
                </tr>`;
            });
        }
        function aksiSelesai(id) {
            let p = dataPesanan.find(x => x.id === id);
            p.status = "Transaksi Selesai (Selesai)";
            let waktu = new Date().toLocaleTimeString();
            p.riwayatRute.push({ jam: waktu, lokasi: p.negaraTujuan, ket: "Final: Barang berhasil diterima dengan konfirmasi aman." });
            alert(`Transaksi ${id} Selesai Sempurna!`);
            renderAllData();
        }

        function hitungLaporan() {
            let totalNilai = dataPesanan.reduce((sum, p) => sum + p.harga, 0);
            let ruteAktif = dataPesanan.filter(p => p.negaraTujuan !== "-").length;
            
            let counts = {};
            let topDest = "-";
            let maxCount = 0;
            dataPesanan.forEach(p => {
                if(p.negaraTujuan !== "-") {
                    counts[p.negaraTujuan] = (counts[p.negaraTujuan] || 0) + 1;
                    if(counts[p.negaraTujuan] > maxCount) {
                        maxCount = counts[p.negaraTujuan];
                        topDest = p.negaraTujuan;
                    }
                }
            });
            
            document.getElementById("rep-exec-nilai").innerText = "Rp " + totalNilai.toLocaleString();
            document.getElementById("rep-exec-rute-aktif").innerText = ruteAktif + " Transaksi";
            document.getElementById("rep-exec-top-dest").innerText = topDest;

            let sukses = dataPesanan.filter(p => p.status === "Transaksi Selesai (Selesai)").length;
            let transit = dataPesanan.filter(p => p.status === "Dalam Perjalanan Laut").length;
            document.getElementById("rep-exec-sukses").innerText = sukses;
            document.getElementById("rep-exec-transit").innerText = transit;

            document.getElementById("rep-sum-total").innerText = dataPesanan.length;
            document.getElementById("rep-sum-done").innerText = sukses;
            
            let lunas = dataPesanan.filter(p => p.bayar === "Lunas").reduce((sum, p) => sum + p.harga, 0);
            let piutang = dataPesanan.filter(p => p.bayar === "Belum Lunas").reduce((sum, p) => sum + p.harga, 0);
            document.getElementById("rep-sum-kas").innerText = "Rp " + lunas.toLocaleString();
            document.getElementById("rep-sum-piutang").innerText = "Rp " + piutang.toLocaleString();

            const tbodyDetail = document.getElementById("table-detail-pesanan");
            tbodyDetail.innerHTML = "";
            dataPesanan.forEach(p => {
                tbodyDetail.innerHTML += `<tr><td>${p.id}</td><td>${p.customer}</td><td>${p.barang}</td><td>${p.negaraTujuan}</td><td>${p.status}</td></tr>`;
            });

            const tbodyJurnal = document.getElementById("table-detail-jurnal");
            tbodyJurnal.innerHTML = "";
            if(jurnalAkuntansi.length === 0) {
                tbodyJurnal.innerHTML = `<tr><td colspan="5" style="text-align:center; color:#94a3b8">Belum ada transaksi lunas (Jurnal Kosong)</td></tr>`;
            } else {
                jurnalAkuntansi.forEach(j => {
                    tbodyJurnal.innerHTML += `<tr>
                        <td>${j.tgl}</td><td>${j.akun}</td>
                        <td>${j.deb > 0 ? 'Rp ' + j.deb.toLocaleString() : '-'}</td>
                        <td>${j.kre > 0 ? 'Rp ' + j.kre.toLocaleString() : '-'}</td>
                        <td><small>${j.ref}</small></td>
                    </tr>`;
                });
            }
        }

        window.onload = initDashboard;
    </script>
</body>
</html>
