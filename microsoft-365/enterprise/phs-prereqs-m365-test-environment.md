---
title: Microsoft 365 테스트 환경에서 암호 해시 동기화를 위한 ID 및 장치 액세스 필수 구성 요소
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 암호 해시 동기화를 위한 필수 구성 요소를 사용하여 ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: 125d8c6e1e954a05edd630c8f4d55848fa3314b3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066038"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="0f264-103">Microsoft 365 테스트 환경에서 암호 해시 동기화를 위한 ID 및 장치 액세스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0f264-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="0f264-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="0f264-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="0f264-105">[ID 및 장치 액세스 구성](microsoft-365-policies-configurations.md)은 Microsoft 365 Enterprise의 Office 365 및 Enterprise Mobility + Security(EMS) 등 Azure Directory(Azure AD)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 일련의 구성 및 조건부 액세스 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="0f264-106">이 문서에서는 ID와 장치 액세스를 위해 [암호 해시 동기화 필수 구성를 사용하여 Active Directory](identity-access-prerequisites.md#prerequisites)의 요구사항을 충족하는 Microsoft 365 테스트 환경을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="0f264-107">이 테스트 환경의 8가지 주요 설정 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="0f264-108">암호 해시 동기화 테스트 환경에서 시뮬레이션된 엔터프라이즈 만들기</span><span class="sxs-lookup"><span data-stu-id="0f264-108">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="0f264-109">Azure AD Seamless Single Sign-On 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="0f264-110">명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-110">Configure named locations</span></span>
4.  <span data-ttu-id="0f264-111">암호 쓰기 저장 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-111">Configure password writeback</span></span>
5.  <span data-ttu-id="0f264-112">모든 사용자 계정에 사용할 수 있는 셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-112">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="0f264-113">모든 사용자 계정을 위한 다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-113">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="0f264-114">Azure AD Identity Protection 사용</span><span class="sxs-lookup"><span data-stu-id="0f264-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="0f264-115">Exchange Online 및 비즈니스용 Skype Online에 대한 최신 인증을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="0f264-116">1단계: 암호 해시 동기화 Microsoft 365 테스트 환경을 사용하여 시뮬레이션된 엔터프라이즈 빌드</span><span class="sxs-lookup"><span data-stu-id="0f264-116">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="0f264-117">[암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0f264-117">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="0f264-118">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-118">Here is the resulting configuration.</span></span>

![암호 해시 동기화 테스트 환경을 사용하여 시뮬레이션된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="0f264-120">2단계: Azure AD Seamless Single Sign-on 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="0f264-121">[Azure AD Seamless Single Sign-on 테스트 랩 가이드의 2 단계](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="0f264-122">3단계: 명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="0f264-123">먼저 조직에서 사용하는 공개 IP 주소 또는 주소 범위를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="0f264-124">그 다음 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)에서 명명된 위치 구성의 지침에 따라 주소 또는 주소 범위를 명명된 위치로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="0f264-125">4단계: 비밀번호 쓰기 저장 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="0f264-126">[암호 재작성 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 테스트 랩 가이드의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="0f264-127">5단계: 셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="0f264-128">[암호 재설정 3단계](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 테스트 랩 가이드의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="0f264-129">특정 Azure AD 그룹의 계정에 대한 비밀번호 재설정을 활성화 할 때 다음 계정을 **비밀번호 재설정** 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="0f264-130">사용자 2</span><span class="sxs-lookup"><span data-stu-id="0f264-130">User 2</span></span>
- <span data-ttu-id="0f264-131">사용자 3</span><span class="sxs-lookup"><span data-stu-id="0f264-131">User 3</span></span>
- <span data-ttu-id="0f264-132">사용자 4</span><span class="sxs-lookup"><span data-stu-id="0f264-132">User 4</span></span>
- <span data-ttu-id="0f264-133">사용자 5</span><span class="sxs-lookup"><span data-stu-id="0f264-133">User 5</span></span>

<span data-ttu-id="0f264-134">사용자 2 계정에 대해서만 암호 재설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="0f264-135">6단계: Multi-Factor Authentication 구성</span><span class="sxs-lookup"><span data-stu-id="0f264-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="0f264-136">다음 사용자 계정에 대해 [다중 요소 인증 테스트 랩 가이드의  2 단계](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="0f264-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="0f264-137">사용자 2</span><span class="sxs-lookup"><span data-stu-id="0f264-137">User 2</span></span>
- <span data-ttu-id="0f264-138">사용자 3</span><span class="sxs-lookup"><span data-stu-id="0f264-138">User 3</span></span>
- <span data-ttu-id="0f264-139">사용자 4</span><span class="sxs-lookup"><span data-stu-id="0f264-139">User 4</span></span>
- <span data-ttu-id="0f264-140">사용자 5</span><span class="sxs-lookup"><span data-stu-id="0f264-140">User 5</span></span>

<span data-ttu-id="0f264-141">사용자 2 계정에 대해서만 다중 요소 인증을 테스트하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f264-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="0f264-142">7단계: Azure Active Directory Identity Protection 사용</span><span class="sxs-lookup"><span data-stu-id="0f264-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="0f264-143">[Azure AD ID 보호 테스트 랩 가이드의 2 단계](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="0f264-144">8단계: Exchange Online 및 Skype for Business Online에 대한 최신 인증을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="0f264-145">Exchange Online의 경우에는 [이 지침](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="0f264-146">Online 비즈니스용 Skype의 경우:</span><span class="sxs-lookup"><span data-stu-id="0f264-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="0f264-147">[온라인 비즈니스를 위한 Skype에 연결](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0f264-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="0f264-148">이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="0f264-149">이 명령을 사용하여 변경되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="0f264-150">결과는 ID와 장치 액세스를 위해 [암호 해시 동기화 필수 구성을 사용하여 Active Directory](identity-access-prerequisites.md#prerequisites)의 요구 사항을 충족하는 테스트 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-150">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="0f264-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0f264-151">Next step</span></span>

<span data-ttu-id="0f264-152">[일반 ID 및 장치 액세스 정책](identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치를 보호하는 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f264-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f264-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f264-153">See also</span></span>

[<span data-ttu-id="0f264-154">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="0f264-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="0f264-155">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="0f264-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="0f264-156">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="0f264-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0f264-157">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="0f264-157">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0f264-158">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="0f264-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
