---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-26"

---
{:new_window: target="_blank"}


# Gestion de {{site.data.keyword.filestorage_short}}

Vous pouvez gérer vos volumes {{site.data.keyword.filestorage_full}} via le portail {{site.data.keyword.slportal}}.

## Autorisation des hôtes pour l'accès à {{site.data.keyword.filestorage_short}}

Les hôtes "autorisés" sont des hôtes auxquels des droits d'accès à un volume spécifique ont été accordés. Sans autorisation d'hôte, vous ne pouvez pas accéder au stockage ni l'utiliser depuis votre système. L'autorisation d'un hôte pour l'accès à votre volume génère le nom d'utilisateur et le mot de passe. 

**Remarque** : vous pouvez autoriser et connecter des hôtes qui se trouvent dans le même centre de données que votre stockage. Néanmoins, si vous disposez de plusieurs comptes, vous ne pouvez pas autoriser un hôte d'un autre compte à accéder à votre stockage sur un autre compte. 

1. Cliquez sur **Stockage** > **{{site.data.keyword.filestorage_short}}**, puis sur **Nom de volume**.
2. Faites défiler l'écran jusqu'à la section **Hôtes autorisés** de la page.
3. Cliquez sur **Hôte autorisé** sur le côté droit. Sélectionnez les hôtes qui peuvent accéder à ce volume en particulier.
 

## Affichage de la liste des hôtes autorisés à accéder à un volume {{site.data.keyword.filestorage_short}}

1. Cliquez sur **Stockage > {{site.data.keyword.filestorage_short}}**, puis sur **Nom du volume**.
2. Faites défiler la page jusqu'à la section **Hôtes autorisés**.

Cette section affiche la liste des hôtes actuellement autorisés à accéder au volume.


## Affichage des volumes {{site.data.keyword.filestorage_short}} auxquels un hôte est autorisé à accéder

Vous pouvez afficher les volumes auxquels un hôte peut accéder, y compris les informations nécessaires pour l'établissement d'une connexion (Nom du volume, Type de stockage, Adresse cible, Capacité et Emplacement).

1. Cliquez sur **Unités** > **Liste des unités** dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Cliquez sur l'unité appropriée.
2. Sélectionnez l'onglet Stockage.

La liste des volumes de stockage auxquels cet hôte particulier a accès s'affiche (les volumes sont regroupés par type de stockage : bloc, fichier, autre). Les menus **Action** respectifs vous permettent d'autoriser davantage de stockage ou de retirer l'accès.


## Montage et démontage de {{site.data.keyword.filestorage_short}}

Vous pouvez vous reporter aux informations relatives aux points de montage fournies dans la vue ** Détails du volume** pour monter {{site.data.keyword.filestorage_short}} à partir d'un hôte. Voir [Accès à {{site.data.keyword.filestorage_short}} sur Linux](accessing-file-storage-linux.html).


## Révocation de l'accès d'un hôte à {{site.data.keyword.filestorage_short}}

Si vous souhaitez ne plus autoriser un hôte à accéder à un volume de stockage en particulier, vous pouvez révoquer l'accès. Lorsque l'accès est révoqué, la connexion à l'hôte est retirée du volume. Le système d'exploitation et les applications ne peuvent plus communiquer avec le volume. 

**Remarque** : pour éviter les problèmes côté hôte, démontez le volume de stockage de votre système d'exploitation avant de révoquer l'accès afin de prévenir tout incident lié à des unités manquantes ou à l'altération des données.

Vous pouvez révoquer l'accès à partir de Stockage dans la Liste des unités ou dans les vues Stockage.

### Révocation de l'accès à partir de la liste des unités

1. Cliquez sur **Unités** > **Liste des unités** dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. 
2. Cliquez deux fois sur l'unité appropriée.
3. Sélectionnez l'onglet **Stockage**.
4. La liste des volumes de stockage auxquels cet hôte particulier a accès s'affiche (les volumes sont regroupés par type de stockage : bloc, fichier, autre). Sélectionnez le menu **Action** adéquat en regard du volume pour lequel vous souhaitez révoquer l'accès et cliquez sur **Révoquer le droit d'accès**.
5. Confirmez que vous souhaitez révoquer l'accès à un volume car cette action ne peut pas être annulée. Cliquez sur **Oui** pour révoquer l'accès au volume ou sur **Non** pour annuler l'action.

**Remarque** : si vous souhaitez déconnecter plusieurs volumes d'un hôte spécifique, vous devez répéter l'action Révoquer le droit d'accès pour chaque volume.

 

### Révocation de l'accès à partir de la vue Stockage

1. Cliquez sur **Stockage, {{site.data.keyword.filestorage_short}}** et sélectionnez le **Volume** pour lequel vous souhaitez révoquer l'accès.
2. Faites défiler l'écran jusqu'à la section **Hôtes autorisés** de la page.
3. Cliquez sur **Actions** en regard de l'hôte dont l'accès doit être révoqué et sélectionnez **Révoquer le droit d'accès**.
4. Confirmez que vous souhaitez révoquer l'accès à un volume car cette action ne peut pas être annulée. Cliquez sur **Oui** pour révoquer l'accès au volume ou sur **Non** pour annuler l'action.

**Remarque :** si vous souhaitez déconnecter plusieurs hôtes d'un volume spécifique, vous devez répéter l'action Révoquer le droit d'accès pour chaque hôte.
 

## Annulation d'un volume de stockage

Si vous n'avez plus besoin d'un volume spécifique, vous pouvez l'annuler. Pour ce faire, vous devez d'abord révoquer l'accès à partir de tous les hôtes.

1. Cliquez sur **Stockage**>**{{site.data.keyword.filestorage_short}}**.
2. Cliquez sur **Actions** correspondant au volume à annuler et sélectionnez **Annuler {{site.data.keyword.filestorage_short}}**.
3. Confirmez l'annulation du volume de manière immédiate ou à la date anniversaire de la mise à disposition du volume.
   >**Remarque** : si vous sélectionnez l'option d'annulation du volume à sa date anniversaire, vous pouvez annuler la demande d'annulation avant la date anniversaire.
4. Cliquez sur **Continuer** ou sur **Fermer**. 
5. Cochez la case d'accusé de réception et cliquez sur **Confirmer**.
