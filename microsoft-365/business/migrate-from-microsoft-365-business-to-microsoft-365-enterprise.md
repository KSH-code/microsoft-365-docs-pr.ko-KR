---
title: Microsoft 365 Business에서 Microsoft 365 Enterprise로 마이그레이션
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business에서 Microsoft 365 Enterprise e 3로 비즈니스를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: efdf4030a2a638a3fd56d1c415fcc6e6ac261c1a
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772725"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a><span data-ttu-id="3e2a3-103">Microsoft 365 Business에서 Microsoft 365 Enterprise e 3로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3e2a3-103">Migrate from Microsoft 365 Business to Microsoft 365 Enterprise E3</span></span>

<span data-ttu-id="3e2a3-104">Microsoft 365 Business에는 최고의 비즈니스에 필요한 모든 것이 있으며, 최상의 클라우드 기반 생산성 앱을 간단한 장치 관리 및 보안과 함께 사용 하 여 직원 들이 최고의 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="3e2a3-105">그러나 경우에 따라 Microsoft 365 비즈니스 구독을 Microsoft 365 Enterprise로 마이그레이션해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="3e2a3-106">예를 들어 비즈니스가 성장 했으며 300 개 이상의 라이선스가 필요 합니다 (방식으로 축 하 합니다).</span><span class="sxs-lookup"><span data-stu-id="3e2a3-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="3e2a3-107">또는 회사에 Office 365 ProPlus, Windows 10 Enterprise E3 또는 엔터프라이즈 Cal (클라이언트 액세스 라이선스)과 같은 enterprise 기능이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="3e2a3-108">마이그레이션은 단순히 라이선스를 전환 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-108">Migrating is easy: Just switch licenses.</span></span> <span data-ttu-id="3e2a3-109">현재 구독의 모든 데이터와 구성이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="3e2a3-110">새 기능을 사용 하는 경우를 제외 하 고는 마이그레이션을 준비 하 고 나중에 수행 해야 하는 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-110">There is nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span> 

>[!Note]
><span data-ttu-id="3e2a3-111">또한 최대 300의 사용자를 위해 Microsoft 365 비즈니스 구독을 사용할 수 있으며, 300 명 보다 더 많은 Microsoft 365 Enterprise E3 구독을 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 Enterprise E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="3e2a3-112">그러나 Office 365 ATP는 Microsoft 365 Enterprise e 3에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-112">However, Office 365 ATP is not included with Microsoft 365 Enterprise E3.</span></span> <span data-ttu-id="3e2a3-113">Microsoft 365 Enterprise E3 구독의 사용자에 대 한 Office 365 ATP 라이선스를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-113">You should add additional Office 365 ATP licenses for the users in your Microsoft 365 Enterprise E3 subscription.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="3e2a3-114">Microsoft 365 비즈니스 및 Microsoft 365 Enterprise의 차이점</span><span class="sxs-lookup"><span data-stu-id="3e2a3-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3e2a3-115">이 표에서는 Microsoft 365 Business 및 Microsoft 365 Enterprise e 3의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 Enterprise E3.</span></span>

