---
title: Office 365 E3에서 Microsoft 365 Business로 마이그레이션
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Office 365 E3에서 Microsoft 365 Business Premium으로 비즈니스를 이동하는 방법을 학습합니다.
ms.openlocfilehash: ffb82fa40f05383260ac1b97ed0bdf5f2f30c1df
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578330"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="ddccf-103">Office 365 E3에서 Microsoft 365 Business Premium으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ddccf-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="ddccf-104">Microsoft 365 Business Premium에는 동급 최고의 클라우드 기반 생산성 앱을 간단한 장치 관리 및 보안과 결합하여 중소기업에 필요한 모든 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="ddccf-105">현재 Office 365 E3 구독이 있지만 직원이 300명을 넘지 않는 경우 추가 보안 기능을 위해 Microsoft 365 Business Premium으로 전환하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="ddccf-106">마이그레이션은 간단합니다. 먼저 라이선스를 전환하면 현재 구독의 모든 데이터 및 사용자 정보가 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="ddccf-107">마이그레이션 후 Microsoft 365 Business Premium에 추가된 기능을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="ddccf-108">Office 365 E3와 Microsoft 365 Business Premium의 차이점</span><span class="sxs-lookup"><span data-stu-id="ddccf-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="ddccf-109">이 표에서는 Microsoft 365 Business Premium과 Office 365 E3의 차이점을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="ddccf-110">기능</span><span class="sxs-lookup"><span data-stu-id="ddccf-110">Feature</span></span>    | <span data-ttu-id="ddccf-111">Microsoft 365 Business Premium의 지원</span><span class="sxs-lookup"><span data-stu-id="ddccf-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="ddccf-112">Office 365 E3의 지원</span><span class="sxs-lookup"><span data-stu-id="ddccf-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="ddccf-113">**On-premises**</span><span class="sxs-lookup"><span data-stu-id="ddccf-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="ddccf-114">Office 앱<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ddccf-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="ddccf-115">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="ddccf-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="ddccf-116">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="ddccf-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="ddccf-117">**클라우드 생산성 앱**</span><span class="sxs-lookup"><span data-stu-id="ddccf-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="ddccf-118">Exchange Online 및 Outlook</span><span class="sxs-lookup"><span data-stu-id="ddccf-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="ddccf-119">사서함당 50GB 저장소 제한 및 제한 없는 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="ddccf-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="ddccf-120">사서함당 100GB 저장소 제한 및 제한 없는 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="ddccf-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="ddccf-121">Teams</span><span class="sxs-lookup"><span data-stu-id="ddccf-121">Teams</span></span>    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="ddccf-124">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="ddccf-124">OneDrive for Business</span></span>    | <span data-ttu-id="ddccf-125">사용자당 1 TB 저장소 제한</span><span class="sxs-lookup"><span data-stu-id="ddccf-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="ddccf-126">무제한</span><span class="sxs-lookup"><span data-stu-id="ddccf-126">Unlimited</span></span> | 
| <span data-ttu-id="ddccf-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="ddccf-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="ddccf-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="ddccf-130">StaffHub</span></span>    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="ddccf-133">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="ddccf-133">Outlook Customer Manager</span></span>    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | | 
| <span data-ttu-id="ddccf-135">**위협 방지**</span><span class="sxs-lookup"><span data-stu-id="ddccf-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="ddccf-136">Office 365용 Defender 플랜 1</span><span class="sxs-lookup"><span data-stu-id="ddccf-136">Defender for Office 365 Plan 1</span></span> | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | <span data-ttu-id="ddccf-138">포함되지 않지만 에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="ddccf-139">**ID 관리**</span><span class="sxs-lookup"><span data-stu-id="ddccf-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="ddccf-140">하이브리드 Azure AD(Azure Active Directory) 계정, Azure AD MFA(다단계 인증), 조건부 액세스,온-프레미스 ID에 대한 암호 쓰기 저장에 대한 셀프 서비스 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="ddccf-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    |  | 
| <span data-ttu-id="ddccf-142">**장치 및 앱 관리**</span><span class="sxs-lookup"><span data-stu-id="ddccf-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="ddccf-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="ddccf-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    |  |
| <span data-ttu-id="ddccf-145">공유 컴퓨터 활성화</span><span class="sxs-lookup"><span data-stu-id="ddccf-145">Shared computer activation</span></span>|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png)| 
| <span data-ttu-id="ddccf-148">Win 7/8.1 Pro 라이선스에서 Windows 10 Pro로 업그레이드 권한</span><span class="sxs-lookup"><span data-stu-id="ddccf-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    || 
| <span data-ttu-id="ddccf-150">**정보 보호**</span><span class="sxs-lookup"><span data-stu-id="ddccf-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="ddccf-151">Office 365 데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="ddccf-151">Office 365 Data Loss Prevention</span></span>|    ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)|![Office 365 E3에 포함](../media/check-mark.png)|
|<span data-ttu-id="ddccf-154">Azure Information Protection 계획 1, Bitlocker 적용</span><span class="sxs-lookup"><span data-stu-id="ddccf-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Microsoft 365 Business Premium에 포함](../media/check-mark.png)||
|<span data-ttu-id="ddccf-156">Azure Information Protection 계획 1, 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ddccf-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Microsoft 365 Business Premium에 포함](../media/check-mark.png)||
|<span data-ttu-id="ddccf-158">**CAL(클라이언트 액세스 라이선스)**</span><span class="sxs-lookup"><span data-stu-id="ddccf-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="ddccf-159">Enterprise CAL Suite(Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="ddccf-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Office 365 E3에 포함](../media/check-mark.png)|

