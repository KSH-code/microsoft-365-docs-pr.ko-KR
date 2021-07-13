---
title: 비즈니스용 Microsoft 365 Office 365 E3 마이그레이션
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: 구독이 Office 365 E3 직원 수가 300명을 넘지 않는 경우 전환을 Microsoft 365 Business Premium.
ms.openlocfilehash: c1b4da07b3bf28cce1a48424ab45cde6ea54d367
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394174"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="3c234-103">마이그레이션에서 Office 365 E3 Microsoft 365 Business Premium 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3c234-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="3c234-104">Microsoft 365 Business Premium 중소기업에 필요한 모든 것을 사용하여 동급 최고의 클라우드 기반 생산성 앱을 간단한 장치 관리 및 보안과 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="3c234-105">현재 Office 365 E3 구독이 있지만 직원 수가 300명을 넘지 않는 경우 추가된 보안 기능을 위해 Microsoft 365 Business Premium 전환하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="3c234-106">마이그레이션은 간단합니다. 먼저 라이선스를 전환하면 현재 구독의 모든 데이터 및 사용자 정보가 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="3c234-107">마이그레이션 후 마이그레이션 후 마이그레이션에 추가된 기능을 설정해야 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3c234-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="3c234-108">Office 365 E3 및 Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3c234-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="3c234-109">다음 표에서는 두 가지 Microsoft 365 Business Premium 차이점을 Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="3c234-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="3c234-110">기능</span><span class="sxs-lookup"><span data-stu-id="3c234-110">Feature</span></span>    | <span data-ttu-id="3c234-111">지원 Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3c234-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="3c234-112">지원 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="3c234-112">Support in Office 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="3c234-113">**온-프레미스**</span><span class="sxs-lookup"><span data-stu-id="3c234-113">**On-premises**</span></span>        | | |
| <span data-ttu-id="3c234-114">Office 앱<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3c234-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="3c234-115">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="3c234-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="3c234-116">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="3c234-116">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="3c234-117">**클라우드 생산성 앱**</span><span class="sxs-lookup"><span data-stu-id="3c234-117">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="3c234-118">Exchange Online Outlook</span><span class="sxs-lookup"><span data-stu-id="3c234-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="3c234-119">사서함당 50GB 저장소 제한 및 제한 없는 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="3c234-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="3c234-120">사서함당 100GB 저장소 제한 및 제한 없는 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="3c234-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> |
| <span data-ttu-id="3c234-121">Teams</span><span class="sxs-lookup"><span data-stu-id="3c234-121">Teams</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="3c234-124">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="3c234-124">OneDrive for Business</span></span>    | <span data-ttu-id="3c234-125">사용자당 1 TB 저장소 제한</span><span class="sxs-lookup"><span data-stu-id="3c234-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="3c234-126">무제한</span><span class="sxs-lookup"><span data-stu-id="3c234-126">Unlimited</span></span> | 
| <span data-ttu-id="3c234-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="3c234-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="3c234-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="3c234-130">StaffHub</span></span>    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Office 365 E3](../media/check-mark.png) |
| <span data-ttu-id="3c234-133">**위협 방지**</span><span class="sxs-lookup"><span data-stu-id="3c234-133">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="3c234-134">Office 365용 Defender 플랜 1</span><span class="sxs-lookup"><span data-stu-id="3c234-134">Defender for Office 365 Plan 1</span></span> | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="3c234-136">포함되지 않지만 에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-136">Not included, but can be added on</span></span> |
| <span data-ttu-id="3c234-137">**ID 관리**</span><span class="sxs-lookup"><span data-stu-id="3c234-137">**Identity management**</span></span>        | | |
| <span data-ttu-id="3c234-138">하이브리드 AZURE ACTIVE DIRECTORY(Azure AD) 계정, Azure AD MFA(다단계 인증), 조건부 액세스,온-프레미스 ID에 대한 암호 쓰기 저장에 대한 셀프 서비스 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="3c234-138">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="3c234-140">**장치 및 앱 관리**</span><span class="sxs-lookup"><span data-stu-id="3c234-140">**Device and app management**</span></span>        | | |
| <span data-ttu-id="3c234-141">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="3c234-141">Microsoft Intune, Windows AutoPilot</span></span>|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="3c234-143">공유 컴퓨터 활성화</span><span class="sxs-lookup"><span data-stu-id="3c234-143">Shared computer activation</span></span>|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="3c234-146">Win 7/Windows 10 Pro 8.1 라이선스에서 업그레이드 Pro 권한</span><span class="sxs-lookup"><span data-stu-id="3c234-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    ||
| <span data-ttu-id="3c234-148">**정보 보호**</span><span class="sxs-lookup"><span data-stu-id="3c234-148">**Information protection**</span></span>        | | |
|<span data-ttu-id="3c234-149">Office 365 데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="3c234-149">Office 365 Data Loss Prevention</span></span>|    ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)|![포함된 Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="3c234-152">Azure Information Protection 계획 1, BitLocker 적용</span><span class="sxs-lookup"><span data-stu-id="3c234-152">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![포함된 Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="3c234-154">Azure Information Protection 계획 1, 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="3c234-154">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![포함된 Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="3c234-156">**CAL(클라이언트 액세스 라이선스)**</span><span class="sxs-lookup"><span data-stu-id="3c234-156">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="3c234-157">Enterprise CAL 제품군(Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="3c234-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![포함된 Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="3c234-159"><sup>1</sup> Microsoft 365 Business Premium 버전의 Office 앱의 경우 그룹 정책, 앱 원격 분석, 업데이트 컨트롤, 스프레드시트 비교 및 문의 또는 비즈니스 인텔리전스를 통한 볼륨 정품 인증을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-159"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="3c234-160">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3c234-160">Migration</span></span>

<span data-ttu-id="3c234-161">구독을 마이그레이션하려면 일부 [](../commerce/subscriptions/change-plans-manually.md) 사용자만 구독할 수 있도록 이동하려는 경우 수동으로 요금제 변경을 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3c234-161">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="3c234-162">모든 사람을 [자동으로](../commerce/subscriptions/upgrade-to-different-plan.md)업그레이드하거나 파트너와 협력하여 E3 구독 및 라이선스를 모든 구독으로 Microsoft 365 Business Premium 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-162">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="3c234-163">다음 섹션에서는 필요한 변경 내용(있는 경우)과 마이그레이션 후 할 수 있는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-163">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="3c234-164">Office 365 E3 구성 및 데이터 관리</span><span class="sxs-lookup"><span data-stu-id="3c234-164">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="3c234-165">마이그레이션하기 전에 다음을 포함하는 현재 구독 또는 데이터를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-165">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="3c234-166">DNS 레코드 및 도메인 이름과 같은 구독 구성</span><span class="sxs-lookup"><span data-stu-id="3c234-166">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="3c234-167">사용자 및 그룹 계정 및 인증 설정(예: 다단계 인증 또는 조건부 액세스 정책)</span><span class="sxs-lookup"><span data-stu-id="3c234-167">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="3c234-168">생산성 서비스 구성 및 데이터(예: Teams, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더 및 전자 필기장 OneNote).</span><span class="sxs-lookup"><span data-stu-id="3c234-168">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="3c234-169">Office 자동으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-169">Office applications will scale automatically.</span></span> <span data-ttu-id="3c234-170">Office 365 최신 라이선스는 72시간마다 사용자의 라이선스 할당을 확인하고 Office 응용 프로그램을 사용자 구독과 일치하는 버전으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-170">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="3c234-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3c234-171">Windows 10</span></span>

<span data-ttu-id="3c234-172">크리에이터 Windows 아직 Windows Pro 없는 경우 크리에이터스 업데이트로 Windows Pro [업그레이드합니다.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="3c234-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="3c234-173">사용자 장치 및 파일을 보호하기 위한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3c234-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="3c234-174">MDM Office 365 장치를 설정하면 해당 디바이스가 MDM 정책  및 디바이스의 장치 페이지에 Microsoft 365 관리 센터.</span><span class="sxs-lookup"><span data-stu-id="3c234-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3c234-175">설정한 모든 정책은 [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)포털의 클래식 정책 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="3c234-176">사용자에게 라이선스를 할당한 Microsoft 365 Business Premium 사용자의 장치 및 파일 보호를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-176">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="3c234-177">조직의 모든 사람을 업그레이드한 Microsoft 365 Business Premium 홈 페이지에 설치 마법사가 표시될 수 있으며, 설정 [](set-up.md) 마법사 단계의 Microsoft 365 Business Premium 설정 단계를 따라 파일 및 모바일 장치를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-177">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="3c234-178">장치 페이지에서 다음 단계를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="3c234-179">관리 센터의 왼쪽 네비게이트에서 장치 **정책으로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="3c234-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="3c234-180">장치 **정책 페이지에서** 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c234-180">On the **Device policies** page, choose **Add**.</span></span>

3. <span data-ttu-id="3c234-181">정책 **추가 창에서** 정책에 이름을 지정한 다음  드롭다운에서 정책 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span>

     <span data-ttu-id="3c234-182">Android 및 iPhone 디바이스에서 파일을 보호하기 위한 응용 프로그램 정책을 설정할 수 Windows 10 회사 소유의 Windows 10 장치 구성 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="3c234-183">자세한 내용은 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c234-183">See the following links for details:</span></span>

  - [<span data-ttu-id="3c234-184">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="3c234-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

  - [<span data-ttu-id="3c234-185">Windows 10 장치에서 응용 프로그램 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="3c234-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

  - [<span data-ttu-id="3c234-186">PC의 장치 보호 Windows 10 설정</span><span class="sxs-lookup"><span data-stu-id="3c234-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="3c234-187">정책을 설정하면 사용자와 직원이 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-187">Once you set up policies, you and your employees can set up devices:</span></span>

  - <span data-ttu-id="3c234-188">Windows 대한 단계는 [Microsoft 365 Business Premium 사용자에](set-up-windows-devices.md) 대한 Windows 장치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c234-188">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 

  - <span data-ttu-id="3c234-189">Android 휴대폰 및 [iPhone에 Microsoft 365 Business Premium](set-up-mobile-devices.md) 사용자에 대한 모바일 장치 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c234-189">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="3c234-190">사서함 크기</span><span class="sxs-lookup"><span data-stu-id="3c234-190">Mailbox Size</span></span>

<span data-ttu-id="3c234-191">Microsoft 365 Business Premium 계획 1을 사용할 때 50GB의 Exchange Online 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-191">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="3c234-192">Microsoft 365 Business Premium 마이그레이션하는 동안 사용자가 50GB의 사서함 저장소를 초과하는 경우 이 사용자에게 Exchange Online Plan 2를 할당하고 Exchange Online Plan 1을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3c234-192">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>

### <a name="threat-protection"></a><span data-ttu-id="3c234-193">위협 방지</span><span class="sxs-lookup"><span data-stu-id="3c234-193">Threat protection</span></span>

<span data-ttu-id="3c234-194">마이그레이션 후 Microsoft 365 Business Premium 대한 Defender가 Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c234-194">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="3c234-195">개요는 [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c234-195">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="3c234-196">설정하는 내용은 금고 링크 [설정,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)금고 첨부 파일 설정 [및](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)에 대한 [Defender에서](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)피싱 방지 Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c234-196">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="3c234-197">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="3c234-197">Sensitivity labels</span></span>

<span data-ttu-id="3c234-198">민감도 레이블 사용을 시작하기 위해 민감도 레이블 개요를 [참조하고](../compliance/sensitivity-labels.md) 민감도 레이블 비디오를 만들고 [관리하세요.](../business-video/create-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="3c234-198">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>

## <a name="related-content"></a><span data-ttu-id="3c234-199">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="3c234-199">Related content</span></span>

<span data-ttu-id="3c234-200">[수동으로 계획](../commerce/subscriptions/change-plans-manually.md) 변경(문서)</span><span class="sxs-lookup"><span data-stu-id="3c234-200">[Change plans manually](../commerce/subscriptions/change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="3c234-201">[Windows 장치를 Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) 업그레이드(동영상)</span><span class="sxs-lookup"><span data-stu-id="3c234-201">[Upgrade Windows devices to Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span></span>\
<span data-ttu-id="3c234-202">[Android 또는 iOS 장치에](app-protection-settings-for-android-and-ios.md) 대한 앱 보호 설정 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="3c234-202">[Set app protection settings for Android or iOS devices](app-protection-settings-for-android-and-ios.md) (article)</span></span>\
<span data-ttu-id="3c234-203">[Windows 10 장치에](protection-settings-for-windows-10-devices.md) 대한 응용 프로그램 보호 설정 또는 편집(문서)</span><span class="sxs-lookup"><span data-stu-id="3c234-203">[Set or edit application protection settings for Windows 10 devices](protection-settings-for-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="3c234-204">[]</span><span class="sxs-lookup"><span data-stu-id="3c234-204">[]</span></span>

