---
title: 이벤트 구동 보존 개요
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: 일반적으로 레코드 관리 솔루션의 일부는 사용자가 식별하는 이벤트에 기반하여 보존 기간을 시작하는 보존 레이블을 구성할 수 있습니다.
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817807"
---
# <a name="overview-of-event-driven-retention"></a>이벤트 구동 보존 개요

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them. But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
예를 들어 다음에 대해 이벤트 구동 보존이 적용된 레이블을 사용할 수 있습니다.
  
- **Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization. After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed. The event that triggers the 10-year retention period is the employee leaving the organization. 
    
- **Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- Labels based on events also usually classify content as a record. For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- 기록으로 선언되었으나 해당 이벤트 트리거가 아직 발생하지 않은 문서는 문서의 보존 기간을 트리거하는 이벤트가 발생할 때까지 무기한 보존됩니다(기록을 영구히 삭제할 수 없음).
    
- Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content. For more information, see [Disposition of content](disposition.md).
    
이벤트 기반의 레이블은 Office 365의 모든 보존 레이블과 같은 기능을 제공합니다. 자세한 내용은 [보존 레이블에 대해 자세히 알아보기](labels.md)를 참조하세요.

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>이벤트 유형, 레이블, 이벤트 및 자산 ID 간 관계 이해

이벤트 구동 보존을 성공적으로 사용하려면 다음과 같은 다이어그램 및 설명에 있는 것처럼 이벤트 유형, 보존 레이블, 이벤트 및 자산 ID 간 관계를 이해하는 것이 중요합니다. 
  
