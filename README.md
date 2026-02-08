# Yazılım Kalite Güvencesi ve Testi - Proje Özeti ve Kriter Karşılama



## 1) Teknik Gereksinimler

- **Framework: Spring Boot Web MVC**
  - Kod: `src/main/java/com/example/weather/WeatherApplication.java`
- **Test Coverage %80+ (JaCoCo)**
  - Konfigürasyon: `pom.xml` -> `jacoco-maven-plugin`
  - Rapor: `target/site/jacoco/index.html`
- **Zorunlu Test Seviyeleri (5+)**
  - Unit: `src/test/java/com/example/weather/unit/OutfitServiceTest.java`
  - Integration: `src/test/java/com/example/weather/integration/WeatherIntegrationTest.java`
  - UI (Selenium): `src/test/java/com/example/weather/ui/WeatherUITest.java`
  - Regression Suite: `src/test/java/com/example/weather/RegressionTestSuite.java`
  - End-to-End: `src/test/java/com/example/weather/e2e/WeatherE2ETest.java`

## 2) UI / Dashboard Kriterleri (Kontrol Paneli)

- **Benzersiz ID'ler:** `input-city`, `input-temp`
  - Dosya: `src/main/resources/templates/index.html`
- **Form validasyonu + hata mesajı**
  - `:invalid` kırmızı çerçeve + uyarı metni
- **Sonuç ikonu + timestamp**
  - Kar tanesi / güneş ikonları + `timestampLabel`
- **Risk rozeti + sparkline**
  - Risk rozeti: `stats.lastRisk`
  - Sparkline: `trendData` (son 5 sıcaklık)
- **Mock servis durumu**
  - “Sistem Aktif” yeşil ikon
- **Gece/Gündüz modu**
  - Toggle ile tema değişimi
- **Son İşlemler tablosu + Sil butonu**
  - Regresyon/E2E testleri için fonksiyonel aksiyon

## 3) STLC Başlıklarına Göre Yapılanlar

1. **Gereklilik Analizi**
   - Uygulama: şehir + sıcaklık girilerek kıyafet önerisi üretir.
   - UI kriterleri: validasyon, hata mesajı, sonuç logu (timestamp).
2. **Test Planlama**
   - Araçlar: JUnit5, Spring Test, MockMvc, Selenium, JaCoCo.
3. **Test Tasarımı**
   - Sıcaklık aralıkları için senaryolar (soğuk, serin, ılık, sıcak).
4. **Test Ortamı**
   - `src/test/resources/application-test.properties`
   - Maven bağımlılıkları: `pom.xml`
5. **Test Uygulama**
   - Tüm test sınıfları `src/test/java/...` içinde.
6. **Test Kapanışı**
   - Regression Suite ile tüm testlerin tek koşumda çalıştırılması.
7. **Test Sonuçları**
   - JaCoCo raporu: `target/site/jacoco/index.html`
8. **Test Sonuçlarının Değerlendirilmesi**
   - Rapor kısmında pass/fail ve coverage özetlenecek.
9. **Proje Değerlendirmesi**
   - Yapılanlar/yapılamayanlar rapora eklenecek.
10. **Alınan Hatalar ve Çözümleri**
   - Bug listesi + severity/priority rapora eklenecek.
11. **Projeden Öğrenilenler**
   - Best practice + kazanımlar rapora eklenecek.

## 4) Ekran Görüntüsü Listesi

- `screenshots/ui-dashboard.png`
- `screenshots/unit-test.png`
- `screenshots/integration-test.png`
- `screenshots/ui-test.png`
- `screenshots/e2e-test.png`
- `screenshots/regression-suite.png`
- `screenshots/jacoco-summary.png`
- `screenshots/test-summary-table.png`
- `screenshots/ui-validation-error.png`
- `screenshots/ui-theme-dark.png`
- `screenshots/ui-theme-light.png`
- `screenshots/ui-system-status.png`
- `screenshots/ui-delete-action.png`

## 5) Eclipse Üzerinden Çalıştırma

- **Proje içe aktarma**
  - File > Import > Existing Maven Projects
  - Proje kökü: `Enes Furkan Albayrak - 2203013031`
- **Testleri çalıştırma**
  - `src/test/java` altında paket seç → Right click → Run As → JUnit Test
- **Regression suite**
  - `RegressionTestSuite.java` → Run As → JUnit Test
- **Coverage (Eclipse/EclEmma)**
  - Test paketini seç → Coverage As → JUnit Test
  - Rapor: Coverage view + `target/site/jacoco/index.html`

## 6) Test Komutları (Maven)

- Tüm testler + JaCoCo: `mvn test`
- Regression Suite: IDE üzerinden `RegressionTestSuite`


