---
title: 기본 이동성 및 보안 기능
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 이동성 및 보안은 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.
ms.openlocfilehash: a88afd539209d20046a778f8c6d16cadd51b5a9a
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430265"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="b7f16-103">기본 이동성 및 보안 기능</span><span class="sxs-lookup"><span data-stu-id="b7f16-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="b7f16-104">기본 이동성 및 보안은 조직의 라이선스를 받은 Microsoft 365 사용자가 사용 하는 Iphone, Ipad, Androids 및 Windows phone과 같은 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="b7f16-105">지원 되는 모바일 장치 및 앱에 대 한 조직의 Microsoft 365 전자 메일 및 문서에 대 한 액세스를 제어 하는 데 도움이 되는 설정을 사용 하 여 모바일 장치 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="b7f16-106">장치를 분실하거나 도난 당한 경우 장치의 데이터를 원격으로 지워 중요한 조직 정보를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="b7f16-107">지원되는 장치</span><span class="sxs-lookup"><span data-stu-id="b7f16-107">Supported devices</span></span>

<span data-ttu-id="b7f16-108">기본 이동성 및 보안을 사용 하 여 다음 장치를 보호 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="b7f16-109">iOS 11.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="b7f16-109">iOS 11.0 or later versions</span></span>
    
- <span data-ttu-id="b7f16-110">Android 5.0 이상 버전<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b7f16-110">Android 5.0 or later versions<sup>3</sup></span></span>
    
- <span data-ttu-id="b7f16-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b7f16-111">Windows 8.1<sup>1</sup></span></span>
    
- <span data-ttu-id="b7f16-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b7f16-112">Windows 8.1 RT<sup>1</sup></span></span>
    
- <span data-ttu-id="b7f16-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b7f16-113">Windows 10<sup>2</sup></span></span>
    
- <span data-ttu-id="b7f16-114">Windows 10 모바일<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b7f16-114">Windows 10 Mobile<sup>2</sup></span></span>   

