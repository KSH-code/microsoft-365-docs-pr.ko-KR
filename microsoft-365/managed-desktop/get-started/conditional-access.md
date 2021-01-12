---
title: 등록 후 설정 수정
description: 특정 Microsoft 계정을 제외하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88a832f6c4e17756bfb25ef5cb7c4c5ecedaf2c0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794391"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="7e209-104">등록 후 설정 수정</span><span class="sxs-lookup"><span data-stu-id="7e209-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="7e209-105">Microsoft Managed Desktop에서 등록을 완료한 후 일부 관리 설정을 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-105">After you’ve completed enrollment in Microsoft Managed Desktop, some management settings might need to be adjusted.</span></span> <span data-ttu-id="7e209-106">필요한 경우 확인하고 조정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-106">To check and adjust if needed, follow these steps:</span></span>

1. <span data-ttu-id="7e209-107">다음 섹션에서 설명하는 Microsoft Intune 및 Azure Active Directory 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-107">Review the Microsoft Intune and Azure Active Directory settings described in the next section.</span></span>
2. <span data-ttu-id="7e209-108">해당 환경에 항목이 적용되는 경우 설명된 항목을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-108">If any of the items apply to your environment, make the adjustments described.</span></span>
3. <span data-ttu-id="7e209-109">모든 설정이 올바른지 다시 확인하려면 준비 평가 도구를 [](https://aka.ms/mmdart) 다시 실행하여 Microsoft Managed Desktop과 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-109">If you want to double-check that all settings are correct, you can rerun the [readiness assessment tool](https://aka.ms/mmdart) to make sure nothing conflicts with Microsoft Managed Desktop.</span></span>

> [!NOTE]
> <span data-ttu-id="7e209-110">다음 달에 작업을 계속할 때 Microsoft Intune, Azure Active Directory 또는 Microsoft 365에서 Microsoft Managed Desktop에 영향을 주는 정책에 등록한 후 변경하는 경우 Microsoft Managed Desktop이 제대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-110">As your operations continue in following months, if you make changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365 that affect Microsoft Managed Desktop, it's possible that Microsoft Managed Desktop could stop operating properly.</span></span> <span data-ttu-id="7e209-111">서비스 문제를 방지하려면 준비 평가 도구에서 [](../get-ready/readiness-assessment-fix.md) 찾은 문제 해결에 설명된 특정 설정을 확인한 후 여기에 나열된 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-111">To avoid problems with the service, check the specific settings described in [Fix issues found by the readiness assessment tool](../get-ready/readiness-assessment-fix.md) before you change the policies listed there.</span></span> <span data-ttu-id="7e209-112">준비 평가 도구를 다시 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-112">You can also rerun the readiness assessment tool at any time.</span></span>


## <a name="microsoft-intune-settings"></a><span data-ttu-id="7e209-113">Microsoft Intune 설정</span><span class="sxs-lookup"><span data-stu-id="7e209-113">Microsoft Intune settings</span></span>

- <span data-ttu-id="7e209-114">Autopilot 배포 프로필: Autopilot 정책을 사용하는 경우 각 정책을 업데이트하여 최신 작업 공간 장치 **-All** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-114">Autopilot deployment profile: if you use any Autopilot policies, update each one to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="7e209-115">업데이트하려면 배정  아래에 있는 제외된 그룹 섹션에서 Microsoft Managed Desktop 등록 중에 만들어진 최신 작업 공간 장치 **-모든** Azure AD 그룹을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="7e209-115">To update them, in the **Excluded groups** section under **Assignments**, select the **Modern Workplace Devices -All** Azure AD group that was created during Microsoft Managed Desktop enrollment.</span></span> <span data-ttu-id="7e209-116">Microsoft Managed Desktop은 이름(최신 Workplace Autopilot 프로필)에 "최신 작업 공간"이 있는 Autopilot 프로필도 **만들게 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7e209-116">Microsoft Managed Desktop will also have created an Autopilot profile, which will have "Modern Workplace" in the name (the **Modern Workplace Autopilot Profile**).</span></span> <span data-ttu-id="7e209-117">자체 Autopilot 프로필을 업데이트할 때 Microsoft  Managed Desktop에서 만든 최신 Workplace **Autopilot 프로필에서** 최신 작업 공간 장치 **-모든** Azure AD 그룹을 제외하지 않는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7e209-117">When you update your own Autopilot profiles, make sure that you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from the **Modern Workplace Autopilot Profile** that was created by Microsoft Managed Desktop.</span></span>

- <span data-ttu-id="7e209-118">조건부 액세스 정책: 만든 조건부 액세스 정책의 경우 최신 **Workplace Service Accounts** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-118">Conditional Access policies: for conditional access policies you've created, exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="7e209-119">단계는 조건부 [액세스: 사용자 및 그룹을 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)</span><span class="sxs-lookup"><span data-stu-id="7e209-119">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span> <span data-ttu-id="7e209-120">Microsoft Managed Desktop은 일부 조건부 액세스 정책도 만들며, 이러한 정책의 모든 정책은 이름에 "최신 작업 공간"(예: **Modern Workplace Secure Workstation)이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7e209-120">Microsoft Managed Desktop will also have created some conditional access policies, all of which will have "Modern Workplace" in the name (for example, **Modern Workplace Secure Workstation**).</span></span> <span data-ttu-id="7e209-121">조건부 액세스 정책을 직접 업데이트할 때  Microsoft Managed Desktop에서 만든 정책에서 최신 작업 공간 장치 **-모든** Azure AD 그룹을 제외하지 않는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7e209-121">When you update your own conditional access policies, make sure you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from any policies created by Microsoft Managed Desktop.</span></span>

- <span data-ttu-id="7e209-122">다단계 인증: 다단계 인증이 필요한 조건부 액세스 정책 중 최신 **Workplace Service Accounts** Azure AD 그룹을 제외하는지 확인</span><span class="sxs-lookup"><span data-stu-id="7e209-122">Multifactor authentication: make sure any of your conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="7e209-123">자세한 내용은 [조건부 액세스](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 정책 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요를 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="7e209-123">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

- <span data-ttu-id="7e209-124">Windows 10 업데이트 링: 만든 Windows 10 업데이트 링 정책의 경우 각 정책에서 최신 **Workplace Devices -All** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-124">Windows 10 update ring: for any Windows 10 update ring policies you've created, exclude the **Modern Workplace Devices -All** Azure AD group from each policy.</span></span> <span data-ttu-id="7e209-125">단계는 업데이트 [링 만들기 및 할당을 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)</span><span class="sxs-lookup"><span data-stu-id="7e209-125">For steps, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings).</span></span> <span data-ttu-id="7e209-126">Microsoft Managed Desktop은 일부 업데이트 링 정책도 만들며, 모든 정책은 이름(예: 최신 작업 공간 업데이트 정책 **[광범위],** 최신 작업 공간 업데이트 정책 **[Fast],** 최신 작업 공간 업데이트 정책 **[첫 번째]** 및 최신 작업 공간 업데이트 정책 **[테스트]))에**"최신 작업 공간"이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-126">Microsoft Managed Desktop will also have created some update ring policies, all of which will have "Modern Workplace" in the name (for example **Modern Workplace Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]**, and **Modern Workplace Update Policy [Test]**).</span></span> <span data-ttu-id="7e209-127">자체 정책을 업데이트할 때 Microsoft  Managed Desktop에서 만든 그룹에서 최신 작업 공간 장치 **-모든** Azure AD 그룹을 제외하지 않는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7e209-127">When you update your own policies, make sure that you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from those that Microsoft Managed Desktop created.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="7e209-128">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="7e209-128">Azure Active Directory settings</span></span>

<span data-ttu-id="7e209-129">셀프 서비스 암호 재설정: 모든 사용자에 대해 셀프 서비스 암호 재설정을 사용하는 경우 할당을 조정하여 Microsoft Managed Desktop 서비스 계정을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-129">Self-service password reset: if you use self-service password reset for all users, adjust the assignment to exclude Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="7e209-130">이 할당을 조정하기 위해 *Microsoft* Managed Desktop 서비스 계정을 제외한 모든 사용자에 대해 Azure AD 동적 그룹을 만든 다음 "모든 사용자" 대신 해당 그룹을 할당에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-130">To adjust this assignment, create a Azure AD dynamic group for all users *except* Microsoft Managed Desktop service accounts, and then use that group for assignment instead of "all users."</span></span>

<span data-ttu-id="7e209-131">서비스 계정을 찾고 제외할 수 있도록 사용할 수 있는 동적 쿼리의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-131">To help you find and exclude the service accounts, here is an example of a dynamic query you can use:</span></span>

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

<span data-ttu-id="7e209-132">이 쿼리에서 테넌트 @TENANT 이름으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="7e209-132">In this query, replace @TENANT with your tenant domain name.</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="7e209-133">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="7e209-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="7e209-134">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="7e209-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="7e209-135">등록 후 설정 조정(이 문서)</span><span class="sxs-lookup"><span data-stu-id="7e209-135">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="7e209-136">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="7e209-136">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="7e209-137">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="7e209-137">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="7e209-138">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="7e209-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="7e209-139">장치 설정</span><span class="sxs-lookup"><span data-stu-id="7e209-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="7e209-140">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="7e209-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="7e209-141">앱 배포</span><span class="sxs-lookup"><span data-stu-id="7e209-141">Deploy apps</span></span>](deploy-apps.md)
