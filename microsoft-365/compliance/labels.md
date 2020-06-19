---
title: 보존 레이블에 대한 자세한 정보
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
description: Learn how retention labels classify data across your organization for governance, and enforce retention rules based on that classification. You can also use retention labels to implement a records management solution for Microsoft 365.
ms.openlocfilehash: 90039930d94de238a784cc4f8cea6463ff4e49b3
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761698"
---
# <a name="learn-about-retention-labels"></a>보존 레이블에 대한 자세한 정보

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:
  
- 최소 기간 동안 **보존**해야 하는 세금 양식 
    
- 특정 기간에 도달할 때 **영구적으로 삭제**되어야 하는 보도 자료 
    
- **보존**되었다가 **영구적으로 삭제**되어야 하는 경쟁업체 연구 자료 
    
- 편집하거나 삭제할 수 없게 **기록으로 표시**해야 하는 취업 비자 
    
In all of these cases, retention labels can help you take the right actions on the right content. With retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.
  
보존 레이블을 사용하여 다음을 수행할 수 있습니다.
  
- **Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Microsoft 365 Groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied. 
    
- 콘텐츠에 다음이 포함된 경우처럼 특정 조건과 일치하는 경우 **콘텐츠에 보존 레이블을 자동으로 적용**합니다. 
    
    - 특정 중요한 정보 유형
    
    - 만든 쿼리와 일치하는 특정 키워드
    
    - 학습 가능한 분류자에 대한 패턴 일치
    
  콘텐츠에 자동으로 보존 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.
    
     - 사용자에게 모든 분류를 교육할 필요가 없습니다.
    
     - 모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.
    
   - 사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 그 대신 업무에 집중할 수 있습니다.

- SharePoint의 **문서 라이브러리, 폴더 또는 문서 집합에 기본 보존 레이블을 적용**하여 해당 위치에 저장된 모든 문서가 기본 보존 레이블을 상속하도록 합니다.

또한, 보존 레이블은 Microsoft 365 앱과 서비스에서 전자 메일 및 문서의 [레코드 관리](records-management.md)를 지원합니다. 보존 레이블을 사용하여 콘텐츠를 레코드로 분류할 수 있습니다. 이런 경우 콘텐츠가 Microsoft 365에 남아 있으면 레이블을 변경하거나 제거할 수 없으며 콘텐츠를 편집하거나 삭제할 수 없습니다. 

보존 레이블은 [민감도 레이블](sensitivity-labels.md)과 달리 Microsoft 365 외부로 콘텐츠를 이동해도 유지되지 않습니다.

테넌트에 지원되는 보존 레이블 개수에는 제한이 없습니다. 그러나 10,000은 테넌트에 지원되는 최대 정책의 수이며, 여기에는 레이블뿐만 아니라 보존 정책이 적용되는 정책(보존 레이블 정책과 자동 적용 보존 정책)도 포함됩니다.

## <a name="how-retention-labels-work-with-retention-label-policies"></a>보존 레이블이 보존 레이블 정책과 작동하는 방식

콘텐츠를 분류할 수 있도록 조직의 사용자에게 보존 레이블을 제공하는 작업은 2단계 프로세스입니다. 

1. 보존 레이블 만들기

2. 보존 레이블 정책을 사용하여 보존 레이블 게시하기
  
