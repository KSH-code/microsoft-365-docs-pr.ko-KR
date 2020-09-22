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
description: Microsoft 365 Business Premium에서 Microsoft 365 E3로 비즈니스를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: fbd5c0710bffa92cfc17447094bb9b2683641d5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195522"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="1efed-103">Microsoft 365 Business Premium에서 Microsoft 365 E3로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1efed-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="1efed-104">Microsoft 365 Business Premium에는 소규모 기업에 필요한 모든 것이 있으며, 최상의 클라우드 기반 생산성 앱을 간단한 장치 관리 및 보안과 함께 사용 하 여 직원 들이 최상의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="1efed-105">그러나 경우에 따라 Microsoft 365 Business Premium subscription을 Microsoft 365 E3으로 마이그레이션해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="1efed-106">예를 들어 비즈니스가 성장 했으며 300 개 이상의 라이선스가 필요 합니다 (방식으로 축 하 합니다).</span><span class="sxs-lookup"><span data-stu-id="1efed-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="1efed-107">또는 업무상 Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3 또는 Enterprise Cal (클라이언트 액세스 라이선스)과 같은 enterprise 기능을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="1efed-108">업그레이드는 [관리 센터에서](../commerce/subscriptions/upgrade-to-different-plan.md)업그레이드를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="1efed-109">현재 구독의 모든 데이터와 구성이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="1efed-110">새 기능을 사용 하는 경우를 제외 하 고는 마이그레이션을 준비 하 고 나중에 수행 해야 하는 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="1efed-111">또한 최대 300의 사용자를 위해 Microsoft 365 Business Premium subscription을 사용 하 고, 300 명 보다 더 많은 Microsoft 365 E3 구독을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="1efed-112">그러나 Office 365 ATP는 Microsoft 365 E3에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-112">However, Office 365 ATP is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="1efed-113">계속 해 서 위협 방지를 위해 office 365 ATP 정책 범위에 있는 모든 사용자에 게 라이선스가 있도록 Office 365 ATP 라이선스를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-113">For continued threat protection, you should add additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="1efed-114">Microsoft 365 Business Premium과 Microsoft 365 Enterprise의 차이점</span><span class="sxs-lookup"><span data-stu-id="1efed-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1efed-115">이 표에서는 Microsoft 365 Business Premium과 Microsoft 365 E3 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="1efed-116">기능</span><span class="sxs-lookup"><span data-stu-id="1efed-116">Feature</span></span>    | <span data-ttu-id="1efed-117">Microsoft 365 Business Premium의 지원</span><span class="sxs-lookup"><span data-stu-id="1efed-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="1efed-118">Microsoft 365 E3의 지원</span><span class="sxs-lookup"><span data-stu-id="1efed-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="1efed-119">**온-프레미스**</span><span class="sxs-lookup"><span data-stu-id="1efed-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="1efed-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1efed-120">Windows 10</span></span>    | <span data-ttu-id="1efed-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="1efed-121">Windows 10 Business</span></span>  |     <span data-ttu-id="1efed-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="1efed-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="1efed-123">Office 앱 \*</span><span class="sxs-lookup"><span data-stu-id="1efed-123">Office apps\*</span></span>    | [<span data-ttu-id="1efed-124">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="1efed-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="1efed-125">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="1efed-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="1efed-126">**클라우드 생산성 앱**</span><span class="sxs-lookup"><span data-stu-id="1efed-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="1efed-127">Exchange Online 및 Outlook</span><span class="sxs-lookup"><span data-stu-id="1efed-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="1efed-128">사서함 당 50 GB 저장소 제한 및 무제한 Exchange 온라인 보관</span><span class="sxs-lookup"><span data-stu-id="1efed-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="1efed-129">사서함 당 100 GB 저장소 제한 및 무제한 Exchange 온라인 보관</span><span class="sxs-lookup"><span data-stu-id="1efed-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="1efed-130">Teams</span><span class="sxs-lookup"><span data-stu-id="1efed-130">Teams</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-133">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="1efed-133">OneDrive for Business</span></span>    | <span data-ttu-id="1efed-134">사용자 당 1TB 저장소 제한</span><span class="sxs-lookup"><span data-stu-id="1efed-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="1efed-135">무제한</span><span class="sxs-lookup"><span data-stu-id="1efed-135">Unlimited</span></span> | 
| <span data-ttu-id="1efed-136">Yammer, SharePoint Online, Planner, 스트림</span><span class="sxs-lookup"><span data-stu-id="1efed-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-139">Outlook 고객 관리자, MileIQ</span><span class="sxs-lookup"><span data-stu-id="1efed-139">Outlook Customer Manager, MileIQ</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | | 
| <span data-ttu-id="1efed-141">**위협 방지**</span><span class="sxs-lookup"><span data-stu-id="1efed-141">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="1efed-142">공격 표면 축소 기능</span><span class="sxs-lookup"><span data-stu-id="1efed-142">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="1efed-143">이 목록 보기</span><span class="sxs-lookup"><span data-stu-id="1efed-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="1efed-144">Microsoft Edge에 대 한 하드웨어 기반 격리의 엔터프라이즈 관리</span><span class="sxs-lookup"><span data-stu-id="1efed-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="1efed-145">Office 365 ATP (Advanced Threat Protection) 계획 1</span><span class="sxs-lookup"><span data-stu-id="1efed-145">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | <span data-ttu-id="1efed-147">포함 되지 않지만 추가할 수 있음</span><span class="sxs-lookup"><span data-stu-id="1efed-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="1efed-148">**Id 관리**</span><span class="sxs-lookup"><span data-stu-id="1efed-148">**Identity management**</span></span>        | | | 
| <span data-ttu-id="1efed-149">하이브리드 Azure Active Directory에 대 한 셀프 서비스 암호 재설정 (Azure AD) 계정, Azure MFA (다단계 인증), 조건부 액세스, 온-프레미스 id에 대 한 암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="1efed-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-152">Cloud App Discovery, Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="1efed-152">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-154">Azure AD Office 365 앱 SSO (Single Sign-on): 사용자 당 10 개의 앱 (예: Salesforce와 같은 SaaS 응용 프로그램) \*</span><span class="sxs-lookup"><span data-stu-id="1efed-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-157">Azure AD Premium 1 SSO: 제한 없음 (셀프 서비스 앱 통합 서식 파일을 사용 하는 Azure AD 응용 프로그램 프록시 및 비 갤러리 앱을 통한 온-프레미스 앱)</span><span class="sxs-lookup"><span data-stu-id="1efed-157">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-159">**장치 및 앱 관리**</span><span class="sxs-lookup"><span data-stu-id="1efed-159">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="1efed-160">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="1efed-160">Microsoft Intune, Windows Autopilot</span></span>|     ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
|<span data-ttu-id="1efed-163">VDA (가상 데스크톱 액세스)</span><span class="sxs-lookup"><span data-stu-id="1efed-163">Virtual Desktop Access (VDA)</span></span>    |  |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
|<span data-ttu-id="1efed-165">WVD (Windows 가상 데스크톱)</span><span class="sxs-lookup"><span data-stu-id="1efed-165">Windows Virtual Desktop (WVD)</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png) |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
|<span data-ttu-id="1efed-168">SCA (공유 컴퓨터 활성화)</span><span class="sxs-lookup"><span data-stu-id="1efed-168">Shared Computer Activation (SCA)</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png) |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-171">Microsoft 데스크톱 최적화 패키지</span><span class="sxs-lookup"><span data-stu-id="1efed-171">Microsoft Desktop Optimization Package</span></span>    | |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-173">**정보 보호**</span><span class="sxs-lookup"><span data-stu-id="1efed-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="1efed-174">Office 365 데이터 손실 방지, Azure Information Protection 계획 1</span><span class="sxs-lookup"><span data-stu-id="1efed-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-177">끝점 DLP에 대 한 창 정보 보호</span><span class="sxs-lookup"><span data-stu-id="1efed-177">Window Information Protection for endpoint DLP</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-180">**클라이언트 액세스 라이선스 (CAL 권한)**</span><span class="sxs-lookup"><span data-stu-id="1efed-180">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="1efed-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="1efed-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-183">**규정 준수**</span><span class="sxs-lookup"><span data-stu-id="1efed-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="1efed-184">무제한 전자 메일 보관</span><span class="sxs-lookup"><span data-stu-id="1efed-184">Unlimited email archiving</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-187">규정 관리자</span><span class="sxs-lookup"><span data-stu-id="1efed-187">Compliance Manager</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-190">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1efed-190">eDiscovery</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-193">원본 위치 유지 및 소송 보존</span><span class="sxs-lookup"><span data-stu-id="1efed-193">In-place hold and litigation hold</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="1efed-196">MRM (메시징 레코드 관리) 보존 태그 및 보존 정책</span><span class="sxs-lookup"><span data-stu-id="1efed-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Microsoft 365 Business Premium에 포함 된 내용](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
||||

