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
search.appverid:
- MOE150
- MET150
description: 필요한 항목을 보존하고 필요하지 않은 항목을 삭제하는 데 도움을 주는 보존 정책과 보존 레이블에 대해 알아봅니다.
ms.openlocfilehash: b0ce412609ac9c7084c1c598a327cde7c055c101
ms.sourcegitcommit: 919b5d0f33b41b4beaca5fbb06e1c75d65027b7e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46757571"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블에 대해 자세히 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

대부분의 조직에서는 전자 메일, 문서, 인스턴트 메시지 등을 비롯하여 데이터의 양과 복잡성이 계속해서 매일 증가하고 있습니다. 이러한 정보를 효과적으로 관리하거나 제어하는 일은 다음 작업을 수행해야 하므로 중요합니다.
  
- 최소 기간 동안 콘텐츠를 보존하도록 요구하는 **산업 규정 및 내부 정책을 사전에 준수**합니다. 예를 들어 Sarbanes-Oxley Act는 7년 동안 특정 유형의 콘텐츠를 보존하도록 요구할 수 있습니다. 
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

콘텐츠에 보존 설정이 할당된 경우 해당 콘텐츠는 원래 위치에 그대로 유지됩니다. 사용자는 아무것도 변경된 사항이 없는 것처럼 계속해서 문서나 사서함을 사용하여 작업할 수 있습니다. 그러나 사용자가 보존 정책에 포함된 콘텐츠를 편집하거나 삭제하는 경우에는 해당 보존 설정이 적용된 시점의 콘텐츠 사본이 자동으로 보존됩니다.
  
- SharePoint 및 OneDrive 사이트의 경우: 사본은 **자료 보존** 라이브러리에 보존됩니다.

- Exchange 사서함의 경우: **복구 가능한 항목** 폴더에 사본이 보존됩니다. 

- Teams 채널 및 채팅 메시지의 경우: 사본은 Exchange **복구 가능한 항목** 폴더 내에 하위 폴더로 **SubstrateHolds**라는 이름의 숨겨진 폴더에 보존됩니다.

> [!NOTE]
> 자료 보존 라이브러리는 사이트의 저장소 할당량에서 제외되지 않은 저장소를 사용합니다. SharePoint 및 Microsoft 365 그룹에 대한 보존 설정을 사용하는 경우 저장소를 늘려야 할 수 있습니다.
> 
대부분의 사용자는 해당 보안 위치와 보존된 콘텐츠를 볼 수 없습니다. 대부분의 경우 사용자는 해당 콘텐츠에 보존 설정이 적용되어 있다는 사실을 알 필요도 없습니다.

다양한 워크로드에 대해 보존 설정이 작동하는 방법에 대한 자세한 내용은 다음의 문서를 참조하세요.

