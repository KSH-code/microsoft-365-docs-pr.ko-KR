---
title: Microsoft 365 테스트 환경에서 암호 해시 동기화를 위한 ID 및 장치 액세스 필수 구성 요소
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 암호 해시 동기화를 위한 필수 구성 요소를 사용하여 ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: 8e8db4aae39acda0762f9b6394b23ab047727ea5
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233787"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="84c23-103">Microsoft 365 테스트 환경에서 암호 해시 동기화를 위한 ID 및 장치 액세스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="84c23-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="84c23-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="84c23-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="84c23-105">[ID 및 장치](../security/office-365-security/microsoft-365-policies-configurations.md) 액세스 구성은 Azure AD(Azure Active Directory)와 통합된 엔터프라이즈용 Microsoft 365의 모든 서비스에 대한 액세스를 보호하기 위한 구성 및 조건부 액세스 정책 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="84c23-106">이 문서에서는 ID 및 장치 액세스에 대한 암호 해시 동기화 [](../security/office-365-security/identity-access-prerequisites.md#prerequisites) 인증 선행 조건 구성을 사용하여 하이브리드의 요구 사항을 충족하는 Microsoft 365 테스트 환경을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [hybrid with password hash sync authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="84c23-107">이 테스트 환경을 설정하는 데는 10단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="84c23-108">암호 해시 동기화 테스트 환경에서 시뮬레이션된 엔터프라이즈 만들기</span><span class="sxs-lookup"><span data-stu-id="84c23-108">Create a simulated enterprise with password hash sync test environment</span></span>
2. <span data-ttu-id="84c23-109">Azure AD Seamless Single Sign-On 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="84c23-110">명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-110">Configure named locations</span></span>
4. <span data-ttu-id="84c23-111">암호 쓰기 저장 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-111">Configure password writeback</span></span>
5. <span data-ttu-id="84c23-112">모든 사용자 계정에 사용할 수 있는 셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-112">Configure self-service password reset for all user accounts</span></span>
6. <span data-ttu-id="84c23-113">모든 사용자 계정을 위한 다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-113">Configure multifactor authentication for all user accounts</span></span>
7. <span data-ttu-id="84c23-114">도메인에 가입된 Windows 컴퓨터의 자동 장치 등록 사용</span><span class="sxs-lookup"><span data-stu-id="84c23-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="84c23-115">Azure AD 암호 보호 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="84c23-116">Azure AD Identity Protection 사용</span><span class="sxs-lookup"><span data-stu-id="84c23-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="84c23-117">Exchange Online 및 비즈니스용 Skype Online에 대한 최신 인증을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="84c23-118">1단계: 암호 해시 동기화 Microsoft 365 테스트 환경을 사용하여 시뮬레이션된 엔터프라이즈 빌드</span><span class="sxs-lookup"><span data-stu-id="84c23-118">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="84c23-119">암호 해시 동기화 테스트 랩 가이드의 [지침을](password-hash-sync-m365-ent-test-environment.md) 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-119">Follow the instructions in [the password hash synchronization](password-hash-sync-m365-ent-test-environment.md) Test Lab Guide.</span></span>
<span data-ttu-id="84c23-120">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-120">Here is the resulting configuration.</span></span>

![암호 해시 동기화 테스트 환경을 사용하여 시뮬레이션된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="84c23-122">2단계: Azure AD Seamless Single Sign-on 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="84c23-123">[Azure AD Seamless Single Sign-on 테스트 랩 가이드의 2 단계](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="84c23-124">3단계: 명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="84c23-125">먼저 조직에서 사용하는 공개 IP 주소 또는 주소 범위를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="84c23-126">그 다음 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)에서 명명된 위치 구성의 지침에 따라 주소 또는 주소 범위를 명명된 위치로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="84c23-127">4단계: 비밀번호 쓰기 저장 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="84c23-128">[암호 재작성 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 테스트 랩 가이드의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="84c23-129">5단계: 셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="84c23-130">[암호 재설정 3단계](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 테스트 랩 가이드의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="84c23-131">특정 Azure AD 그룹의 계정에 대한 비밀번호 재설정을 활성화 할 때 다음 계정을 **비밀번호 재설정** 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="84c23-132">사용자 2</span><span class="sxs-lookup"><span data-stu-id="84c23-132">User 2</span></span>
- <span data-ttu-id="84c23-133">사용자 3</span><span class="sxs-lookup"><span data-stu-id="84c23-133">User 3</span></span>
- <span data-ttu-id="84c23-134">사용자 4</span><span class="sxs-lookup"><span data-stu-id="84c23-134">User 4</span></span>
- <span data-ttu-id="84c23-135">사용자 5</span><span class="sxs-lookup"><span data-stu-id="84c23-135">User 5</span></span>

<span data-ttu-id="84c23-136">사용자 2 계정에 대해서만 암호 재설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="84c23-137">6단계: Multi-Factor Authentication 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="84c23-138">다음 사용자 계정에 대해 [다중 요소 인증 테스트 랩 가이드의  2 단계](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="84c23-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="84c23-139">사용자 2</span><span class="sxs-lookup"><span data-stu-id="84c23-139">User 2</span></span>
- <span data-ttu-id="84c23-140">사용자 3</span><span class="sxs-lookup"><span data-stu-id="84c23-140">User 3</span></span>
- <span data-ttu-id="84c23-141">사용자 4</span><span class="sxs-lookup"><span data-stu-id="84c23-141">User 4</span></span>
- <span data-ttu-id="84c23-142">사용자 5</span><span class="sxs-lookup"><span data-stu-id="84c23-142">User 5</span></span>

<span data-ttu-id="84c23-143">사용자 2 계정에 대해서만 다단계 인증을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="84c23-144">7단계: 도메인에 가입된 Windows 컴퓨터의 자동 장치 등록 사용</span><span class="sxs-lookup"><span data-stu-id="84c23-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="84c23-145">다음 [지침에 따라](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) 도메인에 가입된 Windows 컴퓨터의 자동 장치 등록을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-145">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="84c23-146">8단계: Azure AD 암호 보호 구성</span><span class="sxs-lookup"><span data-stu-id="84c23-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="84c23-147">다음 [지침에 따라](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 알려진 약한 암호 및 해당 변형을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-147">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="84c23-148">9단계: Azure AD ID 보호 사용</span><span class="sxs-lookup"><span data-stu-id="84c23-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="84c23-149">[Azure AD ID 보호 테스트 랩 가이드의 2 단계](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="84c23-150">10단계: Exchange Online 및 비즈니스용 Skype Online에 대해 최신 인증 사용</span><span class="sxs-lookup"><span data-stu-id="84c23-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="84c23-151">Exchange Online의 경우에는 [이 지침](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-151">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="84c23-152">Online 비즈니스용 Skype의 경우:</span><span class="sxs-lookup"><span data-stu-id="84c23-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="84c23-153">[온라인 비즈니스를 위한 Skype에 연결](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="84c23-153">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="84c23-154">이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="84c23-155">이 명령을 사용하여 변경되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="84c23-156">결과는 ID와 장치 액세스를 위해 [암호 해시 동기화 필수 구성을 사용하여 Active Directory](../security/office-365-security/identity-access-prerequisites.md#prerequisites)의 요구 사항을 충족하는 테스트 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-156">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="84c23-157">다음 단계</span><span class="sxs-lookup"><span data-stu-id="84c23-157">Next step</span></span>

<span data-ttu-id="84c23-158">[일반 ID 및 장치 액세스 정책](identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치를 보호하는 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="84c23-158">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="84c23-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84c23-159">See also</span></span>

[<span data-ttu-id="84c23-160">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="84c23-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="84c23-161">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="84c23-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="84c23-162">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="84c23-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="84c23-163">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="84c23-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="84c23-164">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="84c23-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
