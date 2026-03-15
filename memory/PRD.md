# TuningTalálkozó - PRD (Product Requirements Document)

## Eredeti Feladat
- questgearhub.com hivatkozások eltávolítása és cseréje
- Bio szerkesztési funkció formázási lehetőségekkel
- Resend e-mail integráció (noreply@tuningtalalkozok.hu)
- Jelszó-visszaállítás funkció
- Email cím módosítás megerősítéssel

## Felhasználói Személyek
- **Tuning rajongók**: Magyar autósok, akik szeretik a tuning kultúrát
- **Eseményszervezők**: Találkozókat és versenyeket szerveznek
- **Admin**: Felügyelik a tartalmat és jóváhagyják az eseményeket

## Alapfunkciók (Core Requirements)
- Regisztráció és bejelentkezés
- Email megerősítés
- Profil kezelés (profilkép, borítókép, bio)
- Bejegyzések létrehozása
- Események kezelése
- Ismerős rendszer
- Valós idejű chat
- Admin panel

## Implementált Funkciók (2026-03-14)
✅ questgearhub.com hivatkozások eltávolítva
✅ FRONTEND_URL környezeti változó bevezetése
✅ Bio szerkesztés formázási lehetőségekkel
✅ Resend integráció (noreply@tuningtalalkozok.hu)
✅ Jelszó-visszaállítás (/forgot-password, /reset-password)
✅ Email cím módosítás (/settings)
✅ Verification email újraküldés endpoint

## Implementált Funkciók (2026-03-15) - Nagy frissítés

### Jogi oldalak (ÁSZF, Adatvédelem)
✅ /aszf - Általános Szerződési Feltételek oldal
✅ /adatvedelem - Adatvédelmi Tájékoztató oldal (GDPR kompatibilis)
✅ Footer frissítve: ÁSZF, Adatvédelem linkek + support email (info@tuningtalalkozok.hu)

### Események javítások
✅ $ jel eltávolítva - csak "Ft" jelenik meg
✅ Helyszín kattintható Google Maps link
✅ Cím mező hozzáadva (város + utca)
✅ Linkek kattinthatóak a leírásban (új ablakban nyílnak)
✅ "Bővebben" gomb az eseményeknél
✅ Teljes esemény megtekintése dialog

### Feed oldal újdonságok
✅ Profilkép és név kattintható (profil megtekintés)
✅ Videó feltöltés támogatása
✅ Emoji picker poszt íráshoz
✅ Kép vágás/igazítás feltöltés előtt
✅ Poszt moderáció (admin jóváhagyás szükséges)
✅ "Jóváhagyásra vár" státusz megjelenítése

### Admin panel bővítés
✅ Posztok moderáció fül
✅ Jóváhagyás/elutasítás gombok
✅ Függőben lévő posztok száma

### Backend API bővítések
✅ /api/posts/pending - függőben lévő posztok
✅ /api/posts/{id}/approve - poszt jóváhagyás
✅ /api/posts/{id}/reject - poszt elutasítás
✅ /api/friends/list/{user_id} - más felhasználó ismerősei

## Technikai Stack
- **Frontend**: React.js, TailwindCSS, Shadcn/ui
- **Backend**: FastAPI, Python
- **Database**: MongoDB
- **Email**: Resend API
- **Real-time**: Socket.io

## VPS Telepítési infók
- Domain: tuningtalalkozok.hu
- Email: noreply@tuningtalalkozok.hu (Resend)
- Backend: systemd service (tuning-backend)
- Frontend: nginx + React build
