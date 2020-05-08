---
title: 기본 보호 기능으로 팀 구성
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365solutions
ms.custom:
- Ent_Solutions
description: 기본 수준의 보호로 팀을 배포하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 4be93ce98f0066dcc65d7f532bd1d9d50acae406
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159970"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="4f41a-103">기본 보호 기능으로 팀 구성</span><span class="sxs-lookup"><span data-stu-id="4f41a-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="4f41a-104">이 문서에서는 기본 수준의 보호 기능으로 팀을 배포하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="4f41a-105">이 수준을 통해 사용자는 다양한 공동 작업 옵션을 사용하면서 권한 관리를 강화하고 과잉 공유에 대한 기본 보호를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="4f41a-106">이 수준에 대한 권장 보호에는 ID 및 장치 액세스 정책과 맬웨어 방지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="4f41a-107">또한 필요에 따라 조건부 액세스 정책 및 데이터 손실 방지를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="4f41a-108">초기 보호</span><span class="sxs-lookup"><span data-stu-id="4f41a-108">Initial protections</span></span>

<span data-ttu-id="4f41a-109">첫 번째 단계로 기본 ID 및 장치 액세스 정책을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="4f41a-110">자세한 내용은 [팀 채팅, 그룹, 파일에 대한 정책 권장 사항](https://docs.microsoft.com/microsoft-365/enterprise/teams-access-policies)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-110">See [Policy recommendations for securing Teams chats, groups, and files](https://docs.microsoft.com/microsoft-365/enterprise/teams-access-policies) for details.</span></span>

<span data-ttu-id="4f41a-111">또한 문서, 첨부 파일 및 링크의 맬웨어를 방지하기 위해 기본 고급 위협 방지 기능을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-111">We also recommend turning on basic Advanced Threat Protection features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="4f41a-112">다음 표의 각 옵션을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="4f41a-113">옵션</span><span class="sxs-lookup"><span data-stu-id="4f41a-113">Option</span></span>|<span data-ttu-id="4f41a-114">정보</span><span class="sxs-lookup"><span data-stu-id="4f41a-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="4f41a-115">ATP SPO, OneDrive 및 팀을 위한 안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="4f41a-115">ATP Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="4f41a-116">Office 365 ATPATP 안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="4f41a-116">Office 365 ATP Safe Attachments</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[<span data-ttu-id="4f41a-117">SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4f41a-117">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|<span data-ttu-id="4f41a-118">ATP 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="4f41a-118">ATP Safe Documents</span></span>|[<span data-ttu-id="4f41a-119">Office 365 고급 위협 보호의 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="4f41a-119">Safe Documents in Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|<span data-ttu-id="4f41a-120">Teams용 ATP 안전 링크</span><span class="sxs-lookup"><span data-stu-id="4f41a-120">ATP Safe Links for Teams</span></span>|[<span data-ttu-id="4f41a-121">Teams의 Office 365 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="4f41a-121">Office 365 Safe Links in Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[<span data-ttu-id="4f41a-122">Office 365 ATP 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="4f41a-122">Office 365 ATP Safe Links</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="4f41a-123">Teams 게스트 공유</span><span class="sxs-lookup"><span data-stu-id="4f41a-123">Teams guest sharing</span></span>

<span data-ttu-id="4f41a-124">각 계층에서 조직 외부의 사용자와 공유할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="4f41a-125">중요하고 매우 중요한 계층의 경우 중요도 종류 레이블을 사용하여 팀 수준에서 게스트 공유를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="4f41a-126">그러나 팀에서 게스트 공유를 사용하려면 조직 수준의 게스트 공유 설정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Teams의 게스트 액세스 토글의 스크린샷](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="4f41a-128">Teams 게스트 액세스를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="4f41a-129">[https://admin.microsoft.com](https://admin.microsoft.com)에서 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="4f41a-130">왼쪽 탐색 창에서 **모두 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="4f41a-131">**관리 센터**에서 **Teams**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="4f41a-132">Teams 관리 센터의 왼쪽 탐색 창에서 **조직 전체 설정**을 확장한 다음 **게스트 액세스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="4f41a-133">Teams의 **게스트 액세스 허용**이 **사용**으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="4f41a-134">추가 게스트 설정을 원하는대로 변경 한 다음 **저장**을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="4f41a-135">Teams 게스트 설정을 켠 후 활성화되려면 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="4f41a-136">Office 365 그룹 ​​및 SharePoint에서는 게스트 공유가 기본적으로 사용 설정되어 있지만 이전에 조직의 게스트 공유 설정을 변경한 경우 [팀의 게스트와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 검토하여 게스트 공유를 Teams에서 사용할 수 있는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="4f41a-137">사이트 및 파일 공유</span><span class="sxs-lookup"><span data-stu-id="4f41a-137">Site and file sharing</span></span>

<span data-ttu-id="4f41a-138">실수로 조직 외부 사람과 파일 또는 폴더를 공유 할 위험을 줄이려면 SharePoint의 기본 공유 링크를 *조직 내 사용자 전용*으로 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="4f41a-139">(사용자가 외부에서 공유해야 하고 게스트 공유를 활성화한 경우 공유할 때 링크 유형을 계속 변경할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="4f41a-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="4f41a-140">기본 공유 링크를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="4f41a-140">To change the default sharing link</span></span>
1. <span data-ttu-id="4f41a-141">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="4f41a-142">**정책**에서 **공유**를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="4f41a-143">**파일 및 폴더 링크**에서 **조직 내 사용자만**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="4f41a-144">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-144">Click **Save**.</span></span>

<span data-ttu-id="4f41a-145">최상의 게스트 공유 환경을 위해서는 [Azure AD B2B와의 SharePoint 및 OneDrive 통합](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="4f41a-146">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="4f41a-146">Create a team</span></span>

<span data-ttu-id="4f41a-147">기준 수준의 보호에 대한 추가 구성은 팀과 연결된 SharePoint 사이트에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="4f41a-148">다음 섹션으로 진행하기 전에 [공개 또는 개인 팀을 만드세요](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="4f41a-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="4f41a-149">사이트 공유 설정</span><span class="sxs-lookup"><span data-stu-id="4f41a-149">Site sharing settings</span></span>

<span data-ttu-id="4f41a-150">기본적으로 SharePoint 사이트의 구성원은 다른 사용자를 사이트에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="4f41a-151">사이트가 팀의 일부인 경우 팀 구성원이 사이트 구성원으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="4f41a-152">그러나 사이트에 직접 추가된 사람들은 나머지 팀에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="4f41a-153">따라서 팀을 통해서만 권한을 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="4f41a-154">권한 관리를 돕기 위해 소유자만 사이트를 공유할 수 있도록 연결된 사이트를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="4f41a-155">이는 권한 관리를 단순화하고 팀 소유자 모르게 사람들이 액세스하지 못하게합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="4f41a-156">기본 보호가 필요한 각 팀에 대해 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="4f41a-157">사이트 공유 설정을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="4f41a-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="4f41a-158">팀의 도구 막대에서 **파일**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="4f41a-159">\*\* SharePoint에서 열기\*\*를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="4f41a-160">SharePoint 사이트의 도구 모음에서 설정 아이콘을 클릭한 다음 **사이트 권한**을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="4f41a-161">**사이트 권한** 창의 **공유 설정**에서 **공유 설정 변경**을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-161">In the **Site permissions** pane, under **Sharing settings**, click **Change sharing settings**.</span></span>
5. <span data-ttu-id="4f41a-162">**권한 공유**에서 **사이트 소유자 및 회원을 선택하고 편집 권한이 있는 사용자는 파일 및 폴더를 공유할 수 있지만 사이트 소유자 만 사이트를 공유할 수 있습니다**를 선택한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="4f41a-163">추가 보호</span><span class="sxs-lookup"><span data-stu-id="4f41a-163">Additional protections</span></span>

<span data-ttu-id="4f41a-164">Microsoft 365에서는 콘텐츠를 보호하기 위한 추가 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="4f41a-165">다음 옵션이 조직의 보안을 개선하는 데 도움이 되는지 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4f41a-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="4f41a-166">게스트 사용자가 [사용 약관](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)에 동의하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-166">Have your guest users agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="4f41a-167">게스트 사용자에 대한 [세션 시간 초과 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-167">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="4f41a-168">[중요한 정보 유형](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)을 만들고 [데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)를 사용하여 중요한 정보에 액세스하는 방법에 대한 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f41a-168">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f41a-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f41a-169">See Also</span></span>

[<span data-ttu-id="4f41a-170">Teams에서의 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4f41a-170">Manage meeting policies in Teams</span></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="4f41a-171">내부자 위험 관리 시작</span><span class="sxs-lookup"><span data-stu-id="4f41a-171">Get started with insider risk management</span></span>](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
