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
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="1f66a-103">온-프레미스 사용자의 Teams 채팅 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="1f66a-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="1f66a-104">조직에 Exchange 하이브리드 배포가 있고 (또는 Office 365를 사용하여 조직을 온-프레미스 Exchange 조직과 동기화하고) Microsoft Teams를 사용한 경우 온-프레미스 사용자는 Teams 채팅 응용 프로그램을 사용하여 인스턴트 메시지를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="1f66a-105">클라우드 기반 사용자의 경우 Teams 채팅 데이터(*1x1 또는 1xN 채팅* 이라고도 함)는 기본 클라우드 기반 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="1f66a-106">온-프레미스 사용자가 Teams 채팅 응용 프로그램을 사용하는 경우 채팅 메시지는 온-프레미스에 위치한 기본 사서함에 저장될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="1f66a-107">이 문제를 해결하기 위해 Microsoft는 eDiscovery 도구를 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 내보낼 수 있도록 클라우드 기반 저장소 영역을 만드는 새로운 기능을 출시했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="1f66a-108">다음은 온-프레미스 사용자의 클라우드 기반 사서함을 설정하기 위한 요구 사항 및 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="1f66a-109">온-프레미스 디렉터리 서비스(예: Active Directory)의 사용자 계정은 Microsoft 365의 디렉터리 서비스인 Azure Active Directory와 동기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="1f66a-110">즉, 메일 사용자 계정이 Microsoft 365에서 만들어지고 기본 사서함이 온-프레미스 조직에 있는 사용자와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="1f66a-111">기본 사서함이 온-프레미스 조직에 있는 사용자에게 Microsoft Teams 라이선스와 최소 Exchange Online 계획 1 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="1f66a-112">온-프레미스 사용자와 연결된 Teams 채팅 데이터만 클라우드 기반 저장소 영역에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-112">Only Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="1f66a-113">온-프레미스 사용자는 이 저장소 영역에 어떤 방법으로든 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-113">An on-premises user can't access this storage area in any way.</span></span>

- <span data-ttu-id="1f66a-114">조직에서 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있도록 Microsoft 지원 요청을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-114">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="1f66a-115">이 문서의 [이 기능을 사용하도록 설정할 수 있도록 Microsoft 지원 요청 제출](#filing-a-request-with-microsoft-support-to-enable-this-feature)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f66a-115">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="1f66a-116">Teams 채널 대화는 항상 팀과 연결된 클라우드 기반 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="1f66a-117">즉 지원 요청을 제출할 필요 없이 콘텐츠 검색을 사용하여 채널 대화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-117">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="1f66a-118">Teams 채널 대화를 검색하는 방법에 대한 자세한 내용은 [Microsoft Teams 및 Microsoft 365 그룹 검색](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f66a-118">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="1f66a-119">작동 방식</span><span class="sxs-lookup"><span data-stu-id="1f66a-119">How it works</span></span>

<span data-ttu-id="1f66a-120">Microsoft Teams 지원 사용자에게 온-프레미스 사서함이 있고 사용자 계정/ID가 클라우드에 동기화된 경우 Microsoft는 온-프레미스 사용자의 1xN Teams 채팅 데이터와 연결된 클라우드 기반 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-120">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="1f66a-121">온-프레미스 사용자의 Teams 채팅 데이터는 검색을 위해 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-121">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="1f66a-122">따라서 콘텐츠 검색(및 핵심 eDiscovery 사례와 고급 eDiscovery 사례와 연결된 검색)을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-122">This lets you Use Content Search (and searches associated with Core and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="1f66a-123">보안 및 규정 준수 센터 PowerShell에서 **\*ComplianceSearch** cmdlet을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-123">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="1f66a-124">다음 그래픽은 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보내는 방법에 대한 워크플로를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-124">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams에서 온-프레미스 사용자의 클라우드 기반 저장소](../media/EHAMShard1.png)
  
