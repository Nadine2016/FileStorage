---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-18"

---
{:new_window: target="_blank"}

# Häufig gestellte Fragen

## Wie lässt sich erkennen, welche der {{site.data.keyword.filestorage_short}}-Datenträger verschlüsselt sind?
Zeigen Sie die Liste Ihrer {{site.data.keyword.filestorage_short}}-Instanzen im Kundenportal an. Bei verschlüsselten Datenträgern steht rechts vom LUN-/Datenträgernamen ein Sperrsymbol.

## Kann ich meinen {{site.data.keyword.filestorage_short}}-Speicher verschlüsseln, wenn ich nicht verschlüsselten {{site.data.keyword.filestorage_short}}-Speicher in einem Rechenzentrum erworben habe, das für die Verschlüsselung aktualisiert wurde?
{{site.data.keyword.filestorage_short}}-Speicher, der vor der Aktualisierung eines Rechenzentrums bereitgestellt wurde, kann nicht verschlüsselt werden. Neuer {{site.data.keyword.filestorage_short}}-Speicher, der in aktualisierten Rechenzentren bereitgestellt wird, ist automatisch verschlüsselt. Es gibt keine auswählbare Einstellung für die Verschlüsselung, sie erfolgt automatisch. Daten im nicht verschlüsselten Speicher können verschlüsselt werden, indem ein neuer Datenträger erstellt wird und die Daten mithilfe der hostbasierten Migration auf den neuen verschlüsselten Datenträger kopiert werden. Weitere Informationen finden Sie im Abschnitt [File Storage migrieren](/docs/infrastructure/FileStorage/migrate-file-storage-encrypted-file-storage.html).

## Wie lässt sich erkennen, ob {{site.data.keyword.filestorage_short}} in einem aktualisierten Rechenzentrum bereitgestellt wird?
Im {{site.data.keyword.filestorage_short}}-Bestellformular sind alle aktualisierten Rechenzentren mit einem Stern (`*`) gekennzeichnet. Während des Bestellablaufs erhalten Sie eine Meldung des Inhalts, dass Sie Speicher mit Verschlüsselung erwerben. Wird der Speicher bereitgestellt, gibt ein Symbol in der Speicherliste an, dass der Datenträger verschlüsselt ist. 

