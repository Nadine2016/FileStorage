---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-17"

---
{:new_window: target="_blank"}


# Snapshots verwalten

## Snapshotzeitplan erstellen

Durch Erstellen von Snapshotzeitplänen können Sie entscheiden, wie häufig und wann Sie eine zeitpunktbasierte Referenz des Speicherdatenträgers erstellen wollen. Es können maximal 50 Snapshots pro Speicherdatenträger erstellt werden. Zeitpläne werden über die Registerkarte **Speicher** > **{{site.data.keyword.filestorage_short}}** im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} verwaltet.


Bevor Sie Ihren ersten Zeitplan einrichten können, müssen Sie zunächst Snapshotbereich kaufen, sofern Sie diesen nicht bei der Erstbereitstellung des Speicherdatenträgers gekauft haben.

### Snapshotzeitplan hinzufügen

Snapshotzeitpläne können für stündliche, tägliche und wöchentliche Intervalle jeweils mit einem eigenen Aufbewahrungszyklus eingerichtet werden. Pro Speicherdatenträger besteht ein Grenzwert von maximal 50 geplanten (dies kann eine Mischung aus stündlichen, täglichen und wöchentlichen Zeitplänen sein) und manuellen Snapshots.

1. Klicken Sie auf Ihren Speicherdatenträger, klicken Sie auf **Aktionen** und klicken Sie auf die Option **Snapshot planen**.
2. Im Fenster für den neuen Snapshotzeitplan können Sie aus drei verschiedenen Snapshothäufigkeiten wählen. Sie können eine beliebige Kombination aus diesen drei verwenden, um einen umfassenden Snapshotzeitplan zu erstellen.
   - Stündlich
      - Geben Sie die Minute an, in der ein Snapshot stündlich ausgeführt werden soll. Der Standardwert ist die aktuelle Minute.
      - Geben Sie die Anzahl der stündlichen Snapshots an, die aufbewahrt werden sollen, bevor der älteste Snapshot gelöscht wird.
   - Täglich
      - Geben Sie die Stunde und die Minute an, in der ein Snapshot ausgeführt werden soll. Der Standardwert ist die aktuelle Stunde und Minute.
      - Wählen Sie die Anzahl der stündlichen Snapshots aus, die aufbewahrt werden sollen, bevor der älteste Snapshot gelöscht wird.
   - Wöchentlich
      - Geben Sie den Wochentag, die Stunde und die Minute des Zeitpunkts an, zu dem ein Snapshot ausgeführt werden soll. Der Standardwert ist der aktuelle Zeitpunkt (Tag, Stunde und Minute).
      - Wählen Sie die Anzahl der wöchentlichen Snapshots aus, die aufbewahrt werden sollen, bevor der älteste Snapshot gelöscht wird.
3. Klicken Sie auf **Speichern** und erstellen Sie einen weiteren Zeitplan mit einer anderen Häufigkeit. Wenn die Gesamtzahl der geplanten Snapshots 50 übersteigt, erhalten Sie eine Warnnachricht und können nicht speichern.

Die Liste der Snapshots wird in der Reihenfolge ihrer Ausführung im Abschnitt **Snapshots** der Seite **Detail** angezeigt.

## Manuellen Snapshot erstellen

Manuelle Snapshots können an verschiedenen Punkten während eines Anwendungsupgrades oder einer Wartungsoperation erfasst werden. Darüber hinaus können Sie Snapshots serverübergreifend für mehrere Server erstellen, die auf der Anwendungsebene vorübergehend inaktiviert wurden.

Die Anzahl manueller Snapshots ist auf maximal 50 pro Speicherdatenträger begrenzt.

1. Klicken Sie auf Ihren Speicherdatenträger.
2. Klicken Sie auf **Aktionen**.
3. Klicken Sie auf **Manuellen Snapshot erstellen**.
Der Snapshot wird erstellt und im Abschnitt **Snapshots** der Seite **Detail** angezeigt. Als Zeitplanangabe wird 'Manuell' angezeigt.

## Alle Snapshots mit Informationen zum belegten Speicherbereich und mit Managementfunktionen auflisten

Eine Liste der aufbewahrten Snapshots und des belegten Speicherbereichs wird auf der Seite **Detail** (**Speicher** > **{{site.data.keyword.filestorage_short}}**) angezeigt. Managementfunktionen (Zeitplanbearbeitung und Hinzufügen weiteren Speicherbereichs) werden auf der Seite 'Details' über das Menü **Aktionen** oder über Links in den verschiedenen Abschnitten der Seite ausgeführt.

## Liste der aufbewahrten Snapshots anzeigen

