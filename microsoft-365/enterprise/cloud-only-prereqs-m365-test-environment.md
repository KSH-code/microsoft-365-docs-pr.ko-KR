---
title: Microsoft 365 테스트 환경에서 클라우드 전용 ID 및 장치 액세스 필수 구성 요소
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
description: 클라우드 전용 인증을 위한 필수 구성 요소를 사용하여 ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: 1e659304eee330960937b641c9a39b03920f52e7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233133"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="f41cb-103">Microsoft 365 테스트 환경에서 클라우드 전용 ID 및 장치 액세스 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f41cb-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="f41cb-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="f41cb-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="f41cb-105">[ID 및 장치 액세스 구성은](../security/office-365-security/microsoft-365-policies-configurations.md) Azure AD(Azure Active Directory)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 권장 구성 및 조건부 액세스 정책 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="f41cb-106">이 문서에서는 ID 및 장치 액세스를 위해 [클라우드 전용 필수 구성](../security/office-365-security/identity-access-prerequisites.md#prerequisites)의 요구 사항을 충족하는 Microsoft 365 테스트 환경을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="f41cb-107">이 테스트 환경의 8가지 주요 설정 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="f41cb-108">간단한 테스트 환경 빌드</span><span class="sxs-lookup"><span data-stu-id="f41cb-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="f41cb-109">명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="f41cb-109">Configure named locations</span></span>
3. <span data-ttu-id="f41cb-110">셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="f41cb-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="f41cb-111">Multi-Factor Authentication를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="f41cb-112">도메인에 가입된 Windows 컴퓨터의 자동 장치 등록 사용</span><span class="sxs-lookup"><span data-stu-id="f41cb-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="f41cb-113">Azure AD 암호 보호 구성</span><span class="sxs-lookup"><span data-stu-id="f41cb-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="f41cb-114">Azure AD Identity Protection 사용</span><span class="sxs-lookup"><span data-stu-id="f41cb-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="f41cb-115">Exchange Online 및 비즈니스용 Skype Online에 대한 최신 인증을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="f41cb-116">1단계: 간단한 Microsoft 365 테스트 환경 빌드</span><span class="sxs-lookup"><span data-stu-id="f41cb-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="f41cb-117">[간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="f41cb-118">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-118">Here is the resulting configuration.</span></span>

![간단한 Microsoft 365 Enterprise 테스트 환경](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="f41cb-120">2단계: 명명된 위치 구성</span><span class="sxs-lookup"><span data-stu-id="f41cb-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="f41cb-121">먼저 조직에서 사용하는 공개 IP 주소 또는 주소 범위를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="f41cb-122">그 다음 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)에서 명명된 위치 구성의 지침에 따라 주소 또는 주소 범위를 명명된 위치로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="f41cb-123">3단계: 셀프 서비스 암호 재설정 구성</span><span class="sxs-lookup"><span data-stu-id="f41cb-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="f41cb-124">[암호 재설정 테스트 랩 가이드의 3단계](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="f41cb-125">특정 Azure AD 그룹의 계정에 대한 비밀번호 재설정을 활성화 할 때 다음 계정을 **비밀번호 재설정** 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="f41cb-126">사용자 2</span><span class="sxs-lookup"><span data-stu-id="f41cb-126">User 2</span></span>
- <span data-ttu-id="f41cb-127">사용자 3</span><span class="sxs-lookup"><span data-stu-id="f41cb-127">User 3</span></span>
- <span data-ttu-id="f41cb-128">사용자 4</span><span class="sxs-lookup"><span data-stu-id="f41cb-128">User 4</span></span>
- <span data-ttu-id="f41cb-129">사용자 5</span><span class="sxs-lookup"><span data-stu-id="f41cb-129">User 5</span></span>

<span data-ttu-id="f41cb-130">사용자 2 계정에 대해서만 암호 재설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="f41cb-131">4단계: 다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="f41cb-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="f41cb-132">다음 사용자 계정에 대해 [다중 요소 인증 테스트 랩 가이드의  2 단계](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="f41cb-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="f41cb-133">사용자 2</span><span class="sxs-lookup"><span data-stu-id="f41cb-133">User 2</span></span>
- <span data-ttu-id="f41cb-134">사용자 3</span><span class="sxs-lookup"><span data-stu-id="f41cb-134">User 3</span></span>
- <span data-ttu-id="f41cb-135">사용자 4</span><span class="sxs-lookup"><span data-stu-id="f41cb-135">User 4</span></span>
- <span data-ttu-id="f41cb-136">사용자 5</span><span class="sxs-lookup"><span data-stu-id="f41cb-136">User 5</span></span>

<span data-ttu-id="f41cb-137">사용자 2 계정에 대해서만 다단계 인증을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="f41cb-138">5단계: 도메인에 가입된 Windows 컴퓨터의 자동 장치 등록 사용</span><span class="sxs-lookup"><span data-stu-id="f41cb-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="f41cb-139">다음 [지침에 따라](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) 도메인에 가입된 Windows 컴퓨터의 자동 장치 등록을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-139">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="f41cb-140">6단계: Azure AD 암호 보호 구성</span><span class="sxs-lookup"><span data-stu-id="f41cb-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="f41cb-141">다음 [지침에 따라](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 알려진 약한 암호 및 해당 변형을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-141">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="f41cb-142">7단계: Azure Active Directory Identity Protection 사용</span><span class="sxs-lookup"><span data-stu-id="f41cb-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="f41cb-143">[Azure AD ID 보호 테스트 랩 가이드의 2 단계](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="f41cb-144">8단계: Exchange Online 및 Skype for Business Online에 대한 최신 인증을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="f41cb-145">Exchange Online의 경우에는 [이 지침](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="f41cb-146">Online 비즈니스용 Skype의 경우:</span><span class="sxs-lookup"><span data-stu-id="f41cb-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="f41cb-147">[온라인 비즈니스를 위한 Skype에 연결](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f41cb-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="f41cb-148">이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="f41cb-149">이 명령을 사용하여 변경되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="f41cb-150">그 결과 ID 및 장치 액세스에 [](../security/office-365-security/identity-access-prerequisites.md#prerequisites) 대한 클라우드 전용 선행 조건 구성의 요구 사항을 충족하는 테스트 환경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="f41cb-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f41cb-151">Next step</span></span>

<span data-ttu-id="f41cb-152">[일반 ID 및 장치 액세스 정책](identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치를 보호하는 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f41cb-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="f41cb-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f41cb-153">See also</span></span>

[<span data-ttu-id="f41cb-154">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="f41cb-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="f41cb-155">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="f41cb-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="f41cb-156">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="f41cb-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f41cb-157">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="f41cb-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f41cb-158">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="f41cb-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
