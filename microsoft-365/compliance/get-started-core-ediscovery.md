---
title: Microsoft 365에서 핵심 eDiscovery 사례 시작
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Microsoft 365에서 코어 eDiscovery 사용을 시작 하는 방법에 대해 설명 합니다. EDiscovery 권한을 할당 하 고 사례를 만든 후에는 구성원을 추가 하 고, eDiscovery 보류를 만든 다음, 조사와 관련 된 데이터를 검색 하 고 내보낼 수 있습니다.
ms.openlocfilehash: 94c85987be4cbc5da7a378abb7ea74294f6fe740
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357916"
---
# <a name="get-started-with-core-ediscovery"></a><span data-ttu-id="e8232-104">핵심 eDiscovery 시작</span><span class="sxs-lookup"><span data-stu-id="e8232-104">Get started with Core eDiscovery</span></span>

<span data-ttu-id="e8232-105">Microsoft 365의 핵심 eDiscovery는 조직이 Microsoft 365 및 Office 365에서 콘텐츠를 검색 하 고 내보내는 데 사용할 수 있는 기본 eDiscovery 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-105">Core eDiscovery in Microsoft 365 provides a basic eDiscovery tool that organizations can use to search and export content in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="e8232-106">또한 코어 eDiscovery를 사용 하 여 Exchange 사서함, SharePoint 사이트, OneDrive 계정, Microsoft 팀 등의 콘텐츠 위치에 eDiscovery 보류를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-106">You can also use Core eDiscovery to place an eDiscovery hold on content locations, such as Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft Teams.</span></span> <span data-ttu-id="e8232-107">핵심 eDiscovery를 배포 하는 데 아무 것도 필요 하지 않지만 조직에서 핵심 eDiscovery를 사용 하 여 콘텐츠를 검색, 내보내기 및 보존 하기 전에 IT 관리자 및 eDiscovery 관리자가 완료 해야 하는 몇 가지 필수 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-107">Nothing is needed to deploy Core eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start using Core eDiscovery to search, export, and preserve content.</span></span>

<span data-ttu-id="e8232-108">이 문서에서는 핵심 eDiscovery를 설정 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-108">This article discusses the steps necessary to set up Core eDiscovery.</span></span> <span data-ttu-id="e8232-109">여기에는 핵심 eDiscovery에 액세스 하 고 콘텐츠 위치에 eDiscovery 보류를 배치 하는 데 필요한 적절 한 라이선스를 보장 하는 것과 IT, 법률 및 조사 팀이 서비스 케이스에 액세스 하 고 관리할 수 있도록 권한을 할당 하는 것도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-109">This includes ensuring the proper licensing required to access Core eDiscovery and place an eDiscovery hold on content locations, as well as assigning permissions to your IT, legal, and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="e8232-110">이 문서에서는 콘텐츠를 검색 하 고 내보내는 사례를 사용 하는 방법에 대 한 간략 한 개요도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-110">This article also provides a high-level overview of using cases to search for and export content.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="e8232-111">1 단계: 적절 한 라이선스 확인 및 할당</span><span class="sxs-lookup"><span data-stu-id="e8232-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="e8232-112">핵심 eDiscovery에 대 한 라이선스에는 적절 한 조직 구독 및 사용자 단위 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-112">Licensing for Core eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="e8232-113">**조직 구독:** Microsoft 365 준수 센터 또는 Office 365 보안 & 준수 센터의 핵심 eDiscovery에 액세스 하 고 보류 및 내보내기 기능을 사용 하려면 조직에 Microsoft 365 E3 또는 Office 365 E3 구독 이상이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-113">**Organization subscription:** To access Core eDiscovery in the Microsoft 365 compliance center or the Office 365 Security & Compliance Center and use the hold and export features, your organization must have a Microsoft 365 E3 or Office 365 E3 subscription or higher.</span></span>