<span data-ttu-id="1efed-199">\* SaaS 앱에 대 한 액세스 권한이 할당 된 사용자는 최대 10 개의 앱에 대 한 SSO 액세스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="1efed-200">관리자는 SSO를 구성 하 고 다른 SaaS 앱에 대 한 사용자 액세스를 변경할 수 있지만 SSO 액세스는 사용자 당 10 개의 앱에 한 번에 하나씩만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="1efed-201">모든 Office 365 앱은 단일 앱으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="1efed-202">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1efed-202">Migration</span></span>

<span data-ttu-id="1efed-203">마이그레이션하기 위해 파트너와 협력 하 여 Microsoft 365 Business Premium 구독 및 라이선스를 해당 라이선스와 함께 적절 한 Microsoft 365 E3 구독으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-203">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="1efed-204">다음 섹션에서는 마이그레이션 후에 수행 해야 하는 작업 및 변경 내용에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="1efed-205">Microsoft 365 구독 구성 및 데이터</span><span class="sxs-lookup"><span data-stu-id="1efed-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="1efed-206">마이그레이션을 수행 하기 전에 다음을 비롯 하 여 현재 구독 또는 데이터를 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-206">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="1efed-207">구독 구성 (예: DNS 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="1efed-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="1efed-208">사용자 및 그룹 계정 및 인증 설정 (예: 다단계 인증 또는 조건부 액세스 정책)</span><span class="sxs-lookup"><span data-stu-id="1efed-208">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="1efed-209">팀, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더, OneNote 전자 필기장 등의 생산성 서비스 구성 및 데이터</span><span class="sxs-lookup"><span data-stu-id="1efed-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="1efed-210">이제 사용자는 Exchange Online 사서함 및 비즈니스용 OneDrive 폴더에 무제한 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="1efed-211">앱을 10 개 넘게 사용 하려면 Cloud App Discovery, Azure AD Connect Health 및 SSO를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="1efed-212">Microsoft 365 E3으로 마이그레이션된 사용자는 더 이상 Outlook 고객 관리자 및 MileIQ를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-212">Users migrated to Microsoft 365 E3 can no longer use Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="1efed-213">위협 방지</span><span class="sxs-lookup"><span data-stu-id="1efed-213">Threat protection</span></span>

