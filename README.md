# kilsat-legal

Julkinen GitHub Pages -repo Kilsat (Ajopäiväkirja) -sovellusten **tietosuojaselosteille ja käyttöehdoille**.

Sovellusten lähdekoodi pysyy **private**-repositorioissa:
- iOS: `digital_ajopaivakirja`
- Android: `digital_ajopaivakirja-android`

## Julkiset URL:t (Pages `/docs`)

| Alusta | Tietosuojaseloste | Käyttöehdot |
|--------|-------------------|-------------|
| Android | https://aleksipii.github.io/kilsat-legal/android/tietosuojaseloste/ | https://aleksipii.github.io/kilsat-legal/android/kayttoehdot/ |
| iOS | https://aleksipii.github.io/kilsat-legal/ios/tietosuojaseloste/ | https://aleksipii.github.io/kilsat-legal/ios/kayttoehdot/ |
| Etusivu | https://aleksipii.github.io/kilsat-legal/ | |

## Pages päälle

1. Repo → **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` · Folder: **`/docs`** → Save

## Synkkaus private-repoista

**Lähde totuus** on private-repojen `Legal/`-kansioissa. Päivitä sitten tämän repon `docs/ios/` tai `docs/android/` (säilytä YAML-front matter), commit + push.

## Store

- **Play Console** Privacy Policy → Android-tietosuojaseloste-URL
- **App Store Connect** Privacy Policy → iOS-tietosuojaseloste-URL (kun vaihdat `LegalDocumentLinks.swift`)

Tuki: kilsat.tuki@gmail.com