<span data-ttu-id="1f66a-126">이 새로운 기능 외에도 클라우드 기반 사용자의 Exchange Online 사서함에서 콘텐츠 검색을 사용하여 각 Microsoft Team 및 1xN Teams 채팅 데이터와 연결된 클라우드 기반 SharePoint 사이트와 Exchange 사서함의 Teams 콘텐츠를 검색하고 미리 보고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-126">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="1f66a-127">이 기능을 사용하도록 설정할 수 있도록 Microsoft 지원 요청 제출</span><span class="sxs-lookup"><span data-stu-id="1f66a-127">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="1f66a-128">조직에서 보안 및 준수 센터의 그래픽 사용자 인터페이스를 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있도록 하려면 Microsoft 지원에 요청을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-128">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="1f66a-129">이 기능은 보안 및 준수 센터 PowerShell에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-129">This feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="1f66a-130">PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 데는 지원 요청을 제출하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-130">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="1f66a-131">Microsoft 지원 요청을 제출할 때 다음 정보를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-131">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="1f66a-132">조직의 기본 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="1f66a-132">The default domain name of your organization.</span></span>

- <span data-ttu-id="1f66a-133">조직의 테넌트 이름 및 테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="1f66a-133">The tenant name and tenant ID of your organization.</span></span> <span data-ttu-id="1f66a-134">이를 Azure Active Directory 포털(**관리** \> **속성** 아래)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-134">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="1f66a-135">[Microsoft 365 테넌트 ID 찾기](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f66a-135">See [Find your Microsoft 365 tenant ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).</span></span>

- <span data-ttu-id="1f66a-136">다음은 지원 요청의 목적에 대한 다음 제목 또는 설명입니다. “온-프레미스 사용자의 응용 프로그램 콘텐츠 검색 사용”</span><span class="sxs-lookup"><span data-stu-id="1f66a-136">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="1f66a-137">이를 통해 요청을 구현할 eDiscovery 엔지니어 팀에게 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-137">This helps route the request to the eDiscovery engineering team who will implement the request.</span></span>

<span data-ttu-id="1f66a-138">엔지니어링 변경되면 Microsoft 지원에서 예상 배포 날짜를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-138">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="1f66a-139">지원 요청을 제출한 후에는 일반적으로 배포 프로세스에 2~3 주 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-139">The deployment process usually takes 2–3 weeks after you submit the support request.</span></span>
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="1f66a-140">이 기능을 사용하도록 설정한 후에는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="1f66a-140">What happens after this feature is enabled?</span></span>