Alle verschlüsselten Datenträger und gemeinsam genutzten Dateispeicher werden nur in aktualisierten Rechenzentren bereitgestellt. Eine vollständige Liste der aktualisierten Rechenzentren und der verfügbaren Features finden Sie [hier](/docs//infrastructure/BlockStorage/new-ibm-block-and-file-storage-location-and-features.html).

## Warum kann {{site.data.keyword.filestorage_short}} mit einer Endurance-Stufe von 10 IOPS in einigen Rechenzentren bereitgestellt werden, in anderen jedoch nicht?
Der {{site.data.keyword.filestorage_short}}-Typ Endurance mit der 10 IOPS/GB-Stufe ist nur in ausgewählten Rechenzentren verfügbar. Weitere Rechenzentren werden in Kürze hinzugefügt. Eine vollständige Liste der aktualisierten Rechenzentren und der verfügbaren Features finden Sie [hier](/docs//infrastructure/BlockStorage/new-ibm-block-and-file-storage-location-and-features.html).

## Wie wird der richtige Mountpunkt für den eigenen {{site.data.keyword.filestorage_short}}-Speicher ermittelt?
Alle verschlüsselten {{site.data.keyword.filestorage_short}}-Datenträger, die in den erweiterten Rechenzentren bereitgestellt werden, haben einen anderen Mountpunkt als nicht verschlüsselte Datenträger. Um sicherzustellen, dass Sie den richtigen Mountpunkt verwenden, zeigen Sie die Mountpunktinformationen auf der Seite **Datenträgerdetails** in der Benutzerschnittstelle an. Sie können auch über einen API-Aufruf auf den richtigen Mountpunkt zugreifen: `SoftLayer_Network_Storage::getNetworkMountAddress()`.

## Wie viele Datenträger können bereitgestellt werden?
Sie können standardmäßig eine kombinierte Gesamtzahl von 250 Block- und Dateispeicherdatenträger bereitstellen. Wenden Sie sich an Ihren Vertriebsbeauftragten, wenn Sie Ihren Grenzwert erhöhen möchten. Weitere Informationen finden Sie in [Speichergrenzwerte verwalten](managing-storage-limits.html).

## Wie viele Instanzen können einen bereitgestellten {{site.data.keyword.filestorage_short}}-Datenträger gemeinsam nutzen?
Die Standardbegrenzung für die Anzahl von Autorisierungen pro Datenträger ist 64. Wenden Sie sich an Ihren Vertriebsbeauftragten, wenn Sie diesen Grenzwert erhöhen möchten.

## Wie viele {{site.data.keyword.filestorage_short}}-Datenträger können einem einzelnen Host zugeordnet werden?
Dies ist abhängig von Kapazität des Hostbetriebssystems, nicht von {{site.data.keyword.BluSoftlayer_full}}-Grenzwerten. Die Dokumentation des jeweiligen Betriebssystems enthält Informationen zu den Grenzwerten für die Anzahl der gemeinsam genutzten Dateisysteme, die angehängt werden können.

## Wie viele gemeinsam genutzte Dateisysteme sind pro Dateidatenträgergröße zulässig? Wie viele gemeinsam genutzte Dateisysteme sind pro Datenträgergröße maximal zulässig?

<table>
  <caption>Tabelle 1 zeigt die maximale Anzahl von zulässigen I-Nodes auf der Basis der Datenträgergröße. Die Datenträgergrößen sind in der linken Spalte aufgeführt. Die Anzahl der I-Nodes/gemeinsam genutzten Dateispeicher steht auf der rechten Seite.</caption>
  <thead>
    <tr>
      <th>Datenträgergröße</th>
      <th>I-Nodes/gemeinsam genutzte Dateispeicher</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>20 GB - 39 GB</td>
      <td>622.484</td>
    </tr>
    <tr>
      <td>40 GB - 79 GB</td>
      <td>1.245.084</td>
    </tr>          
    <tr>
      <td>80 GB - 99 GB</td>
      <td>2.490.263</td>
    </tr>          
    <tr>
      <td>100 GB - 249 GB</td>
      <td>3.112.863</td>
    </tr>          
    <tr>
      <td>250 GB - 499 GB</td>
      <td>7.782.300</td>
    </tr>          
    <tr>
      <td>500 GB - 999 GB</td>
      <td>15.564.695</td>
    </tr>
    <tr>
      <td>1 TB</td>
      <td>31.876.593</td>
    </tr>
    <tr>
      <td>2 TB</td>
      <td>63.753.186</td>
    </tr>
    <tr>
      <td>3 TB</td>
      <td>95.629.970</td>
    </tr>
    <tr>
      <td>4 TB - 12 TB</td>
      <td>127.506.359</td>
    </tr>
   </tbody>
</table>

## IOPS messen
E/A-Operationen pro Sekunde werden auf der Basis einen Belastungsprofils von 16-KB-Blöcken mit 50 Prozent Zufallsleseoperationen und 50 Prozent Zufallsschreiboperationen gemessen. Workloads, die von diesem Profil abweichen, erreichen möglicherweise eine schlechte Leistung.

## Was geschieht, wenn die Leistung mit einer kleineren Blockgröße gemessen wird?
Ein Maximum an E/A-Operationen pro Sekunde kann auch bei Verwendung kleinerer Blockgrößen erreicht werden. Allerdings wird der Durchsatz in diesem Fall geringer. Ein Datenträger mit 6000 IOPS hat bei verschiedenen Blockgrößen zum Beispiel den folgenden Durchsatz:

- 16 KB * 6000 IOPS == ~93,75 MB/Sek
- 8 KB * 6000 IOPS == ~46,88 MB/Sek
- 4 KB * 6000 IOPS == ~23,44 MB/Sek


## Werden die zugeordneten E/A-Operationen pro Sekunde auf Instanz- oder Datenträgerebene umgesetzt?
Die E/A-Operationen pro Sekunde (IOPS) werden auf Datenträgerebene umgesetzt. Mit anderen Worten, zwei Hosts, die mit einem Datenträger mit 6000 IOPS verbunden sind, nutzen diese 6000 IOPS gemeinsam.

## Benötigt der Datenträger zuvor eine Einlaufphase, um den erwarteten Durchsatz zu erzielen?
Ein Einlaufen des Datenträgers ist nicht erforderlich. Sie verfügen sofort nach Bereitstellung des Datenträgers über den angegebenen Durchsatz.

## Kann ein höherer Durchsatz erzielt werden, wenn eine schnellere Ethernet-Verbindung verwendet wird?
Durchsatzbegrenzungen werden auf Datenträger- bzw. LUN-Ebene festgelegt. Daher führt die Verwendung einer schnelleren Ethernet-Verbindung nicht zu einer Erhöhung dieser Begrenzung. Bei einer langsameren Ethernet-Verbindung kann Ihre Bandbreite allerdings einen Engpass verursachen.

## Wirken sich Firewalls/Sicherheitsgruppen auf die Leistung aus?
Es ist am besten, den Speicherdatenverkehr über ein VLAN zu leiten, das die Firewall umgeht. Wenn der Speicherdatenverkehr über Software-Firewalls geleitet wird, erhöht sich dadurch die Latenz und die Speicherleistung wird beeinträchtigt.

## Welche Leistungslatenz ist von {{site.data.keyword.filestorage_short}}-Speicher zu erwarten?   
Die Ziellatenz innerhalb des Speichers beträgt < 1 ms. File Storage-Speicher wird mit Compute-Instanzen in einem gemeinsam genutzten Netz verbunden, sodass die genaue Leistungslatenz vom Netzverkehr während der Operation abhängig ist.

## Was geschieht mit den Daten, wenn {{site.data.keyword.filestorage_short}}-Datenträger gelöscht werden?
{{site.data.keyword.filestorage_full}} stellt den Kunden gemeinsam genutzte Dateien auf physischem Speicher bereit, der vor der Wiederverwendung bereinigt wird. Kunden mit bestimmten Compliance-Anforderungen, z. B. hinsichtlich der Einhaltung der NIST 800-88-Richtlinien für das sichere Löschen von Datenträgern, müssen die entsprechende Bereinigungsprozedur durchführen, bevor sie den Speicher löschen.

## Was passiert mit den Laufwerken, die über das Cloud-Rechenzentrum außer Betrieb gesetzt werden?
Wenn Laufwerke außer Betrieb gesetzt werden, werden sie vor dem Entsorgen durch IBM zerstört. Die Laufwerke werden unbrauchbar. Auf Daten, die auf diesem Laufwerk gespeichert waren, kann nicht mehr zugegriffen werden.