![레이블의 역할 및 작업 다이어그램](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
보존 레이블은 한 개 이상의 보존 레이블 정책에 포함되는 독립적인 재사용 가능한 구성 요소입니다. 보존 레이블 정책의 기본 목적은 보존 레이블 집합을 그룹화하고 해당 레이블을 표시할 위치를 지정하는 것입니다.
  
![레이블, 레이블 정책 및 위치 다이어그램](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. 보존 레이블을 게시하면 보존 레이블 정책에 포함됩니다. 보존 레이블 이름은 변경할 수 없습니다. 즉, 레이블 이름을 만든 후에는 수정할 수 없습니다.

2. 하나의 보존 레이블이 여러 보존 레이블 정책에 포함될 수 있습니다.

3. 하나의 위치가 여러 보존 레이블 정책에 포함될 수도 있습니다.
    
3. 보존 레이블 정책은 보존 레이블을 게시할 위치를 지정합니다.
    
## <a name="only-one-retention-label-at-a-time"></a>한 번에 하나의 보존 레이블만

전자 메일 또는 문서와 같은 콘텐츠에는 한 번에 하나씩 단일 보존 레이블만 할당될 수 있다는 점에 유의합니다.
  
- 최종 사용자가 수동으로 할당한 보존 레이블의 경우, 할당된 보존 레이블을 제거하거나 변경할 수 있습니다.
    
- 콘텐츠에 자동 적용 레이블이 할당된 경우 최종 사용자가 자동 적용 레이블을 수동 할당 보존 레이블로 바꿀 수 있습니다.
    
- 최종 사용자가 콘텐츠에 수동으로 보존 레이블을 할당한 경우 자동 적용 레이블로 수동 할당 보존 레이블을 대신할 수 없습니다.
    
- 자동 적용 레이블을 할당하는 여러 규칙이 있고 콘텐츠가 여러 규칙의 조건을 충족하는 경우 가장 오래된 규칙에 대한 보존 레이블이 할당됩니다.
    
한 보존 레이블이 적용되는 방법과 그 이유를 이해하려면 레이블을 명시적으로 할당하는 것과 암시적으로 레이블이 할당되는 것의 차이점을 이해하는 것이 좋습니다.

- 수동으로 할당된 레이블은 명시적으로 할당됩니다.
- 자동으로 적용된 레이블은 암시적으로 할당됩니다.

명시적으로 할당된 보존 레이블이 암시적으로 할당된 보존 레이블에 우선합니다. 자세한 내용은 [보존 원칙 또는 우선하는 항목](#the-principles-of-retention-or-what-takes-precedence)에 대한 이 페이지의 섹션을 참조하세요.

## <a name="retention-label-policies-and-locations"></a>보존 레이블 정책 및 위치

보존 레이블이 수행하는 작업에 따라, 다양한 유형의 보존 레이블을 여러 다른 위치에 게시할 수 있습니다.
  
|**보존 레이블...**|**레이블 정책을 적용할 수 있는 대상...**|
|:-----|:-----|
|최종 사용자에게 게시  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 그룹  <br/> |
|중요한 정보 유형에 따라 자동으로 적용  <br/> |Exchange(모든 사서함만), SharePoint, OneDrive  <br/> |
|쿼리에 따라 자동 적용  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 그룹  <br/> |
   
Exchange에서 자동 적용 보존 레이블(쿼리 및 중요한 정보 유형 모두에 대한)은 현재 사서함에 있는 모든 항목(미사용 데이터)이 아닌 새로 전송된 메시지(전송 중인 데이터)에만 적용됩니다. 또한 민감한 정보 유형에 대한 자동 적용 보존 레이블은 모든 사서함에만 적용되며 특정 사서함을 선택할 수 없습니다.
  
Exchange 공용 폴더, Skype, 팀 채널 메시지 및 채팅은 보존 레이블을 지원하지 않습니다.

## <a name="how-retention-labels-enforce-retention"></a>보존 레이블이 보존을 적용하는 방법

보존 레이블은 보존 정책이 할 수 있는 보존 및 삭제용, 보존 전용 또는 삭제 전용과 같은 보존 작업을 적용할 수 있습니다. 보존 레이블을 사용하여 다양한 보존 설정에 대한 특정 파일을 식별하는 정교한 파일 계획을 구현할 수 있습니다. 보존이 작동하는 방식에 대한 자세한 내용은 [보존 정책 정보](retention-policies.md)를 참조하세요.

In addition, a retention label has two retention options that are available only in a retention label and not in a retention policy. With a retention label, you can:
  
- SharePoint 및 OneDrive 문서가 삭제되기 전에 검토되도록 보존 정책 종료 시 처리 검토를 트리거합니다. 자세한 내용은 [처리 검토](disposition.md#disposition-reviews)를 참조하세요.
    
- 보존 기간은 콘텐츠 사용 기간이나 마지막으로 수정되었을 때가 아니라 콘텐츠에 레이블이 지정될 때 시작됩니다. 이 옵션을 사용하는 경우,
    - SharePoint 사이트 및 OneDrive 계정의 콘텐츠에만 적용됩니다. Exchange 전자 메일의 경우 보존 기간은 항상 메시지를 보냈거나 받은 날짜를 기준으로 합니다.
    - 레이블이 저장된 후에는 보존 기간을 변경할 수 없습니다.
    
![레이블 관련 옵션이 있는 보존 설정](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)

또 다른 중요한 차이점은 SharePoint에서 파일에 보존 정책 보다는 보존 레이블을 적용하고 레이블이 콘텐츠를 보유하도록 구성한 경우, 사용자는 보존 기간이 적용되는 동안에는 파일을 삭제할 수 없다는 것입니다. 사용자는 레이블이 콘텐츠를 레코드로 표시하지 않는 한 OneDrive에서의 파일 및 전자 메일에 동일한 레이블이 적용되는 경우 콘텐츠를 삭제할 수 있습니다.

## <a name="where-published-retention-labels-can-appear-to-end-users"></a>게시된 보존 레이블이 최종 사용자에게 표시될 수 있는 위치

최종 사용자가 콘텐츠에 보존 레이블을 할당하면 해당 레이블을 다음에 게시할 수 있습니다.
  
- Outlook 및 웹용 Outlook
    
- OneDrive
    
- SharePoint
    
- Microsoft 365 그룹(웹용 Outlook의 그룹 사이트 및 그룹 사서함)
    
아래 섹션에서는 다양한 앱에서 레이블이 조직의 사용자에게 표시되는 방식을 설명합니다.
  

### <a name="outlook"></a>Outlook

Outlook 데스크톱 클라이언트에서 항목에 레이블을 지정하려면 해당 항목을 선택합니다. 리본 메뉴의 **홈** 탭에서 **정책 할당**을 클릭한 다음, 보존 레이블을 선택합니다. 
  
![정책 할당 단추](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
항목을 마우스 오른쪽 단추로 클릭하고, 상황에 맞는 메뉴에서 **정책 할당**를 클릭한 다음, 보존 레이블을 선택할 수도 있습니다. 

보존 레이블이 적용된 후 항목 맨 위에서 해당 보존 레이블과 해당 레이블이 수행하는 작업을 볼 수 있습니다. 연결된 보존 기간이 있는 보존 레이블이 전자 메일에 적용된 경우, 해당 전자 메일이 만료되는 시간을 한눈에 알 수 있습니다.
  
폴더에 보존 레이블을 적용할 수도 있습니다. 이러한 경우 다음을 수행됩니다.
  
- 명시적으로 적용된 보존 레이블이 있는 항목의 경우를 **제외하고** 폴더의 모든 항목에 자동으로 같은 보존 레이블이 적용됩니다. 명시적으로 레이블이 지정된 항목은 기존 보존 레이블을 유지합니다. 자세한 내용은 [보존 원칙 또는 우선하는 항목](#the-principles-of-retention-or-what-takes-precedence)에 대한 이 페이지의 섹션을 참조하세요. 
    
- 폴더의 기본 보존 레이블을 변경하거나 제거하는 경우 명시적으로 보존 레이블이 지정된 항목을 **제외하고** 폴더의 모든 항목에 대해서도 보존 레이블이 변경되거나 제거됩니다. 
    
- 기본 보존 레이블이 있는 항목을 한 폴더에서 다른 기본 보존 레이블이 있는 다른 폴더로 이동하면 항목에 새 기본 보존 레이블이 지정됩니다.
    
- 기본 보존 레이블이 있는 항목을 한 폴더에서 기본 보존 레이블이 없는 다른 폴더로 이동하면 이전의 기본 보존 레이블이 제거됩니다.

### <a name="outlook-on-the-web"></a>웹용 Outlook

웹용 Outlook에서 항목에 레이블을 지정하려면 마우스 오른쪽 단추로 항목 \> **정책 할당**을 클릭하고 \> 보존 레이블을 선택합니다. 
  
![웹용 Outlook의 정책 할당 메뉴](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![웹용 Outlook에서 전자 메일에 할당된 레이블](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
웹용 Outlook에서와 마찬가지로 폴더에 보존 레이블을 적용할 수도 있습니다. 

### <a name="onedrive-and-sharepoint"></a>OneDrive 및 SharePoint

OneDrive 또는 SharePoint에서 문서(OneNote 파일 포함)에 레이블을 지정하려면 오른쪽 위 모서리에서 항목 \>을 선택하고 **세부 정보 창 열기**![정보 창 아이콘](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **보존 레이블 적용**을 선택한 후 \> 보존 레이블을 선택합니다. 
  
폴더 또는 문서 집합에 보존 레이블을 적용할 수도 있으며, [문서 라이브러리에 대해 기본 보존 레이블](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)을 설정할 수 있습니다.
  
![SharePoint의 항목에 대해 레이블 목록 적용](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
항목에 보존 레이블이 적용된 후에는 항목을 선택하면 세부 정보 창에서 해당 레이블을 볼 수 있습니다.
  
![세부 정보 창에 표시되는 적용된 레이블](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
OneDrive에서는 아니지만 SharePoint의 경우 **레이블** 열 또는 **레코드 항목임** 열을 포함하는 라이브러리의 보기를 만들 수 있습니다. 이 보기에서는 모든 항목에 할당된 보존 레이블과 레코드인 항목을 한눈에 볼 수 있습니다. 그러나 보기를 **레코드인 항목** 열로 필터링할 수는 없습니다. 열을 추가하는 방법에 대한 자세한 내용은 [목록 또는 라이브러리에서 열 표시 또는 숨기기](https://support.microsoft.com/ko-KR/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2)를 참조하세요.


### <a name="microsoft-365-groups"></a>Microsoft 365 그룹

Microsoft 365 그룹([이전 명칭: Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))에 보존 레이블을 게시하면 보존 레이블은 웹용 Outlook의 그룹 사이트와 그룹 사서함 둘 다에 나타납니다. 콘텐츠에 보존 레이블을 적용하는 환경은 전자 메일 및 문서의 경우와 같습니다.

Microsoft 365 그룹의 콘텐츠를 보존하려면 **Office 365 그룹** 위치를 사용하세요. Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 Exchange 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.

또한 Exchange 위치를 사용하여 특정 그룹 사서함을 포함하거나 제외할 수 없습니다. 초기에 Exchange 위치가 선택될 그룹 사서함을 허용하더라도 보존 정책을 저장하려고 시도할 때 “RemoteGroupMailbox”가 Exchange 위치에 유효하지 않은 선택이라는 오류가 나타나게 됩니다.
  
먼저 앱과 다른 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다. 예를 들어 사용자가 Office 앱에서 보고 적용하도록 하려는 레이블입니다. 

그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다. 이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.

## <a name="applying-a-retention-label-automatically-based-on-conditions"></a>조건에 따라 자동으로 보존 레이블 적용

보존 레이블의 가장 강력한 기능 중 하나는 특정 조건과 일치하는 콘텐츠에 자동으로 레이블을 적용하는 기능입니다. 이 경우 조직의 사용자는 레이블을 적용할 필요가 없습니다. Microsoft 365에서 이 작업을 수행합니다.
  
![자동 적용 레이블의 역할 및 작업 다이어그램](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
자동 적용 보존 레이블은 다음과 같은 이유 때문에 강력합니다.
  
- 사용자에게 모든 분류를 교육할 필요가 없습니다.
    
- 모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.
    
- 사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 업무에 집중할 수 있습니다.
    
콘텐츠에 다음이 포함될 경우 콘텐츠에 자동으로 보존 레이블을 적용하도록 선택할 수 있습니다.
  
- [특정 중요한 정보 유형](create-retention-labels.md#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [만든 쿼리와 일치하는 특정 키워드](create-retention-labels.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [학습 가능한 분류자와 일치](create-retention-labels.md#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![자동 적용 레이블에 대한 조건 페이지 선택](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

> [!TIP]
> SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a>SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 콘텐츠에 기본 보존 레이블 적용

사용자가 개별 문서에 보존 레이블을 적용할 수 있도록 하는 것 외에, SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 문서에 기본 보존 레이블이 적용되도록 해당 위치에 기본 보존 레이블을 적용할 수도 있습니다.
  
문서 라이브러리의 경우 이 작업은 문서 라이브러리의 **라이브러리 설정** 페이지에서 수행합니다. 기본 보존 레이블을 선택하는 경우 라이브러리의 기존 항목에 적용하도록 선택할 수도 있습니다. 
  
예를 들어 마케팅 자료에 대한 태그가 있고 특정 문서 라이브러리에 해당 유형의 콘텐츠만 포함된다는 것을 알 경우 마케팅 자료 태그를 해당 라이브러리의 모든 문서에 대한 기본 태그로 지정할 수 있습니다.
  
![라이브러리 설정 페이지의 레이블 적용 옵션](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
라이브러리, 폴더 또는 문서 집합의 기존 항목에 기본 보존 레이블을 적용하는 경우 다음 작업이 수행됩니다.
  
- 명시적으로 적용된 보존 레이블이 있는 항목(예: 레코드)의 경우를 **제외하고** 라이브러리, 폴더 또는 문서의 모든 항목에 자동으로 같은 보존 레이블이 적용됩니다. 명시적으로 레이블이 지정된 항목은 기존 레이블을 유지합니다. 자세한 내용은 [보존 원칙 또는 우선 순위](#the-principles-of-retention-or-what-takes-precedence)에 대한 아래 섹션을 참조하세요.
    
- 라이브러리, 폴더 또는 문서 집합의 기본 보존 레이블을 변경하거나 제거하는 경우 명시적 보존 레이블이 지정된 항목(예: 레코드)을 **제외하고** 라이브러리, 폴더 또는 문서 집합의 모든 항목에 대해서도 보존 레이블이 변경되거나 제거됩니다.
    
- 한 사이트 컬렉션, 라이브러리, 폴더 또는 문서 집합에서 기본 보존 레이블이 있는 항목을 다른 사이트 컬렉션, 라이브러리, 폴더 또는 다른 레이블이 있는 문서 집합으로 이동하면 새 위치에 다른 기본 보존 레이블이 있더라도 해당 항목은 기존의 기본 보존 레이블을 유지합니다. 항목을 이동하기 전에 레이블이 없으면 새 위치의 기본 보존 레이블을 사용합니다.

**레코드:** 라이브러리, 폴더 또는 문서 집합에 기본 레코드 레이블을 적용하면 해당 위치 내의 모든 개별 항목에 레코드 레이블이 적용됩니다. 새 항목을 레코드 레이블을 사용하여 위치로 이동하면 해당 항목에 레코드 레이블이 지정됩니다. 그러나 콘텐츠를 레코드로 선언하지 않는 레이블로 기본 보존 레이블을 변경하는 경우 해당 작업은 개별 항목에서 레코드 레이블을 제거하지 않습니다. 해당 항목은 레코드 레이블을 보존합니다. 사이트 모음 관리자는 레코드 항목의 보존 레이블을 명시적으로 제거하거나 변경할 수 있습니다.

콘텐츠를 레코드로 선언하는 보존 레이블에 대한 자세한 내용은 [레코드 정보](records.md)를 참조하세요.

## <a name="applying-a-retention-label-to-email-by-using-rules"></a>규칙을 사용하여 전자 메일에 보존 레이블 적용하기

Outlook에서는 보존 레이블 또는 보존 정책을 적용하는 규칙을 만들 수 있습니다.
  
예를 들어, 특정 메일 그룹에서 보내고 받은 모든 메시지에 특정 보존 레이블을 적용하는 규칙을 만들 수 있습니다.
  
규칙을 만들려면 마우스 오른쪽 단추로 항목 \> **규칙** \> **규칙 만들기** \> **고급 옵션** \> **규칙 마법사** \> **보존 정책 적용**을 클릭합니다.
  
![보존 정책을 적용하는 옵션이 포함된 규칙 마법사](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a>작업을 적용하지 않고 콘텐츠 분류

보존 레이블을 만들 때 보존이나 다른 작업을 켜지 않고 레이블을 만들 수 있습니다. 이 경우 작업을 적용하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용할 수 있습니다.
  
예를 들어, 작업 없이 “나중에 검토”라는 보존 레이블을 만든 다음, 해당 보존 레이블을 중요한 정보 유형을 갖는 콘텐츠 또는 쿼리된 콘텐츠에 자동으로 적용할 수 있습니다.
  
![보존이 해제된 레이블 설정 페이지](../media/retention-label-retentionoff.png)

  
## <a name="using-retention-labels-for-records-management"></a>기록 관리에 보존 레이블 사용
    
보존 레이블을 사용하여 콘텐츠를 레코드로 선언할 수 있습니다. 이를 통해 Microsoft 365에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다. 자세한 내용은 [레코드에 대해 자세히 알아보기](records.md)를 참조하세요.
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>보존 레이블을 DLP 정책의 조건으로 사용

A retention label can enforce retention actions on content. In addition, you can use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label. 
  
자세한 내용은 [보존 레이블을 DLP 정책의 조건으로 사용하기](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)를 참조하세요.
  

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>보존 원칙 또는 우선 순위

It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.
  
![보존 원칙 다이어그램](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
보존 작업이 있는 여러 다른 레이블이 콘텐츠에 적용되는 방식을 이해하려면 다음과 같은 보존 원칙에 유의합니다.
  
1. **Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted. 
    
2. **The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period. 
    
3. **Explicit inclusion wins over implicit inclusion.** This means: 
    
    1. 보존 설정이 포함된 보존 레이블이 사용자에 의해 수동으로 항목(예: Exchange 전자 메일 또는 OneDrive 문서)에 할당된 경우 해당 보존 레이블은 사이트 또는 사서함 수준에서 할당된 정책이나 문서 라이브러리에 의해 할당된 기본 보존 레이블보다 우선합니다. 예를 들어 명시적 보존 레이블에서 10년 동안 보존하라고 하지만, 사이트에 할당된 보존 정책에서 5년 동안만 보존하라고 한다면 보존 레이블이 우선합니다. 자동 적용 보존 레이블은 Microsoft 365에서 자동으로 적용하므로 명시적이 아니라 암시적으로 간주됩니다.
    
    2. 보존 정책에 특정 사용자의 사서함 또는 OneDrive 계정과 같은 특정 위치가 포함되는 경우, 해당 정책이 모든 사용자의 사서함 또는 OneDrive 계정에 적용되지만 해당 사용자의 사서함을 특별히 포함하지 않는 다른 보존 정책보다 우선합니다.
    
4. **The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period. 
    
보존 원칙은 위에서 아래로 균형을 깨는 흐름처럼 작동한다는 점을 이해하도록 합니다. 모든 정책 또는 레이블에 의해 적용되는 규칙이 하나의 수준에서 동일한 경우 규칙이 적용되는 우선 순위를 결정하기 위해 흐름은 아래의 다음 수준으로 이동합니다.
  
마지막으로, 보존 정책 또는 보존 레이블은 eDiscovery에 대해 보류된 모든 콘텐츠를 영구적으로 삭제할 수 없습니다. 보류가 해제되면 콘텐츠는 다시 위에서 설명한 정리 프로세스의 적용을 받게 됩니다.

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a>학습 가능한 분류 기준을 사용한 자동 레이블링 우선 순위

학습 가능한 분류 기준으로 구성된 모든 보존 레이블이 동시에 평가됩니다. 교육 가능한 분류 기준이 둘 이상인 항목이 감지되면 다음 기준을 사용하여 적용할 보존 레이블을 결정합니다.

1. 유지 전용 또는 유지 및 삭제용으로 구성된 보존 레이블은 삭제 전용으로 구성된 보존 레이블보다 우선 순위가 높습니다.

2. 보존 전용 또는 보존 및 삭제용으로 구성된 보존 레이블의 경우 가장 긴 보존 기간 동안 구성된 보존 레이블이 우선합니다.

3. 삭제 전용으로 구성된 보존 레이블의 경우 가장 짧은 기간 동안 구성된 보존 레이블이 우선합니다.

4. 동작과 기간이 같은 보존 레이블에는 유지되는 보존 레이블 선택이 포함됩니다.

## <a name="monitor-retention-labels"></a>보존 레이블 모니터링

보존 레이블을 게시하거나 자동 적용한 후에는 보존 레이블이 의도한 대로 콘텐츠에 적용되는지 확인하려고 할 것입니다. 보존 레이블을 모니터링하려면:
  
- **레이블 활동 탐색기**. 탐색기(다음 그림의 예)를 사용하여 지난 30일 동안의 모든 SharePoint 및 OneDrive 콘텐츠에 대한 보존 레이블 활동을 신속하게 검색하고 볼 수 있습니다. 자세한 내용은 [문서에 대한 레이블 활동 보기](view-label-activity-for-documents.md)를 참조하세요.

- **레이블 분석** 페이지. Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터에서 빠르게 상위 보존 레이블 및 레이블이 적용된 위치를 볼 수 있습니다. 특정 보존 레이블이 포함된 모든 콘텐츠를 볼 수도 있습니다. 자세한 내용은 [레이블 분석을 사용한 레이블 사용 현황 보기](label-analytics.md)를 참조하세요.
    
- **데이터 거버넌스 보고서**. 이러한 보고서를 통해 지난 90일 동안의 모든 Exchange, SharePoint, OneDrive 콘텐츠에 대한 보존 레이블 추세 및 활동을 신속하게 볼 수 있습니다. 자세한 내용은 [데이터 거버넌스 보고서 보기](view-the-data-governance-reports.md)를 참조하세요.
    
![레이블 활동 탐색기](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)

## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a>콘텐츠 검색을 사용하여 특정 보존 레이블이 적용된 모든 콘텐츠 찾기

사용자가 콘텐츠에 보존 레이블을 할당하거나 레이블이 자동 적용된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류된 모든 콘텐츠를 찾을 수 있습니다.
  
콘텐츠 검색을 만들 때 **규정 준수 태그** 조건을 선택한 다음 보존 레이블 이름을 전체 또는 일부만 입력하고 와일드카드를 사용합니다. 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.
  
![준수 태그 조건](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="use-retention-labels-instead-of-older-features"></a>이전 기능 대신 보존 레이블 사용하기

보존 레이블은 손쉽게 전체 조직에 제공될 수 있으며 해당 콘텐츠는 손쉽게 Microsoft 365(Exchange, SharePoint, OneDrive, Microsoft 365 그룹 포함) 전체에 제공될 수 있습니다. Microsoft 365의 어느 곳에서든 콘텐츠를 보존 또는 삭제하거나, 레코드를 관리해야 하는 경우에는 보존 레이블을 사용하는 것이 좋습니다.
  
이전에 Microsoft 365에서 콘텐츠를 보존 또는 삭제하거나, 레코드를 관리하는 데 사용된 다른 여러 기능이 있습니다. 이러한 기능은 보존 레이블과 함께 계속해서 작동합니다. 보존 레이블 구현이 이전 기능과 다른 경우가 있기는 하지만, 보존 레이블이 발전하여 앞으로 Microsoft 365에서 레코드를 더 편리하게 관리할 수 있게 될 것입니다. 따라서 앞으로 데이터 거버넌스를 위해 다음과 같은 이전 기능 대신 보존 레이블을 사용하는 것이 좋습니다.
  
### <a name="exchange-online"></a>Exchange Online

- [보존 태그 및 보존 정책](https://go.microsoft.com/fwlink/?linkid=846125), [[MRM(메시징 레코드 관리)](https://go.microsoft.com/fwlink/?linkid=846126)라고도 함(삭제만 해당) 
    
### <a name="sharepoint-and-onedrive"></a>SharePoint 및 OneDrive

- [ 현재 위치 레코드 관리 구성](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)(보존) 
    
- [레코드 센터 소개](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c)(보존) 
    
- [정보 관리 정책](intro-to-info-mgmt-policies.md) (삭제만 해당) 
    
## <a name="next-steps"></a>다음 단계

보존 레이블을 만들고 게시할 준비가 되었으면 [보존 레이블 만들기, 게시 및 자동 적용](create-retention-labels.md)을 참조하세요.
