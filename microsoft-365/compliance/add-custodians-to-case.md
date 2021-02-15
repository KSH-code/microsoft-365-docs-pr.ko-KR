---
title: 고급 eDiscovery 사례에 custodians 추가
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery의 기본 제공 관리 도구를 사용하여 워크플로를 조정하고 관련 데이터 원본을 식별하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740345"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="c5238-103">고급 eDiscovery 사례에 custodians 추가</span><span class="sxs-lookup"><span data-stu-id="c5238-103">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="c5238-104">Advanced eDiscovery의 기본 제공 관리 도구를 사용하여 보호자 관리 및 사례와 관련된 관련성 있는 데이터 원본 식별과 관련된 워크플로를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-104">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="c5238-105">보유자를 추가하면 시스템에서 Exchange 사서함 및 비즈니스용 OneDrive 계정을 자동으로 식별하고 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-105">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="c5238-106">조사를 진행하는 동안, 보호자들이 액세스하거나 참가한 다른 데이터 원본(예: 사서함, 사이트 또는 Teams)을 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-106">During the discovery process of your investigation, you might also identify other data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="c5238-107">이 경우 관리 도구를 사용하여 해당 데이터 원본을 특정 관리인과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-107">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="c5238-108">사례에 양도인을 추가하고 다른 데이터 원본을 연결한 후 데이터를 빠르게 보존하고 양도 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-108">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="c5238-109">Advanced eDiscovery 사례에서 다음 4단계로 보안 주도를 추가하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-109">You can add and manage custodians in Advanced eDiscovery cases in four steps:</span></span>

1. <span data-ttu-id="c5238-110">양도인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-110">Identify the custodians.</span></span>

2. <span data-ttu-id="c5238-111">보호자 데이터 위치를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5238-111">Choose custodian data locations.</span></span>

3. <span data-ttu-id="c5238-112">보류 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-112">Configure hold settings.</span></span>