<span data-ttu-id="b7f16-115"><sup>1</sup> Windows 8.1 RT 장치에 대 한 액세스 제어는 Exchange ActiveSync로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="b7f16-116"><sup>2</sup> Windows 8.1 RT 장치에 대 한 액세스 제어는 Exchange ActiveSync로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="b7f16-117">Windows 10에 대 한 액세스 제어를 사용 하려면 Azure AD Premium이 포함 된 구독 및 장치를 Azure Active Directory에 가입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="b7f16-118"><sup>3</sup> Windows 8.1 RT 장치에 대 한 액세스 제어는 Exchange ActiveSync로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="b7f16-119">6 월 2020 이후 Android 버전 9 이상이 Samsung Knox 장치를 제외 하 고 암호 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="b7f16-120">이전 버전 OS에서 이미 등록 된 장치는 기능이 통지 없이 변경 될 수 있지만 계속 해 서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="b7f16-121">조직의 사용자가 기본 Mobility and Security에서 지원 하지 않는 모바일 장치를 사용 하는 경우에는 Exchange ActiveSync 앱에 해당 장치에 대 한 Microsoft 365 전자 메일 액세스를 차단 하 여 조직의 데이터를 보다 안전 하 게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="b7f16-122">Exchange ActiveSync를 차단 하는 단계는 [기본 이동성 및 보안에서 장치 액세스 설정 관리](manage-device-access-settings.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7f16-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="b7f16-123">Microsoft 365 전자 메일 및 문서에 대 한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="b7f16-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="b7f16-124">다음 표에 나와 있는 여러 유형의 모바일 장치에 대해 지원 되는 앱은 사용자의 장치에 적용 되는 새 모바일 장치 관리 정책이 있고 사용자가 이전에 장치를 등록 하지 않은 경우에 사용자가 기본 이동성 및 보안에 등록 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="b7f16-125">사용자의 장치가 정책을 준수 하지 않는 경우 정책을 설정 하는 방법에 따라 사용자가 이러한 앱에서 Microsoft 365 리소스에 액세스 하지 못하도록 차단 되거나, Microsoft 365에서 정책 위반을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="b7f16-126">**제품**</span><span class="sxs-lookup"><span data-stu-id="b7f16-126">**Product**</span></span>|<span data-ttu-id="b7f16-127">**iOS 10.0 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="b7f16-128">**Android 5.0 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-129">**Exchange** Exchange ActiveSync에는 Exchange ActiveSync 버전 14.1 이상을 사용 하는 기본 제공 전자 메일 및 타사 앱 (예 TouchDown)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="b7f16-130">메일로</span><span class="sxs-lookup"><span data-stu-id="b7f16-130">Mail</span></span> |<span data-ttu-id="b7f16-131">전자 메일</span><span class="sxs-lookup"><span data-stu-id="b7f16-131">Email</span></span> |
|<span data-ttu-id="b7f16-132">**Office**   및 **비즈니스용 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="b7f16-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="b7f16-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="b7f16-133">Outlook</span></span> </br><span data-ttu-id="b7f16-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b7f16-134">OneDrive</span></span> </br><span data-ttu-id="b7f16-135">Word</span><span class="sxs-lookup"><span data-stu-id="b7f16-135">Word</span></span> </br><span data-ttu-id="b7f16-136">Excel</span><span class="sxs-lookup"><span data-stu-id="b7f16-136">Excel</span></span> </br><span data-ttu-id="b7f16-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b7f16-137">PowerPoint</span></span>|<span data-ttu-id="b7f16-138">**휴대폰 및 태블릿**:</span><span class="sxs-lookup"><span data-stu-id="b7f16-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="b7f16-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="b7f16-139">Outlook</span></span> <br/> <span data-ttu-id="b7f16-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b7f16-140">OneDrive</span></span> <br/> <span data-ttu-id="b7f16-141">Word</span><span class="sxs-lookup"><span data-stu-id="b7f16-141">Word</span></span> <br/> <span data-ttu-id="b7f16-142">Excel</span><span class="sxs-lookup"><span data-stu-id="b7f16-142">Excel</span></span> <br/> <span data-ttu-id="b7f16-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b7f16-143">PowerPoint</span></span> <br/> <span data-ttu-id="b7f16-144">**휴대폰만 해당:**</span><span class="sxs-lookup"><span data-stu-id="b7f16-144">**On phones only:**</span></span> <br/> <span data-ttu-id="b7f16-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="b7f16-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="b7f16-146">IOS 10.0 이상 버전에 대 한 지원에는 iPhone 및 iPad 장치가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="b7f16-147">BlackBerry OS 장치 관리는 Microsoft 365 용 모바일 장치 관리에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-147">Management of BlackBerry OS devices isn’t supported by Mobile Device Management for Microsoft 365.</span></span> <span data-ttu-id="b7f16-148">Blackberry의 BBCS (BlackBerry Business Cloud Services)를 사용 하 여 BlackBerry OS 장치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="b7f16-149">Android OS를 실행 하는 Blackberry 장치는 표준 Android 장치로 지원 됨</span><span class="sxs-lookup"><span data-stu-id="b7f16-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="b7f16-150">사용자가 모바일 브라우저를 사용 하 여 Microsoft 365 SharePoint 사이트, Office Online의 문서 또는 Outlook Web App에서 전자 메일에 액세스 하는 경우 등록 하 라는 메시지가 표시 되지 않으며 차단 되거나 정책 위반으로 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>
    
<span data-ttu-id="b7f16-151">다음 다이어그램에서는 새 장치가 있는 사용자가 기본 이동성 및 보안을 사용 하 여 액세스 제어를 지 원하는 앱에 로그인 할 때 수행 되는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="b7f16-152">사용자가 자신의 장치를 등록할 때까지 앱의 Microsoft 365 리소스에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="기본 모바일 및 보안 액세스 제어":::

<span data-ttu-id="b7f16-154">참고: Microsoft 365 비즈니스 Standard 용 MDM에서 만든 정책 및 액세스 규칙은 exchange 관리 센터에서 만든 Exchange ActiveSync 모바일 장치 사서함 정책 및 장치 액세스 규칙을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-154">Note:Policies and access rules created in MDM for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="b7f16-155">장치를 Microsoft 365 Business Standard 용 MDM에 등록 한 후에는 장치에 적용 된 모든 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-155">After a device is enrolled in MDM for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="b7f16-156">Exchange ActiveSync에 대 한 자세한 정보는 exchange [activesync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7f16-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="b7f16-157">모바일 장치에 대한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="b7f16-158">특정 설정을 사용 하 여 액세스를 차단 하는 정책을 만드는 경우 [microsoft 365 전자 메일 및 문서에 대 한 액세스 제어](capabilities.md)에 나열 된 지원 되는 앱을 사용 하면 사용자가 microsoft 365 리소스에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="b7f16-159">사용자가 Microsoft 365 리소스에 액세스 하지 못하도록 차단 하는 설정은 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="b7f16-160">보안</span><span class="sxs-lookup"><span data-stu-id="b7f16-160">Security</span></span>
    
- <span data-ttu-id="b7f16-161">암호화</span><span class="sxs-lookup"><span data-stu-id="b7f16-161">Encryption</span></span>
    
- <span data-ttu-id="b7f16-162">암호 해독</span><span class="sxs-lookup"><span data-stu-id="b7f16-162">Jail broken</span></span>
    
- <span data-ttu-id="b7f16-163">관리되는 전자 메일 프로필</span><span class="sxs-lookup"><span data-stu-id="b7f16-163">Managed email profile</span></span>  

<span data-ttu-id="b7f16-164">예를 들어 다음 다이어그램에는 등록된 장치를 사용하는 사용자가 장치에 적용되는 모바일 장치 관리 정책의 보안 설정을 준수하지 않는 경우 수행되는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="b7f16-165">사용자가 기본 이동성 및 보안을 사용 하 여 액세스 제어를 지 원하는 앱에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="b7f16-166">장치가 보안 설정을 준수 하기 전 까지는 앱의 Microsoft 365 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="기본 모바일 및 보안 준수 메시지":::

<span data-ttu-id="b7f16-168">다음 섹션에는 Microsoft 365 조직 리소스에 연결 하는 모바일 장치를 보호 하 고 관리 하는 데 사용할 수 있는 정책 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="b7f16-169">보안 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-169">Security settings</span></span>

|<span data-ttu-id="b7f16-170">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-170">**Setting name**</span></span>|<span data-ttu-id="b7f16-171">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-172">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-172">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-174">암호 필요</span><span class="sxs-lookup"><span data-stu-id="b7f16-174">Require a password</span></span>|<span data-ttu-id="b7f16-175">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-175">Yes</span></span>|<span data-ttu-id="b7f16-176">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-176">Yes</span></span>|<span data-ttu-id="b7f16-177">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-177">Yes</span></span>|
|<span data-ttu-id="b7f16-178">단순한 암호 금지</span><span class="sxs-lookup"><span data-stu-id="b7f16-178">Prevent simple password</span></span>|<span data-ttu-id="b7f16-179">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-179">Yes</span></span>|<span data-ttu-id="b7f16-180">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-180">No</span></span>|<span data-ttu-id="b7f16-181">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-181">No</span></span>|
|<span data-ttu-id="b7f16-182">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="b7f16-182">Require an alphanumeric password</span></span>|<span data-ttu-id="b7f16-183">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-183">Yes</span></span>|<span data-ttu-id="b7f16-184">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-184">No</span></span>|<span data-ttu-id="b7f16-185">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-185">No</span></span>|
|<span data-ttu-id="b7f16-186">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="b7f16-186">Minimum password length</span></span> |<span data-ttu-id="b7f16-187">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-187">Yes</span></span>|<span data-ttu-id="b7f16-188">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-188">Yes</span></span>|<span data-ttu-id="b7f16-189">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-189">Yes</span></span>|
|<span data-ttu-id="b7f16-190">장치 데이터를 지우기 전 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="b7f16-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="b7f16-191">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-191">Yes</span></span>|<span data-ttu-id="b7f16-192">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-192">Yes</span></span>|<span data-ttu-id="b7f16-193">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-193">Yes</span></span>|
|<span data-ttu-id="b7f16-194">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="b7f16-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="b7f16-195">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-195">Yes</span></span>|<span data-ttu-id="b7f16-196">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-196">Yes</span></span>|<span data-ttu-id="b7f16-197">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-197">Yes</span></span>|
|<span data-ttu-id="b7f16-198">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="b7f16-198">Password expiration (days)</span></span> |<span data-ttu-id="b7f16-199">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-199">Yes</span></span>|<span data-ttu-id="b7f16-200">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-200">Yes</span></span>|<span data-ttu-id="b7f16-201">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-201">Yes</span></span>|
|<span data-ttu-id="b7f16-202">암호 기록 기억 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="b7f16-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="b7f16-203">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-203">Yes</span></span>|<span data-ttu-id="b7f16-204">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-204">Yes</span></span>|<span data-ttu-id="b7f16-205">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="b7f16-206">암호화 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-206">Encryption settings</span></span> 

|<span data-ttu-id="b7f16-207">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-207">**Setting name**</span></span>|<span data-ttu-id="b7f16-208">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-209">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-209">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-211">장치<sup>1</sup> 에서 데이터 암호화 필요</span><span class="sxs-lookup"><span data-stu-id="b7f16-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="b7f16-212">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-212">No</span></span>|<span data-ttu-id="b7f16-213">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-213">Yes</span></span>|<span data-ttu-id="b7f16-214">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-214">Yes</span></span>|

<span data-ttu-id="b7f16-215"><sup>1</sup> Samsung Knox에서는 저장소 카드에서 암호화를 요구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="b7f16-216">암호 해독 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-216">Jail broken setting</span></span> 

|<span data-ttu-id="b7f16-217">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-217">**Setting name**</span></span>|<span data-ttu-id="b7f16-218">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-219">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-219">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-221">장치의 암호를 해독하거나 장치를 루트 경로로 지정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="b7f16-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="b7f16-222">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-222">Yes</span></span>|<span data-ttu-id="b7f16-223">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-223">Yes</span></span>|<span data-ttu-id="b7f16-224">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="b7f16-225">관리되는 전자 메일 프로필 옵션</span><span class="sxs-lookup"><span data-stu-id="b7f16-225">Managed email profile option</span></span> 

<span data-ttu-id="b7f16-226">다음 옵션은 사용자가 수동으로 만든 전자 메일 프로필을 사용 하는 경우 Microsoft 365 전자 메일에 액세스 하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="b7f16-227">전자 메일에 액세스하려면 iOS 장치의 사용자가 수동으로 만든 전자 메일 프로필을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="b7f16-228">프로필을 삭제 하면 장치에 새 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="b7f16-229">최종 사용자가 준수 하는 방법에 대 한 자세한 내용은 [기존 전자 메일 계정을](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7f16-229">For instructions on how end users can get compliant, see [An existing email account was found](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="b7f16-230">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-230">**Setting name**</span></span>|<span data-ttu-id="b7f16-231">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-232">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-232">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-234">전자 메일 프로필이 관리됨</span><span class="sxs-lookup"><span data-stu-id="b7f16-234">Email profile is managed</span></span> |<span data-ttu-id="b7f16-235">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-235">Yes</span></span>|<span data-ttu-id="b7f16-236">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-236">No</span></span>|<span data-ttu-id="b7f16-237">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="b7f16-238">클라우드 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-238">Cloud settings</span></span> 

|<span data-ttu-id="b7f16-239">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-239">**Setting name**</span></span>|<span data-ttu-id="b7f16-240">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-241">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-241">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-243">암호화된 백업 필요</span><span class="sxs-lookup"><span data-stu-id="b7f16-243">Require encrypted backup</span></span> |<span data-ttu-id="b7f16-244">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-244">Yes</span></span>|<span data-ttu-id="b7f16-245">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-245">No</span></span>|<span data-ttu-id="b7f16-246">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-246">No</span></span>|
|<span data-ttu-id="b7f16-247">클라우드 백업 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-247">Block cloud backup</span></span> |<span data-ttu-id="b7f16-248">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-248">Yes</span></span>|<span data-ttu-id="b7f16-249">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-249">No</span></span>|<span data-ttu-id="b7f16-250">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-250">No</span></span>|
|<span data-ttu-id="b7f16-251">문서 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-251">Block document synchronization</span></span> |<span data-ttu-id="b7f16-252">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-252">Yes</span></span>|<span data-ttu-id="b7f16-253">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-253">No</span></span>|<span data-ttu-id="b7f16-254">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-254">No</span></span>|
|<span data-ttu-id="b7f16-255">사진 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-255">Block photo synchronization</span></span>  |<span data-ttu-id="b7f16-256">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-256">Yes</span></span>|<span data-ttu-id="b7f16-257">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-257">No</span></span>|<span data-ttu-id="b7f16-258">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-258">No</span></span>|
|<span data-ttu-id="b7f16-259">Google 백업 허용</span><span class="sxs-lookup"><span data-stu-id="b7f16-259">Allow Google backup</span></span>  |<span data-ttu-id="b7f16-260">해당 없음</span><span class="sxs-lookup"><span data-stu-id="b7f16-260">N/A</span></span>|<span data-ttu-id="b7f16-261">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-261">No</span></span>|<span data-ttu-id="b7f16-262">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-262">Yes</span></span>|
|<span data-ttu-id="b7f16-263">Google 계정 자동 동기화 허용</span><span class="sxs-lookup"><span data-stu-id="b7f16-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="b7f16-264">해당 없음</span><span class="sxs-lookup"><span data-stu-id="b7f16-264">N/A</span></span>|<span data-ttu-id="b7f16-265">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-265">No</span></span>|<span data-ttu-id="b7f16-266">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="b7f16-267">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-267">System settings</span></span> 

|<span data-ttu-id="b7f16-268">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-268">**Setting name**</span></span>|<span data-ttu-id="b7f16-269">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-270">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-270">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-272">화면 캡처 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-272">Block screen capture</span></span> |<span data-ttu-id="b7f16-273">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-273">Yes</span></span>|<span data-ttu-id="b7f16-274">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-274">No</span></span>|<span data-ttu-id="b7f16-275">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-275">Yes</span></span>|
|<span data-ttu-id="b7f16-276">장치에서 진단 데이터 전송 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="b7f16-277">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-277">Yes</span></span>|<span data-ttu-id="b7f16-278">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-278">No</span></span>|<span data-ttu-id="b7f16-279">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="b7f16-280">응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-280">Application settings</span></span> 

|<span data-ttu-id="b7f16-281">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-281">**Setting name**</span></span>|<span data-ttu-id="b7f16-282">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-283">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-283">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-285">장치에서 비디오 회의 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-285">Block video conferences on device</span></span> |<span data-ttu-id="b7f16-286">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-286">Yes</span></span>|<span data-ttu-id="b7f16-287">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-287">No</span></span>|<span data-ttu-id="b7f16-288">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-288">No</span></span>|
|<span data-ttu-id="b7f16-289">응용 프로그램 저장소에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-289">Block access to application store</span></span> |<span data-ttu-id="b7f16-290">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-290">Yes</span></span>|<span data-ttu-id="b7f16-291">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-291">No</span></span>|<span data-ttu-id="b7f16-292">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-292">Yes</span></span>|
|<span data-ttu-id="b7f16-293">응용 프로그램 저장소에 액세스할 때 암호 필요</span><span class="sxs-lookup"><span data-stu-id="b7f16-293">Require password when accessing application store</span></span> |<span data-ttu-id="b7f16-294">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-294">No</span></span>|<span data-ttu-id="b7f16-295">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-295">Yes</span></span>|<span data-ttu-id="b7f16-296">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="b7f16-297">장치 기능 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-297">Device capabilities settings</span></span> 

|<span data-ttu-id="b7f16-298">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-298">**Setting name**</span></span>|<span data-ttu-id="b7f16-299">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-300">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-300">**Android 5 and later**</span></span>|<span data-ttu-id="b7f16-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="b7f16-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-302">이동식 저장소와 연결 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-302">Block connection with removable storage</span></span> |<span data-ttu-id="b7f16-303">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-303">Yes</span></span>|<span data-ttu-id="b7f16-304">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-304">Yes</span></span>|<span data-ttu-id="b7f16-305">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-305">No</span></span>|
|<span data-ttu-id="b7f16-306">Bluetooth 연결 차단</span><span class="sxs-lookup"><span data-stu-id="b7f16-306">Block Bluetooth connection</span></span> |<span data-ttu-id="b7f16-307">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-307">Yes</span></span>|<span data-ttu-id="b7f16-308">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-308">Yes</span></span>|<span data-ttu-id="b7f16-309">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-309">No</span></span>|

##  <a name="additional-settings"></a><span data-ttu-id="b7f16-310">추가 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-310">Additional settings</span></span> 

<span data-ttu-id="b7f16-311">PowerShell cmdlet을 사용하여 다음 추가 정책 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-311">You can set the following additional policy settings by using PowerShell cmdlets.</span></span> <span data-ttu-id="b7f16-312">자세한 내용은 [Security & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7f16-312">For more information, see [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

|<span data-ttu-id="b7f16-313">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="b7f16-313">**Setting name**</span></span>|<span data-ttu-id="b7f16-314">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="b7f16-315">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="b7f16-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7f16-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="b7f16-316">CameraEnabled</span></span>|<span data-ttu-id="b7f16-317">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-317">Yes</span></span>|<span data-ttu-id="b7f16-318">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-318">Yes</span></span>|
|<span data-ttu-id="b7f16-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="b7f16-319">RegionRatings</span></span>|<span data-ttu-id="b7f16-320">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-320">Yes</span></span>|<span data-ttu-id="b7f16-321">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-321">No</span></span>|
|<span data-ttu-id="b7f16-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="b7f16-322">MoviesRatings</span></span>|<span data-ttu-id="b7f16-323">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-323">Yes</span></span>|<span data-ttu-id="b7f16-324">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-324">No</span></span>|
|<span data-ttu-id="b7f16-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="b7f16-325">TVShowsRating</span></span> |<span data-ttu-id="b7f16-326">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-326">Yes</span></span>|<span data-ttu-id="b7f16-327">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-327">No</span></span>|
|<span data-ttu-id="b7f16-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="b7f16-328">AppsRatings</span></span> |<span data-ttu-id="b7f16-329">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-329">Yes</span></span>|<span data-ttu-id="b7f16-330">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-330">No</span></span>|
|<span data-ttu-id="b7f16-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="b7f16-331">AllowVoiceDialing</span></span> |<span data-ttu-id="b7f16-332">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-332">Yes</span></span>|<span data-ttu-id="b7f16-333">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-333">No</span></span>|
|<span data-ttu-id="b7f16-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="b7f16-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="b7f16-335">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-335">Yes</span></span>|<span data-ttu-id="b7f16-336">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-336">No</span></span>|
|<span data-ttu-id="b7f16-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="b7f16-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="b7f16-338">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-338">Yes</span></span>|<span data-ttu-id="b7f16-339">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-339">No</span></span>|
|<span data-ttu-id="b7f16-340">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="b7f16-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="b7f16-341">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-341">Yes</span></span>|<span data-ttu-id="b7f16-342">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-342">No</span></span>|
|<span data-ttu-id="b7f16-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="b7f16-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="b7f16-344">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-344">Yes</span></span>|<span data-ttu-id="b7f16-345">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-345">No</span></span>|
|<span data-ttu-id="b7f16-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="b7f16-346">PasswordQuality</span></span> |<span data-ttu-id="b7f16-347">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-347">No</span></span>|<span data-ttu-id="b7f16-348">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-348">Yes</span></span>|
|<span data-ttu-id="b7f16-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="b7f16-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="b7f16-350">예</span><span class="sxs-lookup"><span data-stu-id="b7f16-350">Yes</span></span>|<span data-ttu-id="b7f16-351">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-351">No</span></span>|
|<span data-ttu-id="b7f16-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="b7f16-352">WLANEnabled</span></span>  |<span data-ttu-id="b7f16-353">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-353">No</span></span>|<span data-ttu-id="b7f16-354">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f16-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="b7f16-355">Windows에서 지원 되는 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-355">Settings supported by Windows</span></span> 

<span data-ttu-id="b7f16-356">Windows 10 장치는 모바일 장치로 등록 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="b7f16-357">적용 가능한 정책이 배포 되 면 Windows 10 장치를 사용 하는 사용자는 기본 제공 전자 메일 앱을 처음 사용할 때 Microsoft 365 전자 메일에 액세스 하기 위해 기본 이동성 및 보안을 등록 해야 합니다 (Azure AD premium 구독이 필요 함).</span><span class="sxs-lookup"><span data-stu-id="b7f16-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="b7f16-358">다음 설정은 모바일 장치로 등록 된 Windows 10 장치에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="b7f16-359">이러한 설정은 사용자가 Microsoft 365 리소스에 액세스 하지 못하도록 차단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="b7f16-360">보안 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-360">Security settings</span></span>

- <span data-ttu-id="b7f16-361">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="b7f16-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="b7f16-362">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="b7f16-362">Minimum password length</span></span>
    
- <span data-ttu-id="b7f16-363">장치 데이터가 지워지기 전 로그인 오류 횟수</span><span class="sxs-lookup"><span data-stu-id="b7f16-363">Number of sign-in failures before device is wiped</span></span>
    
- <span data-ttu-id="b7f16-364">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="b7f16-364">Minutes of inactivity before device is locked</span></span>
    
- <span data-ttu-id="b7f16-365">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="b7f16-365">Password expiration (days)</span></span>
    
- <span data-ttu-id="b7f16-366">암호 기록 저장 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="b7f16-366">Remember password history and prevent reuse</span></span>   

>[!NOTE]
><span data-ttu-id="b7f16-367">다음 설정은 암호를 규정 하는 로컬 Windows 계정만 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="b7f16-368">Join 도메인 또는 Azure Active Directory를 통해 제공 되는 Windows 계정은 이러한 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="b7f16-369">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-369">System settings</span></span>

<span data-ttu-id="b7f16-370">장치에서 진단 데이터 보내기를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="b7f16-371">추가 설정</span><span class="sxs-lookup"><span data-stu-id="b7f16-371">Additional settings</span></span>

<span data-ttu-id="b7f16-372">PowerShell cmdlet을 사용 하 여 다음과 같은 추가 정책 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="b7f16-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="b7f16-373">AllowConvenienceLogon</span></span>
    
- <span data-ttu-id="b7f16-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="b7f16-374">UserAccountControlStatus</span></span>
    
- <span data-ttu-id="b7f16-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="b7f16-375">FirewallStatus</span></span>
    
- <span data-ttu-id="b7f16-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="b7f16-376">AutoUpdateStatus</span></span>
    
- <span data-ttu-id="b7f16-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="b7f16-377">AntiVirusStatus</span></span>   

- <span data-ttu-id="b7f16-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="b7f16-378">AntiVirusSignatureStatus</span></span>
    
- <span data-ttu-id="b7f16-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="b7f16-379">SmartScreenEnabled</span></span>
    
- <span data-ttu-id="b7f16-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="b7f16-380">WorkFoldersSyncUrl</span></span>
    

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="b7f16-381">원격으로 모바일 장치의 데이터 지우기</span><span class="sxs-lookup"><span data-stu-id="b7f16-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="b7f16-382">장치를 분실 하거나 도난당 한 경우 중요 한 조직 데이터를 제거 하 고 **데이터 손실 방지**  >  **장치 관리**> 보안 & 준수 센터에서 초기화를 수행 하 여 Microsoft 365 조직 리소스에 대 한 액세스를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="b7f16-383">선택적 지우기를 수행하여 조직 데이터만 제거하거나, 전체 지우기를 수행하여 장치에서 모든 정보를 삭제하고 장치를 처음 출시될 때의 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f16-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="b7f16-384">자세한 내용은 [기본 Mobility And Security에서 모바일 장치 초기화](wipe-mobile-device.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7f16-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7f16-385">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b7f16-385">Related topics</span></span>

[<span data-ttu-id="b7f16-386">Microsoft 365의 기본 모바일 및 보안 개요</span><span class="sxs-lookup"><span data-stu-id="b7f16-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="b7f16-387">기본 모바일 및 보안에서 장치 보안 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b7f16-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)