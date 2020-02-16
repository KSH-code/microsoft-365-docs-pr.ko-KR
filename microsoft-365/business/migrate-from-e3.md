---
title: Office 365 E3에서 Microsoft 365 Business로 마이그레이션
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: Office 365 E3에서 Microsoft 365 Business로 비즈니스를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: 54320ed60825a28147542094b19761889a70ae9f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065582"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="c41a3-103">Office 365 E3에서 Microsoft 365 Business로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c41a3-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="c41a3-104">Microsoft 365 Business는 최고급 클라우드 기반 생산성 앱과 간단한 장치 관리 및 보안을 결합 하는 소규모 기업에 필요한 모든 것을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="c41a3-105">현재 Office 365 E3 구독을 보유 하 고 있지만 300 명 이상의 직원은 없는 경우 보안 기능을 추가 하기 위해 Microsoft 365 Business로 전환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-105">If you currently have an Office 365 E3 subscription, but don’t have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="c41a3-106">마이그레이션을 쉽게 수행할 수 있습니다. 먼저 라이선스를 전환 하면 현재 구독의 모든 데이터 및 사용자 정보가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="c41a3-107">마이그레이션 후 Microsoft 365 Business에 추가 된 기능을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="c41a3-108">Office 365 E3 및 Microsoft 365 Business의 차이점</span><span class="sxs-lookup"><span data-stu-id="c41a3-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="c41a3-109">이 표에서는 Microsoft 365 Business 및 Office 365 E3의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="c41a3-110">기능</span><span class="sxs-lookup"><span data-stu-id="c41a3-110">Feature</span></span>   | <span data-ttu-id="c41a3-111">Microsoft 365 Business의 지원</span><span class="sxs-lookup"><span data-stu-id="c41a3-111">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="c41a3-112">Office 365 E3의 지원</span><span class="sxs-lookup"><span data-stu-id="c41a3-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="c41a3-113">**온-프레미스**</span><span class="sxs-lookup"><span data-stu-id="c41a3-113">**On-premises**</span></span>       | | | 
| <span data-ttu-id="c41a3-114">Office 앱<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c41a3-114">Office apps<sup>1</sup></span></span>   | <span data-ttu-id="c41a3-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="c41a3-115">Office 365 Business</span></span>   | <span data-ttu-id="c41a3-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="c41a3-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="c41a3-117">**클라우드 생산성 앱**</span><span class="sxs-lookup"><span data-stu-id="c41a3-117">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="c41a3-118">Exchange Online 및 Outlook</span><span class="sxs-lookup"><span data-stu-id="c41a3-118">Exchange Online and Outlook</span></span>   | <span data-ttu-id="c41a3-119">사서함 당 50 GB 저장소 제한 및 무제한 Exchange 온라인 보관</span><span class="sxs-lookup"><span data-stu-id="c41a3-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>   | <span data-ttu-id="c41a3-120">사서함 당 100 GB 저장소 제한 및 무제한 Exchange 온라인 보관</span><span class="sxs-lookup"><span data-stu-id="c41a3-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="c41a3-121">Teams</span><span class="sxs-lookup"><span data-stu-id="c41a3-121">Teams</span></span> | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | ![Office 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="c41a3-124">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="c41a3-124">OneDrive for Business</span></span> | <span data-ttu-id="c41a3-125">사용자 당 1TB 저장소 제한</span><span class="sxs-lookup"><span data-stu-id="c41a3-125">1 TB storage limit per user</span></span>   | <span data-ttu-id="c41a3-126">무제한</span><span class="sxs-lookup"><span data-stu-id="c41a3-126">Unlimited</span></span> | 
| <span data-ttu-id="c41a3-127">Yammer, SharePoint Online, Planner, 스트림</span><span class="sxs-lookup"><span data-stu-id="c41a3-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | ![Office 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="c41a3-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="c41a3-130">StaffHub</span></span>  | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | ![Office 365 E3에 포함](../media/check-mark.png) | 
| <span data-ttu-id="c41a3-133">Outlook 고객 관리자, MileIQ</span><span class="sxs-lookup"><span data-stu-id="c41a3-133">Outlook Customer Manager, MileIQ</span></span>  | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | | 
| <span data-ttu-id="c41a3-135">**위협 방지**</span><span class="sxs-lookup"><span data-stu-id="c41a3-135">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="c41a3-136">Office 365 ATP (Advanced Threat Protection) 계획 1</span><span class="sxs-lookup"><span data-stu-id="c41a3-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Microsoft 365 Business에 포함](../media/check-mark.png) | <span data-ttu-id="c41a3-138">포함 되지 않지만 추가할 수 있음</span><span class="sxs-lookup"><span data-stu-id="c41a3-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="c41a3-139">**Id 관리**</span><span class="sxs-lookup"><span data-stu-id="c41a3-139">**Identity management**</span></span>       | | | 
| <span data-ttu-id="c41a3-140">하이브리드 Azure Active Directory에 대 한 셀프 서비스 암호 재설정 (Azure AD) 계정, Azure MFA (다단계 인증), 조건부 액세스, 온-프레미스 id에 대 한 암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="c41a3-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Microsoft 365 Business에 포함](../media/check-mark.png)    |  | 
| <span data-ttu-id="c41a3-142">**장치 및 앱 관리**</span><span class="sxs-lookup"><span data-stu-id="c41a3-142">**Device and app management**</span></span>     | | |
| <span data-ttu-id="c41a3-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="c41a3-143">Microsoft Intune, Windows AutoPilot</span></span>|  ![Microsoft 365 Business에 포함](../media/check-mark.png)    |  |
| <span data-ttu-id="c41a3-145">공유 컴퓨터 활성화</span><span class="sxs-lookup"><span data-stu-id="c41a3-145">Shared computer activation</span></span>|   ![Microsoft 365 Business에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png)| 
| <span data-ttu-id="c41a3-148">Win 7/8.1 Pro 라이선스에서 Windows 10 Pro로의 업그레이드 권한</span><span class="sxs-lookup"><span data-stu-id="c41a3-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Microsoft 365 Business에 포함](../media/check-mark.png)    || 
| <span data-ttu-id="c41a3-150">**정보 보호**</span><span class="sxs-lookup"><span data-stu-id="c41a3-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="c41a3-151">Office 365 데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="c41a3-151">Office 365 Data Loss Prevention</span></span>|   ![Microsoft 365 Business에 포함](../media/check-mark.png)|![Office 365 E3에 포함](../media/check-mark.png)|
|<span data-ttu-id="c41a3-154">Azure Information Protection 계획 1, Bitlocker 적용</span><span class="sxs-lookup"><span data-stu-id="c41a3-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Microsoft 365 Business에 포함](../media/check-mark.png)||
|<span data-ttu-id="c41a3-156">Azure Information Protection 계획 1, 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="c41a3-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Microsoft 365 Business에 포함](../media/check-mark.png)||
|<span data-ttu-id="c41a3-158">**클라이언트 액세스 라이선스 (CAL 권한)**</span><span class="sxs-lookup"><span data-stu-id="c41a3-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="c41a3-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="c41a3-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Office 365 E3에 포함](../media/check-mark.png)|

<span data-ttu-id="c41a3-161"><sup>1</sup> Office 앱의 Microsoft 365 Business 버전에는 그룹 정책, 앱 원격 분석, 업데이트 컨트롤, 스프레드시트 비교 및 조회, 비즈니스 인텔리전스를 통한 볼륨 정품 인증이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="c41a3-162">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c41a3-162">Migration</span></span>

<span data-ttu-id="c41a3-163">구독을 마이그레이션하려면 소수의 사용자만 Microsoft 365 Business로 이동 하려는 경우 지침을 위해 [다른 요금제로 전환을](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c41a3-163">To migrate your subscription, see [switch to a different plan manually](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="c41a3-164">[모든 사용자를 자동으로 업그레이드](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)하거나 파트너와 함께 작업 하 여 E3 구독 및 라이선스를 Microsoft 365 비즈니스 구독으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-164">You can also [upgrade everyone automatically](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), or work with partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="c41a3-165">다음 섹션에서는 마이그레이션 후 수행 해야 하는 작업 및 변경 내용에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="c41a3-166">Office 365 E3 구독 구성 및 데이터</span><span class="sxs-lookup"><span data-stu-id="c41a3-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="c41a3-167">다음을 포함 하 여 마이그레이션하기 전에 현재 구독 또는 데이터를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-167">You don’t need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="c41a3-168">구독 구성 (예: DNS 레코드 및 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="c41a3-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="c41a3-169">사용자 및 그룹 계정 및 인증 설정 (예: 다단계 인증 또는 조건부 액세스 정책)</span><span class="sxs-lookup"><span data-stu-id="c41a3-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="c41a3-170">팀, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더, OneNote 전자 필기장 등의 생산성 서비스 구성 및 데이터</span><span class="sxs-lookup"><span data-stu-id="c41a3-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="c41a3-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c41a3-171">Windows 10</span></span>

<span data-ttu-id="c41a3-172">Windows Pro Creator update가 아직 없는 경우 windows [Pro 크리에이터 업데이트로 업그레이드](upgrade-to-windows-pro-creators-update.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="c41a3-173">사용자 장치 및 파일을 보호 하기 위한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="c41a3-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="c41a3-174">Office 365 MDM 정책 및 장치를 설정 하는 경우 해당 장치가 Microsoft 365 관리 센터의 **장치** 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c41a3-175">설정 하는 모든 정책은 [Intune 포털](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)의 클래식 정책 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="c41a3-176">Microsoft 365 Business에 대 한 라이선스를 할당 한 후에는 사용자의 장치 및 파일을 보호 하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="c41a3-177">조직의 모든 사용자를 Microsoft 365 Business로 업그레이드 한 경우 홈 페이지에 설치 마법사가 표시 되 고 [설치 마법사의 Microsoft 365 Business 설정 단계에](set-up.md) 따라 파일 및 모바일 장치를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="c41a3-178">장치 페이지에서 다음 단계를 완료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="c41a3-179">관리 센터의 왼쪽 탐색 창에서 **장치** \> **정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="c41a3-180">**장치 정책** 페이지에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="c41a3-181">정책 **추가** 창에서 정책에 이름을 지정 하 고 드롭다운에서 **정책 유형을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="c41a3-182">Windows 10과 함께 Android 및 iPhone 장치에서 파일을 보호 하기 위한 응용 프로그램 정책을 설정 하 고 Windows 10 장치를 소유한 회사에 대 한 장치 구성 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="c41a3-183">자세한 내용은 다음 링크를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c41a3-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="c41a3-184">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="c41a3-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="c41a3-185">Windows 10 장치에서 응용 프로그램 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="c41a3-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="c41a3-186">Windows 10 Pc에 대 한 장치 보호 설정 설정</span><span class="sxs-lookup"><span data-stu-id="c41a3-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="c41a3-187">정책을 설정 하면 사용자와 직원이 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="c41a3-188">Windows 장치에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위해 windows 장치 설정을](set-up-windows-devices.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c41a3-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="c41a3-189">Android 휴대폰 및 Iphone에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위한 모바일 장치 설정을](set-up-mobile-devices.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c41a3-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="c41a3-190">위협 방지</span><span class="sxs-lookup"><span data-stu-id="c41a3-190">Threat protection</span></span>

<span data-ttu-id="c41a3-191">Microsoft 365 Business로 마이그레이션한 후 Office 365 ATP가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c41a3-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="c41a3-192">개요는 [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c41a3-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="c41a3-193">설정 하려면 [atp 안전한 링크 설정](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [atp 안전한 첨부 파일 설정](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)및 [atp 피싱 방지 설정을](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c41a3-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="c41a3-194">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="c41a3-194">Sensitivity labels</span></span>

<span data-ttu-id="c41a3-195">민감도 레이블 사용을 시작 하려면 [민감도 레이블 개요](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 및 [create and manage 민감도 레이블](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) 비디오를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c41a3-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
