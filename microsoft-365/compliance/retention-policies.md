---
title: 콘텐츠를 자동으로 보존하거나 삭제하는 보존 정책에 대해 자세히 알아보기
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
description: 보존 정책을 사용하여 콘텐츠를 보존할지, 삭제할지, 아니면 보존한 다음 삭제할지 사전에 결정할 수 있습니다. 조직 전체 또는 특정 위치 또는 사용자에게 단일 정책을 적용할 수 있고 모든 콘텐츠 또는 특정 조건에 부합하는 콘텐츠에 정책을 적용할 수 있습니다.
ms.openlocfilehash: 377c5e1f21938204123de298e620a3d0d2bb9755
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695141"
---
# <a name="learn-about-retention-policies"></a>보존 정책에 대해 자세히 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

대부분의 조직에서는 전자 메일, 문서, 인스턴트 메시지 등을 비롯하여 데이터의 양과 복잡성이 계속해서 매일 증가하고 있습니다. 이러한 정보를 효과적으로 관리하거나 제어하는 일은 다음 작업을 수행해야 하므로 중요합니다.
  
- 최소 기간 동안 콘텐츠를 보존하도록 요구하는 **산업 규정 및 내부 정책을 사전에 준수**합니다. 예를 들어 Sarbanes-Oxley Act는 7년 동안 특정 유형의 콘텐츠를 보존하도록 요구할 수 있습니다. 
    
- **소송 또는 보안 위반 시 위험 감소** - 더 이상 보존할 필요가 없는 오래된 콘텐츠를 영구적으로 삭제 
    
- **조직에서 효과적이면서 좀 더 민첩하게 지식을 공유하도록 지원** - 사용자가 관련이 있는 최신 콘텐츠만 사용하도록 합니다. 
    
보존 정책은 이러한 모든 목표를 달성하는 데 도움을 줄 수 있습니다. 일반적으로 콘텐츠를 관리하려면 다음 두 가지 작업이 필요합니다.
  
- **보존** - 콘텐츠가 보존 기간이 끝나기 전에 영구적으로 삭제되지 않도록 보존합니다. 
    
- **삭제** - 보존 기간이 끝나면 콘텐츠를 영구적으로 삭제합니다. 
    
보존 정책을 사용하여 다음을 수행할 수 있습니다.
  
- 콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정합니다.
    
- 전체 조직 또는 특정 위치나 사용자에 단일 정책을 적용합니다.
    
- 모든 콘텐츠 또는 특정 조건을 충족하는 콘텐츠(예: 특정 키워드 또는 [특정 유형의 중요 정보](what-the-sensitive-information-types-look-for.md)를 포함하는 콘텐츠)에 정책을 적용합니다.
    