| <span data-ttu-id="3e2a3-116">기능</span><span class="sxs-lookup"><span data-stu-id="3e2a3-116">Feature</span></span>   | <span data-ttu-id="3e2a3-117">Microsoft 365 Business의 지원</span><span class="sxs-lookup"><span data-stu-id="3e2a3-117">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="3e2a3-118">Microsoft 365 Enterprise e 3의 지원</span><span class="sxs-lookup"><span data-stu-id="3e2a3-118">Support in Microsoft 365 Enterprise E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="3e2a3-119">**온-프레미스**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-119">**On-premises**</span></span>       | | | 
| <span data-ttu-id="3e2a3-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3e2a3-120">Windows 10</span></span>    | <span data-ttu-id="3e2a3-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="3e2a3-121">Windows 10 Business</span></span>  |    <span data-ttu-id="3e2a3-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="3e2a3-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="3e2a3-123">Office 앱 \*</span><span class="sxs-lookup"><span data-stu-id="3e2a3-123">Office apps\*</span></span>  | [<span data-ttu-id="3e2a3-124">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="3e2a3-124">Office 365 Business</span></span>](#office-365-business)   | <span data-ttu-id="3e2a3-125">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="3e2a3-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="3e2a3-126">**클라우드 생산성 앱**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-126">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="3e2a3-127">Exchange Online 및 Outlook</span><span class="sxs-lookup"><span data-stu-id="3e2a3-127">Exchange Online and Outlook</span></span>   | <span data-ttu-id="3e2a3-128">사서함 당 50 GB 저장소 제한 및 무제한 Exchange 온라인 보관</span><span class="sxs-lookup"><span data-stu-id="3e2a3-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="3e2a3-129">사서함 당 100 GB 저장소 제한 및 무제한 Exchange 온라인 보관</span><span class="sxs-lookup"><span data-stu-id="3e2a3-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="3e2a3-130">Teams</span><span class="sxs-lookup"><span data-stu-id="3e2a3-130">Teams</span></span> | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-133">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="3e2a3-133">OneDrive for Business</span></span> | <span data-ttu-id="3e2a3-134">사용자 당 1TB 저장소 제한</span><span class="sxs-lookup"><span data-stu-id="3e2a3-134">1 TB storage limit per user</span></span>   | <span data-ttu-id="3e2a3-135">무제한</span><span class="sxs-lookup"><span data-stu-id="3e2a3-135">Unlimited</span></span> | 
| <span data-ttu-id="3e2a3-136">Yammer, SharePoint Online, Planner, 스트림</span><span class="sxs-lookup"><span data-stu-id="3e2a3-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-139">StaffHub</span><span class="sxs-lookup"><span data-stu-id="3e2a3-139">StaffHub</span></span>  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-142">Outlook 고객 관리자, MileIQ</span><span class="sxs-lookup"><span data-stu-id="3e2a3-142">Outlook Customer Manager, MileIQ</span></span>  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | | 
| <span data-ttu-id="3e2a3-144">**위협 방지**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-144">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="3e2a3-145">공격 표면 축소 기능</span><span class="sxs-lookup"><span data-stu-id="3e2a3-145">Attack surface reduction capabilities</span></span> | [<span data-ttu-id="3e2a3-146">이 목록 보기</span><span class="sxs-lookup"><span data-stu-id="3e2a3-146">See this list</span></span>](#threat-protection) | <span data-ttu-id="3e2a3-147">Microsoft Edge에 대 한 하드웨어 기반 격리의 엔터프라이즈 관리</span><span class="sxs-lookup"><span data-stu-id="3e2a3-147">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="3e2a3-148">Office 365 ATP (Advanced Threat Protection) 계획 1</span><span class="sxs-lookup"><span data-stu-id="3e2a3-148">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Microsoft 365 Business에 포함](./media/check-mark.png)  | <span data-ttu-id="3e2a3-150">포함 되지 않지만 추가할 수 있음</span><span class="sxs-lookup"><span data-stu-id="3e2a3-150">Not included, but can be added on</span></span> | 
| <span data-ttu-id="3e2a3-151">**Id 관리**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-151">**Identity management**</span></span>       | | | 
| <span data-ttu-id="3e2a3-152">하이브리드 Azure Active Directory에 대 한 셀프 서비스 암호 재설정 (Azure AD) 계정, Azure MFA (다단계 인증), 조건부 액세스, 온-프레미스 id에 대 한 암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="3e2a3-152">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Microsoft 365 Business에 포함](./media/check-mark.png) | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-155">Cloud App Discovery, Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="3e2a3-155">Cloud App Discovery, Azure AD Connect Health</span></span>  |   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-157">Azure AD Office 365 앱 SSO (Single Sign-on): 사용자 당 10 개의 앱 (예: Salesforce와 같은 SaaS 응용 프로그램) \*</span><span class="sxs-lookup"><span data-stu-id="3e2a3-157">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Microsoft 365 Business에 포함](./media/check-mark.png) | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-160">Azure AD Premium 1 SSO: 제한 없음 (셀프 서비스 앱 통합 서식 파일을 사용 하는 Azure AD 응용 프로그램 프록시 및 비 갤러리 앱을 통한 온-프레미스 앱)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-160">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>  |   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-162">**장치 및 앱 관리**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-162">**Device and app management**</span></span>     | | | 
| <span data-ttu-id="3e2a3-163">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="3e2a3-163">Microsoft Intune, Windows Autopilot</span></span>|  ![Microsoft 365 Business에 포함](./media/check-mark.png) | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
|<span data-ttu-id="3e2a3-166">VDA (가상 데스크톱 액세스)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-166">Virtual Desktop Access (VDA)</span></span>   |  |    ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
|<span data-ttu-id="3e2a3-168">WVD (Windows 가상 데스크톱)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-168">Windows Virtual Desktop (WVD)</span></span>  | ![Microsoft 365 Business에 포함](./media/check-mark.png) |     ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
|<span data-ttu-id="3e2a3-171">SCA (공유 컴퓨터 활성화)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-171">Shared Computer Activation (SCA)</span></span>   | ![Microsoft 365 Business에 포함](./media/check-mark.png) |     ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-174">Microsoft 데스크톱 최적화 패키지</span><span class="sxs-lookup"><span data-stu-id="3e2a3-174">Microsoft Desktop Optimization Package</span></span>    | |     ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-176">**정보 보호**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-176">**Information protection**</span></span>        | | | 
| <span data-ttu-id="3e2a3-177">Office 365 데이터 손실 방지, Azure Information Protection 계획 1</span><span class="sxs-lookup"><span data-stu-id="3e2a3-177">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-180">끝점 DLP에 대 한 창 정보 보호</span><span class="sxs-lookup"><span data-stu-id="3e2a3-180">Window Information Protection for endpoint DLP</span></span>    | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-183">**클라이언트 액세스 라이선스 (CAL 권한)**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-183">**Client Access License (CAL rights)**</span></span>    | | |   
| <span data-ttu-id="3e2a3-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span></span>| |        ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-186">**규정 준수**</span><span class="sxs-lookup"><span data-stu-id="3e2a3-186">**Compliance**</span></span>        | | | 
| <span data-ttu-id="3e2a3-187">무제한 전자 메일 보관</span><span class="sxs-lookup"><span data-stu-id="3e2a3-187">Unlimited email archiving</span></span> | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-190">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="3e2a3-190">Compliance Manager</span></span>    | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-193">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3e2a3-193">eDiscovery</span></span>    | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-196">원본 위치 유지 및 소송 보존</span><span class="sxs-lookup"><span data-stu-id="3e2a3-196">In-place hold and litigation hold</span></span> | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
| <span data-ttu-id="3e2a3-199">MRM (메시징 레코드 관리) 보존 태그 및 보존 정책</span><span class="sxs-lookup"><span data-stu-id="3e2a3-199">Messaging Records Management (MRM) retention tags and retention policies</span></span>  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 Enterprise e 3에 포함](./media/check-mark.png) | 
||||