Die Anzahl der aufbewahrten Snapshots richtet sich nach dem Wert, den Sie in das Feld **Letzte behalten** bei der Einrichtung Ihrer Zeitpläne eingegeben haben. Die Snapshots, die erfasst wurden, werden im Abschnitt **Snapshot** angezeigt. Die Snapshots werden nach Zeitplan aufgelistet.

## Menge des belegten Speicherbereichs anzeigen

Das Kreisdiagramm oben auf der Seite **Details** zeigt an, wie viel Speicherbereich belegt ist und wie viel Speicherbereich noch verfügbar ist. Sie empfangen Benachrichtigungen, wenn Schwellenwerte für die Speicherbelegung erreicht werden – bei 75 Prozent, 90 Prozent und 95 Prozent.

## Menge des Snapshotbereichs für einen Datenträger ändern

Sie müssen einem Datenträger, der zuvor keinen Snapshotbereich hatte oder zusätzlichen Snapshotbereich benötigt, möglicherweise Snapshotbereich hinzufügen. Sie können je nach Bedarf zwischen 5 GB und 4.000 GB hinzufügen. 

**Anmerkung**: Snapshotbereich kann nur vergrößert werden. Es kann nicht verringert werden. Sie können zunächst einen kleinere Speichergröße auswählen, bis Sie ermittelt haben, wie viel Speicherbereich Sie tatsächlich benötigen. Beachten Sie, dass automatisierte und manuelle Snapshots den Speicherbereich gemeinsam nutzen.

Der Snapshotbereich wird über **Speicher** > **{{site.data.keyword.filestorage_short}}** geändert.

1. Klicken Sie auf Ihren Speicherdatenträger, klicken Sie auf **Aktionen** und klicken Sie auf die Option **Snapshot planen**.
2. Wählen Sie in der Eingabeaufforderung unter eine Reihe von Größe die gewünschte Größe aus. Größen reichen in der Regel von 0 bis zur Größe Ihres Datenträgers.
3. Klicken Sie auf **Weiter**.
4. Geben Sie einen Werbeaktionscode ein, wenn Sie einen haben, und klicken Sie auf **Neu berechnen**. Die Felder 'Gebühren für diese Bestellung' und 'Bestellprüfung' sind standardmäßig ausgefüllt.
5. Klicken Sie auf das Kontrollkästchen **Ich habe die Rahmenvereinbarung gelesen** und klicken Sie auf **Bestellung abschicken**. Der zusätzliche Snapshotbereich wird innerhalb weniger Minuten bereitgestellt.

## Benachrichtigungen empfangen, wenn der Grenzwert für den Snapshotbereich erreicht ist und Snapshots gelöscht werden

Über Support-Tickets werden Benachrichtigungen an den Masterbenutzer auf Ihr Konto gesendet, wenn drei verschiedene Speicherschwellenwerte erreicht werden – 75 Prozent, 90 Prozent und 95 Prozent.

- **75 Prozent der Kapazität**: Eine Warnung wird gesendet, dass die Belegung des Snapshotbereichs 75 Prozent überschritten hat. Wenn Sie auf die Warnung reagieren und Speicherbereich manuell hinzufügen oder aufbewahrte und unnötige Snapshots löschen, wird die Aktion vermerkt und das Ticket geschlossen. Wenn Sie nichts unternehmen, müssen Sie das Ticket manuell bestätigen und es wird anschließend geschlossen.
- **90 Prozent der Kapazität**: Eine zweite Warnung wird gesendet, wenn die Belegung des Snapshotbereichs 90 Prozent überschritten hat. Wie bei Erreichen von 75 Prozent der Kapazität gilt auch hier: Wenn Sie die erforderlichen Aktionen ausführen, mit denen die Belegung des Speicherbereichs verringert wird, wird die Aktion vermerkt und das Ticket geschlossen. Wenn Sie nichts unternehmen, müssen Sie das Ticket manuell bestätigen und es wird anschließend geschlossen.
- **95 Prozent der Kapazität**: Eine letzte Warnung wird gesendet. Wenn keine Aktion ausgeführt wird, um die Speicherbelegung unter den Schwellenwert zu senken, wird eine Benachrichtigung generiert und eine automatische Löschung durchgeführt, sodass zukünftige Snapshots erstellt werden können. Geplante Snapshots werden gelöscht, beginnend mit dem ältesten, bis die Belegung unter 95 Prozent liegt. Wenn die Belegung 95 Prozent überschreitet, werden Snapshots so lange gelöscht, bis die Belegung unter dem Schwellenwert liegt. Wenn der Speicherbereich manuell vergrößert oder Snapshots gelöscht werden, wird die Warnung zurückgesetzt und erneut ausgegeben, wenn der Schwellenwert wieder überschritten wird. Wenn keine Aktion ausgeführt wird, ist diese Benachrichtigung die einzige Warnung, die Sie empfangen.

