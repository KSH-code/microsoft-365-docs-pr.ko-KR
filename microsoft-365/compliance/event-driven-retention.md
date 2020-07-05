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
ms.openlocfilehash: 29cf69930cdd99d3023a65e55e1186990a650e85
ms.sourcegitcommit: 2e9e309ec09e5275ac6b3b425fba48a9ffce8eb2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44900802"
---
# <a name="overview-of-event-driven-retention"></a>이벤트 구동 보존 개요

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
이벤트 구동 보존 사용 예제:
  
- **직원 퇴사** 직원이 조직을 떠나는 시점부터 10년 동안 직원 레코드를 보유해야 한다고 가정합니다. 10년이 지난 후에는 해당 직원의 고용, 성과 및 퇴직에 관련된 모든 문서를 처리해야 합니다. 10년의 보존 기간을 트리거하는 이벤트는 직원 퇴사입니다. 
    
- **계약 만료** 예를 들어, 계약과 관련된 모든 레코드를 계약이 만료되는 시간으로부터 5년 동안 유지해야 합니다. 5년 보존 기간을 트리거하는 이벤트는 계약 만료입니다. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- 이벤트 기반의 레이블은 대개 콘텐츠를 레코드로 분류합니다. 자세한 내용은 [레코드에 대해 자세히 알아보기](records.md)를 참조하세요.
    
- 레코드로 분류되었으나 해당 이벤트 트리거가 아직 발생하지 않은 문서는 문서의 보존 기간을 트리거하는 이벤트가 발생할 때까지 무기한 보존됩니다(기록을 영구히 삭제할 수 없음).
    
- 이벤트 기반의 보존 레이블은 일반적으로 보존 기간이 끝나면 처리 검토를 트리거하므로 레코드 관리자는 콘텐츠를 수동으로 검토 및 처리할 수 있습니다. 자세한 내용은 [콘텐츠 처리](disposition.md)를 참조하세요.
    
이벤트 기반의 보존 레이블은 Microsoft 365의 모든 보존 레이블과 같은 기능을 제공합니다. 자세한 내용은 [보존 레이블에 대해 자세히 알아보기](labels.md)를 참조하세요.

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
    
4. 이벤트를 작성한 후, 해당 이벤트 날짜는 해당 이벤트 유형의 보존 레이블이 있으며 지정된 자산 ID 또는 키워드를 포함하는 모든 콘텐츠와 동기화됩니다. 모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다. 이전 다이어그램에서 빨간색 원으로 둘러싸인 모든 항목에는 이 이벤트를 통해 트리거되는 보존 기간이 있습니다. 즉, 이 제품이 수명의 끝에 도달하면 해당 이벤트는 해당 제품의 레코드에 대한 보존 기간을 트리거합니다.
    
이벤트에 대해 자산 ID 또는 키워드를 지정하지 않으면 해당 이벤트 유형의 레이블이 있는 **모든 콘텐츠**가 이벤트에 의해 트리거된 보존 기간을 갖게 됩니다. 이는 위의 다이어그램에서 모든 콘텐츠가 유지되기 시작한다는 것을 의미합니다. 이는 원치 않는 일일 수 있습니다. 
  
마지막으로 각 보존 레이블에는 별도의 보존 설정이 있습니다. 이 예에서는 모든 레이블이 10년을 지정하지만 각 레이블의 보존 기간이 다른 경우 이벤트가 보존 레이블을 트리거할 수 있습니다.
  
## <a name="how-to-set-up-event-driven-retention"></a>이벤트 구동 보존 설정 방법

이벤트 구동 보존의 상위 레벨 워구동우우:
  
![이벤트 구동 보존을 설정하는 워크플로 다이어그램](../media/event-based-retention-process.png)
  
> [!TIP]
> SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>1단계: 보존 기간이 이벤트에 따라 조정되는 레이블 만들기

