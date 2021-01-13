---
title: Microsoft 365에서 Advanced eDiscovery 설정
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
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 사례 만들기 및 관리를 시작할 수 있도록 Advanced eDiscovery를 설정하는 방법을 설명합니다. 또한 필수 Microsoft 구독 및 라이선스에 대해 설명하고 있습니다. 몇 가지 빠른 단계를 완료하면 Advanced eDiscovery 도구를 사용할 수 있습니다.
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841179"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="ad364-105">Microsoft 365 Advanced eDiscovery 설정</span><span class="sxs-lookup"><span data-stu-id="ad364-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="ad364-106">Microsoft 365의 Advanced eDiscovery는 조직의 내부 및 외부 조사에 응답하는 데이터를 보존, 수집, 검토, 분석 및 내보내기 위한 종단 간 워크플로를 제공합니다. [](overview-ediscovery-20.md#advanced-ediscovery-workflow)</span><span class="sxs-lookup"><span data-stu-id="ad364-106">Advanced eDiscovery in Microsoft 365 provides an [end-to-end workflow](overview-ediscovery-20.md#advanced-ediscovery-workflow) to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="ad364-107">Advanced eDiscovery를 배포할 필요는 없지만 조직에서 Advanced eDiscovery 사례를 만들고 사용하여 조사를 관리하기 전에 IT 관리자 및 eDiscovery 관리자가 완료해야 하는 몇 가지 선행 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="ad364-108">이 문서에서는 Advanced eDiscovery를 설정하는 데 필요한 단계에 대해 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="ad364-109">여기에는 Advanced eDiscovery에 액세스하고 사례에 보호자를 추가하는 데 필요한 적절한 라이선스를 보장하고 사례에 액세스하고 관리할 수 있도록 법적 및 조사 팀에 권한을 할당하는 작업도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="ad364-110">1단계: 적절한 라이선스 확인 및 할당</span><span class="sxs-lookup"><span data-stu-id="ad364-110">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="ad364-111">Advanced eDiscovery 라이선스를 사용하려면 적절한 조직 구독 및 사용자당 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-111">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="ad364-112">**조직 구독:** Microsoft 365 규정 준수 센터 또는 보안 & 준수 센터에서 Advanced eDiscovery에 액세스하려면 조직에 다음 중 한 가지가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-112">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="ad364-113">Microsoft 365 E5 또는 Office 365 E5 구독</span><span class="sxs-lookup"><span data-stu-id="ad364-113">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="ad364-114">E5 Compliance 추가 기능이 포함된 Microsoft 365 E3 구독</span><span class="sxs-lookup"><span data-stu-id="ad364-114">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="ad364-115">E5 eDiscovery 및 감사 추가 기능을 통해 Microsoft 365 E3 구독</span><span class="sxs-lookup"><span data-stu-id="ad364-115">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="ad364-116">기존 Microsoft 365 E5 요금제가 없는 경우 Advanced eDiscovery를 사용하려는 경우 기존 구독에 Microsoft [](https://www.microsoft.com/microsoft-365/enterprise) [365를](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 추가하거나 Microsoft 365 E5 평가판을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-116">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="ad364-117">**사용자당 라이선스:** Advance eDiscovery 사례에서 사용자를 취득자로 추가하려면 조직 구독에 따라 사용자에게 다음 라이선스 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-117">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="ad364-118">Microsoft 365: 사용자에게 Microsoft 365 E5 라이선스, E5 준수 추가 기능 라이선스 또는 E5 eDiscovery 및 감사 추가 기능 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-118">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="ad364-119">Office 365: 사용자에게 Office 365 E5 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-119">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="ad364-120">라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="ad364-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="ad364-121">고급 eDiscovery 사례에 취득자로 추가하려면 E5 라이선스(또는 적절한 추가 기능 라이선스)만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-121">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="ad364-122">Advanced eDiscovery를 사용하여 사례를 관리하고 사례 데이터를 검토하는 IT 관리자, eDiscovery 관리자, 변호사, paralegals 또는 조사자는 E5 또는 추가 기능 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-122">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="ad364-123">2단계: eDiscovery 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="ad364-123">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="ad364-124">Advanced eDiscovery에 액세스하거나 Advanced eDiscovery 사례의 구성원으로 추가하려면 사용자에게 적절한 사용 권한이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-124">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="ad364-125">특히 사용자는 보안 및 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원으로 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-125">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="ad364-126">이 역할 그룹의 구성원은 Advanced eDiscovery 사례를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-126">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="ad364-127">또한 구성원을 추가 및 제거하고, 보유자 및 콘텐츠 위치를 보류하고, 법적 보유 알림을 관리하고, 사례에 연결된 검색을 만들고 편집하고, 검토 집합에 검색 결과를 추가하고, 검토 집합의 데이터를 분석하고, Advanced eDiscovery 사례에서 데이터를 내보내고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-127">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="ad364-128">다음 단계를 완료하여 eDiscovery 관리자 역할 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-128">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="ad364-129">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span><span class="sxs-lookup"><span data-stu-id="ad364-129">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="ad364-130">사용 권한 **페이지에서** **eDiscovery 관리자 역할 그룹을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-130">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="ad364-131">eDiscovery 관리자 플라이아웃 페이지에서  **eDiscovery** 관리자 섹션 옆에 있는 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-131">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="ad364-132">역할 그룹 편집 마법사의 **eDiscovery 관리자** 선택 페이지에서 **eDiscovery 관리자 선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ad364-132">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="ad364-133">**추가를** 클릭한 다음 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-133">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="ad364-134">**추가를** 클릭하여 선택한 사용자를 추가한 다음 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ad364-134">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="ad364-135">**저장을** 클릭하여 역할 그룹에 사용자를 추가한 다음 **닫기를** 클릭하여 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-135">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="ad364-136">eDiscovery 관리자 역할 그룹에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ad364-136">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="ad364-137">eDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-137">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="ad364-138">이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-138">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="ad364-139">**eDiscovery 관리자:** 만들거나 구성원으로 있는 Advanced eDiscovery 사례를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-139">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="ad364-140">다른 eDiscovery 관리자가 사례를 만들고 두 번째 eDiscovery 관리자를 해당 사례의 구성원으로 추가하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 Advanced eDiscovery 페이지에서 사례를 보거나 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-140">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="ad364-141">일반적으로 조직의 대부분의 사람은 eDiscovery 관리자 하위 조직에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-141">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="ad364-142">**eDiscovery 관리자:** eDiscovery 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-142">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="ad364-143">또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-143">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="ad364-144">Advanced eDiscovery 페이지에 나열된 모든 사례를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-144">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="ad364-145">자신을 사례의 구성원으로 추가한 후 조직에서 모든 사례를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-145">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="ad364-146">조직의 모든 사례에 대한 사례 데이터에 액세스하고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-146">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="ad364-147">액세스 범위가 넓기 때문에 조직에는 eDiscovery Administrators 하위 그룹 구성원인 관리자만 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-147">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="ad364-148">eDiscovery 사용 권한 및 eDiscovery 관리자 역할 그룹에 할당된 각 역할에 대한 설명에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md)권한 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad364-148">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="ad364-149">3단계: Advanced eDiscovery에 대한 전역 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ad364-149">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="ad364-150">조직의 사용자가 사례를 만들고 사용하기 전에 완료하는 마지막 단계는 조직의 모든 사례에 적용되는 전역 설정을 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-150">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="ad364-151">현재 전역 설정은 *변호사-클라이언트* 권한 검색뿐입니다(향후 더 많은 전역 설정을 사용할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="ad364-151">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="ad364-152">이 설정을 사용하면 검토 집합의 데이터를 분석할 때 변호사-클라이언트 권한 모델을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-152">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="ad364-153">이 모델에서는 기계 학습을 사용하여 문서에 본질적으로 적합한 콘텐츠가 포함되어 있는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-153">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="ad364-154">또한 문서의 참가자를 변호인 목록(모델을 설정할 때 제출)과 비교하여 문서에 적어도 한 명 이상의 변호사 참가자가 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-154">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="ad364-155">변호인 권한 검색 모델을 설정하고 사용하는 데 대한 자세한 내용은 [Advanced eDiscovery에서 변호사-클라이언트](attorney-privilege-detection.md)권한 검색 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad364-155">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ad364-156">이 단계는 언제든지 수행할 수 있는 선택적 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-156">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="ad364-157">변호인 권한 검색 모델을 구현하지 않는 경우 Advanced eDiscovery 사례를 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad364-157">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ad364-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ad364-158">Next steps</span></span>

<span data-ttu-id="ad364-159">Advanced eDiscovery를 설정한 후 사례를 만들 [준비가 된 것입니다.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="ad364-159">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>