<span data-ttu-id="ddccf-161"><sup>1</sup> Office 앱의 Microsoft 365 Business Premium 버전은 그룹 정책, 앱 원격 분석, 업데이트 컨트롤, 스프레드시트 비교 및 문의 또는 비즈니스 인텔리전스를 통한 볼륨 정품 인증을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="ddccf-162">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ddccf-162">Migration</span></span>

<span data-ttu-id="ddccf-163">구독을 마이그레이션하려면 일부 [](../commerce/subscriptions/change-plans-manually.md) 사용자만 Microsoft 365 Business Premium으로 이동하려는 경우 요금제 수동 변경을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddccf-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="ddccf-164">모든 사람을 [자동으로](../commerce/subscriptions/upgrade-to-different-plan.md)업그레이드하거나 파트너와 협력하여 E3 구독 및 라이선스를 Microsoft 365 Business Premium 구독으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="ddccf-165">다음 섹션에서는 필요한 변경 내용(있는 경우)과 마이그레이션 후 할 수 있는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="ddccf-166">Office 365 E3 구독 구성 및 데이터</span><span class="sxs-lookup"><span data-stu-id="ddccf-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="ddccf-167">마이그레이션하기 전에 다음을 포함하는 현재 구독 또는 데이터를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="ddccf-168">DNS 레코드 및 도메인 이름과 같은 구독 구성</span><span class="sxs-lookup"><span data-stu-id="ddccf-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="ddccf-169">사용자 및 그룹 계정 및 인증 설정(예: 다단계 인증 또는 조건부 액세스 정책)</span><span class="sxs-lookup"><span data-stu-id="ddccf-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="ddccf-170">생산성 서비스 구성 및 해당 데이터(예: Teams, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더 및 OneNote 전자 필기장)</span><span class="sxs-lookup"><span data-stu-id="ddccf-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="ddccf-171">Office 응용 프로그램은 자동으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-171">Office applications will scale automatically.</span></span> <span data-ttu-id="ddccf-172">Office 365 최신 라이선스는 72시간마다 사용자의 라이선스 할당을 확인하고 Office 응용 프로그램을 사용자 구독과 일치하는 버전으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="ddccf-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ddccf-173">Windows 10</span></span>

