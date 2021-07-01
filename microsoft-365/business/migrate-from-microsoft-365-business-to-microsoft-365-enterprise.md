---
title: Microsoft 365 Business에서 Microsoft 365 E3로 마이그레이션
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 비즈니스를 새로운 비즈니스로 이동하는 Microsoft 365 Business Premium Microsoft 365 E3.
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227622"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="1eba2-103">Microsoft 365 Business Premium에서 Microsoft 365 E3로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1eba2-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="1eba2-104">Microsoft 365 Business Premium 중소기업에 필요한 모든 것이 있으며, 직원이 최고의 작업을 할 수 있도록 하는 간단한 장치 관리 및 보안과 동급 최고의 클라우드 기반 생산성 앱을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="1eba2-105">그러나 경우에 따라 Microsoft 365 Business Premium 구독을 마이그레이션해야 할 Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="1eba2-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span>

<span data-ttu-id="1eba2-106">예를 들어 비즈니스가 성장하여 300개 이상의 라이선스가 필요합니다(축하합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="1eba2-107">또는 비즈니스에 엔터프라이즈 기능(예: 엔터프라이즈용 Microsoft 365 앱, Windows 10 Enterprise E3 또는 ENTERPRISE 클라이언트 액세스 라이선스)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="1eba2-108">업그레이드는 관리 센터에서 쉽게 시작할 [수 있습니다.](../commerce/subscriptions/upgrade-to-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="1eba2-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="1eba2-109">현재 구독의 모든 데이터 및 구성이 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="1eba2-110">마이그레이션을 준비하기 위해 할 수 있는 것은 아니며, 새 기능을 활용하는 것 외에는 그 이후에 할 일도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

> [!NOTE]
> <span data-ttu-id="1eba2-111">최대 300개 Microsoft 365 Business Premium 사용자 수에 대해 Microsoft 365 E3 구독을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="1eba2-112">그러나 Microsoft Defender for Office 365 포함된 Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="1eba2-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="1eba2-113">계속해서 위협 방지를 위해 Office 365 대한 Defender의 범위에 있는 모든 사용자에게 라이선스가 부여될 수 있도록 Office 365 Defender를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="1eba2-114">Microsoft 365 Business Premium 및 Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1eba2-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1eba2-115">다음 표에서는 두 가지 차이점을 Microsoft 365 Business Premium Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="1eba2-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="1eba2-116">기능</span><span class="sxs-lookup"><span data-stu-id="1eba2-116">Feature</span></span>    | <span data-ttu-id="1eba2-117">지원 Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1eba2-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="1eba2-118">지원 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="1eba2-118">Support in Microsoft 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="1eba2-119">**On-premises**</span><span class="sxs-lookup"><span data-stu-id="1eba2-119">**On-premises**</span></span>        | | |
| <span data-ttu-id="1eba2-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1eba2-120">Windows 10</span></span>    | <span data-ttu-id="1eba2-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="1eba2-121">Windows 10 Business</span></span>  |     <span data-ttu-id="1eba2-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="1eba2-122">Windows 10 Enterprise E3</span></span>|
| <span data-ttu-id="1eba2-123">Office 앱\*</span><span class="sxs-lookup"><span data-stu-id="1eba2-123">Office apps\*</span></span>    | [<span data-ttu-id="1eba2-124">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="1eba2-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="1eba2-125">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="1eba2-125">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="1eba2-126">**클라우드 생산성 앱**</span><span class="sxs-lookup"><span data-stu-id="1eba2-126">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="1eba2-127">Exchange Online Outlook</span><span class="sxs-lookup"><span data-stu-id="1eba2-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="1eba2-128">사서함당 50GB 저장소 제한 및 무제한 Exchange Online 보관</span><span class="sxs-lookup"><span data-stu-id="1eba2-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="1eba2-129">사서함당 100GB 저장소 제한 및 무제한 Exchange Online 보관</span><span class="sxs-lookup"><span data-stu-id="1eba2-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> |
| <span data-ttu-id="1eba2-130">Teams</span><span class="sxs-lookup"><span data-stu-id="1eba2-130">Teams</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-133">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="1eba2-133">OneDrive for Business</span></span>    | <span data-ttu-id="1eba2-134">사용자당 1 TB 저장소 제한</span><span class="sxs-lookup"><span data-stu-id="1eba2-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="1eba2-135">무제한</span><span class="sxs-lookup"><span data-stu-id="1eba2-135">Unlimited</span></span> |
| <span data-ttu-id="1eba2-136">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="1eba2-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-139">**위협 방지**</span><span class="sxs-lookup"><span data-stu-id="1eba2-139">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="1eba2-140">공격 표면 감소 기능</span><span class="sxs-lookup"><span data-stu-id="1eba2-140">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="1eba2-141">이 목록 보기</span><span class="sxs-lookup"><span data-stu-id="1eba2-141">See this list</span></span>](#threat-protection) | <span data-ttu-id="1eba2-142">Enterprise 대한 하드웨어 기반의 고지서 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1eba2-142">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> |
| <span data-ttu-id="1eba2-143">Office 365용 Defender 플랜 1</span><span class="sxs-lookup"><span data-stu-id="1eba2-143">Defender for Office 365 Plan 1</span></span> | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="1eba2-145">포함되지 않지만 에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-145">Not included, but can be added on</span></span> |
| <span data-ttu-id="1eba2-146">**ID 관리**</span><span class="sxs-lookup"><span data-stu-id="1eba2-146">**Identity management**</span></span>        | | |
| <span data-ttu-id="1eba2-147">하이브리드 AZURE ACTIVE DIRECTORY(Azure AD) 계정, Azure AD MFA(다단계 인증), 조건부 액세스,온-프레미스 ID에 대한 암호 쓰기 저장에 대한 셀프 서비스 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="1eba2-147">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-150">Cloud App Discovery, Azure AD 커넥트 Health</span><span class="sxs-lookup"><span data-stu-id="1eba2-150">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-152">Azure AD Office 365 SSO(Single Sign-On): 사용자당 앱 10개(Salesforce와 같은 갤러리 SaaS 앱)\*</span><span class="sxs-lookup"><span data-stu-id="1eba2-152">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-155">Azure AD Premium 1 SSO: 제한 없음(Azure AD 응용 프로그램 프록시를 통한 Self-Service 앱 통합 템플릿을 사용하는 비 갤러리 앱)</span><span class="sxs-lookup"><span data-stu-id="1eba2-155">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-157">**장치 및 앱 관리**</span><span class="sxs-lookup"><span data-stu-id="1eba2-157">**Device and app management**</span></span>        | | |
| <span data-ttu-id="1eba2-158">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="1eba2-158">Microsoft Intune, Windows Autopilot</span></span>|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="1eba2-161">VDA(가상 데스크톱 액세스)</span><span class="sxs-lookup"><span data-stu-id="1eba2-161">Virtual Desktop Access (VDA)</span></span>    |  |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="1eba2-163">Windows WVD(가상 데스크톱)</span><span class="sxs-lookup"><span data-stu-id="1eba2-163">Windows Virtual Desktop (WVD)</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png) |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="1eba2-166">SCA(공유 컴퓨터 정품 인증)</span><span class="sxs-lookup"><span data-stu-id="1eba2-166">Shared Computer Activation (SCA)</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png) |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-169">Microsoft 데스크톱 최적화 패키지</span><span class="sxs-lookup"><span data-stu-id="1eba2-169">Microsoft Desktop Optimization Package</span></span>    | |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-171">**정보 보호**</span><span class="sxs-lookup"><span data-stu-id="1eba2-171">**Information protection**</span></span>        | | |
| <span data-ttu-id="1eba2-172">Office 365 데이터 손실 방지, Azure Information Protection 계획 1</span><span class="sxs-lookup"><span data-stu-id="1eba2-172">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-175">끝점 DLP에 대한 창 정보 보호</span><span class="sxs-lookup"><span data-stu-id="1eba2-175">Window Information Protection for endpoint DLP</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-178">**CAL(클라이언트 액세스 라이선스)**</span><span class="sxs-lookup"><span data-stu-id="1eba2-178">**Client Access License (CAL rights)**</span></span>    | | |
| <span data-ttu-id="1eba2-179">Enterprise CAL 제품군(Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="1eba2-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-181">**규정 준수**</span><span class="sxs-lookup"><span data-stu-id="1eba2-181">**Compliance**</span></span>        | | |
| <span data-ttu-id="1eba2-182">무제한 전자 메일 보관</span><span class="sxs-lookup"><span data-stu-id="1eba2-182">Unlimited email archiving</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-185">규정 관리자</span><span class="sxs-lookup"><span data-stu-id="1eba2-185">Compliance Manager</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-188">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1eba2-188">eDiscovery</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-191">In-place hold and litigation hold</span><span class="sxs-lookup"><span data-stu-id="1eba2-191">In-place hold and litigation hold</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="1eba2-194">MRM(메시징 레코드 관리) 보존 태그 및 보존 정책</span><span class="sxs-lookup"><span data-stu-id="1eba2-194">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
||||

<span data-ttu-id="1eba2-197">\* SaaS 앱에 대한 액세스 권한이 할당된 사용자는 최대 10개 앱에 대한 SSO 액세스 권한을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-197">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="1eba2-198">관리자는 SSO를 구성하고 다른 SaaS 앱에 대한 사용자 액세스를 변경할 수 있지만 SSO 액세스는 사용자당 한 10개 앱만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-198">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="1eba2-199">모든 Office 365 앱은 단일 앱으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-199">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="1eba2-200">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1eba2-200">Migration</span></span>

<span data-ttu-id="1eba2-201">마이그레이션하려면 파트너와 협력하여 Microsoft 365 Business Premium 라이선스가 있는 적절한 Microsoft 365 E3 구독으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="1eba2-201">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="1eba2-202">다음 섹션에서는 변경해야 하는 사항, 변경 내용(있는 경우) 및 마이그레이션 후 할 수 있는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-202">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="1eba2-203">Microsoft 365 구성 및 데이터 관리</span><span class="sxs-lookup"><span data-stu-id="1eba2-203">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="1eba2-204">마이그레이션하기 전에 다음을 포함하는 현재 구독 또는 데이터를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-204">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="1eba2-205">구독 구성(예: DNS 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="1eba2-205">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="1eba2-206">사용자 및 그룹 계정 및 인증 설정(예: 다단계 인증 또는 조건부 액세스 정책)</span><span class="sxs-lookup"><span data-stu-id="1eba2-206">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="1eba2-207">생산성 서비스 구성 및 데이터(예: Teams, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더 및 전자 필기장 OneNote).</span><span class="sxs-lookup"><span data-stu-id="1eba2-207">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="1eba2-208">이제 사용자는 사서함 및 Exchange Online 폴더에서 무제한 저장소를 비즈니스용 OneDrive 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-208">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="1eba2-209">10개 이상의 앱에 대해 Cloud App Discovery, Azure AD 커넥트 상태 및 SSO 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-209">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="1eba2-210">위협 방지</span><span class="sxs-lookup"><span data-stu-id="1eba2-210">Threat protection</span></span>

<span data-ttu-id="1eba2-211">Windows 10 Business 포함된 보호는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-211">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="1eba2-212">운영 체제 부팅 프로세스의 무결성 적용</span><span class="sxs-lookup"><span data-stu-id="1eba2-212">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="1eba2-213">중요한 운영 구성 요소의 무결성 적용</span><span class="sxs-lookup"><span data-stu-id="1eba2-213">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="1eba2-214">고급 취약성 및 제로 데이 악용 완화</span><span class="sxs-lookup"><span data-stu-id="1eba2-214">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="1eba2-215">Microsoft Edge, Internet Explorer 및 Chrome에 대한 신뢰도 기반 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="1eba2-215">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="1eba2-216">호스트 기반 방화벽</span><span class="sxs-lookup"><span data-stu-id="1eba2-216">Host-based firewall</span></span>
- <span data-ttu-id="1eba2-217">랜섬웨어 완화</span><span class="sxs-lookup"><span data-stu-id="1eba2-217">Ransomware mitigations</span></span>
- <span data-ttu-id="1eba2-218">사용자에 대한 하드웨어 기반 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1eba2-218">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="1eba2-219">지능형 보안 기능으로 지원되는 응용 프로그램 Graph</span><span class="sxs-lookup"><span data-stu-id="1eba2-219">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="1eba2-220">디바이스 제어(USB)</span><span class="sxs-lookup"><span data-stu-id="1eba2-220">Device control (USB)</span></span>
- <span data-ttu-id="1eba2-221">웹 기반 위협에 대한 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="1eba2-221">Network protection for web-based threats</span></span>
- <span data-ttu-id="1eba2-222">호스트 침입 방지 규칙</span><span class="sxs-lookup"><span data-stu-id="1eba2-222">Host intrusion prevention rules</span></span>

<span data-ttu-id="1eba2-223">Windows 10 Enterprise E3에는 하드웨어 기반의 하드웨어 기반의 엔터프라이즈 관리도 포함되어 Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1eba2-223">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="1eba2-224">마이그레이션된 사용자는 Microsoft 365 E3 보호를 위해 각각 microsoft Defender for Office 365 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-224">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="1eba2-225">추가 Defender를 구입하여 Office 365 대한 Defender의 범위에 있는 모든 사용자가 라이선스가 Office 365 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-225">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>

### <a name="device-management-with-intune"></a><span data-ttu-id="1eba2-226">Intune을 사용하여 장치 관리</span><span class="sxs-lookup"><span data-stu-id="1eba2-226">Device management with Intune</span></span>

<span data-ttu-id="1eba2-227">등록된 장치와 장치 및 앱 설정을 포함하는 마이그레이션 전에 현재 Intune 구성을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-227">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="1eba2-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1eba2-228">Windows 10</span></span>

<span data-ttu-id="1eba2-229">Microsoft 365 Business Premium AutoPilot을 Windows 10 Business 설치할 수 있는 Windows 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-229">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="1eba2-230">사용자 라이선스로 마이그레이션할 Microsoft 365 E3 각 사용자 라이선스에는 Windows 10 Enterprise E3가 포함되어 Autopilot을 사용하여 설치할 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-230">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="1eba2-231">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="1eba2-231">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="1eba2-232">장치에 비즈니스용 Microsoft 365 앱 클라이언트가 자동으로 클라이언트의 기능을 사용하기 엔터프라이즈용 Microsoft 365 앱.</span><span class="sxs-lookup"><span data-stu-id="1eba2-232">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="1eba2-233">마이그레이션 후 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba2-233">After migration, you can now use:</span></span>

- <span data-ttu-id="1eba2-234">그룹 정책 지원</span><span class="sxs-lookup"><span data-stu-id="1eba2-234">Group Policy support</span></span>
- <span data-ttu-id="1eba2-235">스프레드시트 비교 및 문의</span><span class="sxs-lookup"><span data-stu-id="1eba2-235">Spreadsheet compare and inquire</span></span>
- <span data-ttu-id="1eba2-236">비즈니스 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="1eba2-236">Business intelligence</span></span>
