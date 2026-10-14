# Privater Linux-Testserver-Transfer

Dieser Kandidat ist fuer das private Continuity-Repository bestimmt.
Er wurde lokal geklont und geprueft. Das Remote wird erst nach dessen
Erstellung und erfolgreichem Upload/Readback als verfuegbar gemeldet.
Dies ist keine oeffentliche Produktveroeffentlichung oder Betriebsfreigabe.

## Bezug nach bestaetigtem Upload

    git clone https://github.com/Taracraft/3D-Ultimate-Slicer-Server.git
    cd 3D-Ultimate-Slicer-Server/Slicer-Server/testserver-package/package
    sha256sum -c SHA256SUMS
    python3 verify_test_server_package.py --package-dir .

Private GitHub-Repositories verlangen einen berechtigten GitHub-Zugang.
Zugangsdaten ausschliesslich ueber den normalen Git-Credentialdialog oder
den eingerichteten SSH-Zugang verwenden; niemals in URL, Befehle oder Dateien.

Der Paketordner enthaelt exakt drei Dateien. Keine lokalen Daten ergaenzen.
Nach beiden erfolgreichen Pruefungen in ein neues privates Ziel extrahieren:

    python3 verify_test_server_package.py --package-dir . --extract /srv/ultimate-slicer-testpackage
    cd /srv/ultimate-slicer-testpackage
    python3 clean_host_preflight.py

Bei Hashfehler oder nativem Slicerbestand stoppen. Der Preflight ist lesend.
Er bereinigt, stoppt und migriert nichts. Die weitere manuelle Abnahmefolge
steht in LINUX_TEST_SERVER_RUNBOOK.md im extrahierten Paket.
Kein automatischer Dockerstart und kein Engine-Download.

## Grenzen

container_deploy_ready, engine_included und secret_files_included bleiben false.
Der private Clone-Transport schliesst keine reale Linux-, Supervisor-, Docker-,
TLS-, Upgrade-, Restore-, Engine- oder oeffentliche Lizenzabnahme.
Bestehendes Live-System und HAOS-Planung bleiben ausserhalb dieses Tests.
Keine realen Slices, Jobs, Uploads oder Druckerbefehle.

Paketbytes, Herkunftsmarkierungen und Lizenzhinweise bleiben unveraendert.
Die Bereichslizenz gilt ausschliesslich im definierten Umfang. Die offene
Public-Rechtepruefung wird durch die private Sicherung nicht als erledigt
markiert. Private Checkpoints, Brain-Daten, Hostdetails, Zugangsdaten und
Engine-Binaerdateien gehoeren nicht in dieses Repository.