- [SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기](retention-policies-sharepoint.md)
- [Microsoft Teams의 보존에 대해 자세히 알아보기](retention-policies-teams.md)
- [Exchange의 보존에 대해 자세히 알아보기](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블

보존 정책과 보존 레이블을 모두 사용하여 보존 설정을 콘텐츠에 할당할 수 있습니다. 

보존 정책을 사용하여 사이트 또는 사서함 수준에서 콘텐츠에 대해 같은 보존 설정을 할당하고, 보존 레이블을 사용하여 항목 수준(폴더, 문서, 전자 메일)에 보존 설정을 지정합니다.

예를 들어 SharePoint 사이트의 모든 문서를 5년 동안 보존해야 하면, 해당 사이트의 모든 문서에 동일한 보존 레이블을 적용하는 것보다 보존 정책을 사용하여 이 작업을 수행하는 것이 더욱 효율적입니다. 하지만 해당 사이트의 일부 문서는 5년 동안 보존해야 하고 다른 문서는 10년 동안 보존해야 할 때는 보존 정책으로 이 작업을 수행할 수 없습니다. 항목 수준에서 보존 설정을 지정해야 하는 경우에는 보존 레이블을 사용합니다. 

보존 정책과 달리 보존 레이블의 보존 설정은 콘텐츠를 다른 Microsoft 365 위치로 복사하거나 이동해도 유지됩니다. 또한, 보존 레이블에는 보존 정책에서는 지원되지 않는 다음과 같은 기능이 있습니다. 
 
- 콘텐츠의 기간 또는 콘텐츠가 마지막으로 수정된 시간 외에도 콘텐츠에 레이블이 지정된 시간으로부터 또는 이벤트를 기반으로 보존 기간을 시작하는 옵션이 있습니다.

- [학습 가능한 분류자](classifier-getting-started-with.md)를 사용하여 콘텐츠를 레이블로 식별합니다.

- SharePoint 문서에 대해 기본 레이블을 적용합니다.

- 콘텐츠를 영구적으로 삭제하기 전에 검토할 수 있는 [처리 검토](disposition-reviews.md) 를 지원합니다.

- 콘텐츠를 레이블 설정의 일부로 [레코드](records.md)로 표시하고, 보관 기간이 끝나 콘텐츠가 삭제된 경우 항상  [처리 증명](disposition.md#disposition-of-records) 이 있습니다.

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

단일 정책을 여러 위치 또는 특정 위치 또는 사용자에게 효율적으로 적용할 수 있습니다.
    
모든 콘텐츠 또는 특정 조건을 충족하는 콘텐츠(예: 특정 키워드 또는 [중요한 정보 유형](sensitive-information-type-entity-definitions.md)을 포함하는 콘텐츠)에 정책을 적용할 수 있습니다.

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>보존 잠금을 사용하여 규정 요구 사항을 준수합니다.

일부 조직에서는 보존 정책을 설정한 후에 해제하거나 제한 사항이 거의 없이 설정할 수 없는 SEC(증권 거래 위원회) 규칙 17a-4와 같은 규제 기구에서 정의한 규칙을 준수해야 할 수 있습니다. 

보존 잠금은 조직이 관리자를 비롯하여 어떠한 사용자도 정책을 해제하거나, 삭제하거나, 제한 사항이 거의 없이 설정할 수 없도록 보존 정책을 잠그기 때문에 관련 규정 요구 사항을 충족할 수 있도록 보장합니다.
  
보존 정책이 잠기는 경우:

- 아무도 끌 수 없습니다.
- 위치는 추가할 수 있지만 제거할 수는 없습니다.
- 보존 기간 동안에 해당 정책이 적용된 콘텐츠를 수정하거나 삭제할 수 없습니다.
- 보존 기간을 연장할 수 있지만 줄일 수는 없습니다.

요약하면 잠겨 있는 정책은 늘리거나 확장할 수 있지만 줄이거나 해제할 수 없습니다.
  
> [!IMPORTANT]
> 보존 정책을 잠그기 전에 해당 정책의 영향을 이해하고 조직에서 규정 요구 사항을 충족하는 데 해당 정책이 필요한지 여부를 확인하는 것이 중요합니다. 보존 잠금이 적용된 후에는 관리자가 보존 정책을 사용하지 않도록 설정하거나 삭제할 수 없습니다.

보존 잠금은 PowerShell을 사용하여 보존 정책을 만든 후 적용하는 것입니다. 지침은 [보존 정책 만들기 및 구성하기](create-retention-policies.md)에 포함되어 있습니다.

#### <a name="releasing-a-retention-policy"></a>보존 정책 해제

보존 정책에 보존 잠금이 없으면 언제든지 보존 정책을 끄거나 삭제할 수 있습니다. 

이렇게 하면 자료 보존 라이브러리에 보존되어 있는 모든 SharePoint 또는 OneDrive 콘텐츠가 바로 영구적으로 삭제되지 않습니다. 실수로 데이터가 손실되는 것을 방지하기 위해 30일간의 유예 기간이 있습니다. 이 기간에는 자료 보존 라이브러리에서 해당 정책에 대한 콘텐츠 만료가 발생하지 않으므로 필요한 경우 콘텐츠를 복원할 수 있습니다. 또한 유예 기간에 이 콘텐츠를 수동으로 삭제할 수 없습니다.

유예 기간에 보존 정책을 다시 켤 수 있고 해당 정책에 대한 콘텐츠가 삭제되지 않습니다.

SharePoint 및 OneDrive의 30일간의 유예 기간은 Exchange의 30일 지연 기간에 해당합니다. 자세한 내용은 [지연되는 사서함 관리](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)를 참조하세요.

### <a name="retention-labels"></a>보존 레이블

다른 보존 설정이 있어야 하는 다양한 유형의 콘텐츠에는 보존 레이블을 사용합니다. 예제:
  
- 최소 기간 동안 보존해야 하는 세금 양식 
    
- 특정 기간에 도달하면 영구적으로 삭제되어야 하는 보도 자료 
    
- 특정 기간 동안 보존되었다가 영구적으로 삭제되어야 하는 경쟁 연구 자료 
    
- 편집하거나 삭제할 수 없게 레코드로 표시해야 하는 취업 비자 
    
이 모든 경우 보존 레이블을 사용하여 항목 수준(문서 또는 전자 메일)에서 거버넌스 제어에 대한 보존 설정을 적용할 수 있습니다.
  
보존 레이블을 사용하여 다음을 수행할 수 있습니다.
  
- Outlook, 웹용 Outlook, OneDrive, SharePoint 및 Microsoft 365 그룹의 콘텐츠에 **조직의 사용자가 수동으로 보존 레이블을 적용할 수 있도록 합니다**. 대개 사용자가 자신이 작업 중인 콘텐츠의 유형을 가장 잘 알고 있으므로 사용자가 콘텐츠를 분류하고 적절한 보존 설정이 적용되도록 할 수 있습니다. 
    
- 콘텐츠에 다음이 포함된 경우처럼 특정 조건과 일치하는 경우 **콘텐츠에 보존 레이블을 자동으로 적용**합니다. 
    - 특정 중요한 정보 유형
    - 만든 쿼리와 일치하는 특정 키워드
    - 학습 가능한 분류자에 대한 패턴 일치

- **콘텐츠에 레이블이 지정된 시점부터 보존 기간 시작**(SharePoint 사이트 및 OneDrive 계정의 문서, 일정 항목을 제외한 전자 메일 항목) 이 구성과 함께 보존 레이블을 일정 항목에 적용하는 경우 해당 보존 기간은 보낸 날짜부터 시작됩니다.

- **이벤트가 발생할 때 보존 기간 시작**(예: 직원 퇴사, 계약 만료)

- SharePoint의 **문서 라이브러리, 폴더 또는 문서 집합에 기본 보존 레이블을 적용**하여 해당 위치에 저장된 모든 문서가 기본 보존 레이블을 상속하도록 합니다.

또한, 보존 레이블은 Microsoft 365 앱과 서비스에서 전자 메일 및 문서의 [레코드 관리](records-management.md)를 지원합니다. 보존 레이블을 사용하여 콘텐츠를 레코드로 분류할 수 있습니다. 이 문제가 발생하고 콘텐츠가 Microsoft 365에 남아 있는 경우 레이블은 규정상의 이유로 필요할 수 있는 콘텐츠에 대한 제한을 마련합니다. 허용되거나 차단되는 작업을 비교하여 추가 정보를 보려면 [레코드에 대해 알아보기](records.md)를 참조하세요.

보존 레이블은 [민감도 레이블](sensitivity-labels.md)과 달리 Microsoft 365 외부로 콘텐츠를 이동해도 유지되지 않습니다.

테넌트에 지원되는 보존 레이블 개수에는 제한이 없습니다. 그러나 10,000은 테넌트에 지원되는 최대 정책의 수이며, 여기에는 레이블뿐만 아니라 보존 정책이 적용되는 정책(보존 레이블 정책과 자동 적용 보존 정책)도 포함됩니다.

#### <a name="classifying-content-without-applying-any-actions"></a>작업을 적용하지 않고 콘텐츠 분류하기

보존 레이블의 주요 용도는 콘텐츠를 보존하거나 삭제하는 것이지만, 보존 또는 기타 작업을 설정하지 않고 보존 레이블을 사용할 수도 있습니다. 이 경우 작업을 적용하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용할 수 있습니다.
  
예를 들어 작업이 없는 "나중에 검토"라는 보존 레이블을 만들고 적용한 다음 해당 레이블을 사용하여 나중에 해당 콘텐츠를 찾을 수 있습니다.
  
![보존이 해제된 레이블 설정 페이지](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>보존 레이블을 DLP 정책의 조건으로 사용하기

SharePoint의 문서에 대한 DLP(데이터 손실 방지) 정책에서 보존 레이블을 조건으로 지정할 수 있습니다. 예를 들어 문서에 지정된 보존 레이블이 적용된 경우, 문서를 조직 외부에 공유하지 못하도록 DLP 정책을 구성합니다.

자세한 내용은 [보존 레이블을 DLP 정책의 조건으로 사용하기](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)를 참조하세요.

#### <a name="retention-labels-and-policies-that-apply-them"></a>보존 레이블과 보존 레이블을 적용하는 정책 

보존 레이블은 독립적이고, 다시 사용할 수 있는 구성 요소입니다. 보존 레이블 정책의 기본 목적은 보존 레이블 집합을 그룹화하고 해당 레이블을 표시할 위치를 지정하는 것입니다. 그러면 관리자와 사용자가 해당 위치에 해당 레이블을 적용할 수 있습니다.
  
![레이블, 레이블 정책 및 위치 다이어그램](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
보존 레이블을 게시하면 보존 레이블은 보존 레이블 정책에 포함되어 관리자와 사용자가 다음을 선택할 수 있습니다.

- 하나의 보존 레이블이 여러 보존 레이블 정책에 포함될 수 있습니다.

- 보존 레이블 정책이 보존 레이블을 게시할 위치를 지정합니다.

- 하나의 위치가 여러 보존 레이블 정책에 포함될 수도 있습니다.

보존 레이블 정책 외에도 하나의 보존 레이블을 사용하여 하나 이상의 자동 적용 정책을 만들 수 있습니다. 이 정책을 사용하면 정책에서 지정하는 조건이 충족될 경우 보존 레이블이 자동으로 적용됩니다. 

#### <a name="retention-label-policies-and-locations"></a>보존 레이블 정책 및 위치

보존 레이블이 수행하는 작업에 따라, 다양한 유형의 보존 레이블을 여러 다른 위치에 게시할 수 있습니다.
  
| 보존 레이블이 | 레이블 정책을 적용할 수 있는 위치 |
|:-----|:-----|
|관리자 및 최종 사용자에게 게시됨  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 그룹  <br/> |
|중요한 정보 유형 또는 학습 가능한 분류자를 기반으로 자동 적용됨  <br/> |Exchange(모든 사서함만), SharePoint, OneDrive  <br/> |
|쿼리에 따라 자동 적용  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 그룹  <br/> |
   
Exchange에서 자동 적용 보존 레이블은 현재 사서함에 있는 모든 항목(미사용 데이터)이 아닌 새로 전송된 메시지(전송 중인 데이터)에만 적용됩니다. 또한, 중요한 정보 유형과 학습 가능한 분류자에 대한 자동 적용 보존 레이블은 모든 사서함에만 적용되며, 특정 사서함을 선택할 수 없습니다.
  
Exchange 공용 폴더, Skype, Teams 채널 메시지 및 채팅은 보존 레이블을 지원하지 않습니다. 해당 위치에서 콘텐츠를 보존하고 삭제하려면 보존 정책을 대신 사용하세요.

#### <a name="only-one-retention-label-at-a-time"></a>한 번에 하나의 보존 레이블만

전자 메일 또는 문서에는 한 번에 하나의 보존 레이블만 할당할 수 있습니다.
  
- 관리자나 최종 사용자가 수동으로 할당한 보존 레이블의 경우, 할당된 보존 레이블을 제거하거나 변경할 수 있습니다.
    
- 콘텐츠에 자동 적용 레이블이 할당된 경우에는 이 레이블을 게시된 보존 레이블로 바꿀 수 있습니다.
    
- 콘텐츠에 게시된 보존 레이블이 할당된 경우 자동 적용 레이블은 대체되지 않습니다.
    
- 자동 적용 레이블을 할당하는 여러 규칙이 있고 콘텐츠가 여러 규칙의 조건을 충족하는 경우 가장 오래된 규칙에 대한 보존 레이블이 할당됩니다.
    
한 보존 레이블이 적용되는 방법과 그 이유를 이해하려면 레이블을 명시적으로 할당하는 것과 암시적으로 레이블이 할당되는 것의 차이점을 이해하는 것이 좋습니다.

- 레이블 정책에서 적용되는 보존 레이블은 명시적으로 할당됩니다.
- 자동 적용 정책에서 자동으로 적용되는 보존 레이블은 암시적으로 할당됩니다.

명시적으로 할당된 보존 레이블이 암시적으로 할당된 보존 레이블에 우선합니다. 자세한 내용은 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)에 대한 이 페이지의 섹션을 참조하세요.

#### <a name="monitoring-retention-labels"></a>보존 레이블 모네터링

Microsoft 365 규정 준수 센터에서 **데이터 분류** > **개요**를 사용하여 보존 레이블이 테넌트에게 어떻게 사용되고 있는지 모니터링 하고 레이블 항목의 위치를 식별합니다. 필수 구성 요소를 비롯한 더 자세한 내용은 [데이터 알기 - 데이터 분류 개요](data-classification-overview.md)를 참조하세요.

그런 다음 [콘텐츠 탐색기](data-classification-content-explorer.md) 및 [활동 탐색기](data-classification-activity-explorer.md)를 사용하여 세부 정보로 드릴 다운할 수 있습니다.

> [!TIP]
>훈련가능한 분류자 및 민감한 정보 유형 등 다른 데이터 분류 인사이트를 사용하여 보존하거나 삭제 혹은 기록으로 관리해야 하는 콘텐츠를 식별 하는 것이 좋습니다.

Office 365 보안 및 규정 준수 센터에는 **정보 거버넌스** > **대시보드** 및 **정보 거버넌스** > **레이블 활동 탐색기**에서 더 자세한 정보에 보존 레이블에 해당하는 개요 정보가 있습니다. 이 오래 된 관리 센터에서 보존 레이블을 모니터링 하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.
- [데이터 거버넌스 보고서 보기](view-the-data-governance-reports.md)
- [레이블 분석을 통한 레이블 사용량 보기](label-analytics.md)
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
|워크로드 지원됨:  <br />- Exchange <br />- SharePoint <br />- OneDrive <br />- Microsoft 365 그룹 <br />- 비즈니스용 Skype <br />- Teams|<br /> 예 <br /> 예 <br /> 예 <br /> 예 <br /> 예 <br /> 예 | <br /> 예, 공용 폴더 제외 <br /> 예 <br /> 예 <br /> 예 <br /> 아니요 <br /> 아니요  |
|자동으로 보존 적용됨 | 예 | 예 |
|수동으로 보존 적용됨 | 아니요 | 예 |
|최종 사용자를 위한 UI 존재 | 아니요 | 예 |
|콘텐츠를 이동해도 유지됨 | 아니요 | 예, Microsoft 365 내 |
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

콘텐츠에 작업(보존, 삭제 또는 보존 후 삭제) 및 보존 기간이 각기 다른 여러 보존 정책과 보존 레이블이 적용되어 있을 수 있습니다. 우선하는 항목 

높은 수준에서는 보존이 항상 삭제보다 우선하며 가장 긴 보존 기간이 우선합니다. 

그러나 여기에 몇 가지 요소를 더해야 하므로, 다음 흐름을 사용하여 각 수준이 위에서 아래로의 타이 브레이커 역할을 하는 결과를 이해하세요. 결과가 첫 번째 수준에 의해 결정되면 다음 수준으로 진행할 필요가 없습니다. 해당 수준에 대한 규칙에 따라 결과를 확인할 수 없는 경우에만 흐름이 다음 수준으로 이동하여 보존 설정의 우선순위를 결정합니다.

![보존 원칙 다이어그램](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
네 가지 수준에 대한 설명:
  
1. **삭제보다 보존 우선.** 한 보존 정책에서는 3년 후 Exchange 전자 메일을 삭제하도록 구성하지만 다른 보존 정책에서는 5년 동안 Exchange 전자 메일을 보존한 다음 삭제하도록 구성한다고 가정합니다. 3년에 도달하는 모든 콘텐츠는 삭제되고 사용자의 보기에서 숨겨지지만, 콘텐츠가 영구적으로 삭제되는 5년에 도달하기까지는 복구 가능한 항목 폴더에 여전히 보존됩니다. 
2. **가장 긴 보존 기간 우선.** 콘텐츠가 다른 기간 동안 콘텐츠를 보존하는 여러 보존 설정의 적용을 받는 경우, 가장 긴 보존 기간이 끝날 때까지 콘텐츠는 보존됩니다.
    
3. **암시적 포함보다 명시적 포함 우선.** 의미는 다음과 같습니다. 
    
    1. 보존 설정이 포함된 보존 레이블이 사용자에 의해 수동으로 항목(예: Exchange 전자 메일 또는 OneDrive 문서)에 할당된 경우, 해당 보존 레이블이 사이트 또는 사서함 수준에서 할당된 보존 정책이나 문서 라이브러리에 할당된 기본 보존 레이블보다 우선합니다. 예를 들어 명시적 보존 레이블에서 10년 동안 콘텐츠를 보존하기로 구성하지만 사이트에 할당된 보존 정책에서 5년 동안만 콘텐츠를 보존하기로 구성한다면, 보존 레이블이 우선합니다. 자동 적용 보존 레이블은 Microsoft 365에서 자동으로 적용하므로 명시적이 아니라 암시적으로 간주됩니다.
    
    2. 보존 정책에 특정 사용자의 사서함 또는 OneDrive 계정과 같이 특정 위치가 포함되는 경우 해당 보존 정책이 모든 사용자의 사서함 또는 OneDrive 계정에 적용되지만 특히 해당 사용자의 사서함을 포함하지 않는 다른 보존 정책보다 우선합니다.
    
4. **가장 짧은 삭제 기간이 우선합니다.** 마찬가지로 콘텐츠에 보존 기간 없이 콘텐츠를 삭제하는 여러 보존 설정이 적용된 경우, 해당 콘텐츠는 가장 짧은 보존 기간이 끝나면 삭제됩니다. 

마지막으로, 보존 정책 또는 보존 레이블은 eDiscovery에 대해 보류된 모든 콘텐츠를 영구히 삭제할 수 없습니다. 보류가 해제되면 콘텐츠는 다시 워크로드의 보안 위치에서 정리 프로세스의 적용을 받게 됩니다.

## <a name="auditing-retention-configuration"></a>감사 보존 구성

[감사가 설정되면](turn-audit-log-search-on-or-off.md) 보존 정책과 보존 레이블 관리자 작업이 감사 로그에 저장됩니다. 예를 들어, 보존 정책이나 레이블을 만들고, 구성하고 삭제 할 때 감사 이벤트를 만듭니다. 전체 목록은 [보존 정책 및 보존 레이블 활동](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)을 참조하세요.

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블의 PowerShell cmdlet

보존 정책 cmdlet을 사용하려면 먼저 [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)해야 합니다. 그런 다음, 다음 cmdlet 중 하나를 사용하세요.

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

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>이전 기능 대신 보존 정책 및 보존 레이블 사용하기

정보 거버넌스를 위해 Microsoft 365에서 콘텐츠를 사전에 보존하거나 삭제해야 하는 경우에는 다음과 같은 이전 기능 대신 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다. 
  
현재 이러한 이전 기능을 사용하는 경우 해당 기능은 보존 정책 및 레이블과 함께 계속해서 작동합니다. 하지만 앞으로는 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다. Microsoft 365 전체에서 콘텐츠의 보존 및 삭제를 중앙에서 관리하는 단일 메커니즘을 제공합니다.

**Exchange Online의 이전 기능:**

- [원본 위치 유지 및 소송 보존](https://go.microsoft.com/fwlink/?linkid=846124)(eDiscovery 보류) 

- [Exchange Online 사서함의 보류 유형을 식별하는 방법](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [보존 태그 및 보존 정책](https://go.microsoft.com/fwlink/?linkid=846125), [[MRM(메시징 레코드 관리)](https://go.microsoft.com/fwlink/?linkid=846126)라고도 함(삭제만 해당)
    
또한 [레거시 eDiscovery 도구의 사용 중지](legacy-ediscovery-retirement.md)도 참조하세요.


**SharePoint 및 OneDrive의 이전 기능:**

- [eDiscovery 센터에서 사례에 콘텐츠 추가 및 원본 우 위치 유지](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)(eDiscovery 보류) 
    
- [문서 삭제 정책](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)(삭제만 해당)
    
- [현재 위치 레코드 관리 구성](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (보존만 해당) 
    
- [사이트 폐쇄 및 삭제에 대한 정책 사용](https://support.microsoft.com/ko-KR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (삭제만 해당) 
    
- [정보 관리 정책](intro-to-info-mgmt-policies.md) (삭제만 해당)
     
이전에 정보 거버넌스 용도로 eDiscovery 보류를 사용한 적이 있는 경우 사전 규정 준수를 위해 보존 정책을 사용해야 합니다. 보류 전용으로 eDiscovery를 사용합니다.
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>보존 정책 및 SharePoint 콘텐츠 유형 정책 또는 정보 관리 정책

콘텐츠 유형 정책 또는 정보 관리 정책에 대해 SharePoint 사이트를 구성하여 목록이나 라이브러리에 대한 콘텐츠를 보존하는 경우 보존 정책이 유효하는 동안 해당 정책은 무시됩니다. 

## <a name="related-information"></a>관련 정보

- [SharePoint Online 제한 사항](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams의 제한 사항 및 사양](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [SEC 규칙 17a-4 준수](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>다음 단계

보존 정책을 만들 준비가 되었으면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.

보존 레이블을 만들고 적용하려면:
- [보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)
- [보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)

