---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-12"

---
{:new_window: target="_blank"}

# Ajustement des IOPS (opérations d'entrée-sortie par seconde)

Cette nouvelle fonctionnalité permet aux utilisateurs du stockage {{site.data.keyword.filestorage_full}} d'ajuster immédiatement les IOPS de leur {{site.data.keyword.filestorage_short}} existant. Ils n'ont pas besoin de créer un doublon ou de copier manuellement les données vers un nouveau stockage. Les utilisateurs ne sont confrontés à aucune indisponibilité, ni manque d'accès au stockage lorsque l'ajustement a lieu.

La facturation du stockage est mise à jour : la différence calculée au prorata du nouveau prix est ajoutée au cycle de facturation en cours. Le nouveau montant total est facturé dans le cycle de facturation suivant.


## Avantage des IOPS ajustables+

- Gestion des coûts : certains clients ont besoin d'un nombre élevé d'IOPS uniquement pendant les pics d'utilisation. Par exemple, un grand magasin de détail connaît un pic d'utilisation pendant les jours fériés et peut alors souhaiter bénéficier d'un nombre d'IOPS plus élevé sur son stockage que par rapport au milieu de l'été. Cette fonctionnalité lui permet de gérer ses coûts et de payer pour un nombre d'IOPS plus élevé uniquement en cas de besoin.

## Limitations

Cette fonctionnalité est disponible uniquement dans des [centres de données sélectionnés](new-ibm-block-and-file-storage-location-and-features.html).

Les clients ne peuvent pas basculer entre les volumes Endurance et Performance lorsqu'ils ajustent leurs IOPS. Les utilisateurs peuvent indiquer un nouveau niveau d'IOPS pour leur stockage en fonction des restrictions/critères suivants :

- Si le volume d'origine est de type Endurance avec un niveau de 0,25, il n'est pas possible de le mettre à jour.
- Si le volume d'origine est de type Performance avec un niveau inférieur ou égal à 0,30 IOPS/Go, les options disponibles incluent uniquement les combinaisons de taille et d'IOPS qui génèrent un niveau inférieur ou égal à 0,30 IOPS/Go.
- Si le volume d'origine est de type Performance avec un niveau supérieur à 0,30 IOPS/Go, les options disponibles incluent uniquement les combinaisons de taille et d'IOPS qui génèrent un niveau supérieur à 0,30 IOPS/Go.

## Effet de l'ajustement des IOPS sur la réplication

Si la réplication est activée sur le volume, la réplique est automatiquement mise à jour afin de correspondre à la sélection des IOPS du volume principal.

## Ajustement des IOPS sur votre stockage

1. Accédez à votre liste de {{site.data.keyword.filestorage_short}}
    - A partir du portail client, cliquez sur **Storage** > **{{site.data.keyword.filestorage_short}}** OU
    - A partir du catalogue {{site.data.keyword.BluSoftlayer_full}}, cliquez sur **Infrastructure** > **Stockage** > **{{site.data.keyword.filestorage_short}}**.
2. Sélectionnez le volume dans la liste et cliquez sur **Actions** > **Modifier le volume**
3. Sous les options d'IOPS de stockage, effectuez une nouvelle sélection :
    - Endurance (IOPS hiérarchisées) : sélectionnez un niveau d'IOPS supérieur à 0,25 IOPS/Go de votre stockage. Vous pouvez augmenter le niveau d'IOPS à tout moment. Toutefois, vous ne pouvez le diminuer qu'une seule fois par mois.
    - Performance (IOPS allouées) : indiquez la nouvelle option d'IOPS pour votre stockage en saisissant une valeur comprise entre 100 et 48 000 IOPS. (Prenez soin de tenir compte des limites spécifiques requises par la taille dans le formulaire de commande.)
4. Vérifiez votre sélection et la nouvelle tarification.
5. Cochez la case **J'ai lu et j'accepte l'intégralité du Contrat cadre de service**, puis cliquez sur **Valider la commande**.
6. Votre nouvelle allocation de stockage est disponible en quelques minutes.
