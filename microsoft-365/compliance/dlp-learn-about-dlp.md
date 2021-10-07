---
title: 데이터 손실 방지에 대해 알아보기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 데이터 손실 방지 정책 및 도구를 사용하여 Microsoft 365 보호하는 방법을 알아보고 DLP 수명 주기를 둘러보는 방법을 알아보고 있습니다.
ms.openlocfilehash: 690791369f40c4c73e837ce872428978632881f3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197644"
---
# <a name="learn-about-data-loss-prevention"></a>데이터 손실 방지에 대해 알아보기

조직은 재무 데이터, 소유 데이터, 신용 카드 번호, 의료 기록 또는 주민 등록 번호와 같은 중요한 정보를 제어합니다. 이러한 중요한 데이터를 보호하고 위험을 줄이기 위해 사용자는 이 데이터를 사용할 수 없는 사용자와 부적절하게 공유하지 못하게 하는 방법이 필요합니다. 이 사례를 DLP(데이터 손실 방지)라고 합니다.

이 Microsoft 365 DLP 정책을 정의하고 적용하여 데이터 손실 방지를 구현합니다. DLP 정책을 사용하면 다음을 통해 중요한 항목을 식별, 모니터링 및 자동으로 보호할 수 있습니다.

- Microsoft 365, Teams, Exchange, SharePoint 및 OneDrive
- Office, Excel 및 PowerPoint
- Windows 10 끝점
- 비 Microsoft 클라우드 앱
- On-premises file shares and on-premises file shares and on-premises SharePoint.

Microsoft 365 단순한 텍스트 검색이 아니라 심층 콘텐츠 분석을 사용하여 중요한 항목을 검색할 수 있습니다. 콘텐츠는 키워드와의 기본 데이터 일치, 정규식 평가, 내부 함수 유효성 검사 및 기본 데이터 일치와 근접한 보조 데이터 일치를 통해 분석됩니다. 또한 DLP는 기계 학습 알고리즘 및 기타 방법을 사용하여 DLP 정책과 일치하는 콘텐츠를 검색합니다.

## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>DLP는 더 큰 Microsoft 365 규정 준수 제공의 일부입니다.

Microsoft 365 DLP는 거주하거나 여행하는 모든 Microsoft 365 보호하는 데 사용할 수 있는 규정 준수 도구 중 하나에 불과합니다. 규정 준수 도구 집합의 다른 도구와 Microsoft 365 상호 연결하고 함께 작업하는 방법을 이해해야 합니다.  정보 보호 [Microsoft 365 대한 자세한](protect-information.md) 내용은 준수 도구를 참조하세요.

## <a name="protective-actions-of-dlp-policies"></a>DLP 정책의 보호 작업

Microsoft 365 DLP 정책은 사용자가 미사용 중요한 항목, 전송되는 중요한 항목 또는 사용 중이던 중요한 항목에 대해 수행한 활동을 모니터링하고 보호 조치를 취하는 방식입니다. 예를 들어 사용자가 승인되지 않은 위치에 중요한 항목을 복사하거나 전자 메일 또는 정책에 정해진 기타 조건에서 의료 정보를 공유하는 등 금지된 작업을 수행하려고 할 때 DLP는 다음을 할 수 있습니다.

- 중요한 항목을 부적절하게 공유하려고 할 수 있는 경우를 경고하는 팝업 정책 팁을 사용자에게 표시
- 공유를 차단하고, 정책 팁을 통해 사용자가 차단을 오버라이드하고 사용자의 사유를 캡처할 수 있도록 허용
- Override 옵션 없이 공유 차단
- 미사용 데이터의 경우 중요한 항목을 잠가 안전한 검지 위치로 이동할 수 있습니다.
- Teams 경우 중요한 정보가 표시되지 않습니다.

모든 DLP 모니터링 활동은 기본적으로 [](search-the-audit-log-in-security-and-compliance.md) Microsoft 365 감사 로그에 기록되어 활동 [탐색기로 라우팅됩니다.](data-classification-activity-explorer.md) 사용자가 DLP 정책의 기준을 충족하는 작업을 수행하고 경고가 구성된 경우 DLP는 DLP 경고 관리 대시보드에 [알림을 제공합니다.](dlp-configure-view-alerts-policies.md)

## <a name="dlp-lifecycle"></a>DLP 수명 주기

DLP 구현은 일반적으로 다음과 같은 주요 단계를 따르게 됩니다.

