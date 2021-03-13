---
title: 콘텐츠를 자동으로 보존하거나 삭제하는 보존 정책과 레이블에 대해 자세히 알아보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 필요한 항목을 보존하고 필요하지 않은 항목을 삭제하는 데 도움을 주는 보존 정책과 보존 레이블에 대해 알아봅니다.
ms.openlocfilehash: 67697124df7908dca2ace74dc5de921d18d817c6
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727327"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블에 대해 자세히 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

> [!NOTE]
> 앱에 보존 정책에 대한 메시지가 표시되면 IT 부서에 이러한 보존 정책이 구성된 방식에 대한 정보를 문의하세요. 이러한 메시지가 Teams 채팅 또는 채널 메시지용인 경우 [보존 정책에 대한 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 참조하세요.
>
> 이 페이지의 정보는 규정 준수를 위해 보존 정책 및 보존 레이블을 생성할 수 있는 IT 관리자를 위한 것입니다.

대부분의 조직에서는 전자 메일, 문서, 인스턴트 메시지 등을 비롯하여 데이터의 양과 복잡성이 계속해서 매일 증가하고 있습니다. 이러한 정보를 효과적으로 관리하거나 제어하는 일은 다음 작업을 수행해야 하므로 중요합니다.
  
- 최소 기간 동안 콘텐츠를 보존하도록 요구하는 **산업 규정 및 내부 정책을 사전에 준수** 합니다. 예를 들어 Sarbanes-Oxley Act는 7년 동안 특정 유형의 콘텐츠를 보존하도록 요구할 수 있습니다. 

- **소송 또는 보안 위반 시 위험 감소** - 더 이상 보존할 필요가 없는 오래된 콘텐츠를 영구적으로 삭제 
    
- **조직에서 효과적이면서 좀 더 민첩하게 지식을 공유하도록 지원** - 사용자가 관련이 있는 최신 콘텐츠만 사용하도록 합니다. 
    
사용자가 구성한 보존 설정은 이러한 모든 목표를 달성하는 데 도움이 될 수 있습니다. 콘텐츠 관리에는 일반적으로 다음과 같은 두 가지 작업이 요구됩니다.
  
- **보존** - 콘텐츠가 보존 기간이 끝나기 전에 영구적으로 삭제되지 않도록 보존합니다. 
    
- **삭제** - 보존 기간이 끝나면 콘텐츠를 영구적으로 삭제합니다. 
    

이러한 두 가지 보존 작업을 통해 다음 결과에 대한 보존 설정을 구성할 수 있습니다.

- 보존 전용: 콘텐츠를 영구적으로 또는 지정된 기간 동안 보존합니다.
- 삭제 전용: 지정된 기간이 지난 후 콘텐츠를 삭제합니다.
- 보존한 다음 삭제: 지정된 기간 동안 콘텐츠를 보존한 다음 삭제합니다.

이러한 보존 설정은 규정 준수를 이유로 콘텐츠를 보존해야 할 때 추가 저장소를 만들고 구성하는 추가 오버헤드를 절약하는 콘텐츠와 함께 작동합니다. 또한 이 데이터를 복사 및 동기화하기 위해 사용자 지정된 프로세스를 구현할 필요가 없습니다.

## <a name="how-retention-settings-work-with-content-in-place"></a>보존 설정이 콘텐츠와 함께 작동하는 방법

콘텐츠에 보존 설정이 할당된 경우 해당 콘텐츠는 원래 위치에 그대로 유지됩니다. 사용자는 아무것도 변경된 사항이 없는 것처럼 계속해서 문서나 사서함을 사용하여 작업할 수 있습니다. 그러나 보존 정책에 포함되는 콘텐츠를 편집하거나 삭제하는 경우 해당 콘텐츠의 사본은 자동으로 보존됩니다.
  
- SharePoint 및 OneDrive 사이트의 경우: 사본은 **자료 보존** 라이브러리에 보존됩니다.

- Exchange 사서함의 경우: **복구 가능한 항목** 폴더에 사본이 보존됩니다. 

- Teams 및 채널 및 Yammer 메시지의 경우: 사본은 Exchange **복구 가능한 항목** 폴더 내에 하위 폴더로 **SubstrateHolds** 라는 이름의 숨겨진 폴더에 보존됩니다.

> [!NOTE]
> 자료 보존 라이브러리는 사이트의 저장소 할당량에서 제외되지 않은 저장소를 사용합니다. SharePoint 및 Microsoft 365 그룹에 대한 보존 설정을 사용하는 경우 저장소를 늘려야 할 수 있습니다.
> 
대부분의 사용자는 해당 보안 위치와 보존된 콘텐츠를 볼 수 없습니다. 대부분의 경우 사용자는 해당 콘텐츠에 보존 설정이 적용되어 있다는 사실을 알 필요도 없습니다.

다양한 워크로드에 대해 보존 설정이 작동하는 방법에 대한 자세한 내용은 다음의 문서를 참조하세요.

- [SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기](retention-policies-sharepoint.md)
- [Microsoft Teams의 보존에 대해 자세히 알아보기](retention-policies-teams.md)
- [Yammer의 보존에 대한 자세한 정보](retention-policies-yammer.md)
- [Exchange의 보존에 대해 자세히 알아보기](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블

보존 설정을 콘텐츠에 할당하려면 **레이블 정책과 함께 보존 정책** 및 **보존 레이블** 을 사용합니다. 이러한 방법 중 하나만 사용하거나 여러 가지를 결합할 수 있습니다.

보존 정책을 사용하여 사이트 또는 사서함 수준에서 콘텐츠에 대해 같은 보존 설정을 할당하고, 보존 레이블을 사용하여 항목 수준(폴더, 문서, 전자 메일)에 보존 설정을 지정합니다.

예를 들어 SharePoint 사이트의 모든 문서를 5년 동안 보존해야 하면, 해당 사이트의 모든 문서에 동일한 보존 레이블을 적용하는 것보다 보존 정책을 사용하여 이 작업을 수행하는 것이 더욱 효율적입니다. 하지만 해당 사이트의 일부 문서는 5년 동안 보존해야 하고 다른 문서는 10년 동안 보존해야 할 때는 보존 정책으로 이 작업을 수행할 수 없습니다. 항목 수준에서 보존 설정을 지정해야 하는 경우에는 보존 레이블을 사용합니다. 

보존 정책과 다르게 보존 레이블의 보존 설정은 콘텐츠가 Microsoft 365 테넌트 내에서 다른 위치로 이동되는 경우에 함께 이동됩니다. 또한, 보존 레이블에는 보존 정책에서는 지원되지 않는 다음과 같은 기능이 있습니다. 
 
- 콘텐츠의 기간 또는 콘텐츠가 마지막으로 수정된 시간 외에도 콘텐츠에 레이블이 지정된 시간으로부터 또는 이벤트를 기반으로 보존 기간을 시작하는 옵션이 있습니다.

- [학습 가능한 분류자](classifier-learn-about.md)를 사용하여 콘텐츠를 레이블로 식별합니다.

- SharePoint 문서에 대해 기본 레이블을 적용합니다.

- 콘텐츠를 영구적으로 삭제하기 전에 검토할 수 있는 [처리 검토](disposition-reviews.md) 를 지원합니다.

- 콘텐츠를 레이블 설정의 일부로 [레코드](records-management.md#records)로 표시하고, 보관 기간이 끝나 콘텐츠가 삭제된 경우 항상  [처리 증명](disposition.md#disposition-of-records) 이 있습니다.

### <a name="retention-policies"></a>보존 정책

보존 정책은 다음 위치에 적용할 수 있습니다.
- Exchange 전자 메일
- SharePoint 사이트
- OneDrive 계정
- Microsoft 365 그룹
- 비즈니스용 Skype
- Exchange 공용 폴더
- Teams 채널 메시지
- Teams 채팅
- Yammer 커뮤니티 메시지
- Yammer 개인 메시지

단일 정책을 여러 위치 또는 특정 위치 또는 사용자에게 효율적으로 적용할 수 있습니다.

보존 기간이 시작되는 경우 또한 콘텐츠를 언제 만들어졌을지 또는 콘텐츠가 마지막으로 수정된 경우에는 파일 및 SharePoint, OneDrive 및 Microsoft 365 그룹 위치에 대해서만 지원되었는지의 경우를 선택할 수도 있습니다.

항목은 보존 정책에 지정된 컨테이너의 보존 설정을 상속합니다. 해당 정책이 콘텐츠를 보존하도록 구성될 때 항목이 컨테이너 외부로 이동되는 경우 해당 항목의 사본은 작업의 보안 위치에 유지됩니다. 그러나 보존 설정은 새 위치의 콘텐츠와 함께 이동되지 않습니다. 필요한 경우 보존 정책 대신 보존 레이블을 사용합니다.

### <a name="retention-labels"></a>보존 레이블

다른 보존 설정이 있어야 하는 다양한 유형의 콘텐츠에는 보존 레이블을 사용합니다. 예제:
  
- 최소 기간 동안 보존해야 하는 세금 양식 
    
- 특정 기간에 도달하면 영구적으로 삭제되어야 하는 보도 자료 
    
- 특정 기간 동안 보존되었다가 영구적으로 삭제되어야 하는 경쟁 연구 자료 
    
- 편집하거나 삭제할 수 없게 레코드로 표시해야 하는 취업 비자 
    
이 모든 경우 보존 레이블을 사용하여 항목 수준(문서 또는 전자 메일)에서 거버넌스 제어에 대한 보존 설정을 적용할 수 있습니다.
  
보존 레이블을 사용하여 다음을 수행할 수 있습니다.
  
- Outlook, 웹용 Outlook, OneDrive, SharePoint 및 Microsoft 365 그룹의 콘텐츠에 **조직의 사용자가 수동으로 보존 레이블을 적용할 수 있도록 합니다**. 대개 사용자가 자신이 작업 중인 콘텐츠의 유형을 가장 잘 알고 있으므로 사용자가 콘텐츠를 분류하고 적절한 보존 설정이 적용되도록 할 수 있습니다. 
    
- 콘텐츠에 다음이 포함된 경우처럼 특정 조건과 일치하는 경우 **콘텐츠에 보존 레이블을 자동으로 적용** 합니다. 
    - 특정 중요한 정보 유형
    - 만든 쿼리와 일치하는 특정 키워드
    - 학습 가능한 분류자에 대한 패턴 일치

- **콘텐츠에 레이블이 지정된 시점부터 보존 기간 시작**(SharePoint 사이트 및 OneDrive 계정의 문서, 일정 항목을 제외한 전자 메일 항목) 이 구성과 함께 보존 레이블을 일정 항목에 적용하는 경우 해당 보존 기간은 보낸 날짜부터 시작됩니다.

- **이벤트가 발생할 때 보존 기간 시작**(예: 직원 퇴사, 계약 만료)

- SharePoint의 **문서 라이브러리, 폴더 또는 문서 집합에 기본 보존 레이블을 적용** 하여 해당 위치에 저장된 모든 문서가 기본 보존 레이블을 상속하도록 합니다.

또한, 보존 레이블은 Microsoft 365 앱과 서비스에서 전자 메일 및 문서의 [레코드 관리](records-management.md)를 지원합니다. 보존 레이블을 사용하여 항목을 기록으로 표시할 수 있습니다. 이 문제가 발생하고 콘텐츠가 Microsoft 365에 남아 있는 경우 레이블은 규정상의 이유로 필요할 수 있는 콘텐츠에 대한 제한을 마련합니다. 자세한 내용은 [허용 또는 차단되는 작업에 대한 제한 사항 비교](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)를 참조하세요.

보존 레이블은 [민감도 레이블](sensitivity-labels.md)과 달리 Microsoft 365 외부로 콘텐츠를 이동해도 유지되지 않습니다.

테넌트에 지원되는 보존 레이블 개수에는 제한이 없습니다. 그러나 10,000은 테넌트에 지원되는 최대 정책의 수이며, 여기에는 레이블뿐만 아니라 보존 정책이 적용되는 정책(보존 레이블 정책과 자동 적용 보존 정책)도 포함됩니다.

#### <a name="classifying-content-without-applying-any-actions"></a>작업을 적용하지 않고 콘텐츠 분류하기

보존 레이블의 주요 용도는 콘텐츠를 보존하거나 삭제하는 것이지만, 보존 또는 기타 작업을 설정하지 않고 보존 레이블을 사용할 수도 있습니다. 이 경우 작업을 적용하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용할 수 있습니다.
  
예를 들어 작업이 없는 "나중에 검토"라는 보존 레이블을 만들고 적용한 다음 해당 레이블을 사용하여 나중에 해당 콘텐츠를 찾을 수 있습니다.
  
![분류 전용으로 레이블 설정](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>보존 레이블을 DLP 정책의 조건으로 사용하기

SharePoint의 문서에 대한 DLP(데이터 손실 방지) 정책에서 보존 레이블을 조건으로 지정할 수 있습니다. 예를 들어 문서에 지정된 보존 레이블이 적용된 경우, 문서를 조직 외부에 공유하지 못하도록 DLP 정책을 구성합니다.

자세한 내용은 [보존 레이블을 DLP 정책의 조건으로 사용하기](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)를 참조하세요.

#### <a name="retention-labels-and-policies-that-apply-them"></a>보존 레이블과 보존 레이블을 적용하는 정책 

보존 레이블을 게시하면 관리자 및 사용자가 콘텐츠에 적용할 수 있게 해주는 **보존 레이블 정책** 에 포함됩니다. 다음의 다이어그램은 아래의 사항을 보여줍니다.

1. 단일 보존 레이블이 여러 보존 레이블 정책에 포함될 수 있습니다.

2. 보존 레이블 정책이 보존 레이블을 게시할 위치를 지정합니다. 동일한 위치가 여러 보존 레이블 정책에 포함될 수 있습니다.

![위치를 지정하는 레이블 정책에 보존 레이블을 추가하는 방법](../media/retention-labels-and-policies.png)

또한 단일 보존 레이블을 사용하여 하나 이상의 **보존 레이블 자동 적용 정책** 을 만들 수 있습니다. 이 정책을 사용하면 정책에서 지정하는 조건이 충족될 경우 보존 레이블이 자동으로 적용됩니다.

#### <a name="retention-label-policies-and-locations"></a>보존 레이블 정책 및 위치

보존 레이블이 수행하는 작업에 따라, 다양한 유형의 보존 레이블을 여러 다른 위치에 게시할 수 있습니다.
  
| 보존 레이블이 | 레이블 정책을 적용할 수 있는 위치 |
|:-----|:-----|
|관리자 및 최종 사용자에게 게시됨  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 그룹  <br/> |
|중요한 정보 유형 또는 학습 가능한 분류자를 기반으로 자동 적용됨  <br/> |Exchange(모든 사서함만), SharePoint, OneDrive  <br/> |
|쿼리에 따라 자동 적용  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 그룹  <br/> |
   
Exchange에서 자동으로 적용되는 보존 레이블은 현재 사서함에 있는 모든 항목(미사용 데이터)이 아닌 새로 전송된 메시지(전송 중인 데이터)에만 적용됩니다. 또한, 중요한 정보 유형과 학습 가능한 분류자에 대한 자동 적용 보존 레이블은 모든 사서함에만 적용되며, 특정 사서함을 선택할 수 없습니다.
  
Exchange 공용 폴더, Skype, Teams 및 Yammer 메시지는 보존 레이블을 지원하지 않습니다. 해당 위치에서 콘텐츠를 보존하고 삭제하려면 보존 정책을 대신 사용하세요.

#### <a name="only-one-retention-label-at-a-time"></a>한 번에 하나의 보존 레이블만

전자 메일 또는 문서에는 한 번에 하나의 보존 레이블만 할당할 수 있습니다. 보존 레이블은 최종 사용자나 관리자가 [수동으로](create-apply-retention-labels.md#manually-apply-retention-labels) 적용하거나 다음 방법 중 하나를 사용하여 자동으로 적용할 수 있습니다.

- [자동 적용 레이블 정책](apply-retention-labels-automatically.md)
- [SharePoint Syntex용 문서 이해 모델](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- [SharePoint용 기본 레이블](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 또는 [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)
- [Outlook 규칙](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

표준 보존 레이블의 경우(항목을 [레코드 또는 규제 레코드](records-management.md#records)로 표시하지 않음):

- 관리자 및 최종 사용자는 콘텐츠에 적용된 기존 보존 레이블을 수동으로 변경하거나 제거할 수 있습니다. 

- 콘텐츠에 이미 보존 레이블이 적용된 경우 기존 레이블은 자동으로 제거되거나 다른 보존 레이블로 대체되지 않습니다. 한 가지 예외: 기존 레이블이 기본 레이블로 적용되었습니다.
    
    기본 레이블을 사용하여 적용될 때 레이블 동작에 대한 자세한 내용은 다음을 참조하세요.
    - Sharepoint의 기본 레이블: [SharePoint에서 기본 레이블을 사용하는 경우 레이블 동작](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)
    - Outlook의 기본 레이블: [Outlook 폴더에 기본 보존 레이블 적용](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)

- 보존 레이블을 적용할 수 있는 자동 적용 레이블 정책이 여러 개이고, 콘텐츠가 여러 정책의 조건을 충족하는 경우 가장 오래된 자동 적용 레이블 정책(작성 날짜 기준)의 보존 레이블이 적용됩니다.

보존 레이블이 항목을 레코드 또는 규제 레코드로 표시하는 경우 이러한 레이블은 자동으로 변경되지 않습니다. 컨테이너 관리자만 항목을 레코드로 표시하는 보존 레이블을 수동으로 변경하거나 제거할 수 있지만, 규제 레코드는 변경할 수 없습니다. 자세한 내용은 [허용 또는 차단되는 작업에 대한 제한 사항 비교](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)를 참조하세요.

#### <a name="monitoring-retention-labels"></a>보존 레이블 모네터링

Microsoft 365 규정 준수 센터에서 **데이터 분류** > **개요** 를 사용하여 보존 레이블이 테넌트에게 어떻게 사용되고 있는지 모니터링 하고 레이블 항목의 위치를 식별합니다. 필수 구성 요소를 비롯한 더 자세한 내용은 [데이터 알기 - 데이터 분류 개요](data-classification-overview.md)를 참조하세요.

그런 다음 [콘텐츠 탐색기](data-classification-content-explorer.md) 및 [활동 탐색기](data-classification-activity-explorer.md)를 사용하여 세부 정보로 드릴 다운할 수 있습니다.

> [!TIP]
>훈련가능한 분류자 및 민감한 정보 유형 등 다른 데이터 분류 인사이트를 사용하여 보존하거나 삭제 혹은 기록으로 관리해야 하는 콘텐츠를 식별 하는 것이 좋습니다.

Office 365 보안 및 규정 준수 센터에는 **정보 거버넌스** > **대시보드** 및 **정보 거버넌스** > **레이블 활동 탐색기** 에서 더 자세한 정보에 보존 레이블에 해당하는 개요 정보가 있습니다. 이 오래 된 관리 센터에서 보존 레이블을 모니터링 하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.
- [데이터 거버넌스 보고서 보기](view-the-data-governance-reports.md)
- [데이터 분류 시작하기](data-classification-overview.md)
- [문서의 레이블 활동 보기](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a>콘텐츠 검색을 사용하여 특정 보존 레이블을 사용하는 모든 콘텐츠 찾기

사용자가 콘텐츠에 보존 레이블을 적용하거나 레이블이 자동 적용된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블이 적용된 모든 콘텐츠를 찾을 수 있습니다.

콘텐츠 검색을 만들 때 **보존 레이블** 조건을 선택한 다음 보존 레이블 이름을 전체 또는 일부만 입력하고 와일드 카드를 사용합니다. 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.
  
![보존 레이블 조건](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블의 기능 비교하기

다음 표를 사용하여 기능을 기반으로 보존 정책을 사용할지 또는 보존 레이블을 사용할지를 식별하는 데 도움을 받을 수 있습니다.

|기능|보존 정책 |보존 레이블|
|:-----|:-----|:-----|:-----|
|보존 후 삭제, 보존만 또는 삭제만 할 수 있는 보존 설정 |예 |예 |
|워크로드 지원됨:  <br />- Exchange <br />- SharePoint <br />- OneDrive <br />- Microsoft 365 그룹 <br />- 비즈니스용 Skype <br />- Teams<br />- Yammer|<br /> 예 <br /> 예 <br /> 예 <br /> 예 <br /> 예 <br /> 예 <br /> 예 | <br /> 예, 공용 폴더 제외 <br /> 예 <br /> 예 <br /> 예 <br /> 아니요 <br /> 아니요 <br /> 아니요 |
|자동으로 보존 적용됨 | 예 | 예 |
|조건을 기준으로 보존 적용 <br /> -중요한 정보 유형, KQL 쿼리 및 키워드, 교육 가능한 분류자| 아니요 | 예 |
|수동으로 보존 적용됨 | 아니요 | 예 |
|최종 사용자를 위한 UI 존재 | 아니요 | 예 |
|콘텐츠를 이동해도 유지됨 | 아니요 | 예, Microsoft 365 테넌트 내에서 지원됩니다. |
|항목을 레코드로 선언| 아니요 | 예 |
|레이블이 지정되거나 이벤트를 기반으로 보존 기간 시작 | 아니요 | 예 |
|처리 검토 | 아니요| 예 |
|최대 7년 동안 처리 증명 | 아니요 |예, 항목이 레코드로 선언되는 경우|
|감사 관리 활동| 예 | 예|
|보존될 항목 식별: <br /> - 콘텐츠 검색 <br /> - 데이터 분류 페이지, 콘텐츠 탐색기, 활동 탐색기 | <br /> 아니요 <br /> 아니요 | <br /> 예 <br /> 예|

보존 정책과 보존 레이블을 모두 보완 보존 방법으로 사용할 수 있습니다. 예제:

1. 콘텐츠를 마지막으로 수정한 후 5년이 지나면 콘텐츠를 자동으로 삭제하는 보존 정책을 만들고 구성하여, 모든 OneDrive 계정에 정책을 적용합니다.

2. 콘텐츠를 영구적으로 유지하는 보존 레이블을 만들고 구성하여, 모든 OneDrive 계정에 게시하는 레이블 정책에 추가합니다. 5년 후에 수정하지 않으면 자동 삭제에서 제외되어야 하는 특정 문서에 이 레이블을 수동으로 적용하는 방법을 사용자에게 설명합니다.

보존 정책과 보존 레이블이 함께 작동하는 방식과 결합된 결과를 결정하는 방법에 대한 자세한 내용은 보존 원칙과 우선하는 항목을 설명하는 다음 섹션을 참조하세요.

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>보존 원칙 또는 우선하는 항목

보존 레이블과 달리 동일한 컨텐츠에 둘 이상의 보존 정책을 적용할 수 있습니다. 각 보존 정책으로 인해 보존 작업과 삭제 작업이 발생할 수 있습니다. 또한 해당 항목은 보존 레이블에서 이러한 작업을 수행할 수도 있습니다.

이 시나리오에서 항목이 서로 충돌할 수 있는 여러 보존 설정을 적용할 수 있는 경우 결과를 결정하는 데 우선되는 항목은 무엇인가요?

결과적으로 단일 보존 정책 또는 단일 보존 레이블이 승리하는 것이 아니라 항목이 유지되는 기간(해당되는 경우)과 항목이 삭제되는 시기(해당되는 경우)가 됩니다. 이 두 작업은 항목에 적용되는 모든 보존 설정으로부터 서로 독립적으로 계산됩니다.

예를 들어 항목은 삭제 전용 작업에 대해 구성된 보존 정책 하나와 유지했다가 삭제하도록 구성된 다른 보존 정책의 적용을 받을 수 있습니다. 따라서 이 항목에는 보존 작업이 하나만 있고 삭제 작업이 두 개 있습니다. 보존 및 삭제 작업이 서로 충돌하고 두 삭제 작업의 날짜가 충돌할 수 있습니다. 결과를 파악하기 위해서는 보존 원칙을 적용해야 합니다.

높은 수준에서는 보존이 항상 삭제보다 우선하며 가장 긴 보존 기간이 우선합니다. 이러한 두 가지 간단한 규칙은 항상 항목을 보존하는 기간을 결정합니다.

항목이 삭제되는 시기를 결정하는 몇 가지 요인이 더 있습니다. 여기에는 보존 레이블의 삭제 작업이 보존 정책의 삭제 작업보다 항상 우선합니다.

다음 흐름을 사용하여 각 수준이 위에서 아래로 충돌에 대한 타이브레이커 역할을 하는 단일 항목의 보존 및 삭제 결과를 이해하세요. 추가 충돌이 없기 때문에 첫 번째 수준에서 결과를 확인하는 경우에는 다음 수준으로 진행할 필요가 없습니다.

> [!IMPORTANT]
> 보존 레이블을 사용하는 경우 다음을 수행합니다. 이 흐름을 사용하여 동일한 항목에 대한 여러 보존 설정의 결과를 결정하기 전에 [적용되는 보존 레이블](#only-one-retention-label-at-a-time)을 알고 있어야 합니다.

![보존 원칙 다이어그램](../media/principles-of-retention.png)
  
네 가지 수준에 대한 설명:
  
1. **삭제보다 보존 우선.** 보존 설정이 있는 컨텐츠도 영구적으로 삭제되지 않습니다.  
    
    예: 전자 메일 메시지는 3년 후 항목을 삭제하도록 구성된 Exchange용 보존 정책의 적용을 받으며, 5년 동안 항목을 보존하도록 구성된 보존 레이블도 적용됩니다.
    
    전자 메일 메시지는 삭제보다 보존 작업이 우선하므로 5년 동안 보존됩니다. 전자 메일 메시지는 삭제 작업이 지연되어 5년 후에 삭제됩니다.

2. **가장 긴 보존 기간 우선.** 콘텐츠가 다른 기간 동안 콘텐츠를 보존하는 여러 보존 설정의 적용을 받는 경우, 가장 긴 보존 기간이 끝날 때까지 콘텐츠는 보존됩니다.
    
    예: 마케팅 SharePoint 사이트의 문서는 두 가지 보존 정책을 따릅니다. 첫 번째 보존 정책은 모든 SharePoint 사이트에 대해 5년 동안 항목을 보존하도록 구성됩니다. 두 번째 보존 정책은 특정 SharePoint 사이트에 대해 10년 동안 항목을 보존하도록 구성됩니다.
    
    이 마케팅 SharePoint 사이트의 문서는 보존 기간이 가장 길기 때문에 10년 동안 보존됩니다.

3. **암시적 포함보다 명시적 포함이 우선됩니다.** 항목을 삭제할 시기를 결정하는 데 적용됩니다. 
    
    1. 보존 설정은 컨테이너에서 암시적으로 할당되지 않고 개별 항목에 적용되기 때문에 보존 정책과 비교하여 보존 레이블(그러나 적용됨)은 명시적 보존을 제공합니다. 즉, 보존 레이블의 삭제 작업이 항상 보존 정책의 삭제 작업보다 우선합니다.
        
        예: 문서는 삭제 작업이 각각 5년 및 10년인 두 개의 보존 정책과 삭제 작업이 7년인 보존 정책의 적용을 받습니다.
        
        보존 레이블에서 삭제 작업이 우선하기 때문에 문서는 7년 후에 삭제됩니다.
    
    2. 보존 정책만 있는 경우: 위치에 대한 보존 정책이 포함 구성(예: Exchange 전자 메일의 특정 사용자)을 사용하도록 범위가 지정된 경우 해당 보존 정책이 동일한 위치에 대한 범위 없는 보존 정책보다 우선합니다.
        
        범위 없는 보존 정책은 특정 인스턴스를 지정하지 않고 위치를 선택하는 정책입니다. 예를 들어 **Exchange 전자 메일** 과 **모든 받는 사람** 의 기본 설정은 범가 지정되지 않는 보존 정책입니다. 또는 **SharePoint 사이트** 와 **모든 사이트** 의 기본 설정입니다. 보존 정책의 범위가 지정되면 이 수준에서 동일한 우선 순위를 가집니다.
        
        예 1: 전자 메일 메시지는 두 가지 보존 정책의 적용을 받습니다. 첫 번째 보존 정책은 범위를 해제하고 10년 후 항목을 삭제합니다. 두 번째 보존 정책은 특정 사서함으로 범위를 지정하고 5년 후 항목을 삭제합니다.
        
        범위가 지정되지 않은 보존 정책보다 범위가 지정된 보존 정책의 삭제 작업이 우선하기 때문에 5년 후 전자 메일 메시지가 삭제됩니다.
        
        예 2: 사용자의 OneDrive 계정에 있는 문서는 두 개의 보존 정책을 따릅니다. 첫 번째 보존 정책은 이 사용자의 OneDrive 계정을 포함하도록 범위가 지정되며 10년 후 삭제 작업이 수행됩니다. 두 번째 보존 정책은 이 사용자의 OneDrive 계정을 포함하도록 범위가 지정되며 7년 후 삭제 작업이 수행됩니다.
        
        두 보존 정책의 범위가 모두 지정되어 있으므로 문서가 삭제되는 시기를 이 수준에서 결정할 수 없습니다.

4. **가장 짧은 삭제 기간이 우선합니다.** 보존 정책에서 항목이 삭제되고 이전 수준에서 결과를 확인할 수 없는 시기를 결정하는 데 해당됩니다. 콘텐츠는 가장 짧은 보존 기간이 끝나면 삭제됩니다.
    
    예: 사용자의 OneDrive 계정에 있는 문서는 두 개의 보존 정책을 따릅니다. 첫 번째 보존 정책은 이 사용자의 OneDrive 계정을 포함하도록 범위가 지정되며 10년 후 삭제 작업이 수행됩니다. 두 번째 보존 정책은 이 사용자의 OneDrive 계정을 포함하도록 범위가 지정되며 7년 후 삭제 작업이 수행됩니다.
    
    이 문서는 이 두 가지 보존 정책의 보존 기간이 가장 짧기 때문에 7년 후에 삭제됩니다.

eDiscovery 보존 대상 항목도 보존의 첫 번째 원칙에 속하므로 보존 정책 또는 보존 레이블로 삭제할 수 없습니다. 이 보류가 해제되면 유지 원칙이 계속 적용됩니다. 예를 들어, 만료되지 않은 보존 기간이나 지연된 삭제 작업이 적용될 수 있습니다.

보존 및 삭제 작업을 결합하는 보다 복잡한 예는 다음과 같습니다.

1. 항목에 적용되는 보존 설정은 다음과 같습니다.
    
    - 5년 후 삭제 전용 보존 정책
    - 3년 동안 보존한 뒤 삭제되는 보존 정책
    - 7년간 유지되는 보존 레이블
    
    **결과**: 이 항목은 삭제보다 보존이 우선하며 보존 기간이 가장 길기 때문에 7년 동안 보존됩니다. 이 보존 기간이 끝나면 항목이 유지되는 동안 지연된 보존 정책에서 삭제 작업이 수행되기 때문에 항목이 삭제됩니다.
    
    삭제 작업에 대한 두 보존 정책의 날짜가 다르지만, 항목을 삭제할 수 있는 가장 빠른 보존 기간은 두 삭제 날짜보다 긴 가장 긴 보존 기간의 끝에 있습니다. 이 예제에서는 삭제 날짜에 대해 해결할 충돌이 없으므로 모든 충돌은 두 번째 수준에서 해결됩니다.

2.  항목에 적용되는 보존 설정은 다음과 같습니다.
    
    - 10년 후에만 삭제되는 범위 없는 보존 정책
    - 5년 동안 보존한 다음 삭제되는 범위 지정 보존 정책
    - 3년 동안 보관했다가 삭제되는 보존 라벨
    
    **결과**: 보존 기간이 가장 긴 항목으로 5년 동안 보존됩니다. 보존 기간이 끝나면 항목이 보존되는 동안 지연된 보존 레이블에서 3년간의 삭제 작업으로 인해 항목이 삭제됩니다. 보존 레이블에서 삭제는 모든 보존 정책에서 삭제되는 것보다 우선합니다. 이 예제에서 모든 충돌은 세 번째 수준에서 해결됩니다.

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a>유지 잠금을 사용하여 정책 변경 제한

일부 조직에서는 보존 정책을 설정한 후에 해제하거나 덜 제한적으로 설정할 수 없도록 SEC(증권 거래 위원회) 규칙 17a-4와 같은 규제 기구에서 정의한 규칙을 준수해야 할 수 있습니다. 

유지 잠금은 조직이 관리자를 비롯하여 누구도 정책을 해제하거나 삭제하거나 덜 제한적으로 설정할 수 없도록 보존 정책 또는 보존 레이블 정책을 잠그므로 관련 규정 요구 사항을 충족할 수 있도록 보장합니다.
  
보존 정책 또는 보존 레이블 정책을 생성한 후에 유지 잠금을 적용합니다. 자세한 내용은 [보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 유지 잠금 사용](retention-preservation-lock.md)을 참조하세요.

## <a name="releasing-a-policy-for-retention"></a>보존 정책 릴리스

보존 정책의 제공에는 유지 잠금이 포함되어 있지 않으므로 언제든지 정책을 삭제할 수 있어 이전에 적용된 보존 설정을 효과적으로 해제할 수 있습니다. 정책을 유지하지만 SharePoint 사이트나 OneDrive 계정을 제거하거나 위치 상태를 해제로 변경하거나 정책을 실행 중지할 수도 있습니다.
 
이러한 작업을 수행할 때 정책의 보존 대상이 되는 SharePoint 또는 OneDrive 콘텐츠는 의도하지 않은 데이터 손실을 방지하기 위해 30일 동안 유지됩니다. 이 30일 유예 기간 동안에는 사이트를 삭제할 수 없으며 삭제된 파일은 보존 보류 라이브러리에 계속 추가되지만 보존 보류 라이브러리를 주기적으로 정리하는 타이머 작업은 이러한 파일에 대해 일시 중단되므로 필요할 경우 복원할 수 있습니다.

보존 보류 라이브러리에 대한 자세한 내용은 [SharePoint 및 단일 드라이브에 대한 보존 작동 방식](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive)을 참조하세요.

유예 기간 동안의 동작으로 인해 정책을 다시 실행하거나 30일 이내에 위치 상태를 다시 켜면 이 기간 동안 영구 데이터 손실 없이 정책이 다시 시작됩니다.

## <a name="auditing-retention-configuration"></a>감사 보존 구성

[감사가 설정되면](turn-audit-log-search-on-or-off.md) 보존 정책과 보존 레이블 관리자 작업이 감사 로그에 저장됩니다. 예를 들어, 보존 정책이나 레이블을 만들고, 구성하고 삭제 할 때 감사 이벤트를 만듭니다. 전체 목록은 [보존 정책 및 보존 레이블 활동](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)을 참조하세요.

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블의 PowerShell cmdlet

보존 정책 cmdlet을 사용하려면 먼저 [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)해야 합니다. 그런 다음, 다음 cmdlet 중 하나를 사용하세요.

- [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a>보존 정책 및 보존 레이블 또는 eDiscovery 보류를 사용하는 경우

[eDiscovery 사례를 사용하여 생성한 보류](create-ediscovery-holds.md)와 보존 설정 둘 다에서 데이터가 영구적으로 삭제되는 것을 방지할 수 있지만 다른 시나리오에 맞게 설계되었습니다. 차이점을 이해하고 사용할 항목을 결정하는 데 도움을 받으려면 다음 지침을 활용하세요.

- 보존 정책 및 보존 레이블에 지정할 보존 설정은 장기적인 정보 관리 전략에 맞게 설계되어 규정 준수 요구 사항에 대한 데이터를 보존하거나 삭제합니다. 일반적으로 범위가 넓으며, 개별 사용자보다는 위치와 콘텐츠에 중점을 둡니다. 추가 관리자 개입 없이 콘텐츠를 자동으로 삭제하는 옵션을 사용하여 보존 기간의 시작과 끝을 구성할 수 있습니다.

- eDiscovery를 위한 보류(Core eDiscovery 또는 Advanced eDiscovery 사례)는 제한된 기간 동안 법적 조사를 위해 데이터를 보존하도록 설계되었습니다. 범위는 확인된 사용자가 소유한 콘텐츠에 따라 다릅니다. 보존 기간의 시작과 끝은 구성할 수 없지만 보류가 해제될 때 콘텐츠를 자동으로 삭제하는 옵션이 없으면 개별 관리자 작업에 따라 달라집니다.

보류와 보존을 비교하는 요약:

|고려 사항|보존 |eDiscovery 보존|
|:-----|:-----|:-----|:-----|
|비즈니스 요구 사항: |규정 준수 |법률 정보 |
|시간 범위: |장기 |단기 |
|포커스: |광범위, 내용 기반 |특정, 사용자 기반 |
|시작 및 종료일 구성 가능: |예 |아니요 |
|콘텐츠 삭제: |예(선택 사항) |아니요 |
|관리 오버 헤드: |낮음 |높음 |

콘텐츠가 보존 설정과 eDiscovery 보류의 영향을 모두 받는 경우 eDiscovery 보류의 콘텐츠 보존이 항상 우선합니다. 이렇게 하면 [보존 원칙](#the-principles-of-retention-or-what-takes-precedence)은 관리자가 보류를 수동으로 릴리스할 때까지 데이터가 유지되기 때문에 eDiscovery 보류로 확장됩니다. 그러나 이러한 우선 순위에도 불구하고 장기적인 정보 거버넌스에 eDiscovery 보류를 사용하지 않습니다. 데이터 자동 삭제가 염려되는 경우 항목을 영구적으로 보존하도록 보존 설정을 구성하거나 보존 레이블과 함께 [처리 검토](disposition.md#disposition-reviews)를 사용할 수 있습니다.

오래된 eDiscovery 도구를 사용하여 데이터를 보존하는 경우, 다음 리소스를 참조하세요.

- Exchange: 
    - [원본 위치 유지 및 소송 보존](https://go.microsoft.com/fwlink/?linkid=846124)
    - [Exchange Online 사서함의 보류 유형을 식별하는 방법](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- SharePoint 및 OneDrive: 
    - [eDiscovery 센터에서 사례에 콘텐츠 추가 및 원본 우 위치 유지](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [eDiscovery 도구의 사용 중지](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>이전 기능 대신 보존 정책 및 보존 레이블 사용하기

정보 거버넌스를 위해 Microsoft 365에서 콘텐츠를 사전에 보존하거나 삭제해야 하는 경우에는 다음과 같은 이전 기능 대신 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다.

현재 이러한 이전 기능을 사용하는 경우 해당 기능은 보존 정책 및 레이블과 함께 계속해서 작동합니다. 하지만 앞으로는 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다. Microsoft 365 전체에서 콘텐츠의 보존 및 삭제를 중앙에서 관리하는 단일 메커니즘을 제공합니다.

**Exchange Online의 이전 기능:**

- [MRM(메시징 레코드 관리)](https://go.microsoft.com/fwlink/?linkid=846126)이라고도 하는 [보존 태그 및 보존 정책](https://go.microsoft.com/fwlink/?linkid=846125) (삭제만 해당)

**SharePoint 및 OneDrive의 이전 기능:**

- [문서 삭제 정책](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)(삭제만 해당)
    
- [현재 위치 레코드 관리 구성](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (보존만 해당) 
    
- [사이트 폐쇄 및 삭제에 대한 정책 사용](https://support.microsoft.com/ko-KR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (삭제만 해당)
    
- [정보 관리 정책](intro-to-info-mgmt-policies.md) (삭제만 해당)
     
콘텐츠 유형 정책 또는 정보 관리 정책에 대해 SharePoint 사이트를 구성하여 목록이나 라이브러리에 대한 콘텐츠를 보존하는 경우 보존 정책이 유효하는 동안 해당 정책은 무시됩니다. 

## <a name="related-information"></a>관련 정보

- [SharePoint Online 제한 사항](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams의 제한 사항 및 사양](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [정보 거버넌스 및 레코드 관리를 위해 규정 요구 사항을 충족할 수 있도록 도움이 되는 리소스](retention-regulatory-requirements.md)

## <a name="configuration-guidance"></a>구성 지침

보존 정책을 만들 준비가 되었으면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.

보존 레이블을 만들고 적용하려면:
- [보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)
- [보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)

