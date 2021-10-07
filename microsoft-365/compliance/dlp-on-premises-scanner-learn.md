---
title: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너는 파일 활동과 해당 파일에 대한 보호 작업 모니터링을 온-프레미스 파일 공유와 SharePoint 폴더 및 문서 라이브러리로 확대시킵니다. 파일은 AIP(정보 보호) 스캐너로 스캔되어 보호됩니다.
ms.openlocfilehash: c696d4c4e8504d07ce69554c6ff52f264b8ba491
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207346"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner"></a>Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기

Microsoft 데이터 손실 방지 온-프레미스 검사기는 Microsoft 365 서비스에서 중요한 항목을 검색하고 보호하는 데 사용할 수 있는 Microsoft 365의 DLP(데이터 손실 방지) 제품군의 일부입니다. 모든 Microsoft의 DLP 제공에 대한 자세한 내용은 [엔드포인트 데이터 손실 방지에 대한 자세한 정보](dlp-learn-about-dlp.md)를 참조하세요.

**DLP 온-프레미스 스캐너** 는 유출됐을 경우 조직에 위험을 주거나 규정 준수 정책 위반의 위험을 초래하는 중요한 항목을 위해 파일 공유와 SharePoint 문서 라이브러리 및 폴더의 온-프레미스 미사용 데이터를 크롤링합니다. 이를 통해 중요한 항목이 올바르게 사용되고 보호받으며 위험을 초래하는 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다. DLP 온-프레미스 스캐너는 [기본 제공](sensitive-information-type-entity-definitions.md) 또는 [사용자 지정 중요한 정보](create-a-custom-sensitive-information-type.md) 유형, [민감도 레이블](sensitivity-labels.md) 또는 파일 속성을 사용하여 중요한 정보를 감지합니다. 사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용시킬 수 있습니다.

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>DLP 온-프레미스 스캐너는 Azure Information Protection(AIP) 스캐너를 사용합니다.

DLP 온-프레미스 스캐너는 Azure Information Protection(AIP) 스캐너의 전체 구현을 사용하여 중요한 항목을 모니터링, 레이블 지정 및 보호합니다. AIP 스캐너에 익숙하지 않은 경우 익숙해지도록 하는 것이 좋습니다. 자세한 내용은 다음 문서를 참조하세요.

- [Azure Information Protection이란?](/azure/information-protection/what-is-information-protection)
- [Azure Information Protection 통합 레이블 지정 스캐너란?](/azure/information-protection/deploy-aip-scanner)
- [Azure Information Protection 통합 레이블 지정 스캐너 설치 및 배포를 위한 필수 사항](/azure/information-protection/deploy-aip-scanner-prereqs)
- [자습서: Azure Information Protection(AIP) 통합 라벨링 스캐너 설치](/azure/information-protection/tutorial-install-scanner)
- [Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Azure Information Protection 통합 레이블 지정 클라이언트 - 버전 출시 기록 및 지원 정책](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>DLP 온-프레미스 스캐너 작업

DLP 온-프레미스 스캐너는 다음 네 가지 방법 중 하나를 통해 파일을 검색합니다.

- 중요한 정보 유형
- 민감도 레이블
- 파일 확장명
- Office 파일만 문서 속성 사용자 지정 

검색된 파일이 유출되거나 규정 준수 정책 위반이 발생하여 위험에 처하면, DLP-프레미스 스캐너는 다음 네 가지 작업 중 하나를 수행할 수 있습니다.

|작업 |설명  |
|---------|---------|
|**이러한 사용자들이 온-프레미스 스캐너에 저장된 파일에 액세스하지 못하도록 차단합니다 - 모든 사용자** | 이 작업을 적용하면 콘텐츠 소유자, 항목을 수정한 마지막 계정 및 관리자를 제외한 모든 계정의 액세스가 차단됩니다. 이 작업은 파일 소유자, 리포지토리 소유자(콘텐츠 검색 작업 내 [리포지토리 소유자 설정](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview)에서 설정됨), 마지막 수정자(SharePoint에서만 식별 가능) 및 관리자를 제외하고 파일 수준에서 NTFS/SharePoint 사용 권한으로부터 모든 계정을 제거합니다. 스캐너 계정에는 파일에 대한 FC 권한이 부여됩니다.|
|**이러한 사용자들이 온-프레미스 스캐너에 저장된 파일에 액세스하지 못하도록 차단합니다 - 조직 전체(공개) 액세스 차단**    |이 작업을 적용하면 **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, and _*_Domain Users_** SID를 파일 액세스 제어 목록(ACL)에서 제거합니다. 파일 또는 상위 폴더에 명시적으로 권한을 부여받은 사용자 및 그룹만이 파일에 액세스할 수 있습니다.|
|**파일 사용 권한 설정**|이 작업을 적용하면, 파일이 상위 폴더의 사용 권한을 상속하도록 강제 처리합니다. 기본적으로 이 작업은 파일에 이미 있는 사용 권한보다 상위 폴더에 대한 사용 권한이 더 제한적인 경우만 적용됩니다. 예를 들어 파일의 ACL이 **_특정 사용자_*만_ 허용하도록 설정되어 있고 _*_도메인 사용자_*_ 그룹을 허용하도록 상위 폴더가 구성된 경우, 상위 폴더 사용 권한은 파일에 상속되지 않습니다. _* 상위 사용 권한이 덜 제한적인 옵션인 경우에도 상속을 선택하여** 해당 동작을 재정의할 수 있습니다.|
|**부적절한 위치에서 파일 제거**|이 작업을 적용하면 원본 파일을 .txt 확장명을 가지고 스텁 파일로 대체하고 원본 파일의 복사본을 격리 폴더에 배치합니다. 

## <a name="whats-different-in-the-on-premises-scanner"></a>온-프레미스 스캐너의 특별한 점은?

온-프레미스 스캐너를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.

### <a name="aip-repositories-and-content-scan-jobs"></a>AIP 리포지토리 및 콘텐츠 스캔 작업

AIP 콘텐츠 스캔 작업을 만들고 DLP 엔진으로 평가받고 싶은 파일을 호스트하는 리포지토리를 지정해야 합니다. 만든 AIP 콘텐츠 스캔 작업에서 DLP 규칙을 사용하도록 설정해야 합니다.

### <a name="policy-tips"></a>정책 팁

온-프레미스 스캐너에서는 [정책 팁](use-notifications-and-policy-tips.md)을 사용할 수 없습니다.


### <a name="viewing-dlp-on-premises-scanner-events"></a>DLP 온-프레미스 스캐너 이벤트 보기

M365 규정 준수 센터의 [활동 탐색기](data-classification-activity-explorer.md)에서 DLP 온-프레미스 스캐너 데이터를 볼 수 있습니다. 

## <a name="next-steps"></a>다음 단계

이제 DLP 온-프레미스 스캐너에 대해 살펴보았으므로 다음 단계로 넘어갑니다.

1. [DLP 온-프레미스 스캐너 시작하기](dlp-on-premises-scanner-get-started.md)
2. [DLP 온-프레미스 스캐너 사용하기](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>참고 항목

- [Microsoft 데이터 손실 방지 온-프레미스 스캐너로 시작하기](dlp-on-premises-scanner-get-started.md)
- [Microsoft 데이터 손실 방지 온-프레미스 스캐너 사용하기](dlp-on-premises-scanner-use.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)