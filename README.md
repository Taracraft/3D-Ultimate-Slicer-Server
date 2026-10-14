# 3D Ultimate Slicer Server

Privater, hashgepruefter Transferstand fuer den separaten Linux-Testserver von
Ultimate 3D Studio. Enthalten ist das W53-Testpaket; Engine-Binaerdateien,
Zugangsdaten und private Laufzeitdaten sind nicht enthalten.

## Auf dem Testserver

```sh
git clone https://github.com/Taracraft/3D-Ultimate-Slicer-Server.git
cd 3D-Ultimate-Slicer-Server/Slicer-Server/testserver-package/package
sha256sum -c SHA256SUMS
python3 verify_test_server_package.py --package-dir .
```

Das Repository ist privat. Git muss mit einem berechtigten GitHub-Zugang
authentifiziert sein; keine Zugangsdaten in die Clone-URL schreiben.

Erst nach beiden erfolgreichen Pruefungen in ein neues, noch nicht vorhandenes
privates Ziel extrahieren:

```sh
python3 verify_test_server_package.py --package-dir . --extract /srv/ultimate-slicer-testpackage
cd /srv/ultimate-slicer-testpackage
python3 clean_host_preflight.py
```

Bei Paketabweichung, unvollstaendiger Inventur oder nativem Slicerbestand stoppen.
Der Preflight ist rein lesend und bereinigt oder migriert nichts. Die weitere
manuelle Folge steht im extrahierten LINUX_TEST_SERVER_RUNBOOK.md.

## Stand und Grenzen

- Paket: 38 Archivdateien, 111064 Bytes.
- Archiv-SHA-256: `6d3bf8163d311ae06d344da988e3d915856c8b171965c9e54a1b2ea799b78b00`.
- Lokaler Clone mit core.autocrlf=true sowie Paket und Sidecar geprueft.
- PC-Gesamtgate am 14.10.2026 um 06:57 CEST frisch gruen.
- container_deploy_ready, engine_included und secret_files_included bleiben false.
- Reale Linux-, Supervisor-, Docker-, TLS-, Persistenz-, Upgrade-, Rollback-,
  Restore- und Engine-Abnahmen stehen weiterhin aus.
- Herkunfts- und Lizenzmarkierungen im Paket bleiben erhalten; dieser private
  Transfer ist keine oeffentliche Produkt- oder Lizenzfreigabe.
- Keine echten Slices, Jobs, Uploads, Druckstarts oder Druckerbefehle.
- Das vorhandene Live-System behaelt ausschliesslich seinen nativen Slicer;
  HAOS bleibt reine Planung.

Details und Dateipruefsummen: [Paket-Anleitung](Slicer-Server/testserver-package/README.md)
und [Delivery-Manifest](Slicer-Server/testserver-package/DELIVERY-MANIFEST.json).
