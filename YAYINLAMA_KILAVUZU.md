# MSDS Özetleyici — İnternette Yayınlama Kılavuzu

Bu kılavuz, uygulamayı bir **link** haline getirip herkesin tarayıcıdan
(hiçbir şey kurmadan) kullanabilmesini sağlar. Kullanım modeli:
**her kullanıcı kendi ücretsiz Gemini API anahtarını girer.**

> ⚠️ Vercel bu uygulamayı çalıştıramaz (Streamlit sürekli açık bir Python
> sunucusu ister, Vercel ise serverless'tır). Doğru yer **Streamlit Community
> Cloud** — hem ücretsiz hem de bu iş için tasarlanmış.

---

## Genel Akış

```
Kod  →  GitHub (depo)  →  Streamlit Cloud (yayınla)  →  Link  →  Kullanıcılar
```

---

## Adım 1 — GitHub'a Yükle

1. github.com'da hesabın yoksa ücretsiz aç.
2. Sağ üstten **New repository** (yeni depo) oluştur.
   - İsim: örn. `msds-ozetleyici`
   - **Public** seç (Streamlit ücretsiz katmanı public depo ister)
   - "Create repository" de.
3. Açılan sayfada **"uploading an existing file"** bağlantısına tıkla.
4. Şu dosyaları sürükle-bırak ile yükle:
   - `msds_ozetleyici.py`  ← ana uygulama (ZORUNLU)
   - `requirements.txt`    ← paket listesi (ZORUNLU)
   - `kurulum.md` ve `.bat` dosyaları → buluta gerek yok, ama yüklesen de zararı yok
5. Alttan **Commit changes** de.

> Not: `.streamlit/secrets.toml` dosyasını GitHub'a YÜKLEME. Anahtar oraya
> yazılmaz; aşağıdaki Adım 3'te (opsiyonel) panelden girilir.

---

## Adım 2 — Streamlit Cloud'da Yayınla

1. **share.streamlit.io** adresine git.
2. **"Continue with GitHub"** ile GitHub hesabınla giriş yap, izin ver.
3. **"Create app"** / **"New app"** de.
4. Ayarları seç:
   - **Repository:** az önce oluşturduğun depo (`kullanıcıadın/msds-ozetleyici`)
   - **Branch:** `main`
   - **Main file path:** `msds_ozetleyici.py`
5. **Deploy** de. Birkaç dakika paketleri kurar ve uygulamayı başlatır.
6. Sana şöyle bir link verir:
   `https://msds-ozetleyici-xxxx.streamlit.app`
   İşte göndereceğin link bu. 🎉

---

## Adım 3 — (OPSİYONEL) Ortak anahtar mı, herkes kendi anahtarı mı?

**Senin tercih ettiğin yöntem: herkes kendi anahtarını girer.**
Bunun için ekstra bir şey yapmana gerek yok — uygulama zaten sol panelde
kullanıcıdan anahtar istiyor ve "nasıl alınır" rehberini gösteriyor.
Bu Adım 3'ü atlayabilirsin.

Eğer ileride "kimse anahtar uğraşmasın, herkes benim kotamı kullansın"
dersen:
1. Streamlit Cloud'da uygulamanın sağ alt **⋮ > Settings > Secrets**.
2. Şunu yapıştır (kendi anahtarınla):
   ```
   GEMINI_API_KEY = "AIza...senin_anahtarin..."
   ```
3. Kaydet. Artık kutu boş bırakılırsa uygulama otomatik senin anahtarını
   kullanır. (Dikkat: o zaman tüm kullanım senin günlük kotandan harcanır.)

---

## Kullanıcıya göndereceğin kısa mesaj örneği

> Merhaba, MSDS/SDS özetleyici aracı şu linkte:
> **[LİNK]**
> Kurulum yok, tarayıcıdan açılıyor. İlk açılışta sol panelden ücretsiz bir
> Google Gemini anahtarı istemesi normal — "Anahtarı nasıl alırım?" kutusundaki
> 5 adımı izle (1 dakika sürmez), anahtarı yapıştır ve PDF'leri yükle.

---

## Sık Sorulanlar

**Kullanıcı bir şey indirmek/kurmak zorunda mı?**
Hayır. Sadece linki açar ve kendi Gemini anahtarını girer.

**Ollama (yerel AI) bulutta çalışır mı?**
Hayır, sunucuda GPU/yerel model yok. Bulut sürümü Gemini ile çalışır.
Yerel/çevrimdışı kullanmak isteyen, klasörü indirip kendi bilgisayarında
`baslat.bat` ile Ollama modunu kullanabilir.

**Gizli/hassas MSDS belgeleri için uygun mu?**
Ücretsiz Gemini katmanında veriler Google tarafından model eğitiminde
kullanılabilir. Gizli belgeler için kullanıcıya yerel (Ollama) modunu öner.

**Uygulamayı güncellersem ne olur?**
GitHub'daki `msds_ozetleyici.py` dosyasını güncelle (yeni sürümü yükle);
Streamlit Cloud değişikliği otomatik algılar ve uygulamayı yeniden başlatır.
Link değişmez.

**Uygulama "uyku" moduna geçer mi?**
Ücretsiz katmanda uzun süre kullanılmayan uygulama uykuya geçebilir; bir
sonraki ziyarette birkaç saniyede uyanır. Link aynı kalır.
