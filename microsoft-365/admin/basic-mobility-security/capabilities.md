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
- AdminTemplateSet
search.appverid:
- MET150
description: 기본 모바일 및 보안은 모바일 장치를 보호하고 관리하는 데 도움이 될 수 있습니다.
ms.openlocfilehash: 5619ce6a8fa2c705acc6be08e3af8ad6f90a6d99
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393310"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="41cc3-103">기본 이동성 및 보안 기능</span><span class="sxs-lookup"><span data-stu-id="41cc3-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="41cc3-104">기본 모바일 및 보안을 사용하면 조직의 라이선스가 있는 사용자가 사용하는 iPhone, iPad, Androids 및 Windows 휴대폰과 같은 모바일 Microsoft 365 보호하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="41cc3-105">지원되는 모바일 장치 및 앱에 대한 조직의 전자 메일 및 문서에 대한 액세스를 Microsoft 365 모바일 장치 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="41cc3-106">장치를 분실하거나 도난 당한 경우 장치의 데이터를 원격으로 지워 중요한 조직 정보를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="41cc3-107">지원되는 장치</span><span class="sxs-lookup"><span data-stu-id="41cc3-107">Supported devices</span></span>

<span data-ttu-id="41cc3-108">기본 Mobility and Security를 사용하여 다음 장치를 보호하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="41cc3-109">iOS 11.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="41cc3-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="41cc3-110">Android 5.0 이상 버전<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="41cc3-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="41cc3-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="41cc3-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="41cc3-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="41cc3-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="41cc3-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="41cc3-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="41cc3-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="41cc3-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="41cc3-115"><sup>1</sup> RT Windows 8.1 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="41cc3-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="41cc3-116"><sup>2</sup> 액세스 제어를 Windows 10 제어하려면 Azure AD Premium 포함된 구독이 필요하며 디바이스를 앱에 가입해야 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41cc3-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="41cc3-117"><sup>3</sup> 2020년 6월 이후의 Android 버전은 Samsung Knox 장치를 제외한 암호 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

