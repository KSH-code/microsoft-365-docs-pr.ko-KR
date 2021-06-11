---
title: 2013에서 Core eDiscovery 사례 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 2016에서 Core eDiscovery를 사용하는 방법을 Microsoft 365. eDiscovery 권한을 할당하고 사례를 만든 후 구성원을 추가하고 eDiscovery 보류를 만든 다음 조사와 관련된 콘텐츠를 검색하고 내보낼 수 있습니다.
ms.openlocfilehash: 00506c2f072fff6aa30c7d96bffdc18eb5eda20b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311019"
---
# <a name="get-started-with-core-ediscovery-in-microsoft-365"></a><span data-ttu-id="60175-104">2013에서 Core eDiscovery 시작 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60175-104">Get started with Core eDiscovery in Microsoft 365</span></span>

<span data-ttu-id="60175-105">Microsoft 365 핵심 eDiscovery는 조직이 조직에서 검색 및 내보낼 수 있는 기본 eDiscovery 도구를 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="60175-105">Core eDiscovery in Microsoft 365 provides a basic eDiscovery tool that organizations can use to search and export content in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="60175-106">또한 Core eDiscovery를 사용하여 콘텐츠 위치(예: Exchange 사서함, SharePoint 사이트, OneDrive 계정 및 콘텐츠 위치)에 eDiscovery 보류를 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="60175-106">You can also use Core eDiscovery to place an eDiscovery hold on content locations, such as Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft Teams.</span></span> <span data-ttu-id="60175-107">Core eDiscovery를 배포할 필요는 없지만 조직에서 Core eDiscovery를 사용하여 콘텐츠를 검색, 내보내고 보존하기 전에 IT 관리자 및 eDiscovery 관리자가 완료해야 하는 몇 가지 선행 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-107">Nothing is needed to deploy Core eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start using Core eDiscovery to search, export, and preserve content.</span></span>

<span data-ttu-id="60175-108">이 문서에서는 Core eDiscovery를 설정하는 데 필요한 단계에 대해 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-108">This article discusses the steps necessary to set up Core eDiscovery.</span></span> <span data-ttu-id="60175-109">여기에는 핵심 eDiscovery에 액세스하고 콘텐츠 위치에 eDiscovery 보류를 설정하는 데 필요한 적절한 라이선스를 보장하는 것뿐만 아니라 IT, 법률 및 조사 팀에 사용 권한을 할당하여 사례에 액세스하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-109">This includes ensuring the proper licensing required to access Core eDiscovery and place an eDiscovery hold on content locations, as well as assigning permissions to your IT, legal, and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="60175-110">또한 이 문서에서는 콘텐츠를 검색하고 내보내는 사례에 대한 간략한 개요도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-110">This article also provides a high-level overview of using cases to search for and export content.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="60175-111">1단계: 적절한 라이선스 확인 및 할당</span><span class="sxs-lookup"><span data-stu-id="60175-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="60175-112">Core eDiscovery에 대한 라이선스를 사용하려면 적절한 조직 구독 및 사용자당 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-112">Licensing for Core eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="60175-113">**조직 구독:** Microsoft 365 규정 준수 센터 또는 Office 365 보안 & 준수 센터에서 Core eDiscovery에 액세스하고 보류 및 내보내기 기능을 사용하려면 조직에 E3 Microsoft 365 E3 또는 Office 365 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-113">**Organization subscription:** To access Core eDiscovery in the Microsoft 365 compliance center or the Office 365 Security & Compliance Center and use the hold and export features, your organization must have a Microsoft 365 E3 or Office 365 E3 subscription or higher.</span></span>

