---
title: 보류를 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 보유자 및 해당 데이터 원본에 보류를 설정하여 보유 사례에 대한 관련 콘텐츠를 보존하는 Advanced eDiscovery 방법을 알아보겠습니다.
ms.custom:
- seo-marvel-mar2020
- admindeeplinkMAC
ms.openlocfilehash: 12fdc5e6282358f96dcc1d454156a7fccf7518a4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186147"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>보류를 Advanced eDiscovery

사례를 Advanced eDiscovery 보류를 만들어 사례와 관련이 있을 수 있는 콘텐츠를 보존할 수 있습니다. Advanced eDiscovery 보유 기능을 사용하면 보유자 및 해당 데이터 원본을 보류할 수 있습니다. 또한 사서함 및 사이트와 사서함에 대해 비보류를 비즈니스용 OneDrive 있습니다. 그룹 그룹에 대한 그룹 사서함, SharePoint 사이트 및 비즈니스용 OneDrive 보류할 Microsoft 365 있습니다. 마찬가지로 사서함 및 사이트와 연결된 사서함 및 사이트에 보류를 Microsoft Teams. 콘텐츠 위치를 보류할 경우 보유자 해제, 특정 데이터 위치 제거 또는 보류 정책을 완전히 삭제할 때까지 콘텐츠가 보류됩니다.

## <a name="manage-custodian-based-holds"></a>보유자 기반 보류 관리

경우에 따라 식별하고 사례 중에 데이터를 보존하기로 결정한 관리인 집합이 있을 수 있습니다. Advanced eDiscovery 보유가 적용되면 사용자와 선택한 데이터 원본이 보유 정책에 자동으로 추가됩니다.

보유자 보류 정책을 보시다:

1. 이 Microsoft 365 규정 준수 센터 **eDiscovery** > 고급을 클릭하여 조직의 사례 목록을 표시합니다.

2. 원본 **탭으로** 이동하여 사례 내에 보호자 추가 보유자 추가 및 보유자 추가 및 보류를 Advanced eDiscovery 자세한 내용은 사례에 보유자 추가를 [참조합니다.](add-custodians-to-case.md) 보유자도 이미 추가하고 보류한 경우 3단계로 이동하여 보류합니다.

3. 보류 **탭으로 이동하여** **CustodianHold를 클릭합니다. \<HoldId>**

4. 플라이아웃 페이지에서 정책에 대한 통계를 볼 수 있습니다. 보유자 기반 보류에 쿼리를 적용하는 등의 작업을 수행할 수도 있습니다. 보류 쿼리를 만들고 조건을 사용하는 데 대한 자세한 내용은 콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건을 [참조하세요.](keyword-queries-and-search-conditions.md)

## <a name="manage-non-custodial-holds"></a>비관리 보류 관리

보류를 만들 때 지정된 콘텐츠 위치에 있는 콘텐츠의 범위를 지정하기 위한 다음 옵션이 있습니다.

- 모든 콘텐츠가 보류된 무한 보류를 만들 수 있습니다. 또는 검색 쿼리와 일치하는 콘텐츠만 보류된 쿼리 기반 보류를 만들 수 있습니다.
  
- 해당 날짜 범위 내에서 보내거나 받거나 만든 콘텐츠만 보유할 날짜 범위를 지정할 수 있습니다. 또는 모든 콘텐츠를 전송, 수신 또는 만든 경우와 관계없이 보유할 수 있습니다.

특정 사례에 대한 비보류를 Advanced eDiscovery:

1. 조직 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a> **eDiscovery** > 고급을 클릭하여 조직의 사례 목록을 표시합니다.
  
2. **보류를** 만들 사례 옆에 있는 열기 를 클릭합니다.
  
3. 사례 홈 페이지에서 보류 **탭을** 클릭합니다.
  
4. 보류 **탭에서** 만들기를 **클릭합니다.**
  
5. 이름 **보류 페이지에서** 보류에 이름을 지정합니다. 보류 이름은 조직에서 고유해야 합니다.
 
6. (선택 사항) 설명 **상자에** 보류에 대한 설명을 추가합니다.
  
7. **다음** 을 클릭합니다.
  
