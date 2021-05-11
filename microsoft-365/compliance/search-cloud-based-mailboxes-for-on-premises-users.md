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
description: Microsoft 365의 eDiscovery 도구를 사용하여 Exchange 하이브리드 배포의 온-프레미스 사용자에 대한 Teams 채팅 데이터를 검색하고 내보낼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311804"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="9516a-103">온-프레미스 사용자의 Teams 채팅 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="9516a-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="9516a-104">조직에 Exchange 하이브리드 배포가 있고 (또는 Office 365를 사용하여 조직을 온-프레미스 Exchange 조직과 동기화하고) Microsoft Teams를 사용한 경우 온-프레미스 사용자는 Teams 채팅 응용 프로그램을 사용하여 인스턴트 메시지를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="9516a-105">클라우드 기반 사용자의 경우 Teams 채팅 데이터(*1x1 또는 1xN 채팅* 이라고도 함)는 기본 클라우드 기반 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="9516a-106">온-프레미스 사용자가 Teams 채팅 응용 프로그램을 사용하는 경우 채팅 메시지는 온-프레미스에 위치한 기본 사서함에 저장될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="9516a-107">이 문제를 해결하기 위해 Microsoft는 eDiscovery 도구를 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 내보낼 수 있도록 클라우드 기반 저장소 영역을 만드는 새로운 기능을 출시했습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="9516a-108">다음은 온-프레미스 사용자의 클라우드 기반 사서함을 설정하기 위한 요구 사항 및 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="9516a-109">온-프레미스 디렉터리 서비스(예: Active Directory)의 사용자 계정은 Microsoft 365의 디렉터리 서비스인 Azure Active Directory와 동기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="9516a-110">즉, 메일 사용자 계정이 Microsoft 365에서 만들어지고 기본 사서함이 온-프레미스 조직에 있는 사용자와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="9516a-111">기본 사서함이 온-프레미스 조직에 있는 사용자에게 Microsoft Teams 라이선스와 최소 Exchange Online 계획 1 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="9516a-112">조직에 Exchange 하이브리드 배포가 없는 경우 온-프레미스 Exchange 스키마를 Azure Active Directory에 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-112">If your organization doesn't have an Exchange hybrid deployment, you must synchronize your on-premises Exchange schema to Azure Active Directory.</span></span> <span data-ttu-id="9516a-113">이렇게 하지 않는 경우, 사서함이 있는 사용자에 대해 Exchange Online에서 중복 클라우드 기반 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-113">If you don't do this, you might risk creating duplicate cloud-based mailboxes in Exchange Online for users that have a mailbox in your on-premises Exchange organization.</span></span>

- <span data-ttu-id="9516a-114">온-프레미스 사용자와 연결된 Teams 채팅 데이터만 클라우드 기반 저장소 영역에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-114">Only the Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="9516a-115">온-프레미스 사용자는 이 저장소 영역에 어떤 방법으로든 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-115">An on-premises user can't access this storage area in any way.</span></span>