- <span data-ttu-id="60175-114">**사용자당 라이선스:** 사서함 및 사이트에 eDiscovery를 유지하려면 조직 구독에 따라 사용자에게 다음 라이선스 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-114">**Per-user licensing:** To place an eDiscovery hold on mailboxes and sites, a user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="60175-115">E3 Microsoft 365 E3 또는 Office 365 이상</span><span class="sxs-lookup"><span data-stu-id="60175-115">A Microsoft 365 E3 or Office 365 E3 license or higher</span></span>

   <span data-ttu-id="60175-116">또는</span><span class="sxs-lookup"><span data-stu-id="60175-116">OR</span></span>

  - <span data-ttu-id="60175-117">Office 365 Exchange Online 계획 2 또는 Exchange Online Archiving 라이선스가 있는 E1 라이선스</span><span class="sxs-lookup"><span data-stu-id="60175-117">Office 365 E1 license with an Exchange Online Plan 2 or Exchange Online Archiving add-on license</span></span>

  <span data-ttu-id="60175-118">그리고</span><span class="sxs-lookup"><span data-stu-id="60175-118">AND</span></span>

  - <span data-ttu-id="60175-119">Office 365 SharePoint 계획 2 또는 비즈니스용 OneDrive 추가 기능 라이선스가 있는 E1 라이선스</span><span class="sxs-lookup"><span data-stu-id="60175-119">Office 365 E1 license with an SharePoint Online Plan 2 or OneDrive for Business Plan 2 add-on license</span></span>
  
  <span data-ttu-id="60175-120">라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="60175-120">For information about how to assign licenses, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).</span></span>

<span data-ttu-id="60175-121">라이선스에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="60175-121">For information about licensing:</span></span>

- <span data-ttu-id="60175-122">규정 준수 라이선싱 비교에서 "& 응답 검색" [솔루션을 Microsoft 365 참조합니다.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)</span><span class="sxs-lookup"><span data-stu-id="60175-122">Download and see the "Discover & Respond" solution in the [Microsoft 365 Compliance Licensing Comparison](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).</span></span>

