---
title: Microsoft 365 테스트 환경에서 클라우드 전용 ID 및 장치 액세스 필수 구성 요소
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 클라우드 전용 인증을 위한 필수 구성 요소를 사용하여 ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: aa18e1a9943ec12465737f6c3f2e12c1fa49e2a3
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398880"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="d0183-103">Microsoft 365 테스트 환경에서 클라우드 전용 ID 및 장치 액세스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d0183-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="d0183-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="d0183-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d0183-105">[ID 및 장치 액세스 구성은](../security/office-365-security/microsoft-365-policies-configurations.md) Azure AD(Azure Active Directory)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 구성 및 조건부 액세스 정책 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="d0183-106">이 문서에서는 ID 및 장치 액세스를 위해 [클라우드 전용 필수 구성](../security/office-365-security/identity-access-prerequisites.md#prerequisites)의 요구 사항을 충족하는 Microsoft 365 테스트 환경을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="d0183-107">이 테스트 환경을 설정하는 데 8가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="d0183-108">간단한 테스트 환경 빌드</span><span class="sxs-lookup"><span data-stu-id="d0183-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="d0183-109">명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-109">Configure named locations</span></span>
3.  <span data-ttu-id="d0183-110">암호 쓰기 저장 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-110">Configure password writeback</span></span>
4.  <span data-ttu-id="d0183-111">셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="d0183-112">다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="d0183-113">Azure AD Identity Protection 사용</span><span class="sxs-lookup"><span data-stu-id="d0183-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="d0183-114">Exchange Online 및 비즈니스용 Skype Online에 대한 최신 인증을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="d0183-115">1단계: 간단한 Microsoft 365 테스트 환경 빌드</span><span class="sxs-lookup"><span data-stu-id="d0183-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="d0183-116">[간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="d0183-117">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-117">Here is the resulting configuration.</span></span>

![간단한 Microsoft 365 Enterprise 테스트 환경](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="d0183-119">2단계: 명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="d0183-120">먼저 조직에서 사용하는 공개 IP 주소 또는 주소 범위를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="d0183-121">그 다음 [Azure Active Directory에서 명명된 위치 구성](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)의 지침에 따라 주소 또는 주소 범위를 명명된 위치로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="d0183-122">3단계: 암호 쓰기 저장 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="d0183-123">[암호 쓰기 저장 테스트 랩 가이드의 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="d0183-124">4단계: 셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="d0183-125">[암호 재설정 테스트 랩 가이드의 3단계](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="d0183-126">특정 Azure AD 그룹의 계정에 대한 비밀번호 재설정을 활성화 할 때 다음 계정을 **비밀번호 재설정** 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="d0183-127">사용자 2</span><span class="sxs-lookup"><span data-stu-id="d0183-127">User 2</span></span>
- <span data-ttu-id="d0183-128">사용자 3</span><span class="sxs-lookup"><span data-stu-id="d0183-128">User 3</span></span>
- <span data-ttu-id="d0183-129">사용자 4</span><span class="sxs-lookup"><span data-stu-id="d0183-129">User 4</span></span>
- <span data-ttu-id="d0183-130">사용자 5</span><span class="sxs-lookup"><span data-stu-id="d0183-130">User 5</span></span>

<span data-ttu-id="d0183-131">사용자 2 계정에 대해서만 암호 재설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="d0183-132">5단계: 다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="d0183-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="d0183-133">다음 사용자 계정에 대해 [다단계 인증 테스트 랩 가이드의 2단계](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="d0183-134">사용자 2</span><span class="sxs-lookup"><span data-stu-id="d0183-134">User 2</span></span>
- <span data-ttu-id="d0183-135">사용자 3</span><span class="sxs-lookup"><span data-stu-id="d0183-135">User 3</span></span>
- <span data-ttu-id="d0183-136">사용자 4</span><span class="sxs-lookup"><span data-stu-id="d0183-136">User 4</span></span>
- <span data-ttu-id="d0183-137">사용자 5</span><span class="sxs-lookup"><span data-stu-id="d0183-137">User 5</span></span>

<span data-ttu-id="d0183-138">사용자 2 계정에 대해서만 다단계 인증을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="d0183-139">6단계: Azure Active Directory Identity Protection 사용</span><span class="sxs-lookup"><span data-stu-id="d0183-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="d0183-140">[Azure Active Directory Identity Protection 테스트 랩 가이드의 2단계](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="d0183-141">7단계: Exchange Online 및 비즈니스용 Skype Online에 대해 최신 인증을 사용</span><span class="sxs-lookup"><span data-stu-id="d0183-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="d0183-142">Exchange Online의 경우에는 [이 지침](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="d0183-143">Online 비즈니스용 Skype의 경우:</span><span class="sxs-lookup"><span data-stu-id="d0183-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="d0183-144">[온라인 비즈니스를 위한 Skype에 연결](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d0183-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="d0183-145">이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="d0183-146">이 명령을 사용하여 변경되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="d0183-147">그 결과는 ID 및 장치 액세스에 대한 [클라우드 전용 필수 구성](../security/office-365-security/identity-access-prerequisites.md#prerequisites)의 요구 사항을 충족하는 테스트 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="d0183-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d0183-148">Next step</span></span>

<span data-ttu-id="d0183-149">[일반 ID 및 장치 액세스 정책](identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치를 보호하는 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0183-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0183-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0183-150">See also</span></span>

[<span data-ttu-id="d0183-151">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="d0183-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="d0183-152">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="d0183-152">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="d0183-153">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="d0183-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d0183-154">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="d0183-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d0183-155">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="d0183-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
