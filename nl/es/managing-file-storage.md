---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-26"

---
{:new_window: target="_blank"}


# Gestión de {{site.data.keyword.filestorage_short}}

Puede gestionar los volúmenes de {{site.data.keyword.filestorage_full}} mediante el {{site.data.keyword.slportal}}.

## Autorización de hosts para acceder a {{site.data.keyword.filestorage_short}}

Los hosts “autorizados” son los hosts a los que se les ha otorgado acceso a un volumen determinado. Sin la autorización del host, no puede acceder ni utilizar el almacenamiento de su sistema. El hecho de autorizar a un host el acceso al volumen genera un nombre de usuario y una contraseña. 

**Nota**: Puede autorizar y conectar hosts que estén ubicados en el mismo centro de datos que su almacenamiento. No obstante, si tiene varias cuentas, no puede autorizar a un host de una cuenta a que acceda a su almacenamiento en otra cuenta. 

1. Pulse **Almacenamiento** > **{{site.data.keyword.filestorage_short}}** y pulse el **Nombre de volumen**.
2. Desplácese a la sección **Hosts autorizados** de la página.
3. Pulse **Autorizar host** en la parte derecha. Seleccione los hosts que pueden acceder a ese volumen determinado.
 

## Visualización de la lista de hosts que están autorizados para acceder a un volumen de {{site.data.keyword.filestorage_short}}

1. Pulse **Almacenamiento > {{site.data.keyword.filestorage_short}}** y pulse el **Nombre de volumen**.
2. Desplácese en la página hasta la sección **Hosts autorizados**.

Aquí puede ver la lista de hosts, que actualmente tienen autorización para acceder al volumen.


## Visualización de los volúmenes de {{site.data.keyword.filestorage_short}} a los cuales un host está autorizado

Puede ver los volúmenes a los cuales un host tiene acceso, incluyendo la información necesaria para realizar una conexión: nombre de volumen, tipo de almacenamiento, dirección de destino, capacidad y ubicación.

1. Pulse **Dispositivos** > **Lista de dispositivos** desde el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Pulse el dispositivo adecuado.
2. Seleccione el separador Almacenamiento.

Se le presenta una lista de los volúmenes de almacenamiento a los cuales este host tiene acceso, todos están agrupados por tipo de almacenamiento (bloque, archivo, otros). Desde los menús respectivos de **Acción**, puede autorizar almacenamiento adicional o eliminar el acceso.


## Montaje y desmontaje de {{site.data.keyword.filestorage_short}}

Puede utilizar la información de punto de montaje proporcionada en la vista **Detalles del volumen** para montar {{site.data.keyword.filestorage_short}} desde un host. Consulte [Acceso a {{site.data.keyword.filestorage_short}} en Linux](accessing-file-storage-linux.html)


## Revocación del acceso de un host a {{site.data.keyword.filestorage_short}}

Si quiere detener el acceso desde un host a un volumen de almacenamiento determinado, puede revocar el acceso. Cuando se revoca el acceso, la conexión de host se descarta del volumen. El sistema operativo y las aplicaciones ya no se pueden comunicar con el volumen. 

**Nota**: Para impedir problemas del lado del host, desmonte el volumen de almacenamiento desde el sistema operativo antes de revocar el acceso para evitar perder unidades o corrupción de datos.

Puede revocar el acceso desde el Almacenamiento de la Lista de Dispositivos o desde las vistas de almacenamiento.

### Revocación del acceso de la lista de dispositivos

1. Pulse **Dispositivos** > **Lista de dispositivos** desde el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. 
2. Efectúe una doble pulsación en el dispositivo adecuado.
3. Seleccione el separador **Almacenamiento**.
4. Se le presenta una lista de los volúmenes de almacenamiento a los cuales este host tiene acceso, todos agrupados por tipo de almacenamiento (bloque, archivo, otros). Seleccione el menú respectivo de **Acción** situado junto al volumen del que desea revocar el acceso y pulse **Revocar acceso**.
5. Confirme si desea revocar el acceso al volumen, porque la acción no puede deshacerse. Pulse **Sí** para revocar el acceso al volumen o **No** para cancelar la acción.

**Nota**: Si desea desconectar varios volúmenes desde un host específico, debe repetir la acción Revocar acceso para cada volumen.

 

### Revocación del acceso de la vista de almacenamiento

1. Pulse **Almacenamiento, {{site.data.keyword.filestorage_short}}**, y seleccione el **Volumen** desde el cual desea revocar el acceso.
2. Desplácese a la sección **Hosts autorizados** de la página.
3. Pulse **Acciones** junto al host cuyo acceso se va a revocar y seleccione **Revocar acceso**.
4. Confirme si desea revocar el acceso al volumen, porque la acción no puede deshacerse. Pulse **Sí** para revocar el acceso al volumen o **No** para cancelar la acción.

**Nota**: Si desea desconectar varios hosts desde un host específico, debe repetir la acción Revocar acceso para cada host.
 

## Cancelación de un volumen de almacenamiento

Si ya no necesita un volumen específico, puede cancelarlo. Para cancelar un volumen de almacenamiento, primero debe revocar el acceso desde cualquier host.

1. Pulse **Almacenamiento**>**{{site.data.keyword.filestorage_short}}**.
2. Pulse **Acciones** del volumen que se va a cancelar y seleccione **Cancelar {{site.data.keyword.filestorage_short}}**.
3. Confirme si desea cancelar el volumen inmediatamente o en la fecha de aniversario en la que se suministró el volumen.
   >**Nota**: Si selecciona la opción de cancelar el volumen en su fecha de aniversario, puede anular la solicitud de cancelación antes de su fecha de aniversario.
4. Pulse **Continuar** o **Cerrar**. 
5. Marque el recuadro de selección de acuse de recibo y pulse **Confirmar**.
