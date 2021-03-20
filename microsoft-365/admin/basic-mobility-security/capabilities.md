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
description: 기본 모바일 및 보안은 모바일 장치를 보호하고 관리하는 데 도움이 될 수 있습니다.
ms.openlocfilehash: 468f06edf16eb6ea00fd4d26c716bc145474dd25
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904279"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="65d45-103">기본 이동성 및 보안 기능</span><span class="sxs-lookup"><span data-stu-id="65d45-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="65d45-104">기본 모바일 및 보안은 조직의 라이선스가 있는 Microsoft 365 사용자가 사용하는 iPhone, iPad, Androids 및 Windows Phone과 같은 모바일 장치를 보호하고 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="65d45-105">지원되는 모바일 장치 및 앱에 대한 조직의 Microsoft 365 전자 메일 및 문서에 대한 액세스를 제어하는 데 도움이 되는 설정을 사용하여 모바일 장치 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="65d45-106">장치를 분실하거나 도난 당한 경우 장치의 데이터를 원격으로 지워 중요한 조직 정보를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="65d45-107">지원되는 장치</span><span class="sxs-lookup"><span data-stu-id="65d45-107">Supported devices</span></span>

<span data-ttu-id="65d45-108">기본 Mobility and Security를 사용하여 다음 장치를 보호하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="65d45-109">iOS 11.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="65d45-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="65d45-110">Android 5.0 이상 버전<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="65d45-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="65d45-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65d45-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="65d45-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65d45-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="65d45-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="65d45-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="65d45-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="65d45-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="65d45-115"><sup>1</sup> Windows 8.1 RT 장치에 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="65d45-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="65d45-116"><sup>2</sup> Windows 8.1 RT 장치에 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="65d45-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="65d45-117">Windows 10에 대한 액세스 제어를 사용하려면 Azure AD Premium을 포함하는 구독이 필요하며 디바이스를 Azure Active Directory에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="65d45-118"><sup>3</sup> Windows 8.1 RT 장치에 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="65d45-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="65d45-119">2020년 6월 이후의 Android 버전은 Samsung Knox 장치를 제외한 암호 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="65d45-120">이전 OS 버전에 이미 등록된 장치는 예고 없이 기능이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="65d45-121">조직의 사용자가 기본 모바일 및 보안에서 지원되지 않는 모바일 장치를 사용하는 경우 조직의 데이터를 더 안전하게 Exchange ActiveSync Microsoft 365 전자 메일에 대한 Exchange ActiveSync 앱 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="65d45-122">모바일 기능을 차단하는 Exchange ActiveSync 기본 이동성 및 보안에서 장치 액세스 [설정 관리를 참조하세요.](manage-device-access-settings.md)</span><span class="sxs-lookup"><span data-stu-id="65d45-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="65d45-123">Microsoft 365 전자 메일 및 문서에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="65d45-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="65d45-124">다음 표에 있는 다양한 유형의 모바일 장치에 대해 지원되는 앱은 사용자가 기본 모바일 및 보안에 등록하라는 메시지를 표시하며, 여기서 사용자의 장치에 적용되는 새로운 모바일 장치 관리 정책이 있으며 사용자가 이전에 장치를 등록하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="65d45-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="65d45-125">사용자의 장치가 정책을 설정하는 방법에 따라 정책을 준수하지 않는 경우 사용자가 이러한 앱에서 Microsoft 365 리소스에 액세스하지 못하도록 차단되거나 액세스 권한이 있지만 Microsoft 365는 정책 위반을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="65d45-126">**제품**</span><span class="sxs-lookup"><span data-stu-id="65d45-126">**Product**</span></span>|<span data-ttu-id="65d45-127">**iOS 10.0 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="65d45-128">**Android 5.0 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="65d45-129">**Exchange** Exchange ActiveSync 버전 14.1 이상을 사용하는 TouchDown과 같은 기본 제공 전자 메일 및 타사 Exchange ActiveSync 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="65d45-130">메일</span><span class="sxs-lookup"><span data-stu-id="65d45-130">Mail</span></span> |<span data-ttu-id="65d45-131">전자 메일</span><span class="sxs-lookup"><span data-stu-id="65d45-131">Email</span></span> |
|<span data-ttu-id="65d45-132">**Office**   및  **비즈니스용 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="65d45-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="65d45-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="65d45-133">Outlook</span></span> </br><span data-ttu-id="65d45-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="65d45-134">OneDrive</span></span> </br><span data-ttu-id="65d45-135">Word</span><span class="sxs-lookup"><span data-stu-id="65d45-135">Word</span></span> </br><span data-ttu-id="65d45-136">Excel</span><span class="sxs-lookup"><span data-stu-id="65d45-136">Excel</span></span> </br><span data-ttu-id="65d45-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="65d45-137">PowerPoint</span></span>|<span data-ttu-id="65d45-138">**휴대폰 및 태블릿의 경우**:</span><span class="sxs-lookup"><span data-stu-id="65d45-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="65d45-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="65d45-139">Outlook</span></span> <br/> <span data-ttu-id="65d45-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="65d45-140">OneDrive</span></span> <br/> <span data-ttu-id="65d45-141">Word</span><span class="sxs-lookup"><span data-stu-id="65d45-141">Word</span></span> <br/> <span data-ttu-id="65d45-142">Excel</span><span class="sxs-lookup"><span data-stu-id="65d45-142">Excel</span></span> <br/> <span data-ttu-id="65d45-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="65d45-143">PowerPoint</span></span> <br/> <span data-ttu-id="65d45-144">**휴대폰만 해당:**</span><span class="sxs-lookup"><span data-stu-id="65d45-144">**On phones only:**</span></span> <br/> <span data-ttu-id="65d45-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="65d45-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="65d45-146">iOS 10.0 이상 버전에 대한 지원에는 iPhone 및 iPad 장치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="65d45-147">BlackBerry OS 디바이스 관리는 기본 보안 및 모바일에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-147">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="65d45-148">BlackBerry의 BBCS(BlackBerry Business Cloud Services)를 사용하여 BlackBerry OS 장치를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="65d45-149">Android OS를 실행하는 Blackberry 디바이스는 표준 Android 장치로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="65d45-150">사용자가 모바일 브라우저를 사용하여 Microsoft 365 SharePoint 사이트, Office Online의 문서 또는 전자 메일에 액세스하는 경우 등록하라는 메시지가 표시되거나 정책 위반에 대해 차단되거나 Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="65d45-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="65d45-151">다음 다이어그램은 새 장치를 사용하는 사용자가 기본 Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인할 때 발생하는 일과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="65d45-152">사용자가 디바이스를 등록할 때까지 앱에서 Microsoft 365 리소스에 액세스하지 못하도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="기본 모바일 및 보안 액세스 제어":::