<span data-ttu-id="1f66a-141">조직에 이 기능이 배포된 후 콘텐츠 검색과 보안 및 준수 센터의 eDiscovery 사례와 연결된 검색에서 다음과 같은 사항이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-141">After this feature is deployed in your organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="1f66a-142">**온-프레미스 사용자를 위한 Office 앱 콘텐츠 추가** 확인란이 콘텐츠 검색의 **위치** 아래에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-142">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span>

    !["온-프레미스 사용자를 위한 Office 앱 콘텐츠 추가" 확인란이 콘텐츠 검색 UI에 추가됩니다](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="1f66a-144">검색할 사용자 사서함을 선택할 때 사용하는 콘텐츠 위치 선택기에 온-프레미스 사용자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-144">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="1f66a-145">온-프레미스 사용자의 Teams 채팅 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="1f66a-145">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="1f66a-146">해당 기능을 사용하도록 설정하면 보안 및 규정 준수 센터의 콘텐츠 검색을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-146">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="1f66a-147">보안 및 준수 센터에서 **검색** \> **콘텐츠 검색** 으로 이동합니다</span><span class="sxs-lookup"><span data-stu-id="1f66a-147">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>

2. <span data-ttu-id="1f66a-148">**검색** 페이지에서 ![아이콘 추가](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **새 검색** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-148">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>

    <span data-ttu-id="1f66a-149">앞서 설명한 것처럼 **온-프레미스 사용자를 위한 Office 앱 콘텐츠 추가** 확인란이 **위치** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-149">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="1f66a-150">이 확인란은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-150">It's selected by default.</span></span>

3. <span data-ttu-id="1f66a-151">키워드 쿼리를 만들고 필요한 경우 검색 쿼리에 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-151">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="1f66a-152">팀 채팅 데이터만 검색하려면 **키워드** 상자에 다음 쿼리를 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-152">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im
    ```

4. <span data-ttu-id="1f66a-153">이 시점에서 **위치** 아래에서 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-153">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="1f66a-154">**모든 위치:** 조직에 있는 모든 사용자의 사서함을 검색하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-154">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="1f66a-155">해당 확인란을 선택하면 온-프레미스 사용자에 대한 Teams 채팅 데이터의 모든 클라우드 기반 저장소도 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-155">When the checkbox is selected, all cloud-based storage of Teams chat data for on-premises users will also be searched.</span></span>

    - <span data-ttu-id="1f66a-156">**특정 위치:** 이 옵션을 선택한 다음 **수정** 을 클릭하고 \> 사용자, 그룹 또는 팀을 선택하여 특정 사서함을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-156">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="1f66a-157">앞서 설명한 것처럼 위치 선택기를 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-157">As previously explained, the locations picker lets you search for Teams chat data for on-premises users.</span></span>

5. <span data-ttu-id="1f66a-158">검색을 저장하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-158">Save and run the search.</span></span> <span data-ttu-id="1f66a-159">온-프레미스 사용자의 모든 검색 결과는 다른 검색 결과와 같이 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-159">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="1f66a-160">검색 결과(Teams 채팅 데이터 포함)를 PST 파일로 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-160">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="1f66a-161">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f66a-161">For more information, see:</span></span>

    - [<span data-ttu-id="1f66a-162">검색 만들기</span><span class="sxs-lookup"><span data-stu-id="1f66a-162">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="1f66a-163">검색 결과 미리 보기</span><span class="sxs-lookup"><span data-stu-id="1f66a-163">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="1f66a-164">콘텐츠 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="1f66a-164">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="1f66a-165">PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="1f66a-165">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="1f66a-166">보안 및 준수 센터 PowerShell에서 **New-ComplianceSearch** 및 **Set-ComplianceSearch** cmdlet을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-166">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="1f66a-167">앞서 설명한 것처럼 PowerShell을 사용하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 데는 지원 요청을 제출하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-167">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="1f66a-168">[보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-168">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="1f66a-169">다음 PowerShell 명령을 실행하여 온-프레미스 사용자의 Teams 채팅 데이터를 검색하는 콘텐츠 검색을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-169">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="1f66a-170">*IncludeUserAppContent* 매개 변수는 *ExchangeLocation* 매개 변수로 지정된 한 명 이상의 사용자의 클라우드 기반 저장소를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-170">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="1f66a-171">*AllowNotFoundExchangeLocationsEnabled* 를 통해 온-프레미스 사용자의 클라우드 기반 저장소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-171">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="1f66a-172">이 매개 변수에 `$true` 값을 사용하는 경우 진행하기 전에 사서함의 존재 여부를 확인하는 검색을 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-172">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="1f66a-173">이 클라우드 기반 저장소는 일반 클라우드 기반 사서함으로 확인되지 않으므로 온-프레미스 사용자의 클라우드 기반 저장소를 검색하려면 이 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-173">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="1f66a-174">다음 예제에서는 Contoso 조직의 온-프레미스 사용자인 Sara Davis의 클라우드 기반 저장소에서 “redstone” 키워드를 포함하는 Teams 채팅(인스턴트 메시지)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-174">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="1f66a-175">검색을 만든 후에 **Start-ComplianceSearch** cmdlet를 사용하여 검색을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-175">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="1f66a-176">이러한 cmdlet 사용에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f66a-176">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="1f66a-177">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1f66a-177">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="1f66a-178">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1f66a-178">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="1f66a-179">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1f66a-179">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="1f66a-180">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="1f66a-180">Known issues</span></span>

- <span data-ttu-id="1f66a-181">현재 온-프레미스 사용자의 Teams 채팅 데이터를 검색하고 미리 보고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-181">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="1f66a-182">핵심 eDiscovery 사례 및 고급 eDiscovery 사례와 연결된 보류에 온-프레미스 사용자의 Teams 채팅 데이터를 배치하고 온-프레미스 사용자에 대해 Teams 채팅 또는 채널 메시지 보존 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-182">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="1f66a-183">그러나 현재 온-프레미스 사용자에 대해 다른 콘텐츠 위치(예: Exchange 사서함 및 SharePoint 사이트) 보존 정책을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-183">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1f66a-184">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="1f66a-184">Frequently asked questions</span></span>

<span data-ttu-id="1f66a-185">**온-프레미스 사용자의 클라우드 기반 저장소는 어디에 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1f66a-185">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="1f66a-186">Teams 채팅 데이터는 온-프레미스 사용자의 PDL(기본 데이터 위치)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-186">Teams chat data is stored in the Preferred Data Location (PDL) for an on-premises user.</span></span> <span data-ttu-id="1f66a-187">PDL은 Single-Geo 및 Multi-Geo 환경에서 모두 존중됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-187">The PDL is honored in both Single-Geo and Multi-Geo environments.</span></span> <span data-ttu-id="1f66a-188">자세한 내용은 [Microsoft 365 Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f66a-188">For more information, see [Microsoft 365 Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo).</span></span>
  
 <span data-ttu-id="1f66a-189">**지원 요청을 제출하는 것 외에도 다른 요구 사항이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1f66a-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
<span data-ttu-id="1f66a-190">앞서 설명한 것처럼 Office 365의 각 온-프레미스 사용자 계정에 해당하는 메일 사용자 계정을 만들려면 온-프레미스 사서함이 있는 사용자의 ID를 클라우드 기반 조직과 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-190">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="1f66a-191">또한 조직에 Office 365 Enterprise E1, E3 또는 E5 구독과 같은 Office 365 Enterprise 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-191">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span>
  
 <span data-ttu-id="1f66a-192">**사용자의 온-프레미스 사서함이 클라우드로 마이그레이션될 경우 Teams 채팅 데이터가 손실될 위험이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1f66a-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="1f66a-193">아니요.</span><span class="sxs-lookup"><span data-stu-id="1f66a-193">No.</span></span> <span data-ttu-id="1f66a-194">온-프레미스 사용자의 기본 사서함을 클라우드로 마이그레이션하면 해당 사용자의 Teams 채팅 데이터가 새 클라우드 기반 기본 사서함으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-194">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="1f66a-195">**온-프레미스 사용자에게 eDiscovery 보류 또는 보존 정책을 적용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1f66a-195">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="1f66a-196">예.</span><span class="sxs-lookup"><span data-stu-id="1f66a-196">Yes.</span></span> <span data-ttu-id="1f66a-197">온-프레미스 사용자의 Teams 채팅 및 채널 메시지에 대한 eDiscovery 보류 또는 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-197">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span>
  
 <span data-ttu-id="1f66a-198">**조직에서 이 기능을 사용하기 위해 요청을 제출하기 전에 콘텐츠 검색에서 온-프레미스 사용자의 이전 Teams 채팅 데이터를 찾을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1f66a-198">**Can Content Search find older Teams chat data for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="1f66a-199">Microsoft는 2018년 1월 31일에 온-프레미스 사용자의 Teams 채팅 데이터를 저장하기 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-199">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="1f66a-200">따라서 이 날짜 이후로 Active Directory와 Azure Active Directory 간에 온-프레미스 Teams 사용자의 ID가 동기화된 경우 Teams 채팅 데이터가 클라우드에 저장되며 콘텐츠 검색을 사용하여 이를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-200">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in the cloud and is searchable using Content Search.</span></span> <span data-ttu-id="1f66a-201">Microsoft는 2018년 1월 31일 이전부터 온-프레미스 사용자의 클라우드 기반 저장소에 Teams 채팅 데이터를 저장하는 기능을 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-201">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="1f66a-202">이에 대한 자세한 내용은 곧 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-202">More information about this will be available soon.</span></span>

 <span data-ttu-id="1f66a-203">**온-프레미스 사용자가 클라우드에 Teams 채팅 데이터를 저장하려면 라이선스가 필요하나요?**</span><span class="sxs-lookup"><span data-stu-id="1f66a-203">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="1f66a-204">예.</span><span class="sxs-lookup"><span data-stu-id="1f66a-204">Yes.</span></span> <span data-ttu-id="1f66a-205">클라우드 기반 저장소에 온-프레미스 사용자의 Teams 채팅 데이터를 저장하려면 사용자에게 Microsoft Teams 라이선스 및 Office 365(또는 Microsoft 365)의 Exchange Online 플랜 라이선스가 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f66a-205">To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>