보존 레이블을 만들고 구성하려면 [보존 레이블 만들기 및 구성하기](create-retention-labels.md#create-and-configure-retention-labels)의 지침을 사용하고, 보존을 켤 때 이벤트를 기준으로 콘텐츠를 보존하거나 삭제하는 옵션을 선택합니다. 이 설정은 **이벤트** 페이지에서 이벤트를 작성할 때 5단계까지 보존 설정이 적용되지 않음을 의미합니다. 
  
이벤트 구동 보존은 보통 레코드로 분류되는 콘텐츠에 사용되므로 콘텐츠를 레코드로 표시하는 옵션도 선택해야 하는지 확인하는 것이 좋습니다.
  
이벤트 구동 보존에는 다음과 같은 보존 설정이 필요합니다.
  
- 콘텐츠를 보존합니다.
    
- 보존 기간이 끝나면 콘텐츠를 자동으로 삭제하거나 처리 검토를 트리거합니다.
    
![이벤트를 기준으로 레이블을 지정하는 옵션](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a>2단계: 해당 레이블에 대한 이벤트 유형 선택

레이블 설정에서 **이벤트** 기반의 레이블을 설정을 위한 옵션을 선택하면 **이벤트 유형 선택** 옵션이 표시됩니다. 이벤트 유형은 레이블을 연결할 이벤트에 대한 일반적인 설명입니다.
  
예를 들어, 제품 수명이라는 이벤트 유형을 만드는 경우 레이블을 적용하려는 콘텐츠의 형식을 설명하는 이름(예: “제품 개발 파일” 또는 “제품 비즈니스 결정 기록”)을 사용하여 이벤트 기반 보존 레이블을 만듭니다.
  
이벤트 유형을 선택하고 보존 레이블을 저장한 후에는 이벤트 유형을 변경할 수 없습니다.
  
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
    
자산 ID는 SharePoint 및 OneDrive의 또 다른 문서 속성입니다. 조직에서 이미 다른 문서 속성 및 ID를 사용하여 콘텐츠를 분류하고 있을 수 있습니다. 이 경우에는 이벤트를 작성할 때 해당 속성 및 값을 사용할 수도 있습니다. 아래 6단계를 참조하세요. 중요한 점은 조직이 문서 속성에서 일부 특성:값 조합을 사용하여 해당 항목을 이벤트 유형과 연결시켜야 한다는 것입니다.
  
![자산 ID를 입력하기 위한 텍스트 상자](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>5단계: 이벤트 만들기

해당 이벤트 유형의 특정 인스턴스가 발생하면(예: 제품이 수명 종료에 도달) Microsoft 365 규정 준수 센터의 **레코드 관리** > **이벤트** 페이지로 가서 이벤트를 만듭니다. 이벤트를 만들어 수동으로 트리거해야 합니다.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>6단계: 2단계에서 레이블에 사용된 것과 동일한 이벤트 유형 선택

이벤트를 작성할 때 2단계에서 보존 레이블에 사용되는 동일한 이벤트 유형(예: 제품 수명)을 선택합니다. 해당 이벤트 유형에 적용된 보존 레이블이 있는 콘텐츠에 대해서만 보존 기간이 트리거됩니다.
  
![이벤트 유형을 선택하기 위한 이벤트 설정 옵션](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>7단계: 키워드 또는 자산 ID 입력

Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them. 
  
자산 ID는 SharePoint 및 OneDrive의 또 다른 문서 속성입니다. 자산 ID 속성을 사용하는 경우, 아래 표시된 자산 ID 상자에 `ComplianceAssetID:<value>`를 입력합니다.
  
조직에서 이 이벤트 유형과 관련된 문서에 다른 속성 및 ID를 적용했을 수 있습니다. 예를 들어, 특정 제품의 레코드를 발견해야 하는 경우 ID는 사용자 지정 속성 ProductID와 "XYZ" 값의 조합일 수 있습니다. 이 경우 아래 표시된 자산 ID 상자에 `ProductID:XYZ`를 입력했습니다.
  
For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
마지막으로 이벤트가 발생한 날짜를 선택합니다. 이 날짜는 보존 기간의 시작 날짜로 사용됩니다. 이벤트를 작성한 후, 이벤트 날짜는 해당 이벤트 유형, 자산 ID 및 키워드의 보존 레이블이 있는 모든 콘텐츠와 동기화됩니다. 모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다.
  
![이벤트 설정 페이지](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

> [!NOTE]
> 이벤트를 만든 후 보존 설정은 이미 레이블이 지정되고 인덱싱된 콘텐츠에 적용됩니다. 이벤트를 만든 후 새 콘텐츠에 보존 레이블을 추가한 경우에는 동일한 세부 정보를 사용하여 새 이벤트를 만들어야 합니다.

이벤트를 삭제해도 이미 레이블이 지정된 콘텐츠에 적용되는 보존 설정은 취소되지 않습니다. 보존 설정을 취소하려면 동일한 세부 정보를 사용하여 새 이벤트를 만들되 날짜를 비워 두세요. 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>콘텐츠 검색을 사용하여 특정 레이블 또는 자산 ID를 포함하는 모든 콘텐츠 찾기

콘텐츠에 보존 레이블이 할당된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류되거나 특정 자산 ID를 포함하는 모든 콘텐츠를 찾을 수 있습니다.
  
- 특정 보존 레이블이 있는 모든 콘텐츠를 찾으려면 **준수 레이블** 조건을 선택하고 전체 레이블 이름 또는 레이블 이름 일부를 입력하고 와일드카드를 사용합니다. 
    
- 특정 자산 ID가 있는 모든 콘텐츠를 찾으려면 **ComplianceAssetID** 속성과 값(예: `ComplianceAssetID:<value>`)을 입력합니다. 
    
자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.
  
## <a name="permissions"></a>사용 권한

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
자세한 내용은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.
  
## <a name="automate-events-by-using-powershell"></a>PowerShell을 사용하여 이벤트 자동화

Microsoft 365 규정 준수 센터에서는 이벤트를 수동으로 만들 수 있으며, 이벤트가 발생할 때 이벤트를 자동으로 트리거하는 기능을 지원하지 않습니다. 그러나 Rest API를 사용하여 이벤트를 자동으로 트리거할 수 있습니다. 자세한 내용은 [이벤트 기반 보존 자동화하기](automate-event-driven-retention.md)를 참조하세요.

PowerShell 스크립트를 사용하여 비즈니스 응용 프로그램에서 이벤트 기반 보존을 자동화할 수도 있습니다. 이벤트 구동 보존에 다음 PowerShell cmdlet을 사용할 수 있습니다.
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

