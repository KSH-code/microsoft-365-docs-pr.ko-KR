---
title: '3단계: 하이브리드 ID 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID 옵션을 이해하고 온-프레미스 Active Directory Domain Services를 Azure AD와 동기화하도록 Azure AD Connect를 구성합니다.
ms.openlocfilehash: 0b494047f984d9fd830e840d2d1f4fafa06fe8ab
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073828"
---
# <a name="step-3-configure-hybrid-identity"></a><span data-ttu-id="538d4-103">3단계: 하이브리드 ID 구성</span><span class="sxs-lookup"><span data-stu-id="538d4-103">Step 3: Configure hybrid identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a><span data-ttu-id="538d4-104">ID 동기화</span><span class="sxs-lookup"><span data-stu-id="538d4-104">Synchronize identities</span></span>

<span data-ttu-id="538d4-105">*이 단계는 하이브리드 환경의 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="538d4-105">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="538d4-106">이 섹션에서는 온-프레미스 AD DS(Active Directory Domain Services)를 Office 365 및 EMS(Enterprise Mobility + Security) 구독에서 사용하는 Azure AD(Azure Active Directory)와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-106">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure Active Directory (Azure AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="538d4-107">Azure AD Connect는 단일 또는 다중 포리스트 AD DS 환경에서 실제로 필요한 ID만 Azure AD 테넌트에 동기화하는 과정을 안내하는 지원되는 Microsoft 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-107">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="538d4-108">다음 그림에서는 Azure AD Connect 동기화의 기본 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-108">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Azure AD Connect에서 온-프레미스 디렉터리를 Azure AD와 동기화하는 방법](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. <span data-ttu-id="538d4-110">서버에서 실행되는 Azure AD Connect는 계정, 그룹 및 연락처 변경 내용을 AD DS에서 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-110">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="538d4-111">Azure AD Connect는 이러한 변경 내용을 Microsoft 365 구독의 Azure AD 테넌트로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-111">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="538d4-p102">하이브리드 ID 솔루션에서 가장 처음으로 결정할 사항은 인증 요구 사항입니다. 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-p102">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="538d4-p103">**관리되는 인증**을 사용하는 경우 Azure AD는 사용자 로그인에 대한 인증 프로세스를 처리합니다. 관리되는 인증에는 다음 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-p103">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="538d4-116">**PHS(암호 해시 동기화)**[일부 프리미엄 기능에 권장되고 필요함]</span><span class="sxs-lookup"><span data-stu-id="538d4-116">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="538d4-117">Azure AD에서 온-프레미스 디렉터리 개체에 대한 인증을 사용하도록 설정하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-117">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="538d4-118">Azure AD Connect는 AD DS에서 해시된 암호를 추출하고, 암호의 보안을 강화하고, Azure AD에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-118">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password, and saves it in Azure AD.</span></span> <span data-ttu-id="538d4-119">자세한 내용은 [Azure AD Connect 동기화를 사용하여 암호 해시 동기화 구현](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="538d4-119">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="538d4-120">**PTA(통과 인증)** 는 Azure AD 기반 서비스에 대한 간단한 암호 유효성 검사 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-120">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="538d4-121">PTA는 하나 이상의 온-프레미스 서버에서 실행되는 에이전트를 사용하여 온-프레미스 AD DS를 통해 직접 사용자 인증이 유효한지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-121">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="538d4-122">자세한 내용은 [Azure Active Directory 통과 인증으로 사용자 로그인](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="538d4-122">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="538d4-p106">**페더레이션 인증**을 사용하는 경우 인증 프로세스는 사용자의 로그인에 대해 AD FS(Active Directory Federation Services)와 같은 ID 페더레이션 서버를 통해 다른 ID 공급자로 리디렉션됩니다. ID 공급자는 스마트 카드 기반 인증과 같은 추가 인증 방법을 제공할 수 있습니다. 자세한 내용은 [Azure Active Directory 하이브리드 ID 솔루션에 적합한 인증 방법 선택](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="538d4-p106">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="538d4-126">하이브리드 ID 솔루션을 확인한 후에는 [IdFix 디렉터리 동기화 오류 수정 도구](https://www.microsoft.com/download/details.aspx?id=36832)를 다운로드하고 실행하여 AD DS에서 문제를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-126">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="538d4-127">IdFix 도구에서 식별된 모든 문제를 해결한 후에는 [암호 해시 동기화 구현](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)에서 Azure AD Connect 도구를 설치하는 방법과 Office 365 및 EMS 구독에 대해 온-프레미스 AD DS와 Azure AD 테넌트 간의 디렉터리 동기화를 구성하는 방법에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="538d4-127">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span> <span data-ttu-id="538d4-128">동기화가 시작되면 AD DS와 같은 온-프레미스 ID 공급자를 통해 사용자 계정 및 그룹을 유지 관리하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-128">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="538d4-129">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-129">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="538d4-130">하이브리드 환경에 대한 권장 요구 사항에 대해서는 [필수 구성 요소](identity-access-prerequisites.md#prerequisites) 열의 **암호 해시 동기화를 사용한 Active Directory**를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="538d4-130">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="538d4-131">클라우드 전용 환경에 대한 권장 요구 사항에 대해서는 [필수 구성 요소](identity-access-prerequisites.md#prerequisites) 열의 **클라우드만**을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="538d4-131">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="538d4-132">Azure AD에 온-프레미스 사용자 및 그룹이 있으면 라이선스를 할당하고 Exchange Online을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-132">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using Exchange Online.</span></span> <span data-ttu-id="538d4-133">사용자에게 Exchange Online을 롤아웃하고 온-프레미스 사서함을 마이그레이션하려면 [Microsoft 365 Enterprise에 대한 Exchange Online 배포](exchangeonline-workload.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="538d4-133">To roll out Exchange Online to your users and migrate on-premises mailboxes, see [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="538d4-135">테스트 랩 가이드: 암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="538d4-135">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="538d4-136">테스트 랩 가이드: 경유 인증</span><span class="sxs-lookup"><span data-stu-id="538d4-136">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="538d4-137">중간 검사점으로 이 섹션에 해당하는 [종료 조건](identity-exit-criteria.md#crit-identity-sync)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-137">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="538d4-138">동기화 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="538d4-138">Monitor synchronization health</span></span>

<span data-ttu-id="538d4-139">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="538d4-139">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="538d4-140">이 섹션에서는 각 온-프레미스 ID 서버에 Azure AD Connect 상태 에이전트를 설치하여 Azure AD Connect에서 제공하는 ID 인프라 및 동기화 서비스를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-140">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="538d4-141">모니터링 정보는 Azure AD Connect Health 포털에서 사용할 수 있습니다. 이 포털에서 경고, 성능 모니터링, 사용 현황 분석, 기타 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-141">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health의 구성 요소](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="538d4-143">Azure AD Connect Health 사용 방법에 대한 주요 디자인 의사 결정은 Azure AD Connect 사용 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-143">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="538d4-144">**관리되는 인증** 옵션을 사용하는 경우 [동기화와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-144">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="538d4-145">AD FS(Active Directory Federation Services)에서 **페더레이션 인증**을 사용하여 계정 및 그룹의 이름만 동기화하는 경우 [AD FS와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-145">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="538d4-146">이 섹션을 완료하면 다음과 같은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-146">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="538d4-147">온-프레미스 ID 서버에 Azure AD Connect Health 에이전트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-147">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="538d4-148">Office 365 및 EMS 구독에 대한 Azure AD 테넌트와 함께 온-프레미스 인프라 및 동기화 활동의 현재 상태가 Azure AD Connect Health 포털에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-148">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="538d4-149">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sync-health)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d4-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="538d4-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="538d4-150">Next step</span></span>

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="538d4-151">안전한 사용자 인증을 구성</span><span class="sxs-lookup"><span data-stu-id="538d4-151">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md)
