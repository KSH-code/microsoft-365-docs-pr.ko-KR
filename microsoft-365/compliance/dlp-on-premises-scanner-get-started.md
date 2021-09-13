---
title: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너로 시작하기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 설정
ms.openlocfilehash: fbaf28c1a88f1654154cc53ce731d2f56bfae382
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192979"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner"></a>데이터 손실 방지 온-프레미스 스캐너로 시작하기

이 문서에서는 Microsoft 365 데이터 손실 방지 온-프레미스 스캐너의 필수 구성 요소 및 구성에 관한 정보를 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

DLP 온-프레미스 스캐너를 시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다. DLP 규칙을 설정하는 관리자 계정에 다음 라이선스 중 한 가지가 할당되어 있어야 합니다.

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 정보 보호 및 거버넌스 


전체 라이선싱에 대한 자세한 내용은 [보안 & 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조하세요.

### <a name="permissions"></a>사용 권한


DLP 온-프레미스 스캐너의 데이터는 [활동 탐색기](data-classification-activity-explorer.md)에서 볼 수 있습니다. 활동 탐색기에 대한 사용 권한을 부여하는 네 개의 역할이 있습니다. 데이터에 액세스하는 데 사용하는 계정은 해당 역할 중 하나의 구성원이어야 합니다.

- 전역 관리자
- 준수 관리자
- 보안 관리자
- 규정 준수 데이터 관리자

### <a name="dlp-on-premises-scanner-prerequisites"></a>DLP 온-프레미스 스캐너에 대한 필수 구성 요소

- Azure Information Protection (AIP) 스캐너는 DLP 정책 일치 및 정책 적용을 구현합니다. 스캐너는 AIP 클라이언트의 일부로 설치되어 사용자의 설치가 AIP, AIP 클라이언트 및 AIP 통합 레이블 스캐너의 모든 필수 구성 요소를 갖춰야 합니다.
- AIP 클라이언트 및 스캐너를 배포합니다. [AIP 통합 레이블 지정 클라이언트 설치](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 및 []에 대한 자세한 내용은 [Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install)를 참조하세요.
- 모든 검색 규칙이 중요한 정보 유형만을 기반으로 할지라도 테넌트에 하나 이상의 레이블 및 정책이 게시되어야 합니다.

## <a name="deploy-the-dlp-on-premises-scanner"></a>DLP 온-프레미스 스캐너 배포

1. [AIP 통합 레이블 지정 클라이언트 설치](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 절차를 따르세요. 
2. [Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install)절차를 따라 스캐너 설치를 완료합니다.
    1. 네트워크 검색 작업 구성은 선택적 단계입니다. 이를 건너뛰고 콘텐츠 스캔 작업에서 스캔할 특정 리포지토리를 정의할 수 있습니다.
    2. 콘텐츠 스캔 작업을 만들고 DLP 엔진으로 평가해야 하는 파일을 호스트하는 리포지토리를 지정해야 합니다.
    3. 만든 콘텐츠 스캔 작업의 DLP 규칙을 사용하도록 설정하고, DLP 적용 단계로 직접 진행하지 않는 이상 옵션을 **끄기** 로 **적용** 하도록 설정합니다.
3. 콘텐츠 스캔 작업이 올바른 클러스터에 할당되어 있는지 확인합니다. 아직 콘텐츠 스캔 작업을 만들지 않았을 경우 새 스캔 작업을 만들고 스캐너 노드가 포함된 클러스터에 이를 할당합니다.

4. [Azure Portal 내 Azure Information Protection 확장](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade)에 연결하고 스캔을 수행하는 콘텐츠 스캔 작업으로 리포지토리를 추가합니다.

5. 다음 중 하나를 실행하여 스캔을 실행합니다.
    1. 스캐너 일정 설정
    1. 포털에서 수동 **지금 스캔** 옵션을 사용합니다.
    1. 또는 **Start-AIPScan** PowerShell cmdlet을 실행합니다.

   > [!IMPORTANT]
   > 스캐너는 기본적으로 리포지토리의 델타 스캔을 실행하며, 파일이 변경되거나 전체 다시 스캔을 시작하지 않는 한 이전 스캔 싸이클에서 이미 스캔된 파일은 건너뜁니다. UI에서 **모든 파일 다시 스캔** 옵션을 사용하거나 **Start-AIPScan-Reset** 을 실행하여 전체 다시 스캔을 시작할 수 있습니다.

6.  Microsoft 365 규정 준수 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.

7. **정책을 만들기** 를 선택하고 테스트 DLP 정책을 만듭니다. 정책을 만드는데 도움이 필요한 경우 [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)를 참조하세요. 이 기능에 대해 잘 알게 될 때까지 테스트 실행을 해야 합니다. 정책에 다음 매개 변수를 사용합니다.
    1. 필요한 경우 DLP 온-프레미스 스캐너 규칙을 특정 위치로 지정합니다. **위치** 를 **모든 위치** 로 지정했다면 스캐너로 스캔한 모든 파일에는 DLP 규칙 일치 및 적용이 적용됩니다.
    1. 위치를 지정할 때 배제 또는 포함 목록을 사용할 수 있습니다. 규칙이 포함 목록에 있는 패턴 중 하나와 일치하는 경로와만 관련이 있거나, 또는 포함 목록에 있는 패턴과 일치하는 파일을 제외한 모든 파일과 관련이 있는 것으로 정의할 수 있습니다. 지원되는 로컬 경로가 없습니다. 다음은 유효한 경로의 몇 가지 예입니다.
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. 다음은 허용되지 않는 값의 몇 가지 예입니다.
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> 제외 목록이 포함 목록보다 우선합니다.

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>DLP 경고 관리 대시보드에서 DLP 온-프레미스 스캐너 경고 보기

1. Microsoft 365 규정 준수 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 열고 **경고** 를 선택합니다.

2. 엔드포인트 DLP 정책에 대한 경고를 보려면 [DLP 정책을 구성하고 경고를 보는 방법](dlp-configure-view-alerts-policies.md)의 절차를 참조하세요.

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>활동 탐색기 및 감사 로그에서 DLP 온-프레미스 스캐너 보기

> [!NOTE]
> 온-프레미스 스캐너를 사용하려면 감사를 사용하도록 설정해야 합니다. Microsoft 365 감사는 기본적으로 사용하도록 설정되어 있습니다.

1. Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 활동 탐색기를 선택합니다.

2. [활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 온-프레미스 스캐너 위치에 대한 모든 데이터에 액세스합니다.

3. [규정 준수 센터의 감사 로그](https://security.microsoft.com/auditlogsearch)를 엽니다. DLP 규칙 일치 항목은 감사 로그 UI에서 확인할 수 있으며, [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell을 이용하여 액세스할 수 있습니다. 


## <a name="next-steps"></a>다음 단계
이제 DLP 온-프레미스 위치에 대한 테스트 정책을 배포하였고 활동 탐색기에서 활동 데이터를 볼 수 있으므로, 중요한 항목을 보호하는 DLP 정책을 만드는 다음 단계로 진행할 준비가 되었습니다.

- [DLP 온-프레미스 사용하기](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>참고 항목

- [DLP 온-프레미스 스캐너에 대한 자세한 정보](dlp-on-premises-scanner-learn.md)
- [DLP 온-프레미스 스캐너 사용하기](dlp-on-premises-scanner-use.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)