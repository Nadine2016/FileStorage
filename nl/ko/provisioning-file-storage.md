---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-07"

---
{:new_window: target="_blank"}

# {{site.data.keyword.filestorage_short}} 주문

{{site.data.keyword.filestorage_short}}를 프로비저닝하고 자신의 용량 및 IOPS 요구사항에 맞게 이를 상세 조정할 수 있습니다. 성능을 지정하기 위한 두 가지 옵션을 사용하여 스토리지를 최대한으로 활용하십시오.

- 적절히 정의된 성능 요구사항이 없는 워크로드를 처리할 수 있도록 사전 정의된 성능 레벨을 제공하는 Endurance IOPS 계층을 선택할 수 있습니다. 
- Performance를 사용하여 총 IOPS 수를 지정함으로써 매우 구체적인 성능 요구사항을 만족시키도록 스토리지를 상세 조정할 수 있습니다.

## 사전 정의된 IOPS 계층을 사용하는 {{site.data.keyword.filestorage_short}} 주문(Endurance)

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에서 **스토리지** > **{{site.data.keyword.filestorage_short}}**를 클릭하거나 {{site.data.keyword.BluSoftlayer_full}} 카탈로그에서 **인프라** > **스토리지** > **{{site.data.keyword.filestorage_short}}**를 클릭하십시오.
2. 오른쪽 상단에서 **{{site.data.keyword.filestorage_short}} 주문**을 클릭하십시오.
3. 배치 **위치**(데이터 센터)를 선택하십시오.
   - 새 스토리지가 컴퓨팅 호스트 또는 보유한 호스트와 동일한 위치에 추가되었는지 확인하십시오.
4. 비용 청구 방식을 선택하십시오. 개선된 기능의 데이터 센터(*로 표기됨)를 선택한 경우 월별 또는 시간별 청구 중에 선택할 수 있습니다. 
     1. **시간별** 청구에서 파일 볼륨이 계정에 존재한 시간은 LUN이 삭제된 시점이나 청구 주기가 끝난 시점에 계산됩니다. 둘 중 먼저 발생하는 시점이 사용됩니다. 시간별 스토리지는 수 일간 또는 한달 이내에 사용되는 스토리지에 좋은 선택사항입니다. 시간별 청구는 [특정 데이터 센터](new-ibm-block-and-file-storage-location-and-features.html)에서 프로비저닝된 스토리지에만 사용 가능합니다. 
     2. **월별** 청구에서, 가격에 대한 계산은 작성 날짜로부터 청구 주기의 끝까지 비례 배분되며 즉각적으로 청구됩니다. 청구 주기가 끝나기 전에 파일 볼륨이 삭제되는 경우에는 환불이 되지 않습니다. 월별 청구는 장기간(한달 이상) 저장하고 액세스해야 하는 데이터를 사용하는 프로덕션 워크로드에서 사용되는 스토리지에 대해 좋은 선택사항입니다.
        >**참고** - 개선된 기능으로 업데이트되지 **않은** 데이터 센터에서 프로비저닝된 스토리지에는 기본적으로 월별 청구 유형이 사용됩니다.
5. **새 스토리지 크기** 필드에 스토리지 크기를 입력하십시오.
6. **스토리지 IOPS 옵션** 섹션에서 **Endurance(계층 IOPS)**를 선택하십시오.
7. 애플리케이션에서 필요로 하는 IOPS 계층을 선택하십시오.
    - **0.25IOPS/GB**는 I/O 집약도가 낮은 워크로드용으로 설계되었습니다. 이러한 워크로드는 일반적으로 대부분의 시간 동안 비활성 상태인 데이터를 많이 보유하는 것이 특성입니다. 적용되는 예에는 메일함 또는 부서 레벨 파일 공유의 저장이 포함되어 있습니다.
    - **2IOPS/GB**는 가장 일반적인 사용 용도로 설계되었습니다. 적용 예에는 하이퍼바이저용 가상 머신 디스크 이미지, 또는 웹 애플리케이션을 지원하는 소형 데이터베이스의 호스팅 등이 있습니다.
    - **4IOPS/GB**는 집약도가 높은 워크로드용으로 설계되었습니다. 이러한 워크로드는 일반적으로 대부분의 시간 동안 활성 상태인 데이터를 많이 보유하는 것이 특성입니다. 적용되는 예에는 트랜잭션 및 기타 성능에 민감한 데이터베이스가 포함되어 있습니다.
    - **10IOPS/GB**는 가장 수요가 많은 워크로드(예: NoSQL 데이터베이스에서 생성된 워크로드) 및 분석을 위한 데이터 처리용으로 설계되었습니다. 이 계층은 [특정 데이터 센터](new-ibm-block-and-file-storage-location-and-features.html)에서 최대 4TB 크기로 프로비저닝된 스토리지에 대해 사용 가능합니다.
8. **스냅샷 영역 크기 지정**을 클릭하고 목록에서 스냅샷 크기를 선택하십시오. 이 영역은 사용 가능한 영역에 추가됩니다. 스냅샷 영역 고려사항 및 권장사항을 알아보려면 [스냅샷 주문](ordering-snapshots.html)을 읽으십시오.
9. **이용 약관**의 선택란을 선택하고 **주문하기**를 클릭하십시오.
10. 몇 분 후 새 스토리지 할당이 사용 가능해집니다.