> [!NOTE]
> <span data-ttu-id="9516a-116">Teams 채널 대화는 항상 Teams 연결된 클라우드 기반 사서함에 저장되므로 채널 대화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team, which means you can search for channel conversations.</span></span> <span data-ttu-id="9516a-117">Teams 채널 대화를 검색하는 방법에 대한 자세한 내용은 [Microsoft Teams 및 Microsoft 365 그룹 검색](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9516a-117">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="9516a-118">작동 방식</span><span class="sxs-lookup"><span data-stu-id="9516a-118">How it works</span></span>

<span data-ttu-id="9516a-119">Microsoft Teams 지원 사용자에게 온-프레미스 사서함이 있고 사용자 계정/ID가 클라우드에 동기화된 경우 Microsoft는 온-프레미스 사용자의 1xN Teams 채팅 데이터와 연결된 클라우드 기반 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-119">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="9516a-120">온-프레미스 사용자의 Teams 채팅 데이터는 검색을 위해 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-120">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="9516a-121">따라서 콘텐츠 검색(및 핵심 eDiscovery 및 고급 eDiscovery 케이스와 연결된 검색)을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-121">This lets you Use Content search (and searches associated with Core eDiscovery and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="9516a-122">보안 및 규정 준수 센터 PowerShell에서 **\*ComplianceSearch** cmdlet을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-122">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="9516a-123">다음 그래픽은 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보내는 방법에 대한 워크플로를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-123">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams에서 온-프레미스 사용자의 클라우드 기반 저장소](../media/EHAMShard1.png)
  
<span data-ttu-id="9516a-125">이 기능 외에도 eDiscovery 도구를 사용하여 클라우드 기반 SharePoint 사이트 및 각 Microsoft Teams와 연결된 Exchange 사서함 및 클라우드 기반 사용자를 위한 Exchange Online 사서함의 1xN Teams 채팅 데이터에서 Teams 콘텐츠를 검색하고 미리 보고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-125">In addition to this capability, you can also use eDiscovery tools to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a><span data-ttu-id="9516a-126">콘텐츠 검색 및 핵심 eDiscovery 검색 도구에서 이 기능을 지원하는 방법</span><span class="sxs-lookup"><span data-stu-id="9516a-126">How this feature is supported in Content search and Core eDiscovery search tools</span></span>

<span data-ttu-id="9516a-127">Microsoft 365 규정 준수 센터의 핵심 eDiscovery 케이스와 연결된 콘텐츠 검색 및 검색 도구의 다음 UI 요소:</span><span class="sxs-lookup"><span data-stu-id="9516a-127">The following UI elements in Content search and in the search tool associated with Core eDiscovery cases in the Microsoft 365 compliance center:</span></span>
  
- <span data-ttu-id="9516a-128">**온-프레미스 사용자를 위한 앱 콘텐츠 추가** 확인란은 콘텐츠 검색 도구의 **위치** 마법사 페이지에 표시되고 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-128">The **Add app content for on-premises users** checkbox is displayed on the **Locations** wizard page in Content search tool and selected by default.</span></span> <span data-ttu-id="9516a-129">콘텐츠 검색에 온-프레미스 사용자의 클라우드 기반 저장소를 포함하려면 이 확인란을 선택된 상태로 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="9516a-129">Keep this checkbox selected to include the cloud-based storage for on-premises users in a content search.</span></span>

    !["온-프레미스 사용자를 위한 Office 앱 콘텐츠 추가" 확인란이 콘텐츠 검색 UI에 추가됩니다](../media/EHAMShardCheckBox.png)
  
- <span data-ttu-id="9516a-131">검색할 특정 사용자를 선택할 때 온-프레미스 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-131">You can search for on-premises users when you choose specific users to search for.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="9516a-132">온-프레미스 사용자의 Teams 채팅 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="9516a-132">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="9516a-133">다음은 Microsoft 365 규정 준수 센터에서 콘텐츠 검색을 사용하여 온-프레미스 사용자를 위해 Teams 채팅 데이터를 검색하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-133">Here's how to use Content search in the Microsoft 365 compliance center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="9516a-134">Microsoft 365 규정 준수 센터에서 **콘텐츠 검색** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-134">In the Microsoft 365 compliance center, go to **Content search**.</span></span>

2. <span data-ttu-id="9516a-135">**검색** 탭에서 **새 검색** 을 클릭하고 새 검색의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-135">On the **Searches** tab, click **New search**, and name the new search.</span></span>

3. <span data-ttu-id="9516a-136">**위치** 페이지에서 Exchange 편지함의 토글을 **켜짐** 으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="9516a-136">On the **Locations** page, set the toggle to **On** for Exchange mailboxes.</span></span> <span data-ttu-id="9516a-137">**온-프레미스 사용자를 위한 앱 컨텐츠 추가** 확인란이 표시되고 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-137">Notice that the **Add app content for on-premises users** checkbox is displayed and selected by default.</span></span>

4. <span data-ttu-id="9516a-138">특정 사용자에 대해 Teams 콘텐츠를 검색하려면 **사용자, 그룹 또는 팀 선택** 을 선택하고 검색에 포함할 특정 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-138">To search for Teams content for specific users, select **Choose user, groups, or teams** and choose specific users to include in the search.</span></span> <span data-ttu-id="9516a-139">그렇지 않은 경우 **다음** 을 클릭하여 모든 사용자(온-프레미스 사용자 포함)의 Teams 콘텐츠를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-139">Otherwise, click **Next** to search for Teams content for all users, including  on-premises users</span></span>

5. <span data-ttu-id="9516a-140">**검색 조건 정의** 페이지에서 키워드 쿼리를 만들고 필요한 경우 검색 쿼리에 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-140">On the **Define your search conditions** page, create a keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="9516a-141">Teams 채팅 데이터만 검색하려면 **키워드** 상자에 다음 쿼리를 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-141">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im AND kind:microsoftteams
    ```

6. <span data-ttu-id="9516a-142">검색을 제출하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-142">Submit and run the search.</span></span> <span data-ttu-id="9516a-143">온-프레미스 사용자의 모든 검색 결과는 다른 검색 결과와 같이 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-143">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="9516a-144">검색 결과(Teams 채팅 데이터 포함)를 PST 파일로 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-144">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="9516a-145">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9516a-145">For more information, see:</span></span>

    - [<span data-ttu-id="9516a-146">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="9516a-146">Create a search</span></span>](content-search.md)

    - [<span data-ttu-id="9516a-147">검색 결과 미리 보기</span><span class="sxs-lookup"><span data-stu-id="9516a-147">Preview search results</span></span>](preview-ediscovery-search-results.md)

    - [<span data-ttu-id="9516a-148">검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="9516a-148">Export search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="9516a-149">PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="9516a-149">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="9516a-150">보안 및 준수 센터 PowerShell에서 **New-ComplianceSearch** 및 **Set-ComplianceSearch** cmdlet을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-150">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="9516a-151">앞서 설명한 것처럼 PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 데는 지원 요청을 제출하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-151">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="9516a-152">[보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-152">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="9516a-153">다음 PowerShell 명령을 실행하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 콘텐츠 검색을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-153">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="9516a-154">*IncludeUserAppContent* 매개 변수는 *ExchangeLocation* 매개 변수로 지정된 한 명 이상의 사용자의 클라우드 기반 저장소를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-154">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="9516a-155">*AllowNotFoundExchangeLocationsEnabled* 를 통해 온-프레미스 사용자의 클라우드 기반 저장소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-155">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="9516a-156">이 매개 변수에 `$true` 값을 사용하는 경우 진행하기 전에 사서함의 존재 여부를 확인하는 검색을 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-156">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="9516a-157">이 클라우드 기반 저장소는 일반 클라우드 기반 사서함으로 확인되지 않으므로 온-프레미스 사용자의 클라우드 기반 저장소를 검색하려면 이 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-157">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="9516a-158">다음 예제에서는 Contoso 조직의 온-프레미스 사용자인 Sara Davis의 클라우드 기반 저장소에서 “redstone” 키워드를 포함하는 Teams 채팅을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-158">The following example searches for Teams chats that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="9516a-159">검색을 만든 후에 **Start-ComplianceSearch** cmdlet를 사용하여 검색을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-159">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span>
  
<span data-ttu-id="9516a-160">이러한 cmdlet 사용에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9516a-160">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="9516a-161">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="9516a-161">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="9516a-162">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="9516a-162">Set-ComplianceSearch</span></span>](/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="9516a-163">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="9516a-163">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="9516a-164">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="9516a-164">Known issues</span></span>

- <span data-ttu-id="9516a-165">현재 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-165">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="9516a-166">핵심 eDiscovery 사례 및 고급 eDiscovery 사례와 연결된 보류에 온-프레미스 사용자의 Teams 채팅 데이터를 배치하고 온-프레미스 사용자에 대해 Teams 채팅 또는 채널 메시지 보존 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-166">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="9516a-167">그러나 현재 온-프레미스 사용자에 대해 다른 콘텐츠 위치(예: Exchange 사서함 및 SharePoint 사이트) 보존 정책을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-167">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9516a-168">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="9516a-168">Frequently asked questions</span></span>

<span data-ttu-id="9516a-169">**온-프레미스 사용자를 위한 채팅 메시지를 검색하기 위해 지원 요청을 제출해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="9516a-169">**Do I have to submit a support request to search for chat messages for on-premises users?**</span></span>

<span data-ttu-id="9516a-170">아니요.</span><span class="sxs-lookup"><span data-stu-id="9516a-170">No.</span></span> <span data-ttu-id="9516a-171">이 기능은 기본적으로 모든 조직에 대해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-171">This feature is enabled by default for all organizations.</span></span> <span data-ttu-id="9516a-172">한때는 Microsoft 지원에 문의해야 했지만 더 이상 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-172">At one point, you did have to contact Microsoft Support but that is no longer the case.</span></span>
  
 <span data-ttu-id="9516a-173">**eDiscovery 도구가 모든 조직에서 기본적으로 이 기능을 사용하도록 설정하기 전의 온-프레미스 사용자에 대해 이전 Teams 채팅 데이터를 찾을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="9516a-173">**Can eDiscovery tools find older Teams chat data for on-premises users before the time that this feature was enabled by default for all organizations?**</span></span>
  
<span data-ttu-id="9516a-p116">Microsoft는 2018년 1월 31일에 온-프레미스 사용자용 Teams 채팅 데이터를 저장하기 시작했습니다. 따라서 이 날짜 이후 온-프레미스 Active Directory와 Microsoft 365의 Azure Active Directory 간에 온-프레미스 Teams 사용자의 ID가 동기화되면 해당 Teams 채팅 데이터가 클라우드에 저장되고 eDiscovery 도구를 사용하여 이를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-p116">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018. So, if the identity of an on-premises Teams user has been synched between you on-premises Active Directory and Azure Active Directory in Microsoft 365 since this date, then their Teams chat data is stored in the cloud and is searchable using eDiscovery tools.</span></span>

 <span data-ttu-id="9516a-176">**온-프레미스 사용자가 클라우드에 Teams 채팅 데이터를 저장하려면 라이선스가 필요하나요?**</span><span class="sxs-lookup"><span data-stu-id="9516a-176">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="9516a-p117">네. 클라우드 기반 저장소에 온-프레미스 사용자의 Teams 채팅 데이터를 저장하려면 사용자에게 Microsoft Teams 라이선스 및 Office 365(또는 Microsoft 365)의 Exchange Online 플랜 라이선스가 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-p117">Yes. To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>

<span data-ttu-id="9516a-179">**온-프레미스 사용자의 클라우드 기반 저장소는 어디에 있나요?**</span><span class="sxs-lookup"><span data-stu-id="9516a-179">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="9516a-180">Teams 채팅 데이터는 온-프레미스 사용자의 PDL(기본 데이터 위치)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-180">Teams chat data is stored in the Preferred Data Location (PDL) for an on-premises user.</span></span> <span data-ttu-id="9516a-181">PDL은 Single-Geo 및 Multi-Geo 환경에서 모두 존중됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-181">The PDL is honored in both Single-Geo and Multi-Geo environments.</span></span> <span data-ttu-id="9516a-182">자세한 내용은 [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9516a-182">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

<span data-ttu-id="9516a-183">**사용자의 온-프레미스 사서함이 클라우드로 마이그레이션될 경우 Teams 채팅 데이터가 손실될 위험이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="9516a-183">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="9516a-p119">아니요. 온-프레미스 사용자의 기본 사서함을 클라우드로 마이그레이션하면 해당 사용자의 Teams 채팅 데이터가 새 클라우드 기반 기본 사서함으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-p119">No. When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="9516a-186">**온-프레미스 사용자에게 eDiscovery 보류 또는 보존 정책을 적용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="9516a-186">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="9516a-187">예.</span><span class="sxs-lookup"><span data-stu-id="9516a-187">Yes.</span></span> <span data-ttu-id="9516a-188">온-프레미스 사용자의 Teams 채팅 및 채널 메시지에 대한 eDiscovery 보류 또는 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-188">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span> <span data-ttu-id="9516a-189">그러나 온-프레미스 사용자에 대해 Teams 콘텐츠를 보존하거나 보관하려면 Exchange Online 플랜 2 라이선스를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9516a-189">However, to preserve or retain Teams content for on-premises users, an on-premises user must be assigned an Exchange Online Plan 2 license.</span></span>
