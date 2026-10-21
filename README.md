# Repositorio Kodi — IPTV-org

Hosteá esta carpeta en GitHub Pages y Kodi actualizará el addon solo.

## Publicar en GitHub Pages
1. Creá un repo PÚBLICO en GitHub llamado `kodi-iptvorg` (usuario `psherrera`).
2. Subí TODO el contenido de esta carpeta a la raíz del repo
   (addons.xml, addons.xml.md5 y las carpetas plugin.video.iptvorg/ y repository.iptvorg/).
3. Settings → Pages → Source: `Deploy from a branch`, Branch: `main` / `(root)` → Save.
4. Esperá 1–2 min. Debe abrir: https://psherrera.github.io/kodi-iptvorg/addons.xml

## Instalar en Kodi (una sola vez)
1. Ajustes → Sistema → Add-ons → activar *Orígenes desconocidos*.
2. Add-ons → Instalar desde zip → `repository.iptvorg-1.0.0.zip`.
3. Add-ons → Instalar desde repositorio → *IPTV-org Repo* → Add-ons de vídeo → IPTV-org → Instalar.

Desde ahí, cada versión nueva la toma Kodi automáticamente.

## Publicar una versión nueva del addon
1. Subí el número en `plugin.video.iptvorg/addon.xml` (p. ej. 2.0.2) y en `<news>`.
2. Reconstruí el repo:
   python3 build_repo.py --base-url https://psherrera.github.io/kodi-iptvorg/ \
       --out docs --repo-src repository.iptvorg --addon ../plugin.video.iptvorg
3. Subí la carpeta `docs/` actualizada a GitHub. Kodi ofrecerá la actualización en pocas horas
   (o forzá: Add-ons → IPTV-org Repo → Buscar actualizaciones).