- <span data-ttu-id="e8232-114">**사용자별 라이선스:** 사서함 및 사이트에 eDiscovery 보류를 설정 하려면 조직 구독에 따라 사용자에 게 다음 라이선스 중 하나를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-114">**Per-user licensing:** To place an eDiscovery hold on mailboxes and sites, a user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="e8232-115">Microsoft 365 E3 또는 Office 365 E3 라이선스 이상</span><span class="sxs-lookup"><span data-stu-id="e8232-115">A Microsoft 365 E3 or Office 365 E3 license or higher</span></span>

   <span data-ttu-id="e8232-116">또는</span><span class="sxs-lookup"><span data-stu-id="e8232-116">OR</span></span>

  - <span data-ttu-id="e8232-117">Exchange Online 계획 2 또는 Exchange Online 보관용 추가 기능 라이선스가 있는 Office 365 E1 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8232-117">Office 365 E1 license with an Exchange Online Plan 2 or Exchange Online Archiving add-on license</span></span>

  <span data-ttu-id="e8232-118">그리고</span><span class="sxs-lookup"><span data-stu-id="e8232-118">AND</span></span>

  - <span data-ttu-id="e8232-119">Office 365 E1 license for SharePoint Online 계획 2 또는 비즈니스용 OneDrive 요금제 2 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8232-119">Office 365 E1 license with an SharePoint Online Plan 2 or OneDrive for Business Plan 2 add-on license</span></span>
  
  <span data-ttu-id="e8232-120">라이선스를 할당 하는 방법에 대 한 자세한 내용은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8232-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="e8232-121">라이선스에 대 한 자세한 내용:</span><span class="sxs-lookup"><span data-stu-id="e8232-121">For information about licensing:</span></span>

- <span data-ttu-id="e8232-122">[Microsoft 365 준수 라이선스 비교](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)의 "응답 & 검색" 솔루션을 다운로드 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-122">Download and see the "Discover & Respond" solution in the [Microsoft 365 Compliance Licensing Comparison](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).</span></span>