> [!NOTE]
> <span data-ttu-id="41cc3-118">이전 OS 버전에 이미 등록된 장치는 예고 없이 기능이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="41cc3-119">조직의 사용자가 기본 모바일 및 보안에서 지원되지 않는 모바일 장치를 사용하는 경우 조직의 데이터를 보다 안전하게 Exchange ActiveSync 전자 메일에 Microsoft 365 앱 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="41cc3-120">모바일 기능을 차단하는 Exchange ActiveSync 기본 이동성 및 보안에서 장치 액세스 [설정 관리를 참조하세요.](manage-device-access-settings.md)</span><span class="sxs-lookup"><span data-stu-id="41cc3-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="41cc3-121">전자 메일 및 Microsoft 365 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="41cc3-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="41cc3-122">다음 표에 있는 다양한 유형의 모바일 장치에 대해 지원되는 앱은 사용자가 기본 모바일 및 보안에 등록하라는 메시지를 표시하며, 여기서 사용자의 장치에 적용되는 새로운 모바일 장치 관리 정책이 있으며 사용자가 이전에 장치를 등록하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="41cc3-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="41cc3-123">사용자의 장치가 정책을 설정하는 방법에 따라 정책을 따르지 않는 경우 사용자가 이러한 앱의 Microsoft 365 리소스에 액세스하지 못하게 차단되거나 액세스 권한이 있지만 정책 위반을 보고하지 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="41cc3-124">**제품**</span><span class="sxs-lookup"><span data-stu-id="41cc3-124">**Product**</span></span>|<span data-ttu-id="41cc3-125">**iOS 10.0 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="41cc3-126">**Android 5.0 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-127">**Exchange** Exchange ActiveSync 버전 14.1 이상을 사용하는 TouchDown과 같은 기본 제공 전자 메일 및 타사 Exchange ActiveSync 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="41cc3-128">메일</span><span class="sxs-lookup"><span data-stu-id="41cc3-128">Mail</span></span> |<span data-ttu-id="41cc3-129">전자 메일</span><span class="sxs-lookup"><span data-stu-id="41cc3-129">Email</span></span> |
|<span data-ttu-id="41cc3-130">**Office**   및  **비즈니스용 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="41cc3-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="41cc3-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="41cc3-131">Outlook</span></span> </br><span data-ttu-id="41cc3-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="41cc3-132">OneDrive</span></span> </br><span data-ttu-id="41cc3-133">Word</span><span class="sxs-lookup"><span data-stu-id="41cc3-133">Word</span></span> </br><span data-ttu-id="41cc3-134">Excel</span><span class="sxs-lookup"><span data-stu-id="41cc3-134">Excel</span></span> </br><span data-ttu-id="41cc3-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="41cc3-135">PowerPoint</span></span>|<span data-ttu-id="41cc3-136">**휴대폰 및 태블릿의 경우**:</span><span class="sxs-lookup"><span data-stu-id="41cc3-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="41cc3-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="41cc3-137">Outlook</span></span> <br/> <span data-ttu-id="41cc3-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="41cc3-138">OneDrive</span></span> <br/> <span data-ttu-id="41cc3-139">Word</span><span class="sxs-lookup"><span data-stu-id="41cc3-139">Word</span></span> <br/> <span data-ttu-id="41cc3-140">Excel</span><span class="sxs-lookup"><span data-stu-id="41cc3-140">Excel</span></span> <br/> <span data-ttu-id="41cc3-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="41cc3-141">PowerPoint</span></span> <br/> <span data-ttu-id="41cc3-142">**휴대폰만 해당:**</span><span class="sxs-lookup"><span data-stu-id="41cc3-142">**On phones only:**</span></span> <br/> <span data-ttu-id="41cc3-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="41cc3-143">Office Mobile</span></span> |

> [!NOTE]
>
> - <span data-ttu-id="41cc3-144">iOS 10.0 이상 버전에 대한 지원에는 iPhone 및 iPad 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
> - <span data-ttu-id="41cc3-145">BlackBerry OS 디바이스 관리는 기본 보안 및 모바일에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="41cc3-146">BlackBerry의 BBCS(BlackBerry Business Cloud Services)를 사용하여 BlackBerry OS 장치를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="41cc3-147">Android OS를 실행하는 Blackberry 디바이스는 표준 Android 장치로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
> - <span data-ttu-id="41cc3-148">사용자가 모바일 브라우저를 사용하여 Microsoft 365 SharePoint 사이트, Office Online의 문서 또는 전자 메일에 액세스하는 경우 사용자에게 등록하라는 메시지가 표시되거나 정책 위반에 대해 차단되거나 Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="41cc3-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="41cc3-149">다음 다이어그램은 새 장치를 사용하는 사용자가 기본 Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인할 때 발생하는 일과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="41cc3-150">사용자가 디바이스를 등록할 때까지 Microsoft 365 리소스에 액세스하지 못하도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="기본 모바일 및 보안 액세스 제어":::

