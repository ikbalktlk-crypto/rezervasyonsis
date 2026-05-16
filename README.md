# 🏨 AI Tabanlı Otel Rezervasyon ve Yönetim Sistemi

Bu proje, akıllı bir otel rezervasyon ve envanter yönetim sistemidir. Kullanıcıların doğal dil kullanarak oda araması yapmasını, müsaitlik durumunu kontrol etmesini ve rezervasyon işlemlerini gerçekleştirmesini sağlamak amacıyla geliştirilmektedir.

Projenin temel amacı; dil modellerinin **Tool Calling (Fonksiyon Çağırma)** ve **RAG (Retrieval-Augmented Generation)** yeteneklerini arkadaki ilişkisel veri tabanı (SQL/Excel) süreçleriyle entegre etmektir.

---

## 🛠️ Kullanılan Teknolojiler & Kütüphaneler

* **Dil & Ortam:** Python 3, Google Colab
* **Yapay Zeka Mantığı:** Gemini API (Tool Calling & RAG yapısı)
* **Veri Yönetimi:** SQL, Pandas, Openpyxl (Excel entegrasyonu)

---

## 🎯 Mevcut Durum & Yol Haritası (To-Do)

Proje henüz geliştirme aşamasındadır. Yapılanlar ve yakında eklenecek özellikler şu şekildedir:

- [x] Otel, oda ve müsaitlik veri setlerinin yapılandırılması
- [x] Gemini API entegrasyonu ve temel chatbot yapısı
- [ ] **Tool Calling:** Botun veritabanında oda sorgulaması ve rezervasyon yapabilmesi
- [ ] **RAG Entegrasyonu:** Kullanıcı sorularına otel kuralları ve bilgilerine göre dinamik cevap üretilmesi
- [ ] Kullanıcı deneyimini artıracak temel bir arayüz/dashboard

---

