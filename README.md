# OBS Zoom to Mouse (OBS 30+ Compatible)

An OBS Lua script to zoom a display-capture source to focus on the mouse.

> **Original Project:** [BlankSourceCode/obs-zoom-to-mouse](https://github.com/BlankSourceCode/obs-zoom-to-mouse)

---

## Why This Version? / Neden Bu Sürüm?

The original script throws this error on OBS 30+:

```
[obs-zoom-to-mouse.lua] Failed to call frontend_event_callback for frontend API: 
[string "C:/Users/.../obs-zoom-to-mouse.lua"]:577: attempt to call field 'obs_sceneitem_get_info' (a nil value)
```

This happens because OBS 30.0 removed the `obs_sceneitem_get_info` and `obs_sceneitem_set_info` functions. This version fixes that issue.

---

Orijinal script OBS 30+ sürümlerinde şu hatayı veriyor:

```
[obs-zoom-to-mouse.lua] Failed to call frontend_event_callback for frontend API: 
[string "C:/Users/.../obs-zoom-to-mouse.lua"]:577: attempt to call field 'obs_sceneitem_get_info' (a nil value)
```

Bu hata, OBS 30.0'da `obs_sceneitem_get_info` ve `obs_sceneitem_set_info` fonksiyonlarının kaldırılmasından kaynaklanıyor. Bu sürüm bu sorunu düzeltiyor.

---

## Installation

1. Download `obs-zoom-to-mouse.lua`
2. Launch OBS
3. Add a **Display Capture** source (if you don't have one already)
4. Go to **Tools → Scripts**
5. Click **+** and add the `obs-zoom-to-mouse.lua` file
6. Select your Display Capture source from the **Zoom Source** dropdown
7. Go to **File → Settings → Hotkeys** and set a hotkey for **Toggle zoom to mouse**

### Recommended Display Capture Settings

For best results, configure your Display Capture source:

| Setting | Value |
|---------|-------|
| Positional Alignment | Top Left |
| Bounding Box Type | Scale to inner bounds |
| Alignment in Bounding Box | Top Left |
| Crop | All zeros |

> **Note:** If you want to crop the display, use **Filter → Crop/Pad** instead of transform crop.

---

## Settings

| Setting | Description |
|---------|-------------|
| **Language** | Interface language (English / Türkçe) |
| **Zoom Source** | Display capture source to zoom |
| **Zoom Factor** | How much to zoom in (1-5x) |
| **Zoom Speed** | Speed of zoom animation |
| **Auto follow mouse** | Track cursor automatically while zoomed |
| **Follow outside bounds** | Track cursor even outside source bounds |
| **Follow Speed** | Speed of mouse tracking |
| **Follow Border** | Edge distance (%) to trigger tracking |
| **Lock Sensitivity** | How close tracking needs to get before locking |
| **Auto Lock on reverse** | Stop tracking when mouse reverses direction |
| **Allow any zoom source** | Enable non-display capture sources |
| **Set manual source position** | Override auto-calculated position/size |

---

## Hotkeys

Set these in **File → Settings → Hotkeys**:

- **Toggle zoom to mouse** - Zoom in/out
- **Toggle follow mouse during zoom** - Enable/disable mouse tracking

---

## How It Works

1. Press the zoom hotkey - script zooms to current mouse position
2. A "safe zone" lets you move the mouse without moving the view
3. Move mouse to the edge - tracking begins and follows the cursor
4. Hold mouse still - tracking stops and creates a new safe zone
5. Press hotkey again - zooms back out

---

## What's New / Yenilikler

### Added Features
- ✅ **OBS 30+ Compatibility** - Fixed deprecated API calls (`obs_sceneitem_get_info` → `obs_sceneitem_get_info2`)
- ✅ **Language Support** - Turkish and English interface
- ✅ **Backward Compatible** - Works with OBS 29.x and 30.0+

### Eklenen Özellikler
- ✅ **OBS 30+ Uyumluluğu** - Kaldırılan API fonksiyonları düzeltildi
- ✅ **Dil Desteği** - Türkçe ve İngilizce arayüz
- ✅ **Geriye Uyumluluk** - OBS 29.x ve 30.0+ ile çalışır

---

## Requirements

- OBS Studio 29.0+ or 30.0+ (tested on 32.0.4)
- Display Capture source

---

# OBS Zoom to Mouse (OBS 30+ Uyumlu)

Mouse pozisyonuna odaklanmak için ekran yakalama kaynağını yakınlaştıran OBS Lua scripti.

> **Orijinal Proje:** [BlankSourceCode/obs-zoom-to-mouse](https://github.com/BlankSourceCode/obs-zoom-to-mouse)

---

## Kurulum

1. `obs-zoom-to-mouse.lua` dosyasını indirin
2. OBS'yi başlatın
3. **Ekran Yakalama** kaynağı ekleyin (yoksa)
4. **Araçlar → Scriptler** menüsüne gidin
5. **+** butonuna tıklayıp `obs-zoom-to-mouse.lua` dosyasını ekleyin
6. **Yakınlaştırma Kaynağı** listesinden Ekran Yakalama kaynağınızı seçin
7. **Dosya → Ayarlar → Kısayol Tuşları** menüsünden **Toggle zoom to mouse** için kısayol ayarlayın

### Önerilen Ekran Yakalama Ayarları

En iyi sonuç için Ekran Yakalama kaynağınızı yapılandırın:

| Ayar | Değer |
|------|-------|
| Konumsal Hizalama | Sol Üst |
| Sınırlayıcı Kutu Tipi | İç sınırlara ölçekle |
| Sınırlayıcı Kutuda Hizalama | Sol Üst |
| Kırpma | Hepsi sıfır |

> **Not:** Ekranı kırpmak istiyorsanız, transform kırpma yerine **Filtre → Kırp/Doldur** kullanın.

---

## Ayarlar

| Ayar | Açıklama |
|------|----------|
| **Dil** | Arayüz dili (English / Türkçe) |
| **Yakınlaştırma Kaynağı** | Yakınlaştırılacak ekran yakalama kaynağı |
| **Yakınlaştırma Oranı** | Ne kadar yakınlaştırılacağı (1-5x) |
| **Yakınlaştırma Hızı** | Yakınlaştırma animasyon hızı |
| **Otomatik mouse takibi** | Yakınlaştırıldığında imleci otomatik takip et |
| **Sınır dışında takip et** | Kaynak sınırları dışında bile imleci takip et |
| **Takip Hızı** | Mouse takip hızı |
| **Takip Sınırı** | Takibi tetikleyen kenar mesafesi (%) |
| **Kilit Hassasiyeti** | Kilitlenmeden önce takibin ne kadar yaklaşması gerektiği |
| **Ters yönde otomatik kilitle** | Mouse ters yöne hareket edince takibi durdur |
| **Tüm kaynaklara izin ver** | Ekran yakalama olmayan kaynakları etkinleştir |
| **Manuel kaynak konumu ayarla** | Otomatik hesaplanan konum/boyutu geçersiz kıl |

---

## Kısayol Tuşları

**Dosya → Ayarlar → Kısayol Tuşları** menüsünden ayarlayın:

- **Toggle zoom to mouse** - Yakınlaştır/Uzaklaştır
- **Toggle follow mouse during zoom** - Mouse takibini aç/kapat

---

## Nasıl Çalışır

1. Zoom kısayoluna basın - script mevcut mouse pozisyonuna yakınlaştırır
2. "Güvenli bölge" görünümü hareket ettirmeden mouse'u hareket ettirmenizi sağlar
3. Mouse'u kenara taşıyın - takip başlar ve imleci takip eder
4. Mouse'u sabit tutun - takip durur ve yeni güvenli bölge oluşturur
5. Kısayola tekrar basın - uzaklaştırır

---

## Gereksinimler

- OBS Studio 29.0+ veya 30.0+ (32.0.4 üzerinde test edildi)
- Ekran Yakalama kaynağı

---



 [orijinal repo](https://github.com/BlankSourceCode/obs-zoom-to-mouse)

---

## Development Tools / Geliştirme Araçları

This project was developed with the assistance of:
- **[Kiro](https://kiro.dev)** - AI-powered IDE
- **Claude Opus 4.5** - AI assistant by Anthropic

Bu proje şu araçların yardımıyla geliştirildi:
- **[Kiro](https://kiro.dev)** - Yapay zeka destekli IDE
- **Claude Opus 4.5** - Anthropic tarafından geliştirilen yapay zeka asistanı