<span data-ttu-id="1efed-214">Windows 10 Business에는 다음과 같은 보호 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="1efed-215">운영 체제 부팅 프로세스의 무결성 적용</span><span class="sxs-lookup"><span data-stu-id="1efed-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="1efed-216">중요 한 운영 구성 요소의 무결성 적용</span><span class="sxs-lookup"><span data-stu-id="1efed-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="1efed-217">Advanced 취약성 및 제로 일 악용 완화</span><span class="sxs-lookup"><span data-stu-id="1efed-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="1efed-218">Microsoft Edge, Internet Explorer 및 Chrome에 대 한 신뢰도 기반 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="1efed-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="1efed-219">호스트 기반 방화벽</span><span class="sxs-lookup"><span data-stu-id="1efed-219">Host-based firewall</span></span>
- <span data-ttu-id="1efed-220">랜 섬 웨어 완화</span><span class="sxs-lookup"><span data-stu-id="1efed-220">Ransomware mitigations</span></span>
- <span data-ttu-id="1efed-221">Microsoft Edge에 대 한 하드웨어 기반 격리</span><span class="sxs-lookup"><span data-stu-id="1efed-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="1efed-222">지능형 보안 그래프로 인해 응용 프로그램 제어</span><span class="sxs-lookup"><span data-stu-id="1efed-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="1efed-223">장치 컨트롤 (USB)</span><span class="sxs-lookup"><span data-stu-id="1efed-223">Device control (USB)</span></span>
- <span data-ttu-id="1efed-224">웹 기반 위협에 대 한 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="1efed-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="1efed-225">호스트 침입 방지 규칙</span><span class="sxs-lookup"><span data-stu-id="1efed-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="1efed-226">Windows 10 Enterprise e 3에는 Microsoft Edge에 대 한 하드웨어 기반 격리의 엔터프라이즈 관리도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="1efed-227">Microsoft 365 E3로 마이그레이션된 사용자에 게는 계속 해 서 위협 방지를 위해 Office 365 ATP 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-227">Users migrated to Microsoft 365 E3 will each require an Office 365 ATP license for continued threat protection.</span></span> <span data-ttu-id="1efed-228">Office 365 ATP 정책 범위에 있는 모든 사용자에 게 라이선스가 있도록 추가 Office 365 ATP 라이선스를 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-228">Be sure to purchase additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="1efed-229">Intune을 사용한 장치 관리</span><span class="sxs-lookup"><span data-stu-id="1efed-229">Device management with Intune</span></span>

<span data-ttu-id="1efed-230">마이그레이션 전에 현재 Intune 구성을 변경할 필요가 없습니다 (등록 된 장치 및 장치 및 앱 설정 포함).</span><span class="sxs-lookup"><span data-stu-id="1efed-230">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="1efed-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1efed-231">Windows 10</span></span>

<span data-ttu-id="1efed-232">Microsoft 365 Business Premium에는 windows AutoPilot를 사용 하 여 설치할 수 있는 Windows 10 Business가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-232">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="1efed-233">Microsoft 365 E3로 마이그레이션하는 경우 각 사용자 라이선스에는 windows Autopilot를 사용 하 여 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="1efed-234">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="1efed-234">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="1efed-235">장치에 설치 된 Microsoft 365 Apps for business 클라이언트는 자동으로 Microsoft 365 앱 for enterprise 기능을 사용 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-235">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="1efed-236">마이그레이션 후에는 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efed-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="1efed-237">그룹 정책을 통한 볼륨 정품 인증</span><span class="sxs-lookup"><span data-stu-id="1efed-237">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="1efed-238">앱 원격 분석</span><span class="sxs-lookup"><span data-stu-id="1efed-238">App telemetry</span></span>
 - <span data-ttu-id="1efed-239">업데이트 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1efed-239">Update controls</span></span>
 - <span data-ttu-id="1efed-240">스프레드시트 비교 및 조회</span><span class="sxs-lookup"><span data-stu-id="1efed-240">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="1efed-241">비즈니스 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="1efed-241">Business intelligence</span></span>