## Snapshotzeitplan löschen

Snapshotzeitpläne können über **Speicher** > **{{site.data.keyword.filestorage_short}}** gelöscht werden.

1. Klicken Sie im Feld **Snapshotpläne** auf der Seite **Details** auf den zu löschenden Zeitplan.
2. Klicken Sie auf das Kontrollkästchen neben dem zu löschenden Zeitplan und klicken Sie auf **Speichern**.<br />
**Vorsicht**: Wenn Sie die Replikationsfunktion verwenden, müssen Sie sicherstellen, dass der Zeitplan, den Sie löschen, nicht der von der Replikation verwendete Zeitplan ist. Klicken Sie [hier](replication.html), um weitere Informationen zum Löschen eines Replikationsplans zu erhalten.

## Snapshot löschen

Snapshots, die nicht mehr benötigt werden, können manuell entfernt werden, um Speicherplatz für zukünftige Snapshots freizugeben. Das Löschen erfolgt über **Speicher** > **{{site.data.keyword.filestorage_short}}**.

1. Klicken Sie auf Ihren Speicherdatenträger und blättern Sie zum Abschnitt **Snapshot**, um die Liste der vorhandenen Snapshots anzuzeigen.
2. Klicken Sie neben dem gewünschten Snapshot auf **Aktionen** und klicken Sie auf **Löschen**, um den Snapshot zu löschen. Diese Löschung hat keine Auswirkung auf zukünftige oder frühere Snapshots im selben Zeitplan, da zwischen Snapshots keine Abhängigkeit besteht.

Manuelle Snapshots, die nicht mit der oben beschriebenen Methode gelöscht werden, werden automatisch (älteste zuerst) gelöscht, wenn Sie den Grenzwert des Speicherbereichs erreichen.

## Speicherdatenträger mithilfe eines Snapshots auf dem Stand eines bestimmten Zeitpunkts wiederherstellen

Es ist möglich, dass Sie Ihren Speicherdatenträger aufgrund eines Benutzerfehlers oder einer Datenbeschädigung auf einen bestimmten Zeitpunkt zurücksetzen müssen.

1. Hängen Sie Ihren Speicherdatenträger vom Host ab und trennen Sie die Verbindung.
   - Klicken Sie hier [hier](accessing-file-storage-linux.html), um weitere Anweisungen für {{site.data.keyword.filestorage_short}} unter Linux anzuzeigen.
2. Klicken Sie auf **Speicher** > **{{site.data.keyword.filestorage_short}}** im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Blättern Sie nach unten und klicken Sie auf den Datenträger, der wiederhergestellt werden soll. Im Abschnitt **Snapshots** der Seite **Detail** wird die Liste aller gespeicherten Snapshots mit Angabe ihrer Größe und ihres Erstellungsdatums angezeigt.
4. Klicken Sie neben dem zu verwendenden Snapshot auf **Aktionen** und klicken Sie auf **Wiederherstellen**. <br/>
   >**Anmerkung**: Bei der Wiederherstellung gehen die Daten verloren, die nach der Erstellung des Snapshots erstellt oder geändert wurden. Dieser Datenverlust passiert, weil Ihr Speicherdatenträger in denselben Zustand wiederherstellt wird, den er zum Zeitpunkt der Snapshoterstellung hatte. 
5. Klicken Sie auf **Ja**, um die Wiederherstellung zu starten. Quer über den oberen Bereich der Seite wird die Nachricht angezeigt, dass der Datenträger mit dem ausgewählten Snapshot wiederhergestellt wird. Darüber hinaus wird neben Ihrem Datenträger auf der {{site.data.keyword.filestorage_short}}-Seite ein Symbol angezeigt, das darauf hinweist, dass zurzeit eine Transaktion aktiv ist. Bei Bewegen des Mauszeigers über das Symbol wird die Transaktion in einem Fenster angezeigt. Das Symbol wird ausgeblendet, sobald die Transaktion abgeschlossen ist.
6. Hängen Sie Ihren Speicherdatenträger an den Host an und ordnen Sie ihn erneut zu.
  - Klicken Sie hier [hier](accessing-file-storage-linux.html), um weitere Anweisungen für {{site.data.keyword.filestorage_short}} unter Linux anzuzeigen.
    
>**Hinweis** - Beim Zurücksetzen eines Datenträgers werden alle Snapshots gelöscht, die nach dem für das Zurücksetzen verwendeten Snapshot erstellt wurden.