- <span data-ttu-id="e8232-123">[보안 & 준수 센터 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8232-123">See the [Security & Compliance Center service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="e8232-124">2 단계: eDiscovery 권한 할당</span><span class="sxs-lookup"><span data-stu-id="e8232-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="e8232-125">핵심 eDiscovery에 액세스 하거나 코어 eDiscovery 사례의 구성원으로 추가 하려면 사용자에 게 적절 한 사용 권한이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-125">To access Core eDiscovery or be added as a member of a Core eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="e8232-126">특히 Office 365 보안 & 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원으로 사용자를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="e8232-127">이 역할 그룹의 구성원은 핵심 eDiscovery 사례를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-127">Members of this role group can create and manage Core eDiscovery cases.</span></span> <span data-ttu-id="e8232-128">구성원을 추가 및 제거 하 고, eDiscovery 보류를 사용자에 게 배치 하 고, 검색을 만들고 편집 하 고, 핵심 eDiscovery 사례에서 콘텐츠를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-128">They can add and remove members, place an eDiscovery hold on users, create and edit searches, and export content from a Core eDiscovery case.</span></span>

<span data-ttu-id="e8232-129">다음 단계를 완료 하 여 eDiscovery 관리자 역할 그룹에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="e8232-130">로 이동 하 [https://protection.office.com/permissions](https://protection.office.com/permissions) 여 Microsoft 365 또는 Office 365 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 or Office 365 organization.</span></span>

2. <span data-ttu-id="e8232-131">**사용 권한** 페이지에서 **eDiscovery 관리자** 역할 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="e8232-132">EDiscovery 관리자 플라이 아웃 페이지에서 **Ediscovery 관리자** 섹션 옆에 있는 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="e8232-133">역할 그룹 편집 마법사의 **EDiscovery 관리자 선택** 페이지에서 **검색 관리자 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="e8232-134">**추가** 를 클릭 한 다음 역할 그룹에 추가 하려는 모든 사용자의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="e8232-135">**추가** 를 클릭 하 여 선택한 사용자를 추가한 다음 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="e8232-136">**저장** 을 클릭 하 여 역할 그룹에 사용자를 추가 하 고 **닫기를** 클릭 하 여 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="e8232-137">EDiscovery 관리자 역할 그룹에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="e8232-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="e8232-138">EDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="e8232-139">이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="e8232-140">**EDiscovery 관리자:** 사용자가 만들거나 구성원으로 속해 있는 핵심 eDiscovery 사례를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-140">**eDiscovery Manager:** Can view and manage the Core eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="e8232-141">다른 eDiscovery 관리자가 사례를 만들지만 두 번째 eDiscovery 관리자를 해당 사례 구성원으로 추가 하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 핵심 eDiscovery 페이지에서 사례를 보거나 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Core eDiscovery page in the compliance center.</span></span> <span data-ttu-id="e8232-142">일반적으로 조직의 대부분의 사용자가 eDiscovery 관리자 하위 그룹에 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="e8232-143">**EDiscovery 관리자:** EDiscovery 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="e8232-144">또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="e8232-145">핵심 eDiscovery 페이지에 나열 된 모든 사례를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-145">View all cases that are listed on the Core eDiscovery page.</span></span>
  
  - <span data-ttu-id="e8232-146">조직의 대/소문자를 구성원으로 추가한 후 조직에서 모든 사례를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="e8232-147">조직의 모든 경우에 대 한 사례 데이터 액세스 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="e8232-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="e8232-148">액세스 범위가 광범위 하기 때문에 조직은 eDiscovery Administrators 그룹의 구성원 인 관리자를 몇 명만 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="e8232-149">Ediscovery 권한 및 eDiscovery 관리자 역할 그룹에 할당 된 각 역할에 대 한 설명에 대 한 자세한 내용은 [ediscovery 권한 할당](assign-ediscovery-permissions.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8232-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-create-a-core-ediscovery-case"></a><span data-ttu-id="e8232-150">3 단계: 핵심 eDiscovery 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="e8232-150">Step 3: Create a Core eDiscovery case</span></span>

<span data-ttu-id="e8232-151">다음 단계에서는 사례를 만들고 핵심 eDiscovery 사용을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-151">The next step is to create a case and start using Core eDiscovery.</span></span> <span data-ttu-id="e8232-152">사례를 만들고 구성원을 추가 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-152">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="e8232-153">서비스 케이스를 만드는 사용자는 자동으로 구성원으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-153">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="e8232-154">[https://compliance.microsoft.com](https://compliance.microsoft.com)적절 한 eDiscovery 권한이 할당 된 사용자 계정의 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for a user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="e8232-155">또한 조직 관리 역할 그룹의 구성원은 핵심 eDiscovery 사례를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-155">Members of the Organization Management role group can also create Core eDiscovery cases.</span></span>

2. <span data-ttu-id="e8232-156">Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 코어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-156">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="e8232-157">**핵심 eDiscovery** 페이지에서 **사례 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-157">On the **Core eDiscovery** page, click **Create a case**.</span></span>

4. <span data-ttu-id="e8232-158">**새 사례** 플라이 아웃 페이지에서 사례 이름을 (필수)로 지정 하 고 선택적 사례 번호 및 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-158">On the **New case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="e8232-159">사례 이름은 조직 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-159">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="e8232-160">**저장** 을 클릭 하 여 사례를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-160">Click **Save** to create the case.</span></span>

   <span data-ttu-id="e8232-161">새 사례가 만들어져 코어 eDiscovery 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-161">The new case is created and displayed on the Core eDiscovery page.</span></span> <span data-ttu-id="e8232-162">새 대/소문자를 표시 하려면 **새로 고침** 을 클릭 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-162">You may have to click **Refresh** to display the new case.</span></span> 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a><span data-ttu-id="e8232-163">4 단계 (선택 사항): 핵심 eDiscovery 사례에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="e8232-163">Step 4 (optional): Add members to a Core eDiscovery case</span></span>

<span data-ttu-id="e8232-164">3 단계에서 사례를 만드는 경우 사례를 사용할 사람만 있으면이 단계를 수행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-164">If you create a case in Step 3 and you're the only person who will use the case, then you don't have to perform this step.</span></span> <span data-ttu-id="e8232-165">사례 사용을 시작 하 여 eDiscovery 보류를 만들거나, 콘텐츠를 검색 하거나, 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-165">You can start using the case to create eDiscovery holds, search for content, or export search results.</span></span> <span data-ttu-id="e8232-166">다른 사용자 (또는 역할 그룹)에 게 사례에 대 한 액세스 권한을 부여 하려는 경우이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-166">Perform this step if you want to give other users (or roles group) access to the case.</span></span>

1. <span data-ttu-id="e8232-167">Microsoft 365 준수 센터의 **핵심 eDiscovery** 페이지에서 구성원을 추가 하려는 사례 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-167">On the **Core eDiscovery** page in the Microsoft 365 compliance center, click the name of the case that you want to add members to.</span></span>

2. <span data-ttu-id="e8232-168">**이 사례** 플라이 아웃 관리 페이지의 **구성원 관리**에서 **추가** 를 클릭 하 여 사례에 구성원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-168">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span> 

    <span data-ttu-id="e8232-169">역할 그룹을 사례 구성원으로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-169">You can also choose to add role group as members of a case.</span></span> <span data-ttu-id="e8232-170">**역할 그룹 관리**에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-170">Under **Manage role groups**, click **Add**.</span></span> <span data-ttu-id="e8232-171">사용자가 구성원으로 속해 있는 역할 그룹은 사례에만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-171">You can only assign the role groups that you are a member of to a case.</span></span> <span data-ttu-id="e8232-172">이는 역할 그룹이 eDiscovery 사례에 구성원을 할당할 수 있는 사람을 제어 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-172">That's because role groups control who can assign members to an eDiscovery case.</span></span>

3. <span data-ttu-id="e8232-173">사례 구성원으로 추가할 수 있는 사용자 또는 역할 그룹의 목록에서 추가 하려는 사람 (또는 역할 그룹)의 이름 옆에 있는 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-173">In the list of people or role groups that can be added as members of the case, click the check box next to the names of the people (or role groups) that you want to add.</span></span> <span data-ttu-id="e8232-174">구성원으로 추가할 수 있는 사용자 목록이 많은 경우에는 **검색** 상자를 사용 하 여 목록에서 특정 사용자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-174">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span>
  
4. <span data-ttu-id="e8232-175">사례 구성원으로 추가할 사용자 또는 역할 그룹을 선택한 후 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-175">After you select the people or role groups to add as members of the case, click **Add**.</span></span>

5. <span data-ttu-id="e8232-176">**저장** 을 클릭 하 여 사례 구성원의 새 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-176">Click **Save** to save the new list of case members.</span></span>

## <a name="explore-the-core-ediscovery-workflow"></a><span data-ttu-id="e8232-177">핵심 eDiscovery 워크플로 살펴보기</span><span class="sxs-lookup"><span data-stu-id="e8232-177">Explore the Core eDiscovery workflow</span></span>

<span data-ttu-id="e8232-178">핵심 eDiscovery 사용을 시작 하려면 관심 있는 사용자를 위해 eDiscovery 보류를 만들고 조사와 관련 된 콘텐츠를 검색 한 다음 추가 검토를 위해 해당 데이터를 내보내는 간단한 워크플로를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8232-178">To get you started using core eDiscovery, here's a simple workflow of creating eDiscovery holds for people of interest, searching for content that relevant to your investigation, and then exporting that data for further review.</span></span> <span data-ttu-id="e8232-179">이러한 각 단계에서는 탐색할 수 있는 몇 가지 확장 된 필수 eDiscovery 기능도 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-179">In each of these steps, we'll also highlight some extended Core eDiscovery functionality that you can explore.</span></span>

![핵심 eDiscovery 워크플로](../media/CoreEdiscoveryWorkflow.png)

1. <span data-ttu-id="e8232-181">**[EDiscovery 보류를 만듭니다](create-ediscovery-holds.md)**.</span><span class="sxs-lookup"><span data-stu-id="e8232-181">**[Create an eDiscovery hold](create-ediscovery-holds.md)**.</span></span> <span data-ttu-id="e8232-182">사례를 만든 후 첫 번째 단계는 조사에 관심이 있는 사용자의 콘텐츠 위치에 보류 ( *eDiscovery 보류*라고도 함)를 배치 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-182">The first step after creating a case is placing a hold (also called an *eDiscovery hold*) on the content locations of the people of interest in your investigation.</span></span> <span data-ttu-id="e8232-183">콘텐츠 위치에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정, Microsoft 팀 및 Office 365 그룹과 연결 된 사서함 및 사이트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-183">Content locations include Exchange mailboxes, SharePoint sites, OneDrive accounts, as well as the mailboxes and sites associated with Microsoft Teams and Office 365 Groups.</span></span> <span data-ttu-id="e8232-184">이 단계는 선택 사항 이지만 eDiscovery 보존을 만들려면 조사 중에 사례와 관련이 있을 수 있는 콘텐츠를 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-184">While this step is optional, creating an eDiscovery hold preserves content that may be relevant to the case during the investigation.</span></span> <span data-ttu-id="e8232-185">EDiscovery 보류를 만들 때 특정 콘텐츠 위치의 모든 콘텐츠를 유지 하거나 쿼리 기반 보존을 만들어 보류 쿼리와 일치 하는 콘텐츠만 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-185">When you create an eDiscovery hold you can preserve all content in specific content locations or you can create a query-based hold to preserve only the content that matches a hold query.</span></span> <span data-ttu-id="e8232-186">콘텐츠를 보존 하는 것 외에도 eDiscovery 보류를 만드는 또 다른 이유는 다음 단계에서 검색을 만들고 실행할 때 보류 중인 콘텐츠 위치를 빠르게 검색 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-186">In addition to preserving content, another good reason to create eDiscovery holds is to quickly search the content locations on hold (instead of having to select each location to search) when you create and run searches in the next step.</span></span> <span data-ttu-id="e8232-187">조사를 완료 한 후에는 직접 만든 모든 보류를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-187">After you complete your investigation, you can release any hold that you created.</span></span>

2. <span data-ttu-id="e8232-188">**[콘텐츠를 검색](search-for-content-in-core-ediscovery.md)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-188">**[Search for content](search-for-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="e8232-189">EDiscovery 보류를 만든 후 기본 제공 검색 도구를 사용 하 여 보류 중인 콘텐츠 위치를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-189">After you create eDiscovery holds, use the built-in search tool to search the content locations on hold.</span></span> <span data-ttu-id="e8232-190">사례와 관련이 있을 수 있는 데이터에 대 한 다른 콘텐츠 위치를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-190">You can also search other content locations for data that may be relevant to the case.</span></span> <span data-ttu-id="e8232-191">사례와 연결 된 다른 검색을 만들고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-191">You can create and run different searches that are associated with the case.</span></span> <span data-ttu-id="e8232-192">키워드, 속성 및 조건을 사용 하 여 사례와 관련성이 가장 높은 데이터로 검색 결과를 반환 하는 [검색 쿼리를 작성](keyword-queries-and-search-conditions.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-192">You use keywords, properties, and conditions to [build search queries](keyword-queries-and-search-conditions.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="e8232-193">또한 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-193">You can also:</span></span>

   - <span data-ttu-id="e8232-194">검색 쿼리를 구체화 하 여 결과 범위를 좁히는 데 도움이 될 수 있는 검색 통계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-194">View search statistics that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="e8232-195">검색 결과를 미리 보고 관련 데이터를 찾을 수 있는지 여부를 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-195">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="e8232-196">쿼리를 수정 하 고 검색을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-196">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="e8232-197">**[검색 결과를 내보내고 다운로드](export-content-in-core-ediscovery.md)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-197">**[Export and download search results](export-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="e8232-198">조사와 관련 된 데이터를 검색 하 고 찾은 후 조사 팀 외부의 사용자가 검토를 위해 Office 365에서이를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-198">After you search for and find data that's relevant to your investigation, you can export it out of Office 365 for review by people outside of the investigation team.</span></span> <span data-ttu-id="e8232-199">데이터 내보내기는 두 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-199">Exporting data is a two-step process.</span></span> <span data-ttu-id="e8232-200">첫 번째 단계는 검색 결과를 Office 365의 소문자로 내보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-200">The first step is to export the results of a search in the case out of Office 365.</span></span> <span data-ttu-id="e8232-201">검색 결과를 Microsoft에서 제공한 Azure 저장소 위치로 복사 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-201">This is accomplished by copying the results of a search to a Microsoft-provided Azure Storage location.</span></span> <span data-ttu-id="e8232-202">다음 단계에서는 eDiscovery 내보내기 도구를 사용 하 여 콘텐츠를 로컬 컴퓨터에 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-202">The next step is to use the eDiscovery Export tool to download the content to a local computer.</span></span> <span data-ttu-id="e8232-203">내보낸 데이터 파일 외에도 내보내기 패키지의 포함에는 내보내기 보고서, 요약 보고서 및 오류 보고서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8232-203">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>
