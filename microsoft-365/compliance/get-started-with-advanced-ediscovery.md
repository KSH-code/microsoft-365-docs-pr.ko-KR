---
title: 2016에서 Advanced eDiscovery 설정 Microsoft 365
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
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 사례 만들기 및 관리를 시작할 수 있도록 Advanced eDiscovery 방법을 설명합니다. 또한 필수 Microsoft 구독 및 라이선싱에 대해 설명합니다. 몇 가지 빠른 단계를 완료하면 Advanced eDiscovery 사용할 수 있습니다.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919751"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="cb644-105">설정 Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cb644-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="cb644-106">Advanced eDiscovery 조직의 Microsoft 365 조사에 응답하는 데이터를 보존, 수집, 검토, 분석 및 내보낼 수 있는 종단 간 워크플로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="cb644-107">조직에서 Advanced eDiscovery 배포할 필요는 없지만 IT 관리자 및 eDiscovery 관리자가 몇 가지 선행 작업을 완료해야 조직에서 Advanced eDiscovery 사례를 만들고 사용하여 조사를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="cb644-108">이 문서에서는 설치를 설정하는 데 필요한 다음 단계에 대해 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="cb644-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![설정 단계 Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="cb644-110">여기에는 사례에 액세스하고 Advanced eDiscovery 추가하는 데 필요한 적절한 라이선스를 보장하고 사례에 액세스하고 관리할 수 있도록 법률 및 조사 팀에 권한을 할당하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="cb644-111">1단계: 적절한 라이선스 확인 및 할당</span><span class="sxs-lookup"><span data-stu-id="cb644-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="cb644-112">라이선스를 Advanced eDiscovery 조직 구독 및 사용자당 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="cb644-113">라이선스 요구 사항 목록은 Advanced eDiscovery 및 [라이선싱을 참조하세요.](overview-ediscovery-20.md#subscriptions-and-licensing)</span><span class="sxs-lookup"><span data-stu-id="cb644-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="cb644-114">2단계: eDiscovery 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="cb644-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="cb644-115">사용자 Advanced eDiscovery 액세스하거나 Advanced eDiscovery 구성원으로 추가하려면 사용자에게 적절한 사용 권한이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="cb644-116">특히 사용자를 보안 및 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원으로 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="cb644-117">이 역할 그룹의 구성원은 이러한 사례를 만들고 관리할 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="cb644-118">구성원을 추가 및 제거하고, 보유자 및 콘텐츠 위치를 보류하고, 법적 보류 알림을 관리하고, 사례에 연결된 검색을 만들고 편집하고, 검토 집합에 검색 결과를 추가하고, 검토 집합의 데이터를 분석하고, Advanced eDiscovery 사례에서 내보내고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="cb644-119">다음 단계를 완료하여 eDiscovery 관리자 역할 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="cb644-120">으로 이동한 후 조직에서 관리자 계정의 자격 <https://protection.office.com/permissions> 증명을 사용하여 Microsoft 365 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="cb644-121">사용 **권한 페이지에서** **eDiscovery 관리자 역할 그룹을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="cb644-122">eDiscovery 관리자 플라이아웃 페이지에서  **eDiscovery** 관리자 섹션 옆에 있는 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="cb644-123">역할 그룹 편집 **마법사의 eDiscovery 관리자** 선택 페이지에서 **eDiscovery 관리자 선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cb644-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="cb644-124">**추가를** 클릭한 다음 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="cb644-125">**추가를** 클릭하여 선택한 사용자를 추가한 다음 완료 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cb644-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="cb644-126">**저장을** 클릭하여 역할 그룹에 사용자를 추가한  다음 닫기 를 클릭하여 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="cb644-127">eDiscovery 관리자 역할 그룹에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="cb644-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="cb644-128">eDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="cb644-129">이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="cb644-130">**eDiscovery** 관리자: 만들거나 구성원으로 Advanced eDiscovery 사례를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="cb644-131">다른 eDiscovery 관리자가 사례를 만들어 두 번째 eDiscovery 관리자(Manager)를 해당 사례의 구성원으로 추가하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 Advanced eDiscovery 페이지에서 사례를 보거나 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="cb644-132">일반적으로 조직의 대부분의 사람은 eDiscovery 관리자 하위 조직에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="cb644-133">**eDiscovery 관리자: eDiscovery** 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="cb644-134">또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="cb644-135">Advanced eDiscovery 페이지에 나열된 모든 케이스 보기</span><span class="sxs-lookup"><span data-stu-id="cb644-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="cb644-136">본인을 케이스의 구성원으로 추가한 후 조직의 케이스 관리</span><span class="sxs-lookup"><span data-stu-id="cb644-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="cb644-137">조직의 케이스에 대한 케이스 데이터 액세스 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="cb644-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="cb644-138">광범위한 액세스 권한으로 인해 조직에는 eDiscovery 관리자 하위 그룹의 구성원인 일부 관리자만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="cb644-139">eDiscovery 사용 권한에 대한 자세한 내용과 eDiscovery 관리자 역할 그룹에 할당된 각 역할에 대한 설명은 [eDiscovery](assign-ediscovery-permissions.md)권한 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb644-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="cb644-140">3단계: 사용자에 대한 전역 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cb644-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="cb644-141">조직의 사용자가 사례를 만들고 사용하기 전에 완료하는 마지막 단계는 조직의 모든 사례에 적용되는 전역 설정을 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="cb644-142">현재 전역 설정은 *변호사-클라이언트* 권한 검색뿐입니다(향후 더 많은 전역 설정을 사용할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="cb644-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="cb644-143">이 설정을 사용하면 검토 집합의 데이터를 분석할 때 변호사-클라이언트 권한 모델을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="cb644-144">이 모델에서는 기계 학습을 사용하여 문서에 본질적으로 적합한 콘텐츠가 포함되어 있는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="cb644-145">또한 문서의 참가자를 변호사 목록과 비교하여(모델을 설정할 때 제출한) 문서에 변호사인 참가자가 한 명 이상 있는지도 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="cb644-146">변호사-클라이언트 권한 검색 모델을 설정하고 사용하는 데 대한 자세한 내용은 [Set up attorney-client privilege detection in Advanced eDiscovery.](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="cb644-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cb644-147">이 단계는 언제든지 수행할 수 있는 선택적 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="cb644-148">변호사-클라이언트 권한 검색 모델을 구현하지 않는다고 해서 이러한 사례를 만들고 사용할 Advanced eDiscovery 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb644-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb644-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cb644-149">Next steps</span></span>

<span data-ttu-id="cb644-150">설치 Advanced eDiscovery 사례를 만들 준비가 된 [것입니다.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="cb644-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>