- [DLP 계획](#plan-for-dlp)
- [DLP 준비](#prepare-for-dlp)
- [프로덕션에서 정책 배포](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>DLP 계획

Microsoft 365 DLP 모니터링 및 보호는 사용자가 매일 사용하는 응용 프로그램에 기본적으로 사용됩니다. 이렇게 하면 사용자가 데이터 손실 방지 사고와 관행에 익숙하지 않은 경우에도 조직의 중요한 항목을 위험한 활동으로부터 보호할 수 있습니다. 조직과 사용자가 데이터 손실 방지 방법을 잘 아는 경우 DLP를 채택하려면 비즈니스 프로세스가 변경될 수 있으며 사용자에 대한 문화 변화가 있을 수 있습니다. 그러나 적절한 계획, 테스트 및 조정을 통해 DLP 정책은 잠재적인 비즈니스 프로세스 중단을 최소화하면서 중요한 항목을 보호합니다.

**DLP에 대한 기술 계획**

기술로 DLP는 미사용 데이터, 사용 중 데이터, Microsoft 365 서비스, Windows 10 장치, Windows 10 파일 공유 및 사내 장치 전체에서 이동되는 데이터를 모니터링하고 보호할 수 SharePoint. 다양한 위치, 모니터링 및 보호하려는 데이터의 유형, 정책 일치 시 수행할 작업에 대한 계획이 있습니다.

**DLP에 대한 비즈니스 프로세스 계획**

DLP 정책은 전자 메일을 통해 중요한 정보를 부적절하게 공유하는 등 금지된 활동을 차단할 수 있습니다. DLP 정책을 계획할 때 중요한 항목을 터치하는 비즈니스 프로세스를 식별해야 합니다. 비즈니스 프로세스 소유자는 허용해야 하는 적절한 사용자 동작과 보호해야 하는 부적절한 사용자 동작을 식별하는 데 도움을 줄 수 있습니다. 정책을 계획하고 테스트 모드에서 배포하고, 보다 제한적인 [](data-classification-activity-explorer.md) 모드에서 적용하기 전에 먼저 활동 탐색기를 통해 영향을 평가해야 합니다.

**DLP에 대한 조직 문화 계획**

성공적인 DLP 구현은 사용자가 잘 계획 및 조정된 정책에 따라 데이터 손실 방지 사례를 교육하고 적용하는 데 크게 의존합니다. 사용자의 참여가 까다로워지기 때문에 사용자에 대한 교육도 계획해야 합니다. 정책 적용을 테스트 모드에서 더 제한적인 모드로 변경하기 전에 정책 팁을 전략적으로 사용하여 사용자에 대한 인식을 높일 수 있습니다.

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>DLP 준비

미사용 데이터, 사용 중 데이터 및 위치에서 이동하는 데이터에 DLP 정책을 적용할 수 있습니다.

- Exchange Online 메일 보내기
- SharePoint Online 사이트
- OneDrive 계정
- Teams 채팅 및 채널 메시지
- Microsoft Cloud App Security
- Windows 10 장치
- 사내 리포지토리

각 선행 준비는 서로 다릅니다. 일부 위치의 중요한 항목(예: 온라인 Exchange)은 해당 항목에 적용되는 정책을 구성하기만 하여 DLP umbrella 아래에 가져와야 합니다. 사내 파일 리포지토리와 같은 다른 기능을 사용하려면 AIP(Azure Information Protection) 스캐너를 배포해야 합니다. 차단 작업을 활성화하기 전에 환경, 코드 초안 정책을 준비하고 철저하게 테스트해야 합니다.

### <a name="deploy-your-policies-in-production"></a>프로덕션에서 정책 배포

#### <a name="design-your-policies"></a>정책 디자인

먼저 컨트롤 목표를 정의하고 각 워크로드에 적용되는 방법을 정의합니다. 목표를 구상하는 정책 초안을 작성합니다. 한 번의 작업으로 시작하거나 모든 워크로드에서 자유롭게 시작할 수 있습니다. 아직 영향이 없습니다.

#### <a name="implement-policy-in-test-mode"></a>테스트 모드에서 정책 구현

테스트 모드에서 DLP 정책을 사용하여 컨트롤을 구현하여 컨트롤의 영향을 평가합니다. 모든 결과를 얻을 수 있도록 테스트 모드에서 모든 워크로드에 정책을 적용하는 것이 괜찮지만 필요한 경우 하나의 워크로드로 시작할 수 있습니다.

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>결과 모니터링 및 정책 미세 조정

테스트 모드에서는 정책의 결과를 모니터링하고 컨트롤 목표를 충족하도록 세부 조정하면서 유효한 사용자 워크플로 및 생산성에 부정적인 영향을 미치거나 부적당하게 영향을 끼치지 않는지 보장합니다. 다음은 세부적으로 조정해야 할 몇 가지 예입니다.

- 범위에 포함되거나 범위를 벗어날 위치 및 사람/위치 조정
- 항목 및 해당 항목으로 수행되는 것이 정책과 일치하는지 확인하는 데 사용되는 조건 및 예외 조정
- 중요한 정보 정의/s
- 동작
- 제한 수준
- 새 컨트롤 추가
- 새 사용자 추가
- 새 제한된 앱 추가
- 새 제한된 사이트 추가

#### <a name="enable-the-control-and-tune-your-policies"></a>제어를 사용하도록 설정하고 정책 조정

정책이 모든 목표를 충족하면 켜야 합니다. 정책 응용 프로그램의 결과를 계속 모니터링하고 필요한 경우 조정합니다. 일반적으로 정책은 켜진 후 1시간 정도 적용됩니다.

<!--See, LINK TO topic for SLAs for location specific  details-->

## <a name="dlp-policy-configuration-overview"></a>DLP 정책 구성 개요

DLP 정책을 만들고 구성하는 방법에는 유연성이 있습니다. 미리 정의한 템플릿에서 시작하여 몇 번의 클릭으로 정책을 만들거나 직접 디자인할 수 있습니다. 어떤 DLP 정책을 선택하든 상관없이 모든 DLP 정책에 동일한 정보가 필요합니다.

1. **모니터링할** 정책 선택 - Microsoft 365 미리 정의한 여러 정책 템플릿이 함께 사용되어 시작하거나 사용자 지정 정책을 만들 수 있습니다.
    - 미리 정의한 정책 템플릿: 재무 데이터, 의료 및 의료 데이터, 다양한 국가 및 지역에 대한 개인 정보 보호 데이터.
    - 사용 가능한 중요한 정보 유형, 보존 레이블 및 민감도 레이블을 사용하는 사용자 지정 정책입니다.
2. **모니터링할** 위치 선택 - DLP에서 중요한 정보를 모니터링할 위치를 하나 이상 선택할 수 있습니다. 다음을 모니터링할 수 있습니다.

위치 | 포함/제외 기준|
|---------|---------|
|Exchange 전자 메일| 메일 그룹|
|SharePoint 사이트 |사이트 |
|OneDrive 계정 |계정 또는 메일 그룹 |
|Teams 채팅 및 채널 메시지 |계정 |
|Windows 10 장치 |사용자 또는 그룹 |
|Microsoft Cloud App Security |인스턴스 |
|사내 리포지토리| 리포지토리 파일 경로|

3. **항목에 정책을** 적용하기 위해 일치해야 하는 조건을 선택하십시오. 미리 구성된 조건을 수락하거나 사용자 지정 조건을 정의할 수 있습니다. 예를 들면 다음과 같습니다.

- 항목에는 특정 컨텍스트에서 사용되는 특정 종류의 중요한 정보가 포함되어 있습니다. 예를 들어, 95개 주민 등록 번호를 받는 사람에게 전자 메일로 보내야 합니다.
- 항목에 지정된 민감도 레이블이 있습니다.
- 중요한 정보가 있는 항목은 내부 또는 외부적으로 공유됩니다.

4. **정책 조건이 충족되는** 경우 수행할 작업을 선택하십시오. 작업은 활동이 수행되는 위치에 따라 달라 집니다.  예를 들면 다음과 같습니다.

- SharePoint/Exchange/OneDrive: 조직 외부의 사람이 콘텐츠에 액세스하는 것을 차단합니다. 사용자에게 팁을 표시하고 DLP 정책에 의해 금지된 작업을 수행하고 있는 전자 메일 알림을 전송합니다.
- Teams 채팅 및 채널: 채팅 또는 채널에서 중요한 정보가 공유되지 못하게 차단
- Windows 10 장치: 중요한 항목을 제거 가능한 USB 장치로 복사 감사 또는 제한
- Office 앱: 사용자에게 위험한 동작에 참여하고 있으며 이를 차단하거나 차단하지만 이를 허용하도록 알리는 팝업을 표시하세요.
- On-premises file shares: move the file from where it is stored to a quarantine folder

> [!NOTE]
> 수행할 조건과 동작은 Rule이라는 개체에 정의됩니다.

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

준수 센터에서 DLP 정책을 만든 후 중앙 정책 저장소에 저장되어 다음을 비롯한 다양한 콘텐츠 원본과 동기화됩니다.

- Exchange Online, 웹용 Outlook 및 Outlook.
- 비즈니스용 OneDrive 사이트.
- SharePoint Online 사이트.
- Office 데스크톱 프로그램 (Excel, PowerPoint 및 Word).
- Microsoft Teams 채널 및 채팅 메시지.

정책이 올바른 위치와 동기화된 후 콘텐츠를 평가하고 작업을 적용하기 시작합니다.

## <a name="viewing-policy-application-results"></a>정책 응용 프로그램 결과 보기

DLP는 모니터링, 정책 일치 Microsoft 365 작업 및 사용자 활동에서 광범위한 정보를 보고합니다. 중요한 항목에 대해 수행된 정책 및 선고 작업을 조정하기 위해 해당 정보를 사용 및 조치를 취해야 합니다. 원격 분석은 Microsoft 365 준수 [](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) 센터 감사 로그로 이동하고, 처리된 후 다른 보고 도구로 이동됩니다. 각 보고 도구의 용도는 다릅니다.

### <a name="dlp-alerts-dashboard"></a>DLP 경고 대시보드

DLP가 중요한 항목에 대해 작업을 수행하면 구성 가능한 경고를 통해 해당 작업을 알 수 있습니다. 규정 준수 센터는 이러한 경고를 사서함에 더해지기보다는 DLP 경고 관리 대시보드에서 해당 경고를 사용할 [수 있도록 합니다.](dlp-configure-view-alerts-policies.md) DLP 경고 대시보드를 사용하여 경고를 구성하고, 검토하고, 경고를 심사하고, DLP 경고의 해결 방법을 추적할 수 있습니다. 다음은 정책 일치 및 정책 일치 및 장치 활동으로 생성된 경고의 Windows 10 예입니다.

> [!div class="mx-imgBorder"]
> ![경고 정보](../media/Alert-info-1.png)

동일한 대시보드에서 서식 있는 메타데이터와 관련된 이벤트 세부 정보를 볼 수도 있습니다.

> [!div class="mx-imgBorder"]
> ![이벤트 정보.](../media/Event-info-1.png)

### <a name="reports"></a>보고서

[DLP 보고서는](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) 시간이 경과에 따라 광범위한 추세를 표시하고 다음에 대한 특정 정보를 제공합니다.

- **DLP 정책 날짜** 범위, 위치, 정책 또는 작업을 사용하여 시간이 지날 때 일치하고 필터링합니다.
- **또한 DLP 인시던트 일치는** 시간이 지날 때 일치 항목을 표시하지만 정책 규칙이 아닌 항목에 대한 피벗입니다.
- **DLP 가짓 긍정** 및 다시 설정은 가짓 긍정의 수를 표시하고, 구성된 경우 사용자 정당성과 함께 사용자 다시 설정의 수를 보여줍니다.

### <a name="dlp-activity-explorer"></a>DLP 활동 탐색기

DLP 페이지의 활동 탐색기 탭에는 활동 필터가 *DLPRuleMatch로 미리 설정되어 있습니다.*  이 도구를 사용하여 중요한 정보를 포함하거나 레이블이 적용된 콘텐츠와 관련된 활동을 검토할 수 있습니다(예: 변경된 레이블, 파일이 수정된 후 규칙과 일치).

![DLPRuleMatch 범위 활동 탐색기 스크린샷](../media/dlp-activity-explorer.png)

자세한 내용은 활동 탐색기 [시작을 참조하세요.](data-classification-activity-explorer.md)

DLP에 대한 Microsoft 365 자세한 내용은 다음을 참조합니다.

- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md)
- [Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)](dlp-teams-default-policy.md)
- [Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기(미리 보기)](dlp-on-premises-scanner-learn.md)
- [Microsoft 규정 준수 확장(미리 보기)에 대해 알아보기](dlp-chrome-learn-about.md)
- [데이터 손실 방지 알림 대시보드에 대한 자세한 정보](dlp-alerts-dashboard-learn.md)

데이터 손실 방지를 사용하여 데이터 개인 정보 보호 규정을 준수하는 방법에 대한 자세한 내용은 [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)를 참조하십시오.
