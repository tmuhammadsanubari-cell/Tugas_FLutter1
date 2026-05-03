import 'package:flutter/material.dart';

void main() {
  runApp(const AkademikApp());
}

class AkademikApp extends StatelessWidget {
  const AkademikApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Telkom University',
      debugShowCheckedModeBanner: false,
      theme: AppTheme.themeData,
      home: const BerandaPage(),
    );
  }
}

class AppTheme {
  static const Color primary = Color(0xFF1A3A6E);
  static const Color primaryLight = Color(0xFF3A7BD5);
  static const Color surface = Color(0xFFFFFFFF);
  static const Color background = Color(0xFFF0F4FB);
  static const Color textPrimary = Color(0xFF1A2340);
  static const Color textSecondary = Color(0xFF6B7FA3);
  static const Color borderColor = Color(0xFFDCE4F0);

  static final ThemeData themeData = ThemeData(
    useMaterial3: true,
    colorScheme: ColorScheme.fromSeed(
      seedColor: primary,
      primary: primary,
      secondary: primaryLight,
      surface: surface,
    ),
    scaffoldBackgroundColor: background,
    appBarTheme: const AppBarTheme(
      backgroundColor: primary,
      foregroundColor: Colors.white,
      centerTitle: true,
      elevation: 0,
      titleTextStyle: TextStyle(
        fontSize: 18,
        fontWeight: FontWeight.w600,
        color: Colors.white,
        letterSpacing: 0.3,
      ),
    ),
    
    cardTheme: CardThemeData( 
      color: surface,
      elevation: 0,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(16),
        side: const BorderSide(color: borderColor, width: 0.5),
      ),
    ),
    textTheme: const TextTheme(
      titleLarge: TextStyle(fontSize: 16, fontWeight: FontWeight.w700, color: textPrimary),
      titleMedium: TextStyle(fontSize: 14, fontWeight: FontWeight.w600, color: textPrimary),
      titleSmall: TextStyle(fontSize: 13, fontWeight: FontWeight.w600, color: textPrimary),
      bodyMedium: TextStyle(fontSize: 13, color: textPrimary),
      bodySmall: TextStyle(fontSize: 11, color: textSecondary),
      labelSmall: TextStyle(fontSize: 10, color: textSecondary),
    ),
  );
}


class BerandaPage extends StatelessWidget {
  const BerandaPage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Portal Akademik'),
        bottom: PreferredSize(
          preferredSize: const Size.fromHeight(20),
          child: Padding(
            padding: const EdgeInsets.only(bottom: 12),
            child: Text(
              'Universitas Nusantara',
              style: Theme.of(context).textTheme.bodySmall?.copyWith(
                    color: const Color(0xFF8AB4E8),
                    fontSize: 11,
                  ),
            ),
          ),
        ),
      ),
      body: SingleChildScrollView(
        padding: const EdgeInsets.symmetric(horizontal: 16, vertical: 16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [e
            const MahasiswaCard(
              nama: 'Taura Muhammad Sanubari',
              nim: '103012330280',
              prodi: 'Informatika',
              inisial: 'TR',
            ),
            const SizedBox(height: 12),

            Row(
              children: const [
                Expanded(
                  child: InfoStatCard(
                    label: 'IPK Kumulatif',
                    nilai: '3.87',
                    sub: 'Dari 4.00 maks',
                    iconEmoji: '📊',
                    bgColor: Color(0xFFE8F5E9),
                  ),
                ),
                SizedBox(width: 12),
                Expanded(
                  child: InfoStatCard(
                    label: 'SKS Tempuh',
                    nilai: '101',
                    sub: 'Dari 144 total',
                    iconEmoji: '📚',
                    bgColor: Color(0xFFFFF3E0),
                  ),
                ),
              ],
            ),
            const SizedBox(height: 20),

            Text(
              'Menu Akademik',
              style: Theme.of(context).textTheme.titleSmall,
            ),
            const SizedBox(height: 10),

            GridView.count(
              crossAxisCount: 2,
              crossAxisSpacing: 12,
              mainAxisSpacing: 12,
              shrinkWrap: true,
              physics: const NeverScrollableScrollPhysics(),
              children: const [
                MenuCard(
                  judul: 'KRS',
                  deskripsi: 'Kartu Rencana Studi',
                  iconEmoji: '📋',
                  bgColor: Color(0xFFE8F0FB),
                  route: '/krs',
                ),
                MenuCard(
                  judul: 'Jadwal',
                  deskripsi: 'Jadwal Kuliah',
                  iconEmoji: '📅',
                  bgColor: Color(0xFFFCE8F3),
                  route: '/jadwal',
                ),
                MenuCard(
                  judul: 'Nilai',
                  deskripsi: 'Transkrip Nilai',
                  iconEmoji: '🎓',
                  bgColor: Color(0xFFE8F5E9),
                  route: '/nilai',
                ),
                MenuCard(
                  judul: 'Presensi',
                  deskripsi: 'Kehadiran Kuliah',
                  iconEmoji: '✅',
                  bgColor: Color(0xFFFFF3E0),
                  route: '/presensi',
                ),
              ],
            ),
            const SizedBox(height: 20),
          ],
        ),
      ),
      bottomNavigationBar: const BottomNavBar(),
    );
  }
}


class MahasiswaCard extends StatelessWidget {
  final String nama;
  final String nim;
  final String prodi;
  final String inisial;