<span data-ttu-id="ddccf-174">Windows가 Windows Pro 크리에이터 업데이트에 아직 없는 경우 Windows Pro 크리에이터스 업데이트로 [업그레이드합니다.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="ddccf-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="ddccf-175">사용자 장치 및 파일을 보호하기 위한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="ddccf-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="ddccf-176">Office 365 MDM 정책 및 장치를 설정하면 해당 장치가  Microsoft 365 관리 센터의 장치 페이지에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ddccf-177">설정한 모든 정책은 [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)포털의 클래식 정책 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="ddccf-178">Microsoft 365 Business Premium에 라이선스를 할당한 후 사용자의 장치 및 파일 보호를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="ddccf-179">조직의 모든 사람을 Microsoft 365 Business Premium으로 업그레이드한 경우 홈 페이지에 설정 마법사가 표시될 수 있으며 설정 마법사 단계에 따라 [파일](set-up.md) 및 모바일 장치를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="ddccf-180">장치 페이지에서 다음 단계를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="ddccf-181">관리 센터의 왼쪽 네비게이트에서 장치 **정책으로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="ddccf-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="ddccf-182">장치 **정책 페이지에서** 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddccf-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="ddccf-183">정책 **추가 창에서** 정책에 이름을 지정한 다음  드롭다운에서 정책 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="ddccf-184">Windows 10뿐만 아니라 Android 및 iPhone 장치에서 파일을 보호하기 위한 응용 프로그램 정책을 설정할 수 있으며 회사 소유의 Windows 10 장치에 대한 장치 구성 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="ddccf-185">자세한 내용은 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddccf-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="ddccf-186">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="ddccf-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="ddccf-187">Windows 10 장치에서 응용 프로그램 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="ddccf-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="ddccf-188">Windows 10 PC에 대한 장치 보호 설정 설정</span><span class="sxs-lookup"><span data-stu-id="ddccf-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="ddccf-189">정책을 설정하면 사용자와 직원이 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="ddccf-190">Windows 장치에 대한 단계는 [Microsoft 365 Business Premium](set-up-windows-devices.md) 사용자를 위한 Windows 장치 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddccf-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="ddccf-191">Android 휴대폰 및 iPhone에 대한 단계는 [Microsoft 365 Business Premium](set-up-mobile-devices.md) 사용자를 위한 모바일 장치 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddccf-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="ddccf-192">사서함 크기</span><span class="sxs-lookup"><span data-stu-id="ddccf-192">Mailbox Size</span></span>

<span data-ttu-id="ddccf-193">Microsoft 365 Business Premium의 저장소 제한은 50GB로, Exchange Online 계획 1을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="ddccf-194">Microsoft 365 Business Premium으로 마이그레이션하는 동안 사용자가 50GB의 사서함 저장소를 초과하는 경우 이 사용자에게 Exchange Online 계획 2를 할당하고 Exchange Online 계획 1을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="ddccf-195">위협 방지</span><span class="sxs-lookup"><span data-stu-id="ddccf-195">Threat protection</span></span>

<span data-ttu-id="ddccf-196">Microsoft 365 Business Premium으로 마이그레이션한 후 Office 365용 Defender가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddccf-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="ddccf-197">개요는 [Microsoft Defender for Office 365를](../security/office-365-security/defender-for-office-365.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddccf-197">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="ddccf-198">설정하는 내용은 [안전한](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)링크 [설정,](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)안전한 첨부 파일 설정 및 [Office 365용 Defender에서](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)피싱 방지 설정 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddccf-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="ddccf-199">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="ddccf-199">Sensitivity labels</span></span>

<span data-ttu-id="ddccf-200">민감도 레이블 사용을 시작하기 위해 민감도 레이블 개요를 [참조하고](../compliance/sensitivity-labels.md) 민감도 레이블 비디오를 만들고 [관리하세요.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="ddccf-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