4. <span data-ttu-id="c5238-113">양도인을 검토하고 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-113">Review the custodians and complete the process.</span></span>

   <span data-ttu-id="c5238-114">[![Advanced eDiscovery 사례의 원본 탭 ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c5238-114">[ ![Sources tab in Advanced eDiscovery case](../media/AeD-Sources-Tab.png) ](../media/AeD-Sources-Tab.png#lightbox)</span></span>

## <a name="make-sure-you-have-the-necessary-permissions"></a><span data-ttu-id="c5238-115">필요한 사용 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c5238-115">Make sure you have the necessary permissions</span></span>

<span data-ttu-id="c5238-116">사례에 관리자를 추가하려면 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-116">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="c5238-117">이렇게 하면 보유자에 사례를 추가하고 보유 데이터 원본을 보류하는 데 필요한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-117">This provides you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span> <span data-ttu-id="c5238-118">자세한 내용은 [eDiscovery 권한 할당](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5238-118">For more information, see [Assign eDiscovery permissions](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).</span></span>

## <a name="step-1-identify-custodians"></a><span data-ttu-id="c5238-119">1단계: 양도자 식별</span><span class="sxs-lookup"><span data-stu-id="c5238-119">Step 1: Identify custodians</span></span>

1. <span data-ttu-id="c5238-120">적절한 eDiscovery 권한이 할당된 사용자 계정으로 이동하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-120">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="c5238-121">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-121">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="c5238-122">Advanced **eDiscovery** 페이지에서 사례  탭을 클릭한 다음, 보금주를 추가할 사례를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-122">On the **Advanced eDiscovery** page, click the **Cases** tab, and then select the case that you want to add custodians to.</span></span>

4. <span data-ttu-id="c5238-123">데이터 원본 **탭을 클릭한** 다음 데이터 원본 추가를 클릭합니다.   >  </span><span class="sxs-lookup"><span data-stu-id="c5238-123">Click the **Data sources** tab and then click **Add data source** > **Add new custodians**.</span></span>

5. <span data-ttu-id="c5238-124">사용자 이름 또는 별칭의 첫 번째 부분을 입력하여 조직의 한 명 이상의 사용자를 케이스에 관리인으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-124">Add one or more users in your organization as custodians to the case by typing the first part of a person's name or alias.</span></span> <span data-ttu-id="c5238-125">올바른 사람을 찾은 후 이름을 선택하여 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-125">After you find the correct person, select their name to add them to the list.</span></span>

## <a name="step-2-choose-custodian-data-locations"></a><span data-ttu-id="c5238-126">2단계: 보호자 데이터 위치 선택</span><span class="sxs-lookup"><span data-stu-id="c5238-126">Step 2: Choose custodian data locations</span></span>

<span data-ttu-id="c5238-127">관리인을 선택한 후 시스템은 이러한 사용자 및 해당 데이터 원본을 자동으로 식별하고 확인하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-127">After you select custodians, the system automatically attempts to identify and verify these users and their data sources.</span></span> <span data-ttu-id="c5238-128">목록에 관리인을 추가한 후 도구에는 각 관리인에 대한 기본 사서함 및 OneDrive 계정이 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-128">After adding custodians to the list, the tool automatically includes the primary mailbox and OneDrive account for each custodian.</span></span> <span data-ttu-id="c5238-129">사례에 보호자 추가 시 이러한 데이터 원본을 포함하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-129">You can choose not to include these data sources when adding custodians to the case.</span></span>

<span data-ttu-id="c5238-130">관리인의 사서함 및 OneDrive 계정 외에, 다른 데이터 위치(예: SharePoint 사이트 또는 관리인이 구성원인 Microsoft 팀)에 연결될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-130">In addition to a custodian's mailbox and OneDrive account, you can also associate other data locations to a custodian, such as SharePoint site or a Microsoft Team the custodian is a member of.</span></span> <span data-ttu-id="c5238-131">이를 통해 사례의 보호자와 연결된 다른 데이터 원본의 콘텐츠를 보존, 수집, 분석 및 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-131">This allows you to preserve, collect, analyze, and review content in other data sources associated with the custodians of the case.</span></span>

<span data-ttu-id="c5238-132">관리자에 대한 기본 사서함 및 OneDrive 계정을 선택을 선택을 하려면</span><span class="sxs-lookup"><span data-stu-id="c5238-132">To deselect the primary mailbox and OneDrive account for a custodian:</span></span>

1. <span data-ttu-id="c5238-133">각 보호자에 자동으로 연결된 기본 데이터 위치를 볼 수 있는 보호자 확장</span><span class="sxs-lookup"><span data-stu-id="c5238-133">Expand the custodian to view the primary data locations that have been automatically associated to each custodian.</span></span>

2. <span data-ttu-id="c5238-134">사서함 **또는**  **OneDrive** 옆의 지우기를 선택하여 이 관리인의 데이터 위치로 연결되지 못하게 하는 보호자 사서함 또는 OneDrive 계정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-134">Select **Clear** next to **Mailbox** or **OneDrive** to remove a custodian's mailbox or OneDrive account from being associated as a data location for this custodian.</span></span>

   ![관리인과 연결하도록 위치 구성](../media/ConfigureCustodianLocations.png)

<span data-ttu-id="c5238-136">다른 사서함, 사이트, Teams 또는 Yammer 특정 Yammer 연결:</span><span class="sxs-lookup"><span data-stu-id="c5238-136">To associate other mailboxes, sites, Teams, or Yammer groups to a specific custodian:</span></span>

1. <span data-ttu-id="c5238-137">보호자 확장을 확장하여 다음 서비스를 표시하여 데이터 위치를 관리인과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-137">Expand a custodian to display the following services to associate data locations with the custodian.</span></span> <span data-ttu-id="c5238-138">서비스 **옆에** 있는 편집을 클릭하여 데이터 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-138">Click **Edit** next to a service to add a data location.</span></span>

   - <span data-ttu-id="c5238-139">**Exchange**: 다른 사서함을 거래소에 연결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-139">**Exchange**: Use to associate other mailboxes to the custodian.</span></span> <span data-ttu-id="c5238-140">사용자 사서함 또는 메일 그룹의 이름 또는 별칭(최소 3자)을 검색 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-140">Type into the search box the name or alias (a minimum of three characters) of user mailboxes or distribution groups.</span></span> <span data-ttu-id="c5238-141">Custodian에 할당할 사서함을 선택한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5238-141">Select the mailboxes to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="c5238-142">**SharePoint**: SharePoint 사이트를 양도자에 연결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-142">**SharePoint**: Use to associate SharePoint sites to the custodian.</span></span> <span data-ttu-id="c5238-143">목록에서 사이트를 선택하거나 검색 상자에 URL을 입력하여 사이트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-143">Select a site in the list or search for a site by typing a URL in the search box.</span></span> <span data-ttu-id="c5238-144">양도자에 할당할 사이트를 선택하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5238-144">Select the sites to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="c5238-145">**Teams:** Microsoft Teams를 관리인이 현재 구성원으로 할당하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-145">**Teams**: Use to assign the Microsoft Teams the custodian is currently a member of.</span></span> <span data-ttu-id="c5238-146">양도인에게 할당할 팀을 선택한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5238-146">Select the teams to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="c5238-147">팀을 추가한 후 시스템은 자동으로 해당 팀에 연결된 SharePoint 사이트 및 그룹 사서함을 식별하고 찾아서 관리인에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-147">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that team and assigns them to the custodian.</span></span>

   - <span data-ttu-id="c5238-148">**Yammer**: Yammer 현재 구성원인 그룹 그룹을 할당하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-148">**Yammer**:  Use to assign the Yammer groups the custodian is currently a member of.</span></span> <span data-ttu-id="c5238-149">양도자에 할당할 그룹을 선택한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5238-149">Select the groups to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="c5238-150">팀을 추가한 후 시스템은 자동으로 해당 그룹에 연결된 SharePoint 사이트 및 그룹 사서함을 식별하고 찾아서 관리인에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-150">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that group and assigns them to the custodian.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c5238-151">**Exchange** 및 **SharePoint** 위치 선택을 사용하여 다른 팀 또는 Yammer 그룹(보류자는 구성원이 아닌 그룹)을 교환원과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-151">You can use the **Exchange** and **SharePoint** location pickers to associate other teams or Yammer groups (that a custodian is not a member of) to a custodian.</span></span> <span data-ttu-id="c5238-152">이 작업을 위해 각 팀 또는 그룹과 연결된 사서함과 사이트를 Yammer 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-152">To do this, you have to add both the mailbox and site associated with each team or Yammer group.</span></span>

2. <span data-ttu-id="c5238-153">표의 각 관리인을 확장하여 각 Yammer 할당된 사서함, 사이트, Teams 및 Yammer 그룹의 총 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-153">You can view the total number of mailboxes, sites, Teams, and Yammer groups assigned to each custodian by expanding each custodian in the table.</span></span> <span data-ttu-id="c5238-154">각 관리자에 대해 할당된 데이터 위치를 완료하면 이러한 연결은 Advanced eDiscovery 워크플로의 수집, 처리 및 검토 단계에서 유지 관리 및 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-154">When you've finalized the assigned data locations for each custodian, these associations will be maintained and used during the collection, processing, and review stages in the Advanced eDiscovery workflow.</span></span>

3. <span data-ttu-id="c5238-155">보유자 추가 및 데이터 위치 구성 후 다음을 클릭하여 보류 설정 **페이지로** 이동합니다. </span><span class="sxs-lookup"><span data-stu-id="c5238-155">After adding custodians and configuring their data locations, click **Next** to go to the **Hold settings** page.</span></span>  

## <a name="step-3-configure-hold-settings"></a><span data-ttu-id="c5238-156">3단계: 보류 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c5238-156">Step 3: Configure hold settings</span></span>

 <span data-ttu-id="c5238-157">보유자 및 해당 데이터 위치를 마무리한 후 보유자 중 일부 또는 전체를 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-157">After you've finalized the custodians and their data locations, you can place some or all of the custodians on hold.</span></span> <span data-ttu-id="c5238-158">보유자는 보류를 해제하거나 보류에서 해제할 때까지 보유자와 연결된 모든 콘텐츠 위치에 있는 모든 콘텐츠가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-158">When you place a custodian on hold, all content in all content locations that are associated with the custodian is preserved until you remove the hold or release the custodian from the hold.</span></span> <span data-ttu-id="c5238-159">경우에 따라 보유를 보류하지 않고 사례에 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-159">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="c5238-160">보유자 및 데이터 원본을 보류합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-160">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="c5238-161">보류 **설정 페이지에서** 보류 열 아래에 있는 확인란을 선택하여 개별 보유자에 보류를 적용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-161">On the **Hold settings** page, you can apply a hold to individual custodians by selecting the checkbox under the **Hold** column.</span></span>

   <span data-ttu-id="c5238-162">또는 열의 맨 위에 있는 보류 확인란을 선택하여  모든 보유자에 대한 보류를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-162">Alternatively, you can place all custodians on hold by selecting the **Hold** checkbox at the top of the column.</span></span>

2. <span data-ttu-id="c5238-163">보유자 선택을 확인하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5238-163">Verify the custodian hold selections and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c5238-164">보유자에 보류를 두지 않는 경우 보유자 및 관련 데이터 원본이 사례에 추가되지만 해당 데이터 원본의 콘텐츠는 사례와 연결된 보류로 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-164">If you don't place a hold on a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources won't preserved by the hold that associated with the case.</span></span>

## <a name="step-4-review-the-custodians-and-complete-the-process"></a><span data-ttu-id="c5238-165">4단계: 양도인 검토 및 프로세스 완료</span><span class="sxs-lookup"><span data-stu-id="c5238-165">Step 4: Review the custodians and complete the process</span></span>

<span data-ttu-id="c5238-166">실제로 보유자에 사례를 추가하기 전에 보유자 목록, 보유자에 할당된 데이터 위치 및 보류 설정을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-166">Before you actually add the custodians to the case, you can review the list of custodians, the data locations assigned to them, and the hold settings.</span></span>

1. <span data-ttu-id="c5238-167">테이블의 각 보유자에 연결된 모든 데이터 원본 수 및 보류 설정을 확인하고 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-167">Verify and review all the data sources count and the hold setting associated with each custodian in the table.</span></span> <span data-ttu-id="c5238-168">필요한 경우 보유자 식별 **또는** 설정 보류 페이지로 돌아가서 변경합니다. </span><span class="sxs-lookup"><span data-stu-id="c5238-168">If necessary, go back to the **Identify custodian** or **Hold settings** pages to make any changes.</span></span>

2. <span data-ttu-id="c5238-169">**제출을** 클릭하여 보유자 및 해당 데이터 위치를 사례에 추가하고 모든 보유 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-169">Click **Submit** to add custodians and their data locations to the case and apply all custodial hold settings.</span></span>

   <span data-ttu-id="c5238-170">새 보호자는 사례에 추가되고 데이터 원본 **탭에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5238-170">The new custodians are added to the case and displayed on the **Data sources** tab.</span></span>

   <span data-ttu-id="c5238-171">[![데이터 원본 탭에 나열된 보호자 ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c5238-171">[ ![Custodians listed on the Data sources tab](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)</span></span>