8. 보류할 콘텐츠 위치를 선택하세요. 사서함, 사이트, 공용 폴더를 보류 상태로 지정할 수 있습니다.

   1. **Exchange** 전자 메일 - **사용자,** 그룹 또는 팀 선택을 클릭한 다음 **사용자,** 그룹 또는 팀 선택을 다시 클릭하여 보류할 사서함을 지정합니다. 검색 상자를 사용하여 보류 상태로 지정할 사용자 사서함 및 메일 그룹(그룹 구성원의 사서함을 보류)을 찾습니다. 그룹 또는 Microsoft 팀에 대해 연결된 사서함을 보류할 Microsoft 365 있습니다. 사용자, 그룹, 팀 확인란을 선택하고, **선택을** 클릭한 다음 완료를 **클릭합니다.**
 
      > [!NOTE]
      > 사용자,  그룹 또는 팀 선택을 클릭하여 보류할 사서함을 지정하면 표시되는 사서함 선택이 비어 있습니다. 이것은 성능을 향상시키기 위한 것입니다. 이 목록에 사용자 추가를 위해 검색 상자에 이름(최소 3자)을 입력합니다.

   1. **SharePoint** 사이트 선택 -  사이트 선택을  클릭한 다음 사이트 선택을 다시 클릭하여 SharePoint 비즈니스용 OneDrive 보류할 사이트를 지정합니다. 보류할 각 사이트의 URL을 입력합니다. 그룹 또는 Microsoft 팀에 대한 SharePoint URL을 Microsoft 365 있습니다. 를 **클릭한** 다음 완료를 **클릭합니다.**

      > [!NOTE]
      > 사용자 OneDrive 계정의 URL에는 UPN(사용자 계정 이름)(예: )이 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` 포함됩니다. 드물게 개인의 UPN이 변경되는 경우, 새 UPN을 OneDrive URL도 변경됩니다. 사용자의 OneDrive 계정이 비보류의 일부인 경우 해당 UPN을 변경한 경우 보류를 업데이트하고 새 OneDrive URL을 지정해야 합니다. 자세한 내용은 [UPN 변경 내용이 OneDrive URL에 미치는 영향](/onedrive/upn-changes)을 참조하세요.

   1. **Exchange** 폴더 - 토글 스위치를 모두 위치로 이동하여 Exchange Online 공용 폴더를 보류합니다. 보류할 특정 공용 폴더를 선택할 수 없습니다. 공용 폴더에 보류를 설정하지 않는 경우 토글 스위치를 **None으로** 설정하십시오.

9. 보류에 콘텐츠 위치 추가가 완료되면 다음 을 **클릭합니다.**
  
10. 조건이 있는 쿼리 기반 보류를 만들 경우 다음을 완료합니다. 그렇지 않으면 다음 을 **클릭합니다.**
    
    - 키워드 아래에 **있는** 상자에 검색 조건을 충족하는 콘텐츠만 보류할 수 있도록 상자에 검색 쿼리를 입력합니다. 키워드, 메시지 속성 또는 문서 속성(예: 파일 이름)을 지정할 수 있습니다. AND, OR 또는 NOT과 같은 부울 연산자를 사용하는 좀 더 복잡한 쿼리를 사용할 수도 있습니다. 키워드 상자를 비워 두면 지정된 콘텐츠 위치에 있는 모든 콘텐츠가 보류됩니다.

    - 조건  **추가를** 클릭하여 하나 이상의 조건을 추가하여 보류에 대한 검색 쿼리 범위를 좁힐 수 있습니다. 각 조건은 보류를 만들 때 만들어 실행되는 KQL 검색 쿼리에 절을 추가합니다. 예를 들어 날짜 범위 내에서 만든 전자 메일 또는 사이트 문서가 보류될 수 있도록 날짜 범위를 지정할 수 있습니다. 조건은 AND 연산자를 사용하여 키워드 쿼리(키워드 상자에 지정)에 논리적으로 연결됩니다. 즉, 항목이 키워드 쿼리와 보류 상태를 모두 충족해야 합니다.

     검색 쿼리를 만들고 조건을 사용하는 데 대한 자세한 내용은 콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건을 [참조하세요.](/office365/SecurityCompliance/keyword-queries-and-search-conditions)

11. 쿼리 기반 보류를 구성한 후 다음 을 **클릭합니다.**

12. 설정을 검토하고 이 보류 **만들기 를 클릭합니다.**

## <a name="view-hold-statistics"></a>보류 통계 보기

시간이 지난 후 선택한 보류에 대한 보류 탭의  세부 정보 창에 새 보류에 대한 정보가 표시됩니다. 이 정보에는 보류된 총 항목 수와 크기, 마지막으로 보류 통계를 계산한 시간 등 보류된 콘텐츠에 대한 통계 및 보류된 사서함 및 사이트 수가 포함됩니다. 이러한 보류 통계는 eDiscovery 사례와 관련된 콘텐츠의 양을 식별하는 데 도움이 됩니다.

보류 통계에 대해 다음에 유의하십시오.

- 보류된 총 항목 수는 보류된 모든 콘텐츠 원본의 항목 수를 나타냅니다. 쿼리 기반 보류를 만든 경우 이 통계는 쿼리와 일치하는 항목 수를 나타냅니다.
  
- 보류된 항목 수에는 콘텐츠 위치에 있는 인덱서되지 않은 항목도 포함됩니다. 쿼리 기반 보류를 만들면 콘텐츠 위치의 인덱서되지 않은 모든 항목이 보류됩니다. 여기에는 날짜 범위 조건 외부에 있을 수 있는 쿼리 기반 보류 및 인덱서되지 않은 항목의 검색 조건과 일치하지 않는 인덱서되지 않은 항목이 포함됩니다. 검색 쿼리와 일치하지 않는 인덱서되지 않은 항목이 검색 결과에 포함되지 않은 경우 또는 날짜 범위 조건에 의해 제외되는 콘텐츠 검색을 실행할 때 수행되는 상황과는 다릅니다. 인덱싱되지 않은 항목에 대한 자세한 내용은 에서 콘텐츠 검색의 부분적으로 인덱싱된 항목을 [Office 365.](partially-indexed-items-in-content-search.md) 

- 업데이트 통계 업데이트를 클릭하여 현재 보류 중인 항목 수를 계산하는 검색 예상 결과를 다시 실행하여 최신 보류 통계를 얻을 수 있습니다.

- 필요한 경우 도구 모음에서 새로 고침을 클릭하여 세부 정보 창에서 보류 통계를 업데이트합니다.

- 사서함 또는 사이트가 보류된 사용자는 일반적으로 새 전자 메일 메시지를 보내거나 받고 새 전자 메일 메시지를 보내거나 받고 새 전자 메일 SharePoint 비즈니스용 OneDrive 수 있기 때문에 시간이 비즈니스용 OneDrive 증가합니다.

- 다중 SharePoint 또는 OneDrive 계정이 다중 위치 환경의 다른 지역으로 이동되는 경우 해당 사이트의 통계가 보류 통계에 포함되지 않습니다. 그러나 사이트의 콘텐츠는 계속 보류됩니다. 또한 사이트를 다른 지역으로 이동하면 보류에 표시되는 URL이 업데이트되지 않습니다. 보류를 편집하고 URL을 업데이트해야 합니다.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>그룹 및 Microsoft Teams Office 365 보류

Microsoft Teams 그룹에서 Office 365. 따라서 보류를 Advanced eDiscovery 매우 유사합니다.

- **추가 사용자 그룹 또는 Microsoft 365 사이트를 Microsoft Teams 매핑하는 방법 또한 Microsoft 365 그룹 및 Microsoft Teams.** Microsoft Teams 그룹에서 Microsoft 365 있습니다. 따라서 eDiscovery 사례에서 보류하는 것은 매우 유사합니다. 그룹 및 그룹을 보류할 Microsoft 365 다음 Microsoft Teams 유의합니다.
  - Microsoft 365 그룹에 있는 콘텐츠를 Microsoft Teams 그룹 또는 팀과 연결된 사서함 및 SharePoint 사이트를 지정해야 합니다.
  
  - **Get-UnifiedGroup** cmdlet을 Exchange Online 그룹 또는 Microsoft 팀의 속성을 Microsoft 365 수 있습니다. 이는 그룹 또는 Microsoft 팀과 연결된 사이트의 URL을 Microsoft 365 좋은 방법입니다. 예를 들어, 다음 명령을 실행하면 Senior Leadership Team이라는 Microsoft 365 그룹의 선택된 속성이 표시됩니다.


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Get-UnifiedGroup cmdlet를 실행하려면 Exchange Online에서 보기 전용 받는 사람 역할을 할당받았거나 보기 전용 받는 사람 역할이 할당된 역할 그룹의 구성원이어야 합니다.

 - 사용자의 사서함을 검색하면 사용자가 Microsoft 365 그룹 또는 Microsoft 팀이 검색되지 않습니다. 마찬가지로 그룹 또는 Microsoft Microsoft 365 보류를 설정하면 그룹 사서함 및 그룹 사이트만 보류됩니다. 그룹 구성원의 사서함 및 비즈니스용 OneDrive 사이트는 명시적으로 보유자로 추가하거나 데이터 원본을 보유하지 않는 한 보류되지 않습니다. 따라서 특정 보유자에 대해 Microsoft 365 그룹 또는 Microsoft Team을 보류해야 하는 경우 그룹 사이트 및 그룹 사서함을 보유자에 매핑하는 것이 좋습니다(Advanced eDiscovery에서 보유자 관리 참조). Microsoft 365 그룹 또는 Microsoft 팀이 단일 보유자에 기인하지 않는 경우 비 보유에 원본을 추가하는 것이 고려됩니다. 
 
 - 그룹 또는 Microsoft 팀의 구성원 목록을 Microsoft 365 그룹 페이지의 홈 그룹 페이지에서 속성을 볼  >  [](https://go.microsoft.com/fwlink/p/?linkid=2052855) 수 Microsoft 365 관리 센터. 또는 Exchange Online PowerShell에서 다음 명령을 실행할 수 있습니다.

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > **Get-UnifiedGroupLinks** cmdlet를 실행하려면 Exchange Online에서 보기 전용 받는 사람 역할을 할당받았거나 보기 전용 받는 사람 역할이 할당된 역할 그룹의 구성원이어야 합니다.

- Microsoft Teams 채널의 일부인 채널 대화는 팀과 연결된 사서함에 저장됩니다. 마찬가지로 팀 구성원이 채널에서 공유하는 파일은 팀의 SharePoint 사이트에 저장됩니다. 따라서 채널에서 대화와 파일을 SharePoint Microsoft Team 사서함 및 사이트 관리 사이트를 보류해야 합니다.
  
- 또는 채팅 목록에 Microsoft Teams 대화는 채팅에 참여하는 사용자의 사서함에 저장됩니다.  사용자가 채팅 대화에서 공유하는 파일은 파일을 공유하는 사용자의 비즈니스용 OneDrive 사이트에 저장됩니다. 따라서 채팅 목록에 대화와 파일을 보존하려면 개별 사용자 사서함과 비즈니스용 OneDrive 사이트를 보류해야 합니다. 
  
- 모든 Microsoft 팀 또는 팀 채널에는 메모 및 공동 작업을 위한 Wiki가 포함되어 있습니다. Wiki 콘텐츠는 자동으로 .mht 형식의 파일에 저장됩니다. 이 파일은 팀의 SharePoint 사이트에 있는 Teams Wiki Data 문서 라이브러리에 저장됩니다. 팀의 SharePoint 사이트를 보류하여 Wiki에 콘텐츠를 보류할 수 있습니다.

  > [!NOTE]
  > Microsoft 팀 또는 팀 채널의 Wiki 콘텐츠를 보존하는 기능(팀의 SharePoint 사이트를 보류할 때)은 2017년 6월 22일 출시되었습니다. 팀 사이트가 보류 중이면 해당 날짜부터 위키 콘텐츠가 보존됩니다. 그러나 팀 사이트가 보류 중이고 2017년 6월 22일 전에 위키 콘텐츠가 삭제된 경우 Wiki 콘텐츠는 보존되지 않습니다.
