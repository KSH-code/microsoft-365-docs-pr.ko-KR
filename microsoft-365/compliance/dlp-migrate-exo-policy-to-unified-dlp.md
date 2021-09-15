---
title: 데이터 Exchange Online 방지 정책을 준수 센터로 마이그레이션
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 온라인 데이터 손실 방지 정책을 계획하고 Exchange DLP로 마이그레이션하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 2cf06b7aee9adb63ff85259427bcac818807cc7c
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59357472"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-compliance-center"></a>데이터 Exchange Online 방지 정책을 준수 센터로 마이그레이션

[Exchange Online DLP(데이터 손실 방지)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) 정책이 더는 사용되지 않습니다. [DLP를](dlp-learn-about-dlp.md)비롯한 훨씬 더 풍부한 DLP Exchange Online DLP는 Microsoft 365 규정 준수 [센터에서 제공됩니다.](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP 정책 마이그레이션 마법사를 사용하여 DLP 정책을 관리할 Exchange Online DLP 정책을 안내할 수 있습니다.

마이그레이션 마법사는 마이그레이션 센터에서 DLP 정책의 구성을 Exchange 준수 센터에서 중복된 정책을 만들어 작동합니다. 기본적으로 마법사는 테스트 모드에서 새  버전의 정책을 만들어 작업을 적용하지 않고도 환경에 미치는 영향을 볼 수 있습니다. 준수 센터 버전으로 완전히 전환할 준비가 된 후 **_다음을 해야 합니다._**

1. EAC(Exchange 관리 센터)에서 원본 정책을 비활성화하거나 삭제합니다.
1. 정책의 준수 센터 버전을 편집하고 상태를 **테스트에서 적용으로** **변경합니다.** 

> [!WARNING]
> 준수 센터 버전을 적용으로 설정하기 전에 EAC에서 원본 정책을 삭제하거나  비활성화하지 않은 경우 두 정책 집합이 모두 작업을 적용하려고 시도하고 중복 이벤트를 받게 됩니다. **_지원되지 않는 구성입니다._**


마이그레이션 마법사는 EXO 정책 및 관련 메일 흐름 규칙만 마이그레이션합니다. 독립 실행형 Exchange 흐름 규칙이 마이그레이션되지 않습니다.

## <a name="migration-workflow"></a>마이그레이션 워크플로

DLP 정책을 준수 센터의 통합 DLP 관리 콘솔로 Exchange 단계로 마이그레이션하는 데는 네 가지 단계가 있습니다.  

1. 마이그레이션 준비하기
    1. EXO(exO) DLP Exchange Online 및 준수 센터 DLP 정책을 평가하고 중복 기능을 비교합니다.
    1. 어떤 EXO DLP 정책을 그대로 가져오고 싶은지 결정하려면 마법사를 사용하여 마이그레이션할 수 있습니다.
    1. 통합할 EXO DLP 정책을 결정하고 Exchange 관리 센터에 통합한 다음 마이그레이션 마법사를 사용하여 준수 센터로 가져와야 합니다.
1. 마이그레이션 수행 - 마법사 사용
1. 테스트 및 유효성 검사 - 결과 검사
1. 마이그레이션된 정책 활성화

## <a name="before-you-begin"></a>시작하기 전에

### <a name="licensing-and-versions"></a>라이선스 및 버전

DLP 정책 마이그레이션을 시작하기 전에 Microsoft 365 추가 [](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 기능을 확인해야 합니다. 

정책 마이그레이션 마법사에 액세스하고 사용하려면 이러한 구독 또는 추가 기능 중 하나만 있어야 합니다.

- Microsoft 365 E3
- Microsoft 365 E5
- Microsoft 365 A5(EDU)
- Microsoft 365 E5 compliance
- Microsoft 365 A5 compliance
- Microsoft 365 E5 Information Protection 및 거버넌스
- Microsoft 365 A5 Information Protection 및 거버넌스

DLP 라이선스 요구 사항의 자세한 목록은 Microsoft 365 규정 준수, 데이터 손실 & 라이선싱 지침을 [참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)


### <a name="permissions"></a>사용 권한

마이그레이션 마법사를 실행하기 위해 사용하는 계정에는 Exchange 관리 콘솔 DLP 페이지와 준수 센터의 통합 DLP 콘솔에 모두 액세스할 수 있어야 합니다.

## <a name="prepare-for-migration"></a>마이그레이션 준비하기

1. DLP, 준수 센터 DLP 콘솔 또는 Exchange 관리 센터 DLP 콘솔에 익숙하지 않은 경우 정책 마이그레이션을 시도하기 전에 익숙해야 합니다.
    1. [Exchange Online DLP(데이터 손실 방지) 정책](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
    1. [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
1. 다음 Exchange DLP 및 규정 준수 센터 정책을 평가합니다.


|질문  |작업  | 마이그레이션 절차|
|---------|---------|---------|
|정책이 여전히 필요한가요?    |그렇지 않은 경우 삭제 또는 비활성화 |마이그레이션하지 않습니다.|
|다른 정책 또는 규정 Exchange DLP 정책과 겹치나요?     |그렇다면 겹치는 정책을 통합할 수 있나요?         |- 다른 Exchange 정책과 겹치는 경우 Exchange 관리 센터에서 통합 DLP 정책을 수동으로 만든 다음 마이그레이션 마법사를 사용하세요. </br> - 기존 준수 센터 정책과 겹치는 경우 기존 준수 센터 정책을 일치하도록 수정할 수 있습니다. 기존 준수 센터 Exchange 마이그레이션하지 않습니다.|
|DLP Exchange 범위가 긴밀하게 지정되어 있으며 조건, 작업, 포함 및 제외가 잘 정의되어 있습니까?     |예인 경우 마법사로 마이그레이션하기에 좋은 후보입니다. 나중에 삭제하기 위해 다시 돌아와야 할 수 있도록 정책을 메모해 두는 것이 좋습니다.         | 마법사를 사용하여 마이그레이션|

## <a name="migration"></a>마이그레이션

필요와 호환성을 위해 모든 Exchange 및 규정 준수 센터 DLP 정책을 평가한 후 마이그레이션 마법사를 사용할 수 있습니다.

1. 준수 [Microsoft 365](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP 콘솔을 열 수 있습니다.
2. 마이그레이션할 Exchange DLP 정책이 있는 경우 페이지 맨 위에 배너가 표시되어 알 수 있습니다.
3. **배너에서 정책** 마이그레이션을 선택하면 마이그레이션 마법사를 열 수 있습니다. 모든 Exchange DLP 정책이 나열됩니다. 이전에 마이그레이션된 정책은 선택할 수 없습니다.
4. 마이그레이션할 정책을 선택합니다. 단계적 접근 방식을 사용하여 개별적으로 또는 그룹으로 마이그레이션하거나 한에 모두 마이그레이션할 수 있습니다. **다음** 을 선택합니다.
5. 플라이아웃 창에서 경고 또는 메시지를 검토합니다. 계속하기 전에 문제를 해결합니다.
6. 활성, 테스트 또는 사용 안 하도록 설정 에서 새 준수 센터 정책을 만들 모드를 **선택합니다.**  기본값은 Test **입니다.** **다음** 을 선택합니다.
7. 원하는 경우 다른 통합 DLP 위치에 대한 Exchange 정책을 기반으로 하는 추가 정책을 만들 수 있습니다. 이렇게 하면 마이그레이션된 통합 DLP 정책에 대한 새로운 통합 DLP 정책이 Exchange 추가 위치에 대해 하나의 새로운 통합 DLP 정책이 표시됩니다.

> [!IMPORTANT]
> Exchange, 장치, SharePoint, OneDrive, MCAS 또는 Teams 채팅 및 채널 메시지와 같은 다른 DLP 위치에서 지원되지 않는 모든 DLP 정책 조건 및 작업은 추가 정책에서 삭제됩니다. 또한 다른 위치에 대해 수행해야 하는 사전 작업도 있습니다. 자세한 내용은 다음을 참조하세요.
>- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
>- [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)
>- [엔드포인트 데이터 손실 방지 사용](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
>- [Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [데이터 손실 방지 온-프레미스 스캐너로 시작하기](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)
>- [Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 사용하기](dlp-on-premises-scanner-use.md#use-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)
 
8. 마이그레이션 마법사 세션 설정을 검토합니다. **다음** 을 선택합니다.
9. 마이그레이션 보고서를 검토합니다. 메일 흐름 규칙과 관련된 Exchange 주의해야 합니다. 이러한 정책을 수정하고 연결된 정책을 다시 마이그레이션할 수 있습니다.

이제 마이그레이션된 정책이 준수 센터 DLP 콘솔의 DLP 정책 목록에 표시됩니다. 

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>테스트 및 유효성 검사 <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

정책을 테스트하고 검토합니다.

1. [DLP 정책 테스트 절차를 따르는](create-test-tune-dlp-policy.md#test-a-dlp-policy) 경우
2. 활동 탐색기에서 정책에 의해 생성된 [이벤트를 검토합니다.](data-classification-activity-explorer.md)

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-365-unified-dlp"></a>Exchange 관리 센터 DLP와 통합 DLP 간의 Microsoft 365 검토

마이그레이션된 정책이 예상대로 운영되도록 두 관리 센터에서 보고서를 내보내고 정책 일치를 비교할 수 있습니다.

1. 커넥트 [PowerShell을 Exchange Online 합니다.](/powershell/exchange/connect-to-exchange-online-powershell)
2. [EAC DLP 보고서를 내보낼 수 있습니다.](/powershell/module/exchange/get-maildetaildlppolicyreport?view=exchange-ps) 이 cmdlet을 복사하고 적절한 값을 삽입할 수 있습니다.

```powershell
Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv"> 
```
3. 통합 [DLP 보고서를 내보낼 수 있습니다.](/powershell/module/exchange/get-dlpdetailreport?view=exchange-ps) 이 cmdlet을 복사하고 적절한 값을 삽입할 수 있습니다.

```powershell
Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">  
```

## <a name="activate-your-migrated-policies"></a>마이그레이션된 정책 활성화

마이그레이션된 정책의 작동 방식에 만족하면 적용으로 설정할 수 **있습니다.**

1. 관리 Exchange DLP 콘솔을 니다.
2. 원본 정책을 비활성화하거나 삭제합니다.
3. Microsoft 365 [준수](https://compliance.microsoft.com/datalossprevention?viewid=policies) 센터 DLP 콘솔을 열고 활성으로 만들 정책을 선택하여 편집합니다.
4. 상태를 켜기 **으로 변경합니다.**

## <a name="related-articles"></a>관련 문서

- [Exchange Online DLP(데이터 손실 방지) 정책](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
- [Exchange Online DLP(데이터 손실 방지) 정책](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)