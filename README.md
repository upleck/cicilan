# Cicilan

Frontend cepat di GitHub Pages, backend Supabase Edge Function + Postgres.

## URL

- Frontend GitHub Pages: `https://upleck.github.io/cicilan/`
- Admin: `https://upleck.github.io/cicilan/?admin=1`
- Contoh peminjam test: `https://upleck.github.io/cicilan/?p=supabase-admin-test-token`
- Backend Supabase: `https://lsaqzyqmgvjgpexgavwj.supabase.co/functions/v1/database-access`

## Struktur

- `supabase/migrations/`: schema database Supabase.
- `supabase/functions/database-access/index.ts`: backend API, reminder, FlowKirim.
- `Index.html`: UI utama dan sumber frontend.
- `docs/index.html`: build statis untuk GitHub Pages.
- `preview-server.js`: preview lokal mock.

## Cara Kerja

```text
Peminjam/admin buka GitHub Pages
↓
Frontend cepat dari GitHub
↓
Frontend memanggil Supabase Edge Function
↓
Edge Function baca/tulis Postgres dan kirim WA FlowKirim
```

API key FlowKirim tetap aman di Supabase Function Secrets, tidak ditaruh di GitHub.

## Deploy

1. Edit `Index.html`, `docs/index.html`, atau file `supabase`.
2. Deploy Edge Function Supabase bila backend berubah.
3. Push isi `docs/index.html` ke branch `gh-pages` repo `upleck/cicilan`.

## QRIS

Untuk QRIS, gunakan URL gambar publik langsung, idealnya dari repo GitHub Pages yang sama atau image hosting publik. Hindari Google Drive preview karena sering tidak terbaca sebagai gambar langsung.
