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
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760106"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="af334-104">등록 후 설정 수정</span><span class="sxs-lookup"><span data-stu-id="af334-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="af334-105">Microsoft Managed Desktop에서 등록을 완료한 후 관리 및 보안을 유지 관리하기 위해 특정 Microsoft Intune 및 Azure AD(Azure Active Directory) 설정을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-105">After you've completed enrollment in Microsoft Managed Desktop, you need to adjust certain Microsoft Intune and Azure Active Directory (Azure AD) settings to allow for management and maintain security.</span></span> <span data-ttu-id="af334-106">다음 설정을 설정하여 Microsoft Managed Desktop 장치 및 사용자를 포함하는 Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-106">Set the following settings to exclude the Azure AD groups that contain Microsoft Managed Desktop devices and users.</span></span> <span data-ttu-id="af334-107">그룹을 제외하는 단계는 [조건부 액세스: 사용자 및 그룹을 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)</span><span class="sxs-lookup"><span data-stu-id="af334-107">For steps to exclude groups, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).</span></span>

> [!NOTE]
> <span data-ttu-id="af334-108">Microsoft Intune, Azure Active Directory 또는 Microsoft 365의 정책에 등록한 후 변경한 경우 Microsoft Managed Desktop이 제대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af334-108">If you make any changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, it's possible that Microsoft Managed Desktop could stop operating properly.</span></span> <span data-ttu-id="af334-109">Microsoft Managed Desktop 작업의 문제를 방지하려면 정책을 [](../get-ready/readiness-assessment-fix.md) 변경하기 전에 준비 평가 도구에서 찾은 문제 해결에 설명된 특정 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-109">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in [Fix issues found by the readiness assessment tool](../get-ready/readiness-assessment-fix.md) before you change any policies.</span></span>


## <a name="microsoft-intune-settings"></a><span data-ttu-id="af334-110">Microsoft Intune 설정</span><span class="sxs-lookup"><span data-stu-id="af334-110">Microsoft Intune settings</span></span>

- <span data-ttu-id="af334-111">Autopilot 배포 프로필: 최신 작업 공간 장치 **- 모든**  Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-111">Autopilot deployment profile: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="af334-112">단계는 Windows [Autopilot을 사용하여 Intune에서 Windows 장치 등록을 참조하세요.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)</span><span class="sxs-lookup"><span data-stu-id="af334-112">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span>
- <span data-ttu-id="af334-113">조건부 액세스 정책: 최신 작업 공간 **서비스 계정** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-113">Conditional Access policies: exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="af334-114">단계는 조건부 [액세스: 사용자 및 그룹을 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)</span><span class="sxs-lookup"><span data-stu-id="af334-114">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>
- <span data-ttu-id="af334-115">다단계 인증: 다단계 인증이 필요한 조건부 액세스 정책이 최신 **Workplace Service Accounts** Azure AD 그룹을 제외하는지 확인</span><span class="sxs-lookup"><span data-stu-id="af334-115">Multifactor authentication: make sure any conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="af334-116">자세한 내용은 [조건부 액세스](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 정책 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요를 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="af334-116">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>
- <span data-ttu-id="af334-117">보안 기준: 최신 작업 공간 장치 **- 모든**  Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-117">Security baseline: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="af334-118">단계는 보안 기준을 사용하여 [Intune에서 Windows 10 디바이스를 구성합니다.](https://docs.microsoft.com/mem/intune/protect/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="af334-118">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>
- <span data-ttu-id="af334-119">Windows 10 업데이트 링: 최신 작업 공간 **장치 -모든**  Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-119">Windows 10 update ring: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="af334-120">단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="af334-120">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="af334-121">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="af334-121">Azure Active Directory settings</span></span>

<span data-ttu-id="af334-122">셀프 서비스 암호 재설정: **선택한** 설정을 선택한 다음 최신 작업 공간 장치 **-모든** Azure AD 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-122">Self-service password reset: choose **Selected** setting, and then select **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="af334-123">자세한 내용은 [자습서: 사용자가 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)셀프 서비스 암호 재설정을 사용하여 계정 잠금을 해제하거나 암호를 재설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="af334-123">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="af334-124">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="af334-124">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="af334-125">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="af334-125">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="af334-126">등록 후 설정 조정(이 문서)</span><span class="sxs-lookup"><span data-stu-id="af334-126">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="af334-127">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="af334-127">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="af334-128">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="af334-128">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="af334-129">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="af334-129">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="af334-130">장치 설정</span><span class="sxs-lookup"><span data-stu-id="af334-130">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="af334-131">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="af334-131">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="af334-132">앱 배포</span><span class="sxs-lookup"><span data-stu-id="af334-132">Deploy apps</span></span>](deploy-apps.md)
