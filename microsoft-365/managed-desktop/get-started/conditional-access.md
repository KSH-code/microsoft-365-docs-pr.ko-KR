---
title: 등록 후 설정 조정
description: 특정 Microsoft 계정을 제외 하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527700"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="40e86-104">등록 후 설정 조정</span><span class="sxs-lookup"><span data-stu-id="40e86-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="40e86-105">Microsoft Managed Desktop의 등록을 완료 한 후에는 특정 Microsoft Intune 및 azure AD (Active Directory) 설정을 조정 하 여 관리를 허용 하 고 보안을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-105">After you've completed enrollment in Microsoft Managed Desktop, you need to adjust certain Microsoft Intune and Azure Active Directory (Azure AD) settings to allow for management and maintain security.</span></span> <span data-ttu-id="40e86-106">Microsoft Managed Desktop 장치 및 사용자가 포함 된 Azure AD 그룹을 제외 하려면 다음 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-106">Set the following settings to exclude the Azure AD groups that contain Microsoft Managed Desktop devices and users.</span></span> <span data-ttu-id="40e86-107">그룹을 제외 하는 단계에 대 한 자세한 내용은 [조건부 액세스: 사용자 및 그룹](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="40e86-107">For steps to exclude groups, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="40e86-108">Microsoft Intune 설정</span><span class="sxs-lookup"><span data-stu-id="40e86-108">Microsoft Intune settings</span></span>

- <span data-ttu-id="40e86-109">Autopilot 배포 프로필: **최신 작업 공간 장치 (모든**  Azure AD 그룹)를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-109">Autopilot deployment profile: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="40e86-110">자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="40e86-110">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span>
- <span data-ttu-id="40e86-111">조건부 액세스 정책: **최신 작업 공간 서비스 계정** Azure AD 그룹을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-111">Conditional Access policies: exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="40e86-112">단계에 대 한 자세한 내용은 [조건부 액세스: 사용자 및 그룹](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="40e86-112">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>
- <span data-ttu-id="40e86-113">다단계 인증: 다단계 인증을 필요로 하는 모든 조건부 액세스 정책이 **최신 작업 공간 서비스 계정** Azure AD 그룹을 제외 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-113">Multifactor authentication: make sure any conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="40e86-114">자세한 내용은 [조건부 액세스 정책](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40e86-114">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>
- <span data-ttu-id="40e86-115">보안 기준: **최신 작업 공간 장치 (All**  Azure AD 그룹)를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-115">Security baseline: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="40e86-116">자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="40e86-116">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>
- <span data-ttu-id="40e86-117">Windows 10 업데이트 링: **최신 작업 공간 장치 (모든**  Azure AD 그룹)를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-117">Windows 10 update ring: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="40e86-118">자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40e86-118">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="40e86-119">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="40e86-119">Azure Active Directory settings</span></span>

<span data-ttu-id="40e86-120">셀프 서비스 암호 재설정: **선택한** 설정을 선택한 다음 **최신 작업 공간 장치-모든** Azure AD 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e86-120">Self-service password reset: choose **Selected** setting, and then select **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="40e86-121">자세한 내용은 [Tutorial: 사용자가 Azure Active Directory 셀프 서비스 암호 재설정을 사용 하 여 계정의 잠금을 해제 하거나 암호를 재설정할 수 있도록](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40e86-121">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="40e86-122">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="40e86-122">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="40e86-123">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="40e86-123">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="40e86-124">등록 후 설정 조정 (이 문서)</span><span class="sxs-lookup"><span data-stu-id="40e86-124">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="40e86-125">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="40e86-125">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="40e86-126">Intune 회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="40e86-126">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="40e86-127">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="40e86-127">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="40e86-128">장치 설정</span><span class="sxs-lookup"><span data-stu-id="40e86-128">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="40e86-129">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="40e86-129">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="40e86-130">앱 배포</span><span class="sxs-lookup"><span data-stu-id="40e86-130">Deploy apps</span></span>](deploy-apps.md)
