---
title: 온-프레미스 사용자의 Teams 채팅 데이터 검색
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 Exchange 하이브리드 배포에서 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 내보낼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9620c48056545e6d6cf053040849acfe0a1bc68e
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868016"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>온-프레미스 사용자의 Teams 채팅 데이터 검색

조직에 Exchange 하이브리드 배포가 있고 (또는 Office 365를 사용하여 조직을 온-프레미스 Exchange 조직과 동기화하고) Microsoft Teams를 사용한 경우 온-프레미스 사용자는 Teams 채팅 응용 프로그램을 사용하여 인스턴트 메시지를 이용할 수 있습니다. 클라우드 기반 사용자의 경우 Teams 채팅 데이터(*1x1 또는 1xN 채팅* 이라고도 함)는 기본 클라우드 기반 사서함에 저장됩니다. 온-프레미스 사용자가 Teams 채팅 응용 프로그램을 사용하는 경우 채팅 메시지는 온-프레미스에 위치한 기본 사서함에 저장될 수 없습니다. 이 문제를 해결하기 위해 Microsoft는 eDiscovery 도구를 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 내보낼 수 있도록 클라우드 기반 저장소 영역을 만드는 새로운 기능을 출시했습니다.
  
다음은 온-프레미스 사용자의 클라우드 기반 사서함을 설정하기 위한 요구 사항 및 제한 사항입니다.
  
- 온-프레미스 디렉터리 서비스(예: Active Directory)의 사용자 계정은 Microsoft 365의 디렉터리 서비스인 Azure Active Directory와 동기화되어야 합니다. 즉, 메일 사용자 계정이 Microsoft 365에서 만들어지고 기본 사서함이 온-프레미스 조직에 있는 사용자와 연결됩니다.

- 기본 사서함이 온-프레미스 조직에 있는 사용자에게 Microsoft Teams 라이선스와 최소 Exchange Online 계획 1 라이선스가 할당되어야 합니다.

- 온-프레미스 사용자와 연결된 Teams 채팅 데이터만 클라우드 기반 저장소 영역에 저장됩니다. 온-프레미스 사용자는 이 저장소 영역에 어떤 방법으로든 액세스할 수 없습니다.