- <span data-ttu-id="60175-123">보안 및 [준수 & 설명을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="60175-123">See the [Security & Compliance Center service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="60175-124">2단계: eDiscovery 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="60175-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="60175-125">Core eDiscovery에 액세스하거나 Core eDiscovery 사례의 구성원으로 추가하려면 사용자에게 적절한 사용 권한이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-125">To access Core eDiscovery or be added as a member of a Core eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="60175-126">특히 사용자를 Office 365 보안 및 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원으로 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="60175-127">이 역할 그룹의 구성원은 핵심 eDiscovery 사례를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-127">Members of this role group can create and manage Core eDiscovery cases.</span></span> <span data-ttu-id="60175-128">구성원을 추가 및 제거하고, 사용자에게 eDiscovery 보류를 추가하고, 검색을 만들고 편집하고, Core eDiscovery 사례에서 콘텐츠를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-128">They can add and remove members, place an eDiscovery hold on users, create and edit searches, and export content from a Core eDiscovery case.</span></span>

<span data-ttu-id="60175-129">다음 단계를 완료하여 eDiscovery 관리자 역할 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="60175-130">으로 이동하여 조직 또는 조직에서 관리자 계정의 자격 [https://protection.office.com/permissions](https://protection.office.com/permissions) 증명을 Microsoft 365 Office 365 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 or Office 365 organization.</span></span>

2. <span data-ttu-id="60175-131">사용 **권한 페이지에서** **eDiscovery 관리자 역할 그룹을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="60175-132">eDiscovery 관리자 플라이아웃 페이지에서  **eDiscovery** 관리자 섹션 옆에 있는 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="60175-133">역할 그룹 편집 **마법사의 eDiscovery 관리자 선택** 페이지에서 검색 관리자 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="60175-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="60175-134">**추가를** 클릭한 다음 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="60175-135">**추가를** 클릭하여 선택한 사용자를 추가한 다음 완료 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="60175-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="60175-136">**저장을** 클릭하여 역할 그룹에 사용자를 추가한  다음 닫기 를 클릭하여 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="60175-137">eDiscovery 관리자 역할 그룹에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="60175-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="60175-138">eDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="60175-139">이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="60175-140">**eDiscovery 관리자:** 작성하거나 구성원인 Core eDiscovery 사례를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-140">**eDiscovery Manager**: Can view and manage the Core eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="60175-141">다른 eDiscovery 관리자가 사례를 만들어 두 번째 eDiscovery 관리자(Manager)를 해당 사례의 구성원으로 추가하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 Core eDiscovery 페이지에서 사례를 보거나 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Core eDiscovery page in the compliance center.</span></span> <span data-ttu-id="60175-142">일반적으로 조직의 대부분의 사람은 eDiscovery 관리자 하위 조직에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="60175-143">**eDiscovery 관리자: eDiscovery** 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-143">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="60175-144">또한 eDiscovery 관리자는 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="60175-145">Core eDiscovery 페이지에 나열된 모든 사례를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="60175-145">View all cases that are listed on the Core eDiscovery page.</span></span>
  
  - <span data-ttu-id="60175-146">본인을 케이스의 구성원으로 추가한 후 조직의 케이스 관리</span><span class="sxs-lookup"><span data-stu-id="60175-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="60175-147">조직의 케이스에 대한 케이스 데이터 액세스 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="60175-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="60175-148">광범위한 액세스 권한으로 인해 조직에는 eDiscovery 관리자 하위 그룹의 구성원인 일부 관리자만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="60175-149">eDiscovery 사용 권한에 대한 자세한 내용과 eDiscovery 관리자 역할 그룹에 할당된 각 역할에 대한 설명은 [eDiscovery](assign-ediscovery-permissions.md)권한 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60175-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-create-a-core-ediscovery-case"></a><span data-ttu-id="60175-150">3단계: Core eDiscovery 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="60175-150">Step 3: Create a Core eDiscovery case</span></span>

<span data-ttu-id="60175-151">다음 단계는 사례를 만들고 Core eDiscovery 사용을 시작하는입니다.</span><span class="sxs-lookup"><span data-stu-id="60175-151">The next step is to create a case and start using Core eDiscovery.</span></span> <span data-ttu-id="60175-152">다음 단계를 완료하여 사례를 만들고 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-152">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="60175-153">사례를 만드는 사용자는 자동으로 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="60175-153">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="60175-154">으로 이동한 후 적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 [https://compliance.microsoft.com](https://compliance.microsoft.com) 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for a user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="60175-155">조직 관리 역할 그룹의 구성원은 핵심 eDiscovery 사례를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-155">Members of the Organization Management role group can also create Core eDiscovery cases.</span></span>

2. <span data-ttu-id="60175-156">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-156">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="60175-157">Core **eDiscovery** 페이지에서 사례 만들기 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="60175-157">On the **Core eDiscovery** page, click **Create a case**.</span></span>

4. <span data-ttu-id="60175-158">새 사례 **플라이아웃** 페이지에서 사례에 이름(필수)을 지정한 다음 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-158">On the **New case** flyout page, give the case a name (required) and then type an optional description.</span></span> <span data-ttu-id="60175-159">사례 이름은 조직에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-159">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="60175-160">**저장을** 클릭하여 사례를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-160">Click **Save** to create the case.</span></span>

   <span data-ttu-id="60175-161">새 사례가 만들어지며 Core eDiscovery 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60175-161">The new case is created and displayed on the Core eDiscovery page.</span></span> <span data-ttu-id="60175-162">새 사례를 표시하려면 **새로** 고침을 클릭해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-162">You may have to click **Refresh** to display the new case.</span></span>

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a><span data-ttu-id="60175-163">4단계(선택 사항): Core eDiscovery 사례에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="60175-163">Step 4 (optional): Add members to a Core eDiscovery case</span></span>

<span data-ttu-id="60175-164">3단계에서 사례를 만들고 사례를 사용할 유일한 사람인 경우 이 단계를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-164">If you create a case in Step 3 and you're the only person who will use the case, then you don't have to perform this step.</span></span> <span data-ttu-id="60175-165">사례를 사용하여 eDiscovery 보류를 만들고, 콘텐츠를 검색하고, 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-165">You can start using the case to create eDiscovery holds, search for content, and export search results.</span></span> <span data-ttu-id="60175-166">다른 사용자(또는 역할 그룹)에게 사례에 대한 액세스 권한을 부여하려는 경우 이 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-166">Perform this step if you want to give other users (or roles group) access to the case.</span></span>

1. <span data-ttu-id="60175-167">Microsoft 365 준수 센터의 **Core eDiscovery** 페이지에서 구성원을 추가할 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-167">On the **Core eDiscovery** page in the Microsoft 365 compliance center, click the name of the case that you want to add members to.</span></span>

2. <span data-ttu-id="60175-168">사례 홈 페이지에서 설정 **탭을** 선택한 다음 Access & **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="60175-168">On the case home page, select the **Settings** tab, and then select **Access & permissions**.</span></span>

3. <span data-ttu-id="60175-169">**Access** & 권한 플라이아웃 페이지의 구성원 **아래에서**  추가를 클릭하여 사례에 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-169">On the **Access & permissions** flyout page, under **Members**, click **Add** to add members to the case.</span></span>

    <span data-ttu-id="60175-170">역할 그룹을 사례의 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-170">You can also choose to add role groups as members of a case.</span></span> <span data-ttu-id="60175-171">역할 **그룹에서** 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="60175-171">Under **Role groups**, click **Add**.</span></span> <span data-ttu-id="60175-172">사례에 구성원으로 있는 역할 그룹만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-172">You can only assign the role groups that you are a member of to a case.</span></span> <span data-ttu-id="60175-173">역할 그룹이 eDiscovery 사례에 구성원을 할당할 수 있는 구성원을 제어하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="60175-173">That's because role groups control who can assign members to an eDiscovery case.</span></span>

4. <span data-ttu-id="60175-174">사례의 구성원으로 추가할 수 있는 사용자 또는 역할 그룹 목록에서 추가할 사용자(또는 역할 그룹)의 이름 왼쪽을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-174">In the list of people or role groups that can be added as members of the case, click to the left of the name of the people (or role groups) that you want to add.</span></span> <span data-ttu-id="60175-175">구성원으로 추가할 수 있는 사용자 또는 역할 그룹의 큰  목록이 있는 경우 검색 상자를 사용하여 목록에서 특정 사용자 또는 역할 그룹을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-175">If you have a large list of people or role groups who can added as members, use the **Search** box to search for a specific person or role group in the list.</span></span>
  
5. <span data-ttu-id="60175-176">사례의 구성원으로 추가할 사용자 또는 역할 그룹을 선택한  후 저장을 클릭하여 새 구성원 또는 역할 그룹을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-176">After you select the people or role groups to add as members of the case, click **Save** to save the new members or role groups.</span></span>

## <a name="explore-the-core-ediscovery-workflow"></a><span data-ttu-id="60175-177">Core eDiscovery 워크플로 살펴보기</span><span class="sxs-lookup"><span data-stu-id="60175-177">Explore the Core eDiscovery workflow</span></span>

<span data-ttu-id="60175-178">핵심 eDiscovery 사용을 시작하기 위해 관심 있는 사용자에 대해 eDiscovery 보류를 만들고, 조사와 관련된 콘텐츠를 검색한 다음 추가 검토를 위해 해당 데이터를 내보내는 간단한 워크플로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-178">To get you started using core eDiscovery, here's a simple workflow of creating eDiscovery holds for people of interest, searching for content that relevant to your investigation, and then exporting that data for further review.</span></span> <span data-ttu-id="60175-179">이러한 각 단계에서는 탐색할 수 있는 몇 가지 확장된 Core eDiscovery 기능도 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-179">In each of these steps, we'll also highlight some extended Core eDiscovery functionality that you can explore.</span></span>

![핵심 eDiscovery 워크플로](../media/CoreEdiscoveryWorkflow.png)

1. <span data-ttu-id="60175-181">**[eDiscovery 보류를 생성합니다.](create-ediscovery-holds.md)**</span><span class="sxs-lookup"><span data-stu-id="60175-181">**[Create an eDiscovery hold](create-ediscovery-holds.md)**.</span></span> <span data-ttu-id="60175-182">사례를 작성한 후 첫 번째 단계는 조사에 관심이 있는 사용자 콘텐츠 위치에 *보류(eDiscovery* 보류라고도 불리며)를 배치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60175-182">The first step after creating a case is placing a hold (also called an *eDiscovery hold*) on the content locations of the people of interest in your investigation.</span></span> <span data-ttu-id="60175-183">콘텐츠 위치에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정, Microsoft Teams 그룹과 연결된 사서함 및 Office 365 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="60175-183">Content locations include Exchange mailboxes, SharePoint sites, OneDrive accounts, and the mailboxes and sites associated with Microsoft Teams and Office 365 Groups.</span></span> <span data-ttu-id="60175-184">이 단계는 선택 사항이지만 eDiscovery 보류를 만들면 조사 중에 사례와 관련이 있을 수 있는 콘텐츠가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="60175-184">While this step is optional, creating an eDiscovery hold preserves content that may be relevant to the case during the investigation.</span></span> <span data-ttu-id="60175-185">eDiscovery 보류를 만들 때 특정 콘텐츠 위치에 있는 모든 콘텐츠를 보존하거나 쿼리 기반 보류를 만들어 보류 쿼리와 일치하는 콘텐츠만 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-185">When you create an eDiscovery hold you can preserve all content in specific content locations or you can create a query-based hold to preserve only the content that matches a hold query.</span></span> <span data-ttu-id="60175-186">다음 단계에서 검색을 만들고 실행할 때 eDiscovery 보류를 만드는 또 다른 좋은 이유는 검색할 각 위치를 선택하는 대신 보류된 콘텐츠 위치를 빠르게 검색하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60175-186">In addition to preserving content, another good reason to create eDiscovery holds is to quickly search the content locations on hold (instead of having to select each location to search) when you create and run searches in the next step.</span></span> <span data-ttu-id="60175-187">조사를 완료한 후 만든 보류를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-187">After you complete your investigation, you can release any hold that you created.</span></span>

2. <span data-ttu-id="60175-188">**[콘텐츠를 검색합니다.](search-for-content-in-core-ediscovery.md)**</span><span class="sxs-lookup"><span data-stu-id="60175-188">**[Search for content](search-for-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="60175-189">eDiscovery 보류를 만든 후 기본 제공 검색 도구를 사용하여 보류된 콘텐츠 위치를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-189">After you create eDiscovery holds, use the built-in search tool to search the content locations on hold.</span></span> <span data-ttu-id="60175-190">사례와 관련이 있을 수 있는 데이터의 다른 콘텐츠 위치를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-190">You can also search other content locations for data that may be relevant to the case.</span></span> <span data-ttu-id="60175-191">사례와 연결된 다양한 검색을 만들고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-191">You can create and run different searches that are associated with the case.</span></span> <span data-ttu-id="60175-192">키워드, 속성 및 조건을 사용하여 [](keyword-queries-and-search-conditions.md) 사례와 관련성이 가장 높은 데이터로 검색 결과를 반환하는 검색 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-192">You use keywords, properties, and conditions to [build search queries](keyword-queries-and-search-conditions.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="60175-193">또한 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-193">You can also:</span></span>

   - <span data-ttu-id="60175-194">검색 쿼리를 구체화하여 결과 범위를 좁히는 데 도움이 될 수 있는 검색 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-194">View search statistics that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="60175-195">검색 결과를 미리 보고 관련 데이터가 있는지 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-195">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="60175-196">쿼리를 변경하고 검색을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-196">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="60175-197">**[검색 결과를 내보내고 다운로드합니다.](export-content-in-core-ediscovery.md)**</span><span class="sxs-lookup"><span data-stu-id="60175-197">**[Export and download search results](export-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="60175-198">조사와 관련된 데이터를 검색하고 찾은 후 조사 팀 외부의 Office 365 검토를 위해 외부에서 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-198">After you search for and find data that's relevant to your investigation, you can export it out of Office 365 for review by people outside of the investigation team.</span></span> <span data-ttu-id="60175-199">데이터를 내보내는 과정은 2단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="60175-199">Exporting data is a two-step process.</span></span> <span data-ttu-id="60175-200">첫 번째 단계는 검색 결과를 검색 결과로 내보내는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="60175-200">The first step is to export the results of a search in the case out of Office 365.</span></span> <span data-ttu-id="60175-201">이 작업을 수행하기 위해 검색 결과를 Microsoft에서 제공하는 검색 위치로 Azure Storage 합니다.</span><span class="sxs-lookup"><span data-stu-id="60175-201">This is accomplished by copying the results of a search to a Microsoft-provided Azure Storage location.</span></span> <span data-ttu-id="60175-202">다음 단계는 eDiscovery 내보내기 도구를 사용하여 로컬 컴퓨터에 콘텐츠를 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60175-202">The next step is to use the eDiscovery Export tool to download the content to a local computer.</span></span> <span data-ttu-id="60175-203">내보내는 데이터 파일 외에 내보내기 패키지의 포함에는 내보내기 보고서, 요약 보고서 및 오류 보고서도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60175-203">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>