콘텐츠가 보존 정책을 따르는 경우라도 콘텐츠는 원래 위치에 그대로 보존되므로 아무 것도 변경되지 않는 것과 같이, 계속해서 콘텐츠를 편집하고 사용할 수 있습니다. 그러나 보존 정책을 따르는 콘텐츠를 다른 사용자가 편집 또는 삭제한 경우에는 해당 콘텐츠에 대한 보존 정책이 적용되는 동안 원본 콘텐츠의 복사본이 보존되는 안전한 위치에 저장됩니다. 자세한 내용은 해당 페이지에서 [보존 정책이 원래 위치의 콘텐츠에 적용되는 방식](#how-a-retention-policy-works-with-content-in-place) 섹션을 참조하세요.
  
또한 일부 조직에서는 SEC(증권 거래 위원회) 규칙 17a-4와 같은 규정을 준수해야 합니다. 해당 규정은 보존 정책이 설정된 후에 해제되거나 제한이 거의 없도록 설정될 수 없습니다. 해당 요구 사항을 위해서는 **보존 잠금**을 사용할 수 있습니다. 정책을 잠그면 관리자를 비롯한 어느 누구도 보존 정책을 해제하거나 제한이 거의 없도록 설정할 수 없습니다. 자세한 내용은 해당 페이지에서 [보존 잠금을 사용하여 규정 요구 사항 준수](#use-preservation-lock-to-comply-with-regulatory-requirements) 섹션을 참조하세요.

## <a name="how-a-retention-policy-works-with-content-in-place"></a>보존 정책이 원본 위치의 콘텐츠에 작동하는 방식

보존 정책에 사이트나 사서함과 같은 위치를 포함하면 콘텐츠가 원본 위치에 남아 있게 됩니다. 사용자는 아무것도 변경된 사항이 없는 것처럼 계속해서 문서나 사서함을 사용하여 작업할 수 있습니다. 그러나 사용자가 보존 정책에 포함된 콘텐츠를 편집하거나 삭제하는 경우에는 해당 정책이 적용된 시점의 콘텐츠 사본이 보존됩니다.
  
- SharePoint 및 OneDrive 사이트의 경우: 사본은 **자료 보존** 라이브러리에 보존됩니다. 자료 보존 라이브러리는 사이트에 대한 저장소 할당량을 사용한다는 점에 유의하세요.

- 전자 메일 및 공용 폴더의 경우: **복구 가능한 항목** 폴더에 복사본이 보존됩니다. 

- Teams 콘텐츠의 경우: Exchange **복구 가능한 항목** 폴더에 복사본이 보존됩니다.

- Microsoft 365 그룹([이전 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))의 경우: 
    - Exchange **복구 가능한 항목** 폴더에 그룹 사서함이 보존됩니다.
    - 모든 사이트 콘텐츠는 **자료 보존** 라이브러리에 보존됩니다.

> [!NOTE]
> 자료 보존 라이브러리는 사이트의 저장소 할당량에서 제외되지 않은 저장소를 사용합니다. SharePoint 및 Microsoft 365 그룹에 대한 보존 정책을 사용하는 경우 저장소를 늘려야 할 수 있습니다.
> 
대부분의 사용자는 해당 보안 위치 및 보존된 콘텐츠를 볼 수 없습니다. 보존 정책을 사용하면 사용자는 해당 콘텐츠에 정책이 적용되어 있다는 사실을 알 필요도 없습니다.

보존 정책에서 다양한 작업을 수행하는 방법에 대한 자세한 내용은 다음의 문서를 참조하세요.

- [SharePoint 및 OneDrive의 보존 정책에 대해 자세히 알아보기](retention-policies-sharepoint.md)
- [Microsoft Teams의 보존 정책에 대해 자세히 알아보기](retention-policies-teams.md)
- [Exchange의 보존 정책에 대해 자세히 알아보기](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>보존 원칙 또는 우선 순위

콘텐츠에 작업(보존, 삭제 또는 보존한 다음 삭제) 및 보존 기간이 각기 다른 여러 보존 정책이 적용되어 있을 수 있습니다. 우선 순위는 무엇인가요? 가장 높은 수준에서 한 보존 정책으로 보존되는 콘텐츠가 다른 보존 정책으로 영구히 삭제될 수 없다는 점을 보장합니다.
  
![보존 원칙 다이어그램](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
여러 다른 보존 정책 콘텐츠에 적용되는 방식을 이해하려면 다음과 같은 보존 원칙에 유의합니다.
  
1. **삭제보다 보존 우선.** 한 보존 정책에서는 3년 후 Exchange 전자 메일을 삭제하도록 구성하지만 다른 보존 정책에서는 5년 동안 Exchange 전자 메일을 보존한 다음 삭제하도록 구성한다고 가정합니다. 3년에 도달하는 모든 콘텐츠는 삭제되고 사용자의 보기에서 숨겨지지만, 콘텐츠가 영구적으로 삭제되는 5년에 도달하기까지는 복구 가능한 항목 폴더에 여전히 보존됩니다. 
    
2. **가장 긴 보존 기간 우선.** 콘텐츠가 콘텐츠를 보존하는 여러 보존 정책의 적용을 받는 경우 가장 긴 보존 기간이 끝날 때까지 콘텐츠는 보존됩니다. 
    
3. **암시적 포함보다 명시적 포함 우선.** 의미는 다음과 같습니다. 
    
    1. 보존 설정이 포함된 보존 레이블이 사용자에 의해 수동으로 항목(예: Exchange 전자 메일 또는 OneDrive 문서)에 할당된 경우 해당 보존 레이블이 사이트 또는 사서함 수준에서 할당된 보존 정책이나 문서 라이브러리에 의해 할당된 기본 보존 레이블보다 우선합니다. 예를 들어 명시적 보존 레이블에서 10년 동안 콘텐츠를 보존하기로 구성하지만 사이트에 할당된 보존 정책에서 5년 동안만 콘텐츠를 보존하기로 구성한다면 보존 레이블이 우선합니다. 자동 적용 보존 레이블은 Microsoft 365에서 자동으로 적용하므로 명시적이 아니라 암시적으로 간주됩니다.
    
    2. 보존 정책에 특정 사용자의 사서함 또는 OneDrive 계정과 같이 특정 위치가 포함되는 경우 해당 보존 정책이 모든 사용자의 사서함 또는 OneDrive 계정에 적용되지만 특히 해당 사용자의 사서함을 포함하지 않는 다른 보존 정책보다 우선합니다.
    
4. **가장 짧은 삭제 기간이 우선합니다.** 마찬가지로 콘텐츠에 보존 기간 없이 콘텐츠를 삭제하는 여러 보존 정책이 적용되는 경우 해당 콘텐츠는 가장 짧은 보존 기간이 끝나면 삭제됩니다. 
    
보존 원칙은 위에서 아래로 균형을 깨는 흐름처럼 작동한다는 점을 이해하세요. 모든 보존 정책 또는 보존 레이블에 의해 적용되는 규칙이 하나의 수준에서 동일한 경우 규칙이 적용되는 우선 순위를 결정하기 위해 흐름은 다음 수준으로 아래로 이동합니다.
  
마지막으로, 보존 정책 또는 보존 레이블은 eDiscovery에 대해 보류된 모든 콘텐츠를 영구히 삭제할 수 없습니다. 보류가 해제되면 콘텐츠는 다시 위에서 설명한 정리 프로세스의 적용을 받게 됩니다.

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>보존 잠금을 사용하여 규정 요구 사항을 준수합니다.

일부 조직에서는 보존 정책을 설정한 후에 해제하거나 제한 사항이 거의 없이 설정할 수 없는 SEC(증권 거래 위원회) 규칙 17a-4와 같은 규제 기구에서 정의한 규칙을 준수해야 할 수 있습니다. 

보존 잠금은 조직이 관리자를 비롯하여 어떠한 사용자도 정책을 해제하거나 제한 사항이 거의 없이 설정할 수 없도록 보존 정책을 잠그기 때문에 관련 규정 요구 사항을 충족할 수 있도록 보장합니다.
  
보존 정책이 잠기는 경우:

- 누구도 해당 정책을 해제할 수 없습니다.
- 위치는 추가할 수 있지만 제거할 수는 없습니다. 
- 보존 기간 동안에 해당 정책이 적용된 콘텐츠를 수정하거나 삭제할 수 없습니다.
- 보존 기간을 연장할 수 있지만 줄일 수는 없습니다.

요약하면 잠겨 있는 정책은 늘리거나 확장할 수 있지만 줄이거나 해제할 수 없습니다.
  
> [!IMPORTANT]
> 보존 정책을 잠그기 전에 해당 정책의 영향을 이해하고 조직에서 규정 준수 요구 사항을 충족하는 데 해당 정책이 필요한 지 여부를 확인하는 것이 중요합니다.

## <a name="releasing-a-retention-policy"></a>보존 정책 해제

보존 정책에 보존 잠금이 없으면 언제든지 보존 정책을 끄거나 삭제할 수 있습니다. 

이렇게 하면 자료 보존 라이브러리에 보존되어 있는 모든 SharePoint 또는 OneDrive 콘텐츠가 바로 영구적으로 삭제되지 않습니다. 실수로 데이터가 손실되는 것을 방지하기 위해 30일간의 유예 기간이 있습니다. 이 기간에는 자료 보존 라이브러리에서 해당 정책에 대한 콘텐츠 만료가 발생하지 않으므로 필요한 경우 콘텐츠를 복원할 수 있습니다. 또한 유예 기간에 이 콘텐츠를 수동으로 삭제할 수 없습니다.

유예 기간에 보존 정책을 다시 켤 수 있고 해당 정책에 대한 콘텐츠가 삭제되지 않습니다.

SharePoint 및 OneDrive의 30일간의 유예 기간은 Exchange의 30일 지연 기간에 해당합니다. 자세한 내용은 [지연되는 사서함 관리](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)를 참조하세요.

## <a name="use-a-retention-policy-instead-of-older-features"></a>이전 기능 대신 보존 정책 사용

조직 전체 및 Exchange Online, SharePoint Online, OneDrive 및 Microsoft 365 그룹을 비롯하여 Microsoft 365 전체 위치에 손쉽게 단일 보존 정책을 적용할 수 있습니다. Microsoft 365의 어느 곳에서든 콘텐츠를 보존하거나 삭제하려는 경우에는 보존 정책을 사용하고 필요에 따라 이를 [보존 레이블](labels.md)과 함께 추가하는 것이 좋습니다.
  
이전에 Microsoft 365에서 다른 구성을 사용하여 콘텐츠를 보존하거나 삭제한 경우 보존 정책 및 보존 레이블과 함께 계속해서 작업할 수 있습니다. 하지만 앞으로는 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다. Microsoft 365 전체에서 콘텐츠의 보존 및 삭제를 중앙에서 관리하는 단일 메커니즘을 제공합니다.

사용했을 수도 있는 이전 기능은 다음과 같습니다.
  
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
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a>보류 정책을 보존 정책으로 전환합니다.

보류 정책을 사용하여 사서함, SharePoint 또는 OneDrive 사이트, 공용 폴더에서 데이터를 보존하는 경우 해당 정책은 보존 작업을 전용으로 하는 보존 정책으로 자동 전환됩니다. 해당 보존 정책은 콘텐츠를 삭제하지 않습니다. 구성된 보류 정책과 동일한 결과에 대해 변경 사항은 필요하지 않습니다.

구성된 보류 정책은 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)의 **정책** 페이지나 [보안 &amp; 규정 준수 센터](https://protection.office.com/)의 **정보 거버넌스** 아래 **보존** 페이지에서 찾을 수 있습니다. 보류 정책을 편집하여 보존 기간을 변경할 수 있지만 위치를 추가하거나 제거하는 등의 다른 변경은 수행할 수 없습니다. 


## <a name="related-information"></a>관련 정보

- [보존 레이블에 대한 자세한 정보](labels.md)
- [SharePoint Online 제한 사항](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams의 제한 사항 및 사양](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [SEC 규칙 17a-4 준수](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>다음 단계

보존 정책을 만들 준비가 되었으면 [보존 정책 만들기 및 구성](create-retention-policies.md)을 참조하세요.

