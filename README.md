# Hackaton_ArchAI

Manus "10X Your Brand" hackathonu (12 Ekim 2026, İstanbul) için hazırlanan katman: **ArchAI**'yi (`../ArchAI`) Manus'a **uzak MCP sunucusu** olarak açar. Fikir: arsa ilanından kısa sürede müteahhit için ön fizibilite paketi (plan, metraj, maliyet, teklif). ArchAI kodu bu klasörde yoktur.

## Özellikler
- `server.py`: MCP sunucusu; araçlar `hizli_fizibilite`, `arsa_fizibilite`, `proje_ozet`.
- `/mcp` uç noktası Bearer token ister; `/f/...` imzalı dosya linkleri yalnızca çıktı dosyalarını sunar.
- `baslat.sh` / `durdur.sh`: ArchAI (yalnız 127.0.0.1) + MCP katmanı + Cloudflare hızlı tüneli.
- `scripts/`: uçtan uca test istemcisi, demo hazırlama, fal.ai testi, kayıt/film/altyazı üretimi.
- `console.py` / `console.html`, `demo.html`, `prompts/` (Manus talimatları), `teslim/` (demo videoları, görseller, `ACIKLAMA.md`).
- `NOTLAR.md`: etkinlik planı, riskler ve teslim paketi.

## Teknoloji
Python >= 3.11, `mcp`, `httpx`, `uvicorn`, `pillow`; `uv` ile yönetilir; cloudflared tüneli; fal.ai, Apify ve Manus entegrasyonu.

## Kurulum / çalıştırma
```bash
uv sync
./baslat.sh                       # Manus'a girilecek URL ve token çıktıda yazılır
uv run python scripts/test_client.py [URL]
./durdur.sh
```
Ön koşul: `../ArchAI` projesi (FastAPI, port 8000) ve `cloudflared`.

## Ortam değişkenleri (`.env.example`)
`ARCHAI_MCP_TOKEN`, `ARCHAI_PUBLIC_URL`, `ARCHAI_URL`, `FAL_KEY`, `FAL_IMAGE_MODEL`, `FAL_VIDEO_MODEL`, `APIFY_TOKEN`, `MANUS_API_KEY`

## Güvenlik notu
ArchAI'nin Blender MCP sunucusu (kod çalıştırma içerir) asla dışarı açılmamalıdır. Teklif rakamları "avan / ön fizibilite" niteliğindedir.

## Lisans
Lisans: belirtilmemiş.