<span data-ttu-id="3e2a3-202">\*SaaS 앱에 대 한 액세스 권한이 할당 된 사용자는 최대 10 개의 앱에 대 한 SSO 액세스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-202">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="3e2a3-203">관리자는 SSO를 구성 하 고 다른 SaaS 앱에 대 한 사용자 액세스를 변경할 수 있지만 SSO 액세스는 사용자 당 10 개의 앱에 한 번에 하나씩만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-203">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="3e2a3-204">모든 Office 365 앱은 단일 앱으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-204">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="3e2a3-205">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3e2a3-205">Migration</span></span>

<span data-ttu-id="3e2a3-206">마이그레이션 하려면 파트너와 협력 하 여 365 Microsoft 365 Enterprise E3 구독을 해당 라이선스와 함께 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-206">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to suitable a Microsoft 365 Enterprise E3 subscription with its licenses.</span></span>

<span data-ttu-id="3e2a3-207">다음 섹션에서는 마이그레이션 후에 수행 해야 하는 작업 및 변경 내용에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-207">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="3e2a3-208">Microsoft 365 구독 구성 및 데이터</span><span class="sxs-lookup"><span data-stu-id="3e2a3-208">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="3e2a3-209">다음과 같은 마이그레이션 전에는 현재 구독 또는 데이터를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-209">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="3e2a3-210">구독 구성 (예: DNS 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-210">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="3e2a3-211">사용자 및 그룹 계정 및 인증 설정 (예: 다단계 인증 또는 조건부 액세스 정책)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-211">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="3e2a3-212">팀, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더, OneNote 전자 필기장 등의 생산성 서비스 구성 및 데이터</span><span class="sxs-lookup"><span data-stu-id="3e2a3-212">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="3e2a3-213">이제 사용자는 Exchange Online 사서함 및 비즈니스용 OneDrive 폴더에 무제한 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-213">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="3e2a3-214">앱을 10 개 넘게 사용 하려면 Cloud App Discovery, Azure AD Connect Health 및 SSO를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-214">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="3e2a3-215">Microsoft 365 Enterprise e 3로 마이그레이션한 후에는 더 이상 Outlook 고객 관리자 및 MileIQ을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-215">After migrating to Microsoft 365 Enterprise E3, you no longer Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="3e2a3-216">위협 방지</span><span class="sxs-lookup"><span data-stu-id="3e2a3-216">Threat protection</span></span>

<span data-ttu-id="3e2a3-217">Windows 10 Business에는 다음과 같은 보호 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-217">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="3e2a3-218">운영 체제 부팅 프로세스의 무결성 적용</span><span class="sxs-lookup"><span data-stu-id="3e2a3-218">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="3e2a3-219">중요 한 운영 구성 요소의 무결성 적용</span><span class="sxs-lookup"><span data-stu-id="3e2a3-219">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="3e2a3-220">Advanced 취약성 및 제로 일 악용 완화</span><span class="sxs-lookup"><span data-stu-id="3e2a3-220">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="3e2a3-221">Microsoft Edge, Internet Explorer 및 Chrome에 대 한 신뢰도 기반 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="3e2a3-221">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="3e2a3-222">호스트 기반 방화벽</span><span class="sxs-lookup"><span data-stu-id="3e2a3-222">Host-based firewall</span></span>
- <span data-ttu-id="3e2a3-223">랜 섬 웨어 완화</span><span class="sxs-lookup"><span data-stu-id="3e2a3-223">Ransomware mitigations</span></span>
- <span data-ttu-id="3e2a3-224">Microsoft Edge에 대 한 하드웨어 기반 격리</span><span class="sxs-lookup"><span data-stu-id="3e2a3-224">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="3e2a3-225">지능형 보안 그래프로 인해 응용 프로그램 제어</span><span class="sxs-lookup"><span data-stu-id="3e2a3-225">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="3e2a3-226">장치 컨트롤 (USB)</span><span class="sxs-lookup"><span data-stu-id="3e2a3-226">Device control (USB)</span></span>
- <span data-ttu-id="3e2a3-227">웹 기반 위협에 대 한 네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="3e2a3-227">Network protection for web-based threats</span></span>
- <span data-ttu-id="3e2a3-228">호스트 침입 방지 규칙</span><span class="sxs-lookup"><span data-stu-id="3e2a3-228">Host intrusion prevention rules</span></span>

<span data-ttu-id="3e2a3-229">Windows 10 Enterprise e 3에는 Microsoft Edge에 대 한 하드웨어 기반 격리의 엔터프라이즈 관리도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-229">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="3e2a3-230">Microsoft 365 Enterprise e 3로 마이그레이션한 후 Office 365 ATP가 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-230">After migrating to Microsoft 365 Enterprise E3, you no longer have Office 365 ATP.</span></span> <span data-ttu-id="3e2a3-231">Microsoft 365 Enterprise E3 구독에 대 한 추가 Office 365 ATP 라이선스를 구매한 다음 사용자 계정에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-231">You can purchase additional Office 365 ATP licenses for your Microsoft 365 Enterprise E3 subscription and assign them to your user accounts.</span></span>
>

### <a name="device-management-with-intune"></a><span data-ttu-id="3e2a3-232">Intune을 사용한 장치 관리</span><span class="sxs-lookup"><span data-stu-id="3e2a3-232">Device management with Intune</span></span>

<span data-ttu-id="3e2a3-233">마이그레이션 전에 현재 Intune 구성을 변경할 필요가 없으며, 등록 된 장치 및 장치 및 앱 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-233">You don’t need to do any changes to your current Intune configuration prior to migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="3e2a3-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3e2a3-234">Windows 10</span></span>

<span data-ttu-id="3e2a3-235">Microsoft 365 Business에는 windows Autopilot를 사용 하 여 설치할 수 있는 Windows 10 Business가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-235">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows Autopilot.</span></span> <span data-ttu-id="3e2a3-236">Microsoft 365 Enterprise e 3로 마이그레이션하는 경우 각 사용자 라이선스에는 windows Autopilot를 사용 하 여 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-236">When you migrate to Microsoft 365 Enterprise E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="3e2a3-237">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="3e2a3-237">Office 365 Business</span></span>

<span data-ttu-id="3e2a3-238">장치에 설치 된 Office 365 Business 클라이언트는 자동으로 Office 365 ProPlus의 기능을 사용 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-238">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="3e2a3-239">마이그레이션 후에는 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e2a3-239">After migration, you can now use:</span></span>

 - <span data-ttu-id="3e2a3-240">그룹 정책을 통한 볼륨 정품 인증</span><span class="sxs-lookup"><span data-stu-id="3e2a3-240">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="3e2a3-241">앱 원격 분석</span><span class="sxs-lookup"><span data-stu-id="3e2a3-241">App telemetry</span></span>
 - <span data-ttu-id="3e2a3-242">업데이트 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3e2a3-242">Update controls</span></span>
 - <span data-ttu-id="3e2a3-243">스프레드시트 비교 및 조회</span><span class="sxs-lookup"><span data-stu-id="3e2a3-243">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="3e2a3-244">비즈니스 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="3e2a3-244">Business intelligence</span></span>