>**참고** - 기본적으로 총 250개의 {{site.data.keyword.blockstorageshort}} 볼륨을 프로비저닝할 수 있습니다. 볼륨 수를 늘리려면 영업 담당자에게 문의하십시오. [여기서](managing-storage-limits.html) 한계 늘리기에 대해 읽으십시오.<br/><br/>동시 권한 부여에 대한 한계는 [FAQ](File-Storage-FAQ.html)를 참조하십시오.

## 사용자 정의 IOPS를 사용하는 {{site.data.keyword.filestorage_short}} 주문(Performance)

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에서 **스토리지**, **{{site.data.keyword.filestorage_short}}**를 클릭하거나 {{site.data.keyword.BluSoftlayer_full}} 카탈로그에서 **인프라** >** 스토리지** > **{{site.data.keyword.filestorage_short}}**를 클릭하십시오.
2. 오른쪽 상단에서 **{{site.data.keyword.filestorage_short}} 주문**을 클릭하십시오.
3. **위치**를 클릭하고 데이터 센터를 선택하십시오.
   - 새 스토리지가 컴퓨팅 호스트 또는 보유한 호스트와 동일한 위치에 추가되었는지 확인하십시오.
4. 비용 청구 방식을 선택하십시오. 개선된 기능의 데이터 센터(*로 표기됨)를 선택한 경우 월별 또는 시간별 청구 중에 선택할 수 있습니다. 
     1. **시간별** 청구에서 파일 볼륨이 계정에 존재한 시간은 LUN이 삭제된 시점이나 청구 주기가 끝난 시점에 계산됩니다. 둘 중 먼저 발생하는 시점이 사용됩니다. 시간별 스토리지는 수 일간 또는 한달 이내에 사용되는 스토리지에 좋은 선택사항입니다. 시간별 청구는 [특정 데이터 센터](new-ibm-block-and-file-storage-location-and-features.html)에서 프로비저닝된 스토리지에만 사용 가능합니다. 
     2. **월별** 청구에서, 가격에 대한 계산은 작성 날짜로부터 청구 주기의 끝까지 비례 배분되며 즉각적으로 청구됩니다. 청구 주기가 끝나기 전에 파일 볼륨이 삭제되는 경우에는 환불이 되지 않습니다. 월별 청구는 장기간(한달 이상) 저장하고 액세스해야 하는 데이터를 사용하는 프로덕션 워크로드에서 사용되는 스토리지에 대해 좋은 선택사항입니다.
        >**참고** - 개선된 기능으로 업데이트되지 **않은** 데이터 센터에서 프로비저닝된 스토리지에는 기본적으로 월별 청구 유형이 사용됩니다.
5. **새 스토리지 크기** 필드에 스토리지 크기를 입력하십시오.
6. **스토리지 IOPS 옵션** 섹션에서 **Performance(할당된 IOPS)**를 선택하십시오.
7. **Performance(할당된 IOPS)** 필드에 IOPS를 입력하십시오.
8. **스냅샷 영역 크기 지정**을 클릭하고 목록에서 스냅샷 크기를 선택하십시오. 이 영역은 사용 가능한 영역에 추가됩니다. 스냅샷 영역 고려사항 및 권장사항을 알아보려면 [스냅샷 주문](ordering-snapshots.html)을 읽으십시오.
9. **이용 약관**의 선택란을 선택하고 **주문하기**를 클릭하십시오.
10. 몇 분 후 새 스토리지 할당이 사용 가능해집니다.

>**참고** - 기본적으로 총 250개의 {{site.data.keyword.blockstorageshort}} 볼륨을 프로비저닝할 수 있습니다. 볼륨 수를 늘리려면 영업 담당자에게 문의하십시오. [여기서](managing-storage-limits.html) 한계 늘리기에 대해 읽으십시오.<br/><br/>동시 권한 부여에 대한 한계는 [FAQ](File-Storage-FAQ.html)를 참조하십시오.


## 새 스토리지 연결

프로비저닝 요청이 완료되면 새 스토리지에 액세스할 수 있도록 호스트에 권한을 부여하고 연결을 구성하십시오. 호스트의 운영 체제에 따라 적절한 링크를 사용하십시오.
- [Linux에서 {{site.data.keyword.filestorage_short}} 액세스](accessing-file-storage-linux.html)
- [CentOS의 NFS/{{site.data.keyword.filestorage_short}} 마운트](mounting-nsf-file-storage.html)
- [CoreOS의 {{site.data.keyword.filestorage_short}} 마운트](mounting-storage-coreos.html)
- [cPanel로 백업을 위한 {{site.data.keyword.filestorage_short}} 구성](configure-backup-cpanel.html)
- [Plesk로 백업을 위한 {{site.data.keyword.filestorage_short}} 구성](configure-backup-plesk.html)
- [ESXi 호스트에 {{site.data.keyword.filestorage_short}} 볼륨 마운트](architecture-guide-file-storage-vmware.html)


## 청구서에서 {{site.data.keyword.filestorage_short}} 볼륨 식별

모든 파일 공유는 청구서에 품목명으로 표시됩니다. Endurance 볼륨은 “Endurance 스토리지 서비스”로 표시되고 Performance 볼륨은 "Performance 스토리지 서비스"로 표시됩니다. 요금은 스토리지 레벨에 따라 달라집니다. Endurance 또는 Performance를 펼쳐 해당 볼륨이 {{site.data.keyword.filestorage_short}} 볼륨인지 알아볼 수 있습니다.