  const MahasiswaCard({
    super.key,
    required this.nama,
    required this.nim,
    required this.prodi,
    required this.inisial,
  });

  @override
  Widget build(BuildContext context) {
    return Card(
      child: Padding(
        padding: const EdgeInsets.all(16),
        child: Row(
          children: [
            // Avatar lingkaran dengan inisial
            Container(
              width: 52,
              height: 52,
              decoration: const BoxDecoration(
                shape: BoxShape.circle,
                gradient: LinearGradient(
                  colors: [AppTheme.primary, AppTheme.primaryLight],
                  begin: Alignment.topLeft,
                  end: Alignment.bottomRight,
                ),
              ),
              alignment: Alignment.center,
              child: Text(
                inisial,
                style: const TextStyle(
                  color: Colors.white,
                  fontSize: 20,
                  fontWeight: FontWeight.w700,
                ),
              ),
            ),
            const SizedBox(width: 14),

            // Informasi mahasiswa
            Expanded(
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  Text(nama, style: Theme.of(context).textTheme.titleMedium),
                  const SizedBox(height: 2),
                  Text(prodi, style: Theme.of(context).textTheme.bodySmall),
                  const SizedBox(height: 6),
                  // Badge NIM
                  Container(
                    padding: const EdgeInsets.symmetric(horizontal: 10, vertical: 3),
                    decoration: BoxDecoration(
                      color: const Color(0xFFE8F0FB),
                      borderRadius: BorderRadius.circular(8),
                    ),
                    child: Text(
                      'NIM: $nim',
                      style: const TextStyle(
                        fontSize: 11,
                        fontWeight: FontWeight.w600,
                        color: AppTheme.primary,
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}


class InfoStatCard extends StatelessWidget {
  final String label;
  final String nilai;
  final String sub;
  final String iconEmoji;
  final Color bgColor;

  const InfoStatCard({
    super.key,
    required this.label,
    required this.nilai,
    required this.sub,
    required this.iconEmoji,
    required this.bgColor,
  });

  @override
  Widget build(BuildContext context) {
    return Card(
      child: Padding(
        padding: const EdgeInsets.all(14),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // Icon background
            Container(
              width: 36,
              height: 36,
              decoration: BoxDecoration(
                color: bgColor,
                borderRadius: BorderRadius.circular(10),
              ),
              alignment: Alignment.center,
              child: Text(iconEmoji, style: const TextStyle(fontSize: 18)),
            ),
            const SizedBox(height: 8),
            Text(label, style: Theme.of(context).textTheme.labelSmall),
            const SizedBox(height: 2),
            Text(
              nilai,
              style: const TextStyle(
                fontSize: 24,
                fontWeight: FontWeight.w700,
                color: AppTheme.textPrimary,
                height: 1.1,
              ),
            ),
            const SizedBox(height: 2),
            Text(sub, style: Theme.of(context).textTheme.labelSmall),
          ],
        ),
      ),
    );
  }
}


class MenuCard extends StatelessWidget {
  final String judul;
  final String deskripsi;
  final String iconEmoji;
  final Color bgColor;
  final String route;

  const MenuCard({
    super.key,
    required this.judul,
    required this.deskripsi,
    required this.iconEmoji,
    required this.bgColor,
    required this.route,
  });

  @override
  Widget build(BuildContext context) {
    return Card(
      clipBehavior: Clip.antiAlias,
      child: InkWell(
        onTap: () {
          ScaffoldMessenger.of(context).showSnackBar(
            SnackBar(
              content: Text('Membuka halaman $judul...'),
              duration: const Duration(seconds: 1),
              behavior: SnackBarBehavior.floating,
              shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(10)),
            ),
          );
        },
        child: Padding(
          padding: const EdgeInsets.all(16),
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              // Icon wrapper
              Container(
                width: 46,
                height: 46,
                decoration: BoxDecoration(
                  color: bgColor,
                  borderRadius: BorderRadius.circular(14),
                ),
                alignment: Alignment.center,
                child: Text(iconEmoji, style: const TextStyle(fontSize: 22)),
              ),
              const Spacer(),
              Text(judul, style: Theme.of(context).textTheme.titleSmall),
              const SizedBox(height: 3),
              Text(deskripsi, style: Theme.of(context).textTheme.labelSmall),
            ],
          ),
        ),
      ),
    );
  }
}


class BottomNavBar extends StatelessWidget {
  const BottomNavBar({super.key});

  @override
  Widget build(BuildContext context) {
    return BottomNavigationBar(
      type: BottomNavigationBarType.fixed,
      backgroundColor: Colors.white,
      selectedItemColor: AppTheme.primary,
      unselectedItemColor: AppTheme.textSecondary,
      selectedLabelStyle: const TextStyle(fontSize: 10, fontWeight: FontWeight.w600),
      unselectedLabelStyle: const TextStyle(fontSize: 10),
      currentIndex: 0,
      elevation: 0,
      items: const [
        BottomNavigationBarItem(icon: Icon(Icons.home_rounded), label: 'Beranda'),
        BottomNavigationBarItem(icon: Icon(Icons.person_rounded), label: 'Profil'),
        BottomNavigationBarItem(icon: Icon(Icons.notifications_rounded), label: 'Notif'),
        BottomNavigationBarItem(icon: Icon(Icons.settings_rounded), label: 'Setelan'),
      ],
    );
  }
}