> [!NOTE]
> <span data-ttu-id="65d45-154">Microsoft 365 Business Standard용 기본 이동성 및 보안에서 만든 정책 및 액세스 규칙은 Exchange Exchange ActiveSync 모바일 장치 사서함 정책 및 장치 액세스 규칙을 다시 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-154">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="65d45-155">장치가 Microsoft 365 Business Standard의 기본 Mobility and Security에 등록된 후 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-155">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="65d45-156">자세한 내용은 Exchange ActiveSync Exchange [Online Exchange ActiveSync 참조하세요.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="65d45-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="65d45-157">모바일 장치에 대한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="65d45-158">특정 설정이 켜져 있는 액세스를 차단하는 정책을 만들면 Microsoft 365 전자 메일 및 문서에 대한 액세스 제어에 나열된 지원되는 앱을 사용할 때 사용자가 [Microsoft 365](capabilities.md)리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="65d45-159">사용자가 Microsoft 365 리소스에 액세스하지 수 없는 설정은 다음 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="65d45-160">보안</span><span class="sxs-lookup"><span data-stu-id="65d45-160">Security</span></span>

- <span data-ttu-id="65d45-161">암호화</span><span class="sxs-lookup"><span data-stu-id="65d45-161">Encryption</span></span>

- <span data-ttu-id="65d45-162">암호 해독</span><span class="sxs-lookup"><span data-stu-id="65d45-162">Jail broken</span></span>

- <span data-ttu-id="65d45-163">관리되는 전자 메일 프로필</span><span class="sxs-lookup"><span data-stu-id="65d45-163">Managed email profile</span></span>  

<span data-ttu-id="65d45-164">예를 들어 다음 다이어그램에는 등록된 장치를 사용하는 사용자가 장치에 적용되는 모바일 장치 관리 정책의 보안 설정을 준수하지 않는 경우 수행되는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="65d45-165">사용자는 Basic Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="65d45-166">디바이스가 보안 설정을 준수할 때까지 앱에서 Microsoft 365 리소스에 액세스하지 못하게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="기본 모바일 및 보안 준수 메시지":::

<span data-ttu-id="65d45-168">다음 섹션에는 Microsoft 365 조직 리소스에 연결하는 모바일 장치를 보호하고 관리하는 데 사용할 수 있는 정책 설정이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="65d45-169">보안 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-169">Security settings</span></span>

|<span data-ttu-id="65d45-170">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-170">**Setting name**</span></span>|<span data-ttu-id="65d45-171">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-172">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-172">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-174">암호 필요</span><span class="sxs-lookup"><span data-stu-id="65d45-174">Require a password</span></span>|<span data-ttu-id="65d45-175">예</span><span class="sxs-lookup"><span data-stu-id="65d45-175">Yes</span></span>|<span data-ttu-id="65d45-176">예</span><span class="sxs-lookup"><span data-stu-id="65d45-176">Yes</span></span>|<span data-ttu-id="65d45-177">예</span><span class="sxs-lookup"><span data-stu-id="65d45-177">Yes</span></span>|
|<span data-ttu-id="65d45-178">단순한 암호 금지</span><span class="sxs-lookup"><span data-stu-id="65d45-178">Prevent simple password</span></span>|<span data-ttu-id="65d45-179">예</span><span class="sxs-lookup"><span data-stu-id="65d45-179">Yes</span></span>|<span data-ttu-id="65d45-180">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-180">No</span></span>|<span data-ttu-id="65d45-181">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-181">No</span></span>|
|<span data-ttu-id="65d45-182">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="65d45-182">Require an alphanumeric password</span></span>|<span data-ttu-id="65d45-183">예</span><span class="sxs-lookup"><span data-stu-id="65d45-183">Yes</span></span>|<span data-ttu-id="65d45-184">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-184">No</span></span>|<span data-ttu-id="65d45-185">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-185">No</span></span>|
|<span data-ttu-id="65d45-186">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="65d45-186">Minimum password length</span></span> |<span data-ttu-id="65d45-187">예</span><span class="sxs-lookup"><span data-stu-id="65d45-187">Yes</span></span>|<span data-ttu-id="65d45-188">예</span><span class="sxs-lookup"><span data-stu-id="65d45-188">Yes</span></span>|<span data-ttu-id="65d45-189">예</span><span class="sxs-lookup"><span data-stu-id="65d45-189">Yes</span></span>|
|<span data-ttu-id="65d45-190">장치 데이터를 지우기 전 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="65d45-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="65d45-191">예</span><span class="sxs-lookup"><span data-stu-id="65d45-191">Yes</span></span>|<span data-ttu-id="65d45-192">예</span><span class="sxs-lookup"><span data-stu-id="65d45-192">Yes</span></span>|<span data-ttu-id="65d45-193">예</span><span class="sxs-lookup"><span data-stu-id="65d45-193">Yes</span></span>|
|<span data-ttu-id="65d45-194">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="65d45-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="65d45-195">예</span><span class="sxs-lookup"><span data-stu-id="65d45-195">Yes</span></span>|<span data-ttu-id="65d45-196">예</span><span class="sxs-lookup"><span data-stu-id="65d45-196">Yes</span></span>|<span data-ttu-id="65d45-197">예</span><span class="sxs-lookup"><span data-stu-id="65d45-197">Yes</span></span>|
|<span data-ttu-id="65d45-198">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="65d45-198">Password expiration (days)</span></span> |<span data-ttu-id="65d45-199">예</span><span class="sxs-lookup"><span data-stu-id="65d45-199">Yes</span></span>|<span data-ttu-id="65d45-200">예</span><span class="sxs-lookup"><span data-stu-id="65d45-200">Yes</span></span>|<span data-ttu-id="65d45-201">예</span><span class="sxs-lookup"><span data-stu-id="65d45-201">Yes</span></span>|
|<span data-ttu-id="65d45-202">암호 기록 기억 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="65d45-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="65d45-203">예</span><span class="sxs-lookup"><span data-stu-id="65d45-203">Yes</span></span>|<span data-ttu-id="65d45-204">예</span><span class="sxs-lookup"><span data-stu-id="65d45-204">Yes</span></span>|<span data-ttu-id="65d45-205">예</span><span class="sxs-lookup"><span data-stu-id="65d45-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="65d45-206">암호화 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-206">Encryption settings</span></span>

|<span data-ttu-id="65d45-207">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-207">**Setting name**</span></span>|<span data-ttu-id="65d45-208">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-209">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-209">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-211">디바이스<sup>1에서</sup> 데이터 암호화 필요</span><span class="sxs-lookup"><span data-stu-id="65d45-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="65d45-212">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-212">No</span></span>|<span data-ttu-id="65d45-213">예</span><span class="sxs-lookup"><span data-stu-id="65d45-213">Yes</span></span>|<span data-ttu-id="65d45-214">예</span><span class="sxs-lookup"><span data-stu-id="65d45-214">Yes</span></span>|

<span data-ttu-id="65d45-215"><sup>1</sup> Samsung Knox를 사용하면 저장소 카드에 암호화를 요구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="65d45-216">암호 해독 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-216">Jail broken setting</span></span> 

|<span data-ttu-id="65d45-217">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-217">**Setting name**</span></span>|<span data-ttu-id="65d45-218">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-219">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-219">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-221">장치의 암호를 해독하거나 장치를 루트 경로로 지정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="65d45-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="65d45-222">예</span><span class="sxs-lookup"><span data-stu-id="65d45-222">Yes</span></span>|<span data-ttu-id="65d45-223">예</span><span class="sxs-lookup"><span data-stu-id="65d45-223">Yes</span></span>|<span data-ttu-id="65d45-224">예</span><span class="sxs-lookup"><span data-stu-id="65d45-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="65d45-225">관리되는 전자 메일 프로필 옵션</span><span class="sxs-lookup"><span data-stu-id="65d45-225">Managed email profile option</span></span> 

<span data-ttu-id="65d45-226">다음 옵션은 사용자가 수동으로 만든 전자 메일 프로필을 사용하는 경우 사용자가 Microsoft 365 전자 메일에 액세스하지 못하게 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="65d45-227">전자 메일에 액세스하려면 iOS 장치의 사용자가 수동으로 만든 전자 메일 프로필을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="65d45-228">프로필을 삭제하면 디바이스에 새 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="65d45-229">최종 사용자가 규정을 준수하는 방법에 대한 지침은 기존 전자 메일 계정을 [찾은 을 참조하세요.](/intune-user-help/existing-company-email-account-found)</span><span class="sxs-lookup"><span data-stu-id="65d45-229">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="65d45-230">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-230">**Setting name**</span></span>|<span data-ttu-id="65d45-231">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-232">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-232">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-234">전자 메일 프로필이 관리됨</span><span class="sxs-lookup"><span data-stu-id="65d45-234">Email profile is managed</span></span> |<span data-ttu-id="65d45-235">예</span><span class="sxs-lookup"><span data-stu-id="65d45-235">Yes</span></span>|<span data-ttu-id="65d45-236">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-236">No</span></span>|<span data-ttu-id="65d45-237">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="65d45-238">클라우드 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-238">Cloud settings</span></span>

|<span data-ttu-id="65d45-239">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-239">**Setting name**</span></span>|<span data-ttu-id="65d45-240">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-241">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-241">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-243">암호화된 백업 필요</span><span class="sxs-lookup"><span data-stu-id="65d45-243">Require encrypted backup</span></span> |<span data-ttu-id="65d45-244">예</span><span class="sxs-lookup"><span data-stu-id="65d45-244">Yes</span></span>|<span data-ttu-id="65d45-245">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-245">No</span></span>|<span data-ttu-id="65d45-246">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-246">No</span></span>|
|<span data-ttu-id="65d45-247">클라우드 백업 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-247">Block cloud backup</span></span> |<span data-ttu-id="65d45-248">예</span><span class="sxs-lookup"><span data-stu-id="65d45-248">Yes</span></span>|<span data-ttu-id="65d45-249">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-249">No</span></span>|<span data-ttu-id="65d45-250">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-250">No</span></span>|
|<span data-ttu-id="65d45-251">문서 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-251">Block document synchronization</span></span> |<span data-ttu-id="65d45-252">예</span><span class="sxs-lookup"><span data-stu-id="65d45-252">Yes</span></span>|<span data-ttu-id="65d45-253">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-253">No</span></span>|<span data-ttu-id="65d45-254">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-254">No</span></span>|
|<span data-ttu-id="65d45-255">사진 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-255">Block photo synchronization</span></span>  |<span data-ttu-id="65d45-256">예</span><span class="sxs-lookup"><span data-stu-id="65d45-256">Yes</span></span>|<span data-ttu-id="65d45-257">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-257">No</span></span>|<span data-ttu-id="65d45-258">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-258">No</span></span>|
|<span data-ttu-id="65d45-259">Google 백업 허용</span><span class="sxs-lookup"><span data-stu-id="65d45-259">Allow Google backup</span></span>  |<span data-ttu-id="65d45-260">해당 없음</span><span class="sxs-lookup"><span data-stu-id="65d45-260">N/A</span></span>|<span data-ttu-id="65d45-261">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-261">No</span></span>|<span data-ttu-id="65d45-262">예</span><span class="sxs-lookup"><span data-stu-id="65d45-262">Yes</span></span>|
|<span data-ttu-id="65d45-263">Google 계정 자동 동기화 허용</span><span class="sxs-lookup"><span data-stu-id="65d45-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="65d45-264">해당 없음</span><span class="sxs-lookup"><span data-stu-id="65d45-264">N/A</span></span>|<span data-ttu-id="65d45-265">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-265">No</span></span>|<span data-ttu-id="65d45-266">예</span><span class="sxs-lookup"><span data-stu-id="65d45-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="65d45-267">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-267">System settings</span></span>

|<span data-ttu-id="65d45-268">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-268">**Setting name**</span></span>|<span data-ttu-id="65d45-269">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-270">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-270">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-272">화면 캡처 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-272">Block screen capture</span></span> |<span data-ttu-id="65d45-273">예</span><span class="sxs-lookup"><span data-stu-id="65d45-273">Yes</span></span>|<span data-ttu-id="65d45-274">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-274">No</span></span>|<span data-ttu-id="65d45-275">예</span><span class="sxs-lookup"><span data-stu-id="65d45-275">Yes</span></span>|
|<span data-ttu-id="65d45-276">장치에서 진단 데이터 전송 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="65d45-277">예</span><span class="sxs-lookup"><span data-stu-id="65d45-277">Yes</span></span>|<span data-ttu-id="65d45-278">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-278">No</span></span>|<span data-ttu-id="65d45-279">예</span><span class="sxs-lookup"><span data-stu-id="65d45-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="65d45-280">응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-280">Application settings</span></span>

|<span data-ttu-id="65d45-281">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-281">**Setting name**</span></span>|<span data-ttu-id="65d45-282">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-283">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-283">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-285">장치에서 비디오 회의 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-285">Block video conferences on device</span></span> |<span data-ttu-id="65d45-286">예</span><span class="sxs-lookup"><span data-stu-id="65d45-286">Yes</span></span>|<span data-ttu-id="65d45-287">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-287">No</span></span>|<span data-ttu-id="65d45-288">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-288">No</span></span>|
|<span data-ttu-id="65d45-289">응용 프로그램 저장소에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-289">Block access to application store</span></span> |<span data-ttu-id="65d45-290">예</span><span class="sxs-lookup"><span data-stu-id="65d45-290">Yes</span></span>|<span data-ttu-id="65d45-291">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-291">No</span></span>|<span data-ttu-id="65d45-292">예</span><span class="sxs-lookup"><span data-stu-id="65d45-292">Yes</span></span>|
|<span data-ttu-id="65d45-293">응용 프로그램 저장소에 액세스할 때 암호 필요</span><span class="sxs-lookup"><span data-stu-id="65d45-293">Require password when accessing application store</span></span> |<span data-ttu-id="65d45-294">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-294">No</span></span>|<span data-ttu-id="65d45-295">예</span><span class="sxs-lookup"><span data-stu-id="65d45-295">Yes</span></span>|<span data-ttu-id="65d45-296">예</span><span class="sxs-lookup"><span data-stu-id="65d45-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="65d45-297">장치 기능 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-297">Device capabilities settings</span></span>

|<span data-ttu-id="65d45-298">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-298">**Setting name**</span></span>|<span data-ttu-id="65d45-299">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-300">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-300">**Android 5 and later**</span></span>|<span data-ttu-id="65d45-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="65d45-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65d45-302">이동식 저장소와 연결 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-302">Block connection with removable storage</span></span> |<span data-ttu-id="65d45-303">예</span><span class="sxs-lookup"><span data-stu-id="65d45-303">Yes</span></span>|<span data-ttu-id="65d45-304">예</span><span class="sxs-lookup"><span data-stu-id="65d45-304">Yes</span></span>|<span data-ttu-id="65d45-305">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-305">No</span></span>|
|<span data-ttu-id="65d45-306">Bluetooth 연결 차단</span><span class="sxs-lookup"><span data-stu-id="65d45-306">Block Bluetooth connection</span></span> |<span data-ttu-id="65d45-307">예</span><span class="sxs-lookup"><span data-stu-id="65d45-307">Yes</span></span>|<span data-ttu-id="65d45-308">예</span><span class="sxs-lookup"><span data-stu-id="65d45-308">Yes</span></span>|<span data-ttu-id="65d45-309">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-309">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="65d45-310">추가 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-310">Additional settings</span></span>

<span data-ttu-id="65d45-311">보안 및 준수 센터 PowerShell cmdlet을 사용하여 다음과 같은 추가 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-311">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="65d45-312">자세한 내용은 보안 및 [준수 & PowerShell을 참조하세요.](/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="65d45-312">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="65d45-313">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="65d45-313">**Setting name**</span></span>|<span data-ttu-id="65d45-314">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="65d45-315">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="65d45-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="65d45-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="65d45-316">CameraEnabled</span></span>|<span data-ttu-id="65d45-317">예</span><span class="sxs-lookup"><span data-stu-id="65d45-317">Yes</span></span>|<span data-ttu-id="65d45-318">예</span><span class="sxs-lookup"><span data-stu-id="65d45-318">Yes</span></span>|
|<span data-ttu-id="65d45-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="65d45-319">RegionRatings</span></span>|<span data-ttu-id="65d45-320">예</span><span class="sxs-lookup"><span data-stu-id="65d45-320">Yes</span></span>|<span data-ttu-id="65d45-321">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-321">No</span></span>|
|<span data-ttu-id="65d45-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="65d45-322">MoviesRatings</span></span>|<span data-ttu-id="65d45-323">예</span><span class="sxs-lookup"><span data-stu-id="65d45-323">Yes</span></span>|<span data-ttu-id="65d45-324">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-324">No</span></span>|
|<span data-ttu-id="65d45-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="65d45-325">TVShowsRating</span></span> |<span data-ttu-id="65d45-326">예</span><span class="sxs-lookup"><span data-stu-id="65d45-326">Yes</span></span>|<span data-ttu-id="65d45-327">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-327">No</span></span>|
|<span data-ttu-id="65d45-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="65d45-328">AppsRatings</span></span> |<span data-ttu-id="65d45-329">예</span><span class="sxs-lookup"><span data-stu-id="65d45-329">Yes</span></span>|<span data-ttu-id="65d45-330">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-330">No</span></span>|
|<span data-ttu-id="65d45-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="65d45-331">AllowVoiceDialing</span></span> |<span data-ttu-id="65d45-332">예</span><span class="sxs-lookup"><span data-stu-id="65d45-332">Yes</span></span>|<span data-ttu-id="65d45-333">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-333">No</span></span>|
|<span data-ttu-id="65d45-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="65d45-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="65d45-335">예</span><span class="sxs-lookup"><span data-stu-id="65d45-335">Yes</span></span>|<span data-ttu-id="65d45-336">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-336">No</span></span>|
|<span data-ttu-id="65d45-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="65d45-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="65d45-338">예</span><span class="sxs-lookup"><span data-stu-id="65d45-338">Yes</span></span>|<span data-ttu-id="65d45-339">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-339">No</span></span>|
|<span data-ttu-id="65d45-340">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="65d45-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="65d45-341">예</span><span class="sxs-lookup"><span data-stu-id="65d45-341">Yes</span></span>|<span data-ttu-id="65d45-342">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-342">No</span></span>|
|<span data-ttu-id="65d45-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="65d45-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="65d45-344">예</span><span class="sxs-lookup"><span data-stu-id="65d45-344">Yes</span></span>|<span data-ttu-id="65d45-345">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-345">No</span></span>|
|<span data-ttu-id="65d45-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="65d45-346">PasswordQuality</span></span> |<span data-ttu-id="65d45-347">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-347">No</span></span>|<span data-ttu-id="65d45-348">예</span><span class="sxs-lookup"><span data-stu-id="65d45-348">Yes</span></span>|
|<span data-ttu-id="65d45-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="65d45-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="65d45-350">예</span><span class="sxs-lookup"><span data-stu-id="65d45-350">Yes</span></span>|<span data-ttu-id="65d45-351">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-351">No</span></span>|
|<span data-ttu-id="65d45-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="65d45-352">WLANEnabled</span></span>  |<span data-ttu-id="65d45-353">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-353">No</span></span>|<span data-ttu-id="65d45-354">아니요</span><span class="sxs-lookup"><span data-stu-id="65d45-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="65d45-355">Windows에서 지원하는 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-355">Settings supported by Windows</span></span>

<span data-ttu-id="65d45-356">Windows 10 장치를 모바일 장치로 등록하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="65d45-357">해당 정책을 배포한 후 Windows 10 장치를 사용하는 사용자는 기본 제공 전자 메일 앱을 처음 사용하여 Microsoft 365 전자 메일에 액세스할 때 기본 이동성 및 보안에 등록해야 합니다(Azure AD Premium 구독 필요).</span><span class="sxs-lookup"><span data-stu-id="65d45-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="65d45-358">다음 설정은 모바일 장치로 등록된 Windows 10 장치에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="65d45-359">이러한 설정은 사용자가 Microsoft 365 리소스에 액세스하지 못하게 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="65d45-360">보안 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-360">Security settings</span></span>

- <span data-ttu-id="65d45-361">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="65d45-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="65d45-362">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="65d45-362">Minimum password length</span></span>

- <span data-ttu-id="65d45-363">장치 데이터가 지워지기 전 로그인 오류 횟수</span><span class="sxs-lookup"><span data-stu-id="65d45-363">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="65d45-364">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="65d45-364">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="65d45-365">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="65d45-365">Password expiration (days)</span></span>

- <span data-ttu-id="65d45-366">암호 기록 저장 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="65d45-366">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="65d45-367">암호를 제어하는 다음 설정은 로컬 Windows 계정만 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="65d45-368">도메인 또는 Azure Active Directory 가입을 통해 제공된 Windows 계정은 이러한 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="65d45-369">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-369">System settings</span></span>

<span data-ttu-id="65d45-370">장치에서 진단 데이터 전송을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="65d45-371">추가 설정</span><span class="sxs-lookup"><span data-stu-id="65d45-371">Additional settings</span></span>

<span data-ttu-id="65d45-372">PowerShell cmdlet을 사용하여 이러한 추가 정책 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="65d45-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="65d45-373">AllowConvenienceLogon</span></span>

- <span data-ttu-id="65d45-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="65d45-374">UserAccountControlStatus</span></span>

- <span data-ttu-id="65d45-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="65d45-375">FirewallStatus</span></span>

- <span data-ttu-id="65d45-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="65d45-376">AutoUpdateStatus</span></span>

- <span data-ttu-id="65d45-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="65d45-377">AntiVirusStatus</span></span>

- <span data-ttu-id="65d45-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="65d45-378">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="65d45-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="65d45-379">SmartScreenEnabled</span></span>

- <span data-ttu-id="65d45-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="65d45-380">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="65d45-381">원격으로 모바일 장치의 데이터 지우기</span><span class="sxs-lookup"><span data-stu-id="65d45-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="65d45-382">장치를 분실하거나 도난당한 경우 보안 및 준수 센터 또는 데이터 손실 방지 장치 관리 에서 데이터 손실 & 데이터 지우기를 수행하여 중요한 조직 데이터를 제거하고 Microsoft 365 조직 리소스에 대한 액세스를 **>** 수  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="65d45-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="65d45-383">선택적 지우기를 수행하여 조직 데이터만 제거하거나, 전체 지우기를 수행하여 장치에서 모든 정보를 삭제하고 장치를 처음 출시될 때의 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="65d45-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="65d45-384">자세한 내용은 Basic Mobility and Security에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="65d45-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="65d45-385">관련 주제</span><span class="sxs-lookup"><span data-stu-id="65d45-385">Related topics</span></span>

[<span data-ttu-id="65d45-386">Microsoft 365의 기본 모바일 및 보안 개요</span><span class="sxs-lookup"><span data-stu-id="65d45-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="65d45-387">기본 모바일 및 보안에서 장치 보안 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="65d45-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)