![이벤트 유형, 레이블, 이벤트 및 자산 ID의 다이어그램](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![이벤트 유형, 레이블, 이벤트 및 자산 ID의 다이어그램](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. 콘텐츠 유형에 따라 보존 레이블을 작성한 후 이벤트 유형과 연관시킵니다. 예를 들어, 다양 한 유형의 제품 파일 및 기록에 대한 레이블은 해당 기록을 제품이 수명에 도달한 시점부터 10년 동안 보존해야 하므로 제품 수명이라는 이벤트 유형에 연결됩니다.
    
2. 사용자(일반적으로 레코드 관리자)는 해당 보존 레이블을 콘텐츠에 적용하고, SharePoint 및 OneDrive 문서의 경우에는 각 항목에 대해 자산 ID를 입력합니다. 이 예에서 자산 ID는 조직에서 사용하는 제품 이름 또는 코드입니다. 따라서 각 제품의 레코드에는 보존 레이블이 할당되고 각 레코드는 자산 ID가 포함된 특성을 가집니다. 다이어그램은 조직의 모든 제품 레코드에 대한 **모든 콘텐츠**를 표시하며 각 항목은 레코드가 있는 제품의 자산 ID를 가집니다. 
    
3. Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:
    
  - 자산 ID(SharePoint 및 OneDrive 문서 관련)
    
  - Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.
    
  - The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.
    
4. 이벤트를 작성한 후, 해당 이벤트 날짜는 해당 이벤트 유형의 보존 레이블이 있으며 지정된 자산 ID 또는 키워드를 포함하는 모든 콘텐츠와 동기화됩니다. 모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다. 이전 다이어그램에서 빨간색 원으로 둘러싸인 모든 항목에는이 이벤트를 통해 트리거되는 보존 기간이 있습니다. 즉, 이 제품이 수명의 끝에 도달하면 해당 이벤트는 해당 제품의 레코드에 대한 보존 기간을 트리거합니다.
    
이벤트에 대해 자산 ID 또는 키워드를 지정하지 않으면 해당 이벤트 유형의 레이블이 있는 **모든 콘텐츠**가 이벤트에 의해 트리거된 보존 기간을 갖게 됩니다. 이는 위의 다이어그램에서 모든 콘텐츠가 유지되기 시작한다는 것을 의미합니다. 이는 원치 않는 일일 수 있습니다. 
  
마지막으로 각 보존 레이블에는 별도의 보존 설정이 있습니다. 이 예에서는 모든 레이블이 10년을 지정하지만 각 레이블의 보존 기간이 다른 경우 이벤트가 보존 레이블을 트리거할 수 있습니다.
  
## <a name="how-to-set-up-event-driven-retention"></a>이벤트 구동 보존 설정 방법

이벤트 구동 보존의 상위 레벨 워구동우우:
  
![이벤트 구동 보존을 설정하는 워크플로 다이어그램](../media/event-based-retention-process.png)
  
> [!TIP]
> SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>1단계: 보존 기간이 이벤트에 따라 조정되는 레이블 만들기

Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **정보 거버넌스** > **레이블** > **레이블 만들기**를 선택합니다. 탐색 창에 **정보 관리**가 표시되지 않는 경우 아래로 스크롤하여 **모두 표시**를 선택합니다.
  
When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event. This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page. 
  
이벤트 구동 보존은 일반적으로 레코드로 분류된 콘텐츠에 사용됩니다. 이러한 이유로 이벤트 기반의 보존 레이블을 작성할 때 일반적으로 **레이블을 사용하여 콘텐츠를 "레코드"로 분류**하기 위한 옵션을 선택합니다.
  
또한 이벤트 구동 보존에는 다음과 같은 보존 설정이 필요합니다.
  
- 콘텐츠를 보존합니다.
    
- 보존 기간이 끝나면 콘텐츠를 자동으로 삭제하거나 처리 검토를 트리거합니다.
    
![이벤트를 기준으로 레이블을 지정하는 옵션](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>2단계: 해당 레이블에 대한 이벤트 유형 선택

레이블 설정에서 **이벤트** 기반의 레이블을 설정을 위한 옵션을 선택하면 **이벤트 유형 선택** 옵션이 표시됩니다. 이벤트 유형은 레이블을 연결할 이벤트에 대한 일반적인 설명입니다.
  
예를 들어, 제품 수명이라는 이벤트 유형을 만드는 경우 레이블을 적용하려는 콘텐츠의 형식을 설명하는 이름(예: “제품 개발 파일” 또는 “제품 비즈니스 결정 기록”)을 사용하여 이벤트 기반 보존 레이블을 만듭니다.
  
일단 이벤트 유형을 선택하고 보존 레이블을 만들고 나면 이벤트 유형을 변경할 수 없습니다.
  
![이벤트 유형을 만들거나 선택하는 옵션](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>3단계: 이벤트 기반 보존 레이블 게시 혹은 자동 적용

다른 보존 레이블과 마찬가지로 이벤트 기반 레이블을 [게시하거나 자동 적용](create-retention-labels.md)해야만 콘텐츠에 수동 또는 자동으로 적용됩니다.

> [!NOTE]
> **레코드 관리** > **파일 계획** 탭 혹은 **데이터 관리** > **레이블** 탭에서 이벤트 중심의 보존 레이블을 선택하는 경우, **레이블 자동 적용** 단추를 사용할 수 없습니다.
> 
> 이 단추 대신 다음 위치 중 하나에서 레이블 또는 정책 목록 위에 있는 **레이블 자동 적용** 옵션을 사용합니다.
> - **레코드 관리** > **레이블 정책** 탭
> - **데이터 관리** > **레이블** 탭 또는 **레이블 정책** 탭


![보존 레이블 게시 또는 자동 적용 옵션](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>4단계: 자산 ID 입력

After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:
  
- 특정 제품에 대한 콘텐츠만 보존하는 데 사용할 수 있는 제품 코드
    
- 특정 프로젝트에 대한 콘텐츠만 보존하는 데 사용할 수 있는 프로젝트 코드
    
- 특정 사람에 대한 콘텐츠만 보존하는 데 사용할 수 있는 직원 ID
    
자산 ID는 SharePoint 및 비즈니스용 OneDrive에서는 또 다른 문서 속성일 뿐입니다. 조직에서 이미 다른 문서 속성 및 ID를 사용하여 콘텐츠를 분류하고 있을 수 있습니다. 이 경우에는 이벤트를 작성할 때 해당 속성 및 값을 사용할 수도 있습니다. 아래 6단계를 참조하세요. 중요한 점은 조직이 문서 속성에서 일부 특성:값 조합을 사용하여 해당 항목을 이벤트 유형과 연결시켜야 한다는 것입니다.
  
![자산 ID를 입력하기 위한 텍스트 상자](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>5단계: 이벤트 만들기

When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event. You need to manually trigger an event by creating it.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>6단계: 2단계에서 레이블에 사용된 것과 동일한 이벤트 유형 선택

이벤트를 작성할 때 2단계에서 보존 레이블에 사용되는 동일한 이벤트 유형(예: 제품 수명)을 선택합니다. 해당 이벤트 유형에 적용된 보존 레이블이 있는 콘텐츠에 대해서만 보존 기간이 트리거됩니다.
  
![이벤트 유형을 선택하기 위한 이벤트 설정 옵션](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>7단계: 키워드 또는 자산 ID 입력

Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them. 
  
자산 ID는 SharePoint 및 비즈니스용 OneDrive에서는 또 다른 문서 속성일 뿐입니다. 자산 ID 속성을 사용하는 경우, 아래 표시된 자산 ID 상자에 ComplianceAssetID:\<value\>를 입력합니다.
  
Your organization might have applied other properties and IDs to the documents related to this event type. For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ". In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.
  
For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
마지막으로 이벤트가 발생한 날짜를 선택합니다. 이 날짜는 보존 기간의 시작 날짜로 사용됩니다. 이벤트를 작성한 후, 이벤트 날짜는 해당 이벤트 유형, 자산 ID 및 키워드의 보존 레이블이 있는 모든 콘텐츠와 동기화됩니다. 모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다.
  
![이벤트 설정 페이지](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>콘텐츠 검색을 사용하여 특정 레이블 또는 자산 ID를 포함하는 모든 콘텐츠 찾기

콘텐츠에 보존 레이블이 할당된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류되거나 특정 자산 ID를 포함하는 모든 콘텐츠를 찾을 수 있습니다.
  
콘텐츠 검색을 만들 경우 다음이 적용됩니다.
  
- 특정 보존 레이블이 있는 모든 콘텐츠를 찾으려면 **준수 태그** 조건을 선택하고 전체 레이블 이름 또는 레이블 이름 일부를 입력하고 와일드카드를 사용합니다. 
    
- 특정 자산 ID가 있는 모든 콘텐츠를 찾으려면 **ComplianceAssetID** 속성과 값(예: ComplianceAssetID:\<value\>)을 입력합니다. 
    
자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.
  
## <a name="permissions"></a>사용 권한

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
자세한 내용은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.
  
## <a name="automate-events-by-using-powershell"></a>PowerShell을 사용하여 이벤트 자동화

In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs. However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).

PowerShell 스크립트를 사용하여 비즈니스 응용 프로그램에서 이벤트 기반 보존을 자동화할 수도 있습니다. 이벤트 구동 보존에 다음 PowerShell cmdlet을 사용할 수 있습니다.
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

