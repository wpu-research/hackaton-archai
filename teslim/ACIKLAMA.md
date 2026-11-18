# ArchAI Growth Engine

**Takım / ürün:** ArchAI · Hackathon: ISTANBUL Ignited by Slush'D — Manus "10× Your Brand" · 12 Ekim 2026

**Kod:** https://github.com/wpu-research/archai-growth-engine (bugünkü iş: `growth_engine/` + 12 Ekim commit'leri)

## Türkçe

**Sorun.** İstanbul'da bir müteahhit satılık bir arsayı değerlendirmek için mimardan avan proje ve maliyet tahmini bekliyor: arsa başına 3–5 gün. Fırsatlar kaçıyor ya da yanlış iş modeliyle alınıyor.

**Ne yaptık.** ArchAI'yi (imar bilgisinden avan proje, metraj, maliyet ve teklif üreten mimarlık motorumuz) kendi kendini pazarlayan bir satış motoruna çevirdik:
1. **Manus**, **Apify** ile sahibinden.com'dan satılık arsa ve sıfır daire ilanlarını topluyor, imar/emsal/tapu kurallarıyla eliyor (40 ilan → 9 aday).
2. **ArchAI** (Manus'a MCP ile bağlı) her aday için avan proje, 94 kalemlik metraj, maliyet, teklif ve pafta üretiyor; bölge m² satış fiyatını çıkarıp **satın alma** ve **kat karşılığı** senaryolarını hesaplıyor.
3. **fal** cephe ve iç mekânları fotogerçekçi yapıyor, Kling ile 38 saniyelik tanıtım filmi üretiyor; ArchAI 3D modelinde bina gezilebiliyor.
4. **Manus** müteahhide ve arsa sahibine ayrı WhatsApp teklifleri, Instagram/LinkedIn/TikTok gönderileri hazırlıyor; hiçbiri onaysız gönderilmiyor.

**Öncesi / sonrası.** Arsa başına 3–5 gün → dakikalar. Arsa başına maliyet birkaç dolar (Apify ≈ $0,3 / 40 ilan; fal ≈ $2–3 / film). Kartal'da incelenen 8 arsanın tamamı satın alma senaryosunda zarardaydı; ArchAI doğru modeli (kat karşılığı) ve paylaşımı gösterdi.

**Gün içinde yapılanlar.** ArchAI'nin Manus'a açılan güvenli MCP katmanı (fizibilite, kârlılık, kat karşılığı, bölge fiyatı, fal render/video araçları), salt-okunur imzalı 3D linkleri, Manus API ile çalışan Growth Console, tanıtım filmi hattı, kampanya ve sosyal medya akışı.

**Notlar.** Rakamlar avan / ön fizibilitedir; imar ve çekme mesafeleri belediyeden teyit edilmelidir. Telefon ve satıcı verisi toplanmaz.

## English

**Problem.** In Istanbul, a developer who spots a plot for sale waits 3–5 days for an architect's concept design and cost estimate. Deals are missed or bought under the wrong business model.

**What we built.** We turned ArchAI — our engine that turns zoning data into a concept design, bill of quantities, cost and quote — into a self-marketing sales engine:
1. **Manus** uses **Apify** to collect land and new-apartment listings from sahibinden.com and filters them by zoning, FAR and title rules (40 listings → 9 candidates).
2. **ArchAI** (connected to Manus via MCP) generates a concept design, a 94-item bill of quantities, cost, quote and drawings for each plot, derives the local sales price per m² and compares **buy-the-land** vs **land-for-flats (kat karşılığı)** economics.
3. **fal** renders photorealistic facades and interiors and, with Kling, a 38-second promo film; the building can be explored in ArchAI's 3D model.
4. **Manus** drafts separate WhatsApp offers for the developer and the landowner plus Instagram/LinkedIn/TikTok posts — nothing is sent without approval.

**Before / after.** 3–5 days per plot → minutes, at a few dollars per plot. All 8 Kartal plots lost money if bought outright; ArchAI showed the right model (land-for-flats) and the split.

**Built today.** A secure MCP layer exposing ArchAI to Manus (feasibility, profitability, land-for-flats, local price, fal render/video tools), signed read-only 3D links, a Growth Console driven by the Manus API, the promo-film pipeline, and the campaign and social workflow.

**Notes.** Figures are preliminary feasibility; zoning and setbacks must be confirmed with the municipality. No phone or seller data is collected.

## Kullanılan araçlar / Tools
Manus (orchestration, MCP connectors, API) · Apify (`clearpath/sahibinden-real-estate`) · fal.ai (FLUX Kontext, Kling 2.1) · ArchAI (FastAPI + three.js, MCP server) · Cloudflare Tunnel