> [!NOTE]
> <span data-ttu-id="41cc3-152">기본 모바일 및 보안 for Microsoft 365 Business Standard 정책 및 액세스 규칙은 Exchange ActiveSync 관리 센터에서 만든 모바일 장치 사서함 정책 및 장치 액세스 Exchange 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="41cc3-153">기본 모바일 및 보안에 장치를 등록한 Microsoft 365 Business Standard 장치에 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="41cc3-154">자세한 내용은 Exchange ActiveSync 에서 Exchange ActiveSync [Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="41cc3-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="41cc3-155">모바일 장치에 대한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="41cc3-156">특정 설정이 켜져 있는 액세스를 차단하는 정책을 만들면 [Microsoft 365](capabilities.md)전자 메일 및 문서에 대한 액세스 제어에 나열된 지원되는 앱을 사용할 때 사용자가 Microsoft 365 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span>

<span data-ttu-id="41cc3-157">사용자가 리소스에 액세스하지 Microsoft 365 수 있는 설정은 다음 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="41cc3-158">보안</span><span class="sxs-lookup"><span data-stu-id="41cc3-158">Security</span></span>

- <span data-ttu-id="41cc3-159">암호화</span><span class="sxs-lookup"><span data-stu-id="41cc3-159">Encryption</span></span>

- <span data-ttu-id="41cc3-160">암호 해독</span><span class="sxs-lookup"><span data-stu-id="41cc3-160">Jail broken</span></span>

- <span data-ttu-id="41cc3-161">관리되는 전자 메일 프로필</span><span class="sxs-lookup"><span data-stu-id="41cc3-161">Managed email profile</span></span>

<span data-ttu-id="41cc3-162">예를 들어 다음 다이어그램에는 등록된 장치를 사용하는 사용자가 장치에 적용되는 모바일 장치 관리 정책의 보안 설정을 준수하지 않는 경우 수행되는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="41cc3-163">사용자는 Basic Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="41cc3-164">디바이스가 보안 설정을 준수할 때까지 Microsoft 365 리소스에 액세스하지 못하게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="기본 모바일 및 보안 준수 메시지":::

<span data-ttu-id="41cc3-166">다음 섹션에는 조직 리소스에 연결하는 모바일 장치를 보호하고 관리하는 데 사용할 수 있는 정책 Microsoft 365 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="41cc3-167">보안 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-167">Security settings</span></span>

|<span data-ttu-id="41cc3-168">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-168">**Setting name**</span></span>|<span data-ttu-id="41cc3-169">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-170">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-170">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-172">암호 필요</span><span class="sxs-lookup"><span data-stu-id="41cc3-172">Require a password</span></span>|<span data-ttu-id="41cc3-173">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-173">Yes</span></span>|<span data-ttu-id="41cc3-174">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-174">Yes</span></span>|<span data-ttu-id="41cc3-175">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-175">Yes</span></span>|
|<span data-ttu-id="41cc3-176">단순한 암호 금지</span><span class="sxs-lookup"><span data-stu-id="41cc3-176">Prevent simple password</span></span>|<span data-ttu-id="41cc3-177">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-177">Yes</span></span>|<span data-ttu-id="41cc3-178">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-178">No</span></span>|<span data-ttu-id="41cc3-179">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-179">No</span></span>|
|<span data-ttu-id="41cc3-180">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="41cc3-180">Require an alphanumeric password</span></span>|<span data-ttu-id="41cc3-181">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-181">Yes</span></span>|<span data-ttu-id="41cc3-182">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-182">No</span></span>|<span data-ttu-id="41cc3-183">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-183">No</span></span>|
|<span data-ttu-id="41cc3-184">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="41cc3-184">Minimum password length</span></span> |<span data-ttu-id="41cc3-185">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-185">Yes</span></span>|<span data-ttu-id="41cc3-186">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-186">Yes</span></span>|<span data-ttu-id="41cc3-187">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-187">Yes</span></span>|
|<span data-ttu-id="41cc3-188">장치 데이터를 지우기 전 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="41cc3-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="41cc3-189">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-189">Yes</span></span>|<span data-ttu-id="41cc3-190">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-190">Yes</span></span>|<span data-ttu-id="41cc3-191">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-191">Yes</span></span>|
|<span data-ttu-id="41cc3-192">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="41cc3-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="41cc3-193">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-193">Yes</span></span>|<span data-ttu-id="41cc3-194">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-194">Yes</span></span>|<span data-ttu-id="41cc3-195">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-195">Yes</span></span>|
|<span data-ttu-id="41cc3-196">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="41cc3-196">Password expiration (days)</span></span> |<span data-ttu-id="41cc3-197">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-197">Yes</span></span>|<span data-ttu-id="41cc3-198">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-198">Yes</span></span>|<span data-ttu-id="41cc3-199">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-199">Yes</span></span>|
|<span data-ttu-id="41cc3-200">암호 기록 기억 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="41cc3-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="41cc3-201">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-201">Yes</span></span>|<span data-ttu-id="41cc3-202">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-202">Yes</span></span>|<span data-ttu-id="41cc3-203">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="41cc3-204">암호화 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-204">Encryption settings</span></span>

|<span data-ttu-id="41cc3-205">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-205">**Setting name**</span></span>|<span data-ttu-id="41cc3-206">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-207">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-207">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-209">디바이스<sup>1에서</sup> 데이터 암호화 필요</span><span class="sxs-lookup"><span data-stu-id="41cc3-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="41cc3-210">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-210">No</span></span>|<span data-ttu-id="41cc3-211">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-211">Yes</span></span>|<span data-ttu-id="41cc3-212">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-212">Yes</span></span>|

<span data-ttu-id="41cc3-213"><sup>1</sup> Samsung Knox를 사용하면 저장소 카드에 암호화를 요구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span>

## <a name="jail-broken-setting"></a><span data-ttu-id="41cc3-214">암호 해독 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-214">Jail broken setting</span></span>

|<span data-ttu-id="41cc3-215">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-215">**Setting name**</span></span>|<span data-ttu-id="41cc3-216">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-217">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-217">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-219">장치의 암호를 해독하거나 장치를 루트 경로로 지정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="41cc3-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="41cc3-220">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-220">Yes</span></span>|<span data-ttu-id="41cc3-221">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-221">Yes</span></span>|<span data-ttu-id="41cc3-222">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="41cc3-223">관리되는 전자 메일 프로필 옵션</span><span class="sxs-lookup"><span data-stu-id="41cc3-223">Managed email profile option</span></span>

<span data-ttu-id="41cc3-224">다음 옵션은 사용자가 수동으로 만든 전자 메일 Microsoft 365 전자 메일에 액세스하지 못하게 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="41cc3-225">전자 메일에 액세스하려면 iOS 장치의 사용자가 수동으로 만든 전자 메일 프로필을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="41cc3-226">프로필을 삭제하면 디바이스에 새 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="41cc3-227">최종 사용자가 규정을 준수하는 방법에 대한 지침은 기존 전자 메일 계정을 [찾은 을 참조하세요.](/intune-user-help/existing-company-email-account-found)</span><span class="sxs-lookup"><span data-stu-id="41cc3-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="41cc3-228">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-228">**Setting name**</span></span>|<span data-ttu-id="41cc3-229">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-230">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-230">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-232">전자 메일 프로필이 관리됨</span><span class="sxs-lookup"><span data-stu-id="41cc3-232">Email profile is managed</span></span> |<span data-ttu-id="41cc3-233">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-233">Yes</span></span>|<span data-ttu-id="41cc3-234">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-234">No</span></span>|<span data-ttu-id="41cc3-235">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="41cc3-236">클라우드 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-236">Cloud settings</span></span>

|<span data-ttu-id="41cc3-237">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-237">**Setting name**</span></span>|<span data-ttu-id="41cc3-238">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-239">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-239">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-241">암호화된 백업 필요</span><span class="sxs-lookup"><span data-stu-id="41cc3-241">Require encrypted backup</span></span> |<span data-ttu-id="41cc3-242">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-242">Yes</span></span>|<span data-ttu-id="41cc3-243">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-243">No</span></span>|<span data-ttu-id="41cc3-244">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-244">No</span></span>|
|<span data-ttu-id="41cc3-245">클라우드 백업 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-245">Block cloud backup</span></span> |<span data-ttu-id="41cc3-246">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-246">Yes</span></span>|<span data-ttu-id="41cc3-247">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-247">No</span></span>|<span data-ttu-id="41cc3-248">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-248">No</span></span>|
|<span data-ttu-id="41cc3-249">문서 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-249">Block document synchronization</span></span> |<span data-ttu-id="41cc3-250">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-250">Yes</span></span>|<span data-ttu-id="41cc3-251">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-251">No</span></span>|<span data-ttu-id="41cc3-252">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-252">No</span></span>|
|<span data-ttu-id="41cc3-253">사진 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-253">Block photo synchronization</span></span>  |<span data-ttu-id="41cc3-254">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-254">Yes</span></span>|<span data-ttu-id="41cc3-255">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-255">No</span></span>|<span data-ttu-id="41cc3-256">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-256">No</span></span>|
|<span data-ttu-id="41cc3-257">Google 백업 허용</span><span class="sxs-lookup"><span data-stu-id="41cc3-257">Allow Google backup</span></span>  |<span data-ttu-id="41cc3-258">해당 없음</span><span class="sxs-lookup"><span data-stu-id="41cc3-258">N/A</span></span>|<span data-ttu-id="41cc3-259">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-259">No</span></span>|<span data-ttu-id="41cc3-260">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-260">Yes</span></span>|
|<span data-ttu-id="41cc3-261">Google 계정 자동 동기화 허용</span><span class="sxs-lookup"><span data-stu-id="41cc3-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="41cc3-262">해당 없음</span><span class="sxs-lookup"><span data-stu-id="41cc3-262">N/A</span></span>|<span data-ttu-id="41cc3-263">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-263">No</span></span>|<span data-ttu-id="41cc3-264">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="41cc3-265">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-265">System settings</span></span>

|<span data-ttu-id="41cc3-266">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-266">**Setting name**</span></span>|<span data-ttu-id="41cc3-267">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-268">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-268">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-270">화면 캡처 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-270">Block screen capture</span></span> |<span data-ttu-id="41cc3-271">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-271">Yes</span></span>|<span data-ttu-id="41cc3-272">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-272">No</span></span>|<span data-ttu-id="41cc3-273">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-273">Yes</span></span>|
|<span data-ttu-id="41cc3-274">장치에서 진단 데이터 전송 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="41cc3-275">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-275">Yes</span></span>|<span data-ttu-id="41cc3-276">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-276">No</span></span>|<span data-ttu-id="41cc3-277">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="41cc3-278">응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-278">Application settings</span></span>

|<span data-ttu-id="41cc3-279">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-279">**Setting name**</span></span>|<span data-ttu-id="41cc3-280">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-281">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-281">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-283">장치에서 비디오 회의 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-283">Block video conferences on device</span></span> |<span data-ttu-id="41cc3-284">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-284">Yes</span></span>|<span data-ttu-id="41cc3-285">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-285">No</span></span>|<span data-ttu-id="41cc3-286">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-286">No</span></span>|
|<span data-ttu-id="41cc3-287">응용 프로그램 저장소에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-287">Block access to application store</span></span> |<span data-ttu-id="41cc3-288">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-288">Yes</span></span>|<span data-ttu-id="41cc3-289">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-289">No</span></span>|<span data-ttu-id="41cc3-290">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-290">Yes</span></span>|
|<span data-ttu-id="41cc3-291">응용 프로그램 저장소에 액세스할 때 암호 필요</span><span class="sxs-lookup"><span data-stu-id="41cc3-291">Require password when accessing application store</span></span> |<span data-ttu-id="41cc3-292">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-292">No</span></span>|<span data-ttu-id="41cc3-293">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-293">Yes</span></span>|<span data-ttu-id="41cc3-294">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="41cc3-295">장치 기능 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-295">Device capabilities settings</span></span>

|<span data-ttu-id="41cc3-296">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-296">**Setting name**</span></span>|<span data-ttu-id="41cc3-297">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-298">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-298">**Android 5 and later**</span></span>|<span data-ttu-id="41cc3-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="41cc3-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-300">이동식 저장소와 연결 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-300">Block connection with removable storage</span></span> |<span data-ttu-id="41cc3-301">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-301">Yes</span></span>|<span data-ttu-id="41cc3-302">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-302">Yes</span></span>|<span data-ttu-id="41cc3-303">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-303">No</span></span>|
|<span data-ttu-id="41cc3-304">Bluetooth 연결 차단</span><span class="sxs-lookup"><span data-stu-id="41cc3-304">Block Bluetooth connection</span></span> |<span data-ttu-id="41cc3-305">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-305">Yes</span></span>|<span data-ttu-id="41cc3-306">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-306">Yes</span></span>|<span data-ttu-id="41cc3-307">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="41cc3-308">추가 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-308">Additional settings</span></span>

<span data-ttu-id="41cc3-309">보안 및 준수 센터 PowerShell cmdlet을 사용하여 다음과 같은 추가 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="41cc3-310">자세한 내용은 보안 및 [준수 & PowerShell을 참조하세요.](/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="41cc3-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="41cc3-311">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="41cc3-311">**Setting name**</span></span>|<span data-ttu-id="41cc3-312">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="41cc3-313">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="41cc3-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41cc3-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="41cc3-314">CameraEnabled</span></span>|<span data-ttu-id="41cc3-315">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-315">Yes</span></span>|<span data-ttu-id="41cc3-316">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-316">Yes</span></span>|
|<span data-ttu-id="41cc3-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="41cc3-317">RegionRatings</span></span>|<span data-ttu-id="41cc3-318">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-318">Yes</span></span>|<span data-ttu-id="41cc3-319">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-319">No</span></span>|
|<span data-ttu-id="41cc3-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="41cc3-320">MoviesRatings</span></span>|<span data-ttu-id="41cc3-321">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-321">Yes</span></span>|<span data-ttu-id="41cc3-322">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-322">No</span></span>|
|<span data-ttu-id="41cc3-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="41cc3-323">TVShowsRating</span></span> |<span data-ttu-id="41cc3-324">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-324">Yes</span></span>|<span data-ttu-id="41cc3-325">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-325">No</span></span>|
|<span data-ttu-id="41cc3-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="41cc3-326">AppsRatings</span></span> |<span data-ttu-id="41cc3-327">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-327">Yes</span></span>|<span data-ttu-id="41cc3-328">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-328">No</span></span>|
|<span data-ttu-id="41cc3-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="41cc3-329">AllowVoiceDialing</span></span> |<span data-ttu-id="41cc3-330">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-330">Yes</span></span>|<span data-ttu-id="41cc3-331">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-331">No</span></span>|
|<span data-ttu-id="41cc3-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="41cc3-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="41cc3-333">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-333">Yes</span></span>|<span data-ttu-id="41cc3-334">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-334">No</span></span>|
|<span data-ttu-id="41cc3-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="41cc3-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="41cc3-336">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-336">Yes</span></span>|<span data-ttu-id="41cc3-337">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-337">No</span></span>|
|<span data-ttu-id="41cc3-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="41cc3-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="41cc3-339">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-339">Yes</span></span>|<span data-ttu-id="41cc3-340">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-340">No</span></span>|
|<span data-ttu-id="41cc3-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="41cc3-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="41cc3-342">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-342">Yes</span></span>|<span data-ttu-id="41cc3-343">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-343">No</span></span>|
|<span data-ttu-id="41cc3-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="41cc3-344">PasswordQuality</span></span> |<span data-ttu-id="41cc3-345">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-345">No</span></span>|<span data-ttu-id="41cc3-346">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-346">Yes</span></span>|
|<span data-ttu-id="41cc3-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="41cc3-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="41cc3-348">예</span><span class="sxs-lookup"><span data-stu-id="41cc3-348">Yes</span></span>|<span data-ttu-id="41cc3-349">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-349">No</span></span>|
|<span data-ttu-id="41cc3-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="41cc3-350">WLANEnabled</span></span>  |<span data-ttu-id="41cc3-351">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-351">No</span></span>|<span data-ttu-id="41cc3-352">아니요</span><span class="sxs-lookup"><span data-stu-id="41cc3-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="41cc3-353">설정 지원되는 Windows</span><span class="sxs-lookup"><span data-stu-id="41cc3-353">Settings supported by Windows</span></span>

<span data-ttu-id="41cc3-354">모바일 장치로 Windows 10 등록하여 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="41cc3-355">적용 가능한 정책을 배포한 후 Windows 10 장치를 사용하는 사용자는 기본 제공 전자 메일 앱을 처음 사용하여 Microsoft 365 전자 메일에 액세스할 때 기본 이동성 및 보안에 등록해야 합니다(Azure AD Premium 구독 필요).</span><span class="sxs-lookup"><span data-stu-id="41cc3-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="41cc3-356">모바일 장치로 등록된 Windows 10 다음 설정이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="41cc3-357">이러한 설정은 사용자가 리소스에 액세스하는 Microsoft 365 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="41cc3-358">보안 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-358">Security settings</span></span>

- <span data-ttu-id="41cc3-359">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="41cc3-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="41cc3-360">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="41cc3-360">Minimum password length</span></span>

- <span data-ttu-id="41cc3-361">장치 데이터가 지워지기 전 로그인 오류 횟수</span><span class="sxs-lookup"><span data-stu-id="41cc3-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="41cc3-362">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="41cc3-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="41cc3-363">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="41cc3-363">Password expiration (days)</span></span>

- <span data-ttu-id="41cc3-364">암호 기록 저장 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="41cc3-364">Remember password history and prevent reuse</span></span>

> [!NOTE]
> <span data-ttu-id="41cc3-365">암호를 제어하는 다음 설정은 로컬 계정만 Windows 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="41cc3-366">Windows 또는 도메인 가입을 통해 제공된 Azure Active Directory 이러한 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="41cc3-367">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-367">System settings</span></span>

<span data-ttu-id="41cc3-368">장치에서 진단 데이터 전송을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="41cc3-369">추가 설정</span><span class="sxs-lookup"><span data-stu-id="41cc3-369">Additional settings</span></span>

<span data-ttu-id="41cc3-370">PowerShell cmdlet을 사용하여 이러한 추가 정책 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="41cc3-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="41cc3-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="41cc3-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="41cc3-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="41cc3-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="41cc3-373">FirewallStatus</span></span>

- <span data-ttu-id="41cc3-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="41cc3-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="41cc3-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="41cc3-375">AntiVirusStatus</span></span>

- <span data-ttu-id="41cc3-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="41cc3-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="41cc3-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="41cc3-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="41cc3-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="41cc3-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="41cc3-379">원격으로 모바일 장치의 데이터 지우기</span><span class="sxs-lookup"><span data-stu-id="41cc3-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="41cc3-380">장치를 분실하거나 도난당한 경우 보안 및 준수 센터의 데이터 손실 방지 장치 관리에서 Microsoft 365 & 데이터 손실 방지 > 데이터 지우기를 수행하여 중요한 조직 데이터를 제거하고 Microsoft 365 조직 리소스에 대한 액세스를 방지할 수   >  있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="41cc3-381">선택적 지우기를 수행하여 조직 데이터만 제거하거나, 전체 지우기를 수행하여 장치에서 모든 정보를 삭제하고 장치를 처음 출시될 때의 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc3-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="41cc3-382">자세한 내용은 Basic Mobility and Security에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="41cc3-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="41cc3-383">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="41cc3-383">Related content</span></span>

<span data-ttu-id="41cc3-384">[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)</span><span class="sxs-lookup"><span data-stu-id="41cc3-384">[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)</span></span>\
<span data-ttu-id="41cc3-385">[기본 모바일 및 보안에서](create-device-security-policies.md) 장치 보안 정책 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="41cc3-385">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>