- 조직에서 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있도록 Microsoft 지원 요청을 제출해야 합니다. 이 문서의 [이 기능을 사용하도록 설정할 수 있도록 Microsoft 지원 요청 제출](#filing-a-request-with-microsoft-support-to-enable-this-feature)을 참조하세요.

> [!NOTE]
> Teams 채널 대화는 항상 팀과 연결된 클라우드 기반 사서함에 저장됩니다. 즉 지원 요청을 제출할 필요 없이 콘텐츠 검색을 사용하여 채널 대화를 검색할 수 있습니다. Teams 채널 대화를 검색하는 방법에 대한 자세한 내용은 [Microsoft Teams 및 Microsoft 365 그룹 검색](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)을 참조하세요.
  
## <a name="how-it-works"></a>작동 방식

Microsoft Teams 지원 사용자에게 온-프레미스 사서함이 있고 사용자 계정/ID가 클라우드에 동기화된 경우 Microsoft는 온-프레미스 사용자의 1xN Teams 채팅 데이터와 연결된 클라우드 기반 사서함을 만듭니다. 온-프레미스 사용자의 Teams 채팅 데이터는 검색을 위해 인덱싱됩니다. 따라서 콘텐츠 검색(및 핵심 eDiscovery 사례와 고급 eDiscovery 사례와 연결된 검색)을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보낼 수 있습니다. 보안 및 규정 준수 센터 PowerShell에서 **\*ComplianceSearch** cmdlet을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수도 있습니다.
  
다음 그래픽은 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보내는 방법에 대한 워크플로를 보여줍니다.
  
![Microsoft Teams에서 온-프레미스 사용자의 클라우드 기반 저장소](../media/EHAMShard1.png)
  
이 새로운 기능 외에도 클라우드 기반 사용자의 Exchange Online 사서함에서 콘텐츠 검색을 사용하여 각 Microsoft Team 및 1xN Teams 채팅 데이터와 연결된 클라우드 기반 SharePoint 사이트와 Exchange 사서함의 Teams 콘텐츠를 검색하고 미리 보고 내보낼 수 있습니다.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>이 기능을 사용하도록 설정할 수 있도록 Microsoft 지원 요청 제출

조직에서 보안 및 준수 센터의 그래픽 사용자 인터페이스를 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있도록 하려면 Microsoft 지원에 요청을 제출해야 합니다. 이 기능은 보안 및 준수 센터 PowerShell에서 사용할 수 있습니다. PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 데는 지원 요청을 제출하지 않아도 됩니다.
  
Microsoft 지원 요청을 제출할 때 다음 정보를 포함해야 합니다.
  
- 조직의 기본 도메인 이름

- 조직의 테넌트 이름 및 테넌트 ID 이를 Azure Active Directory 포털(**관리** \> **속성** 아래)에서 찾을 수 있습니다. [Microsoft 365 테넌트 ID 찾기](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)를 참조하세요.

- 다음은 지원 요청의 목적에 대한 다음 제목 또는 설명입니다. “온-프레미스 사용자의 응용 프로그램 콘텐츠 검색 사용” 이를 통해 요청을 구현할 eDiscovery 엔지니어 팀에게 요청을 보낼 수 있습니다.

엔지니어링 변경되면 Microsoft 지원에서 예상 배포 날짜를 보냅니다. 지원 요청을 제출한 후에는 일반적으로 배포 프로세스에 2~3 주 정도 걸립니다.
  
### <a name="what-happens-after-this-feature-is-enabled"></a>이 기능을 사용하도록 설정한 후에는 어떻게 되나요?

조직에 이 기능이 배포된 후 콘텐츠 검색과 보안 및 준수 센터의 eDiscovery 사례와 연결된 검색에서 다음과 같은 사항이 변경됩니다.
  
- **온-프레미스 사용자를 위한 Office 앱 콘텐츠 추가** 확인란이 콘텐츠 검색의 **위치** 아래에 추가됩니다.

    !["온-프레미스 사용자를 위한 Office 앱 콘텐츠 추가" 확인란이 콘텐츠 검색 UI에 추가됩니다](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- 검색할 사용자 사서함을 선택할 때 사용하는 콘텐츠 위치 선택기에 온-프레미스 사용자가 표시됩니다.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>온-프레미스 사용자의 Teams 채팅 콘텐츠 검색

해당 기능을 사용하도록 설정하면 보안 및 규정 준수 센터의 콘텐츠 검색을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있습니다.
  
1. 보안 및 준수 센터에서 **검색** \> **콘텐츠 검색** 으로 이동합니다

2. **검색** 페이지에서 ![아이콘 추가](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **새 검색** 을 클릭합니다.

    앞서 설명한 것처럼 **온-프레미스 사용자를 위한 Office 앱 콘텐츠 추가** 확인란이 **위치** 아래에 표시됩니다. 이 확인란은 기본적으로 선택되어 있습니다.

3. 키워드 쿼리를 만들고 필요한 경우 검색 쿼리에 조건을 추가합니다. 팀 채팅 데이터만 검색하려면 **키워드** 상자에 다음 쿼리를 추가하면 됩니다.

    ```text
    kind:im
    ```

4. 이 시점에서 **위치** 아래에서 다음 옵션 중 하나를 선택할 수 있습니다.

    - **모든 위치:** 조직에 있는 모든 사용자의 사서함을 검색하려면 이 옵션을 선택합니다. 해당 확인란을 선택하면 온-프레미스 사용자에 대한 Teams 채팅 데이터의 모든 클라우드 기반 저장소도 검색됩니다.

    - **특정 위치:** 이 옵션을 선택한 다음 **수정** 을 클릭하고 \> 사용자, 그룹 또는 팀을 선택하여 특정 사서함을 검색합니다. 앞서 설명한 것처럼 위치 선택기를 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있습니다.

5. 검색을 저장하고 실행합니다. 온-프레미스 사용자의 모든 검색 결과는 다른 검색 결과와 같이 미리 볼 수 있습니다. 검색 결과(Teams 채팅 데이터 포함)를 PST 파일로 내보낼 수도 있습니다. 자세한 내용은 다음을 참조하세요.

    - [검색 만들기](content-search.md#create-a-search)

    - [검색 결과 미리 보기](content-search.md#preview-search-results)

    - [콘텐츠 검색 결과 내보내기](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터 검색

보안 및 준수 센터 PowerShell에서 **New-ComplianceSearch** 및 **Set-ComplianceSearch** cmdlet을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있습니다. 앞서 설명한 것처럼 PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 데는 지원 요청을 제출하지 않아도 됩니다.
  
1. [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.

2. 다음 PowerShell 명령을 실행하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 콘텐츠 검색을 만듭니다.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    *IncludeUserAppContent* 매개 변수는 *ExchangeLocation* 매개 변수로 지정된 한 명 이상의 사용자의 클라우드 기반 저장소를 지정하는 데 사용됩니다. *AllowNotFoundExchangeLocationsEnabled* 를 통해 온-프레미스 사용자의 클라우드 기반 저장소를 검색할 수 있습니다. 이 매개 변수에 `$true` 값을 사용하는 경우 진행하기 전에 사서함의 존재 여부를 확인하는 검색을 시도하지 않습니다. 이 클라우드 기반 저장소는 일반 클라우드 기반 사서함으로 확인되지 않으므로 온-프레미스 사용자의 클라우드 기반 저장소를 검색하려면 이 작업이 필요합니다.

    다음 예제에서는 Contoso 조직의 온-프레미스 사용자인 Sara Davis의 클라우드 기반 저장소에서 “redstone” 키워드를 포함하는 Teams 채팅(인스턴트 메시지)을 검색합니다.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   검색을 만든 후에 **Start-ComplianceSearch** cmdlet를 사용하여 검색을 실행해야 합니다. 
  
이러한 cmdlet 사용에 대한 자세한 내용은 다음을 참조하세요.
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>알려진 문제

- 현재 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보낼 수 있습니다. 핵심 eDiscovery 사례 및 고급 eDiscovery 사례와 연결된 보류에 온-프레미스 사용자의 Teams 채팅 데이터를 배치하고 온-프레미스 사용자에 대해 Teams 채팅 또는 채널 메시지 보존 정책을 적용할 수도 있습니다. 그러나 현재 온-프레미스 사용자에 대해 다른 콘텐츠 위치(예: Exchange 사서함 및 SharePoint 사이트) 보존 정책을 적용할 수 없습니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**온-프레미스 사용자의 클라우드 기반 저장소는 어디에 있나요?**
  
Teams 채팅 데이터는 온-프레미스 사용자의 PDL(기본 데이터 위치)에 저장됩니다. PDL은 Single-Geo 및 Multi-Geo 환경에서 모두 존중됩니다. 자세한 내용은 [Microsoft 365 Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo)을 참조하세요.
  
 **지원 요청을 제출하는 것 외에도 다른 요구 사항이 있나요?**
  
앞서 설명한 것처럼 Office 365의 각 온-프레미스 사용자 계정에 해당하는 메일 사용자 계정을 만들려면 온-프레미스 사서함이 있는 사용자의 ID를 클라우드 기반 조직과 동기화해야 합니다. 또한 조직에 Office 365 Enterprise E1, E3 또는 E5 구독과 같은 Office 365 Enterprise 구독이 있어야 합니다.
  
 **사용자의 온-프레미스 사서함이 클라우드로 마이그레이션될 경우 Teams 채팅 데이터가 손실될 위험이 있나요?**
  
아니요. 온-프레미스 사용자의 기본 사서함을 클라우드로 마이그레이션하면 해당 사용자의 Teams 채팅 데이터가 새 클라우드 기반 기본 사서함으로 마이그레이션됩니다.
  
 **온-프레미스 사용자에게 eDiscovery 보류 또는 보존 정책을 적용할 수 있나요?**
  
예. 온-프레미스 사용자의 Teams 채팅 및 채널 메시지에 대한 eDiscovery 보류 또는 보존 정책을 적용할 수 있습니다.
  
 **조직에서 이 기능을 사용하기 위해 요청을 제출하기 전에 콘텐츠 검색에서 온-프레미스 사용자의 이전 Teams 채팅 데이터를 찾을 수 있나요?**
  
Microsoft는 2018년 1월 31일에 온-프레미스 사용자의 Teams 채팅 데이터를 저장하기 시작했습니다. 따라서 이 날짜 이후로 Active Directory와 Azure Active Directory 간에 온-프레미스 Teams 사용자의 ID가 동기화된 경우 Teams 채팅 데이터가 클라우드에 저장되며 콘텐츠 검색을 사용하여 이를 검색할 수 있습니다. Microsoft는 2018년 1월 31일 이전부터 온-프레미스 사용자의 클라우드 기반 저장소에 Teams 채팅 데이터를 저장하는 기능을 작업하고 있습니다. 이에 대한 자세한 내용은 곧 제공될 예정입니다.

 **온-프레미스 사용자가 클라우드에 Teams 채팅 데이터를 저장하려면 라이선스가 필요하나요?**
  
예. 클라우드 기반 저장소에 온-프레미스 사용자의 Teams 채팅 데이터를 저장하려면 사용자에게 Microsoft Teams 라이선스 및 Office 365(또는 Microsoft 365)의 Exchange Online 플랜 라이선스가 할당되어 있어야 합니다.
