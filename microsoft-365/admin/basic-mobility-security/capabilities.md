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
ms.openlocfilehash: 41df5bfba7362d9c2b3a47deca4e4586902bbd98
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706181"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="2c954-103">기본 이동성 및 보안 기능</span><span class="sxs-lookup"><span data-stu-id="2c954-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="2c954-104">기본 모바일 및 보안을 사용하면 조직의 라이선스가 있는 사용자가 사용하는 iPhone, iPad, Androids 및 Windows 휴대폰과 같은 모바일 Microsoft 365 보호하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="2c954-105">지원되는 모바일 장치 및 앱에 대한 조직의 전자 메일 및 문서에 대한 액세스를 Microsoft 365 모바일 장치 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="2c954-106">장치를 분실하거나 도난 당한 경우 장치의 데이터를 원격으로 지워 중요한 조직 정보를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="2c954-107">지원되는 장치</span><span class="sxs-lookup"><span data-stu-id="2c954-107">Supported devices</span></span>

<span data-ttu-id="2c954-108">기본 Mobility and Security를 사용하여 다음 장치를 보호하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="2c954-109">iOS 11.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="2c954-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="2c954-110">Android 5.0 이상 버전<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2c954-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="2c954-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2c954-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="2c954-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2c954-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="2c954-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2c954-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="2c954-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2c954-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="2c954-115"><sup>1</sup> RT Windows 8.1 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="2c954-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="2c954-116"><sup>2</sup> 액세스 제어를 Windows 10 Azure AD Premium 구독이 필요하며 디바이스를 앱에 가입해야 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c954-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="2c954-117"><sup>3</sup> 2020년 6월 이후의 Android 버전은 Samsung Knox 장치를 제외한 암호 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="2c954-118">이전 OS 버전에 이미 등록된 장치는 예고 없이 기능이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="2c954-119">조직의 사용자가 기본 모바일 및 보안에서 지원되지 않는 모바일 장치를 사용하는 경우 조직의 데이터를 보다 안전하게 Exchange ActiveSync 전자 메일에 Microsoft 365 앱 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="2c954-120">모바일 기능을 차단하는 Exchange ActiveSync 기본 이동성 및 보안에서 장치 액세스 [설정 관리를 참조하세요.](manage-device-access-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2c954-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="2c954-121">전자 메일 및 Microsoft 365 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="2c954-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="2c954-122">다음 표에 있는 다양한 유형의 모바일 장치에 대해 지원되는 앱은 사용자가 기본 모바일 및 보안에 등록하라는 메시지를 표시하며, 여기서 사용자의 장치에 적용되는 새로운 모바일 장치 관리 정책이 있으며 사용자가 이전에 장치를 등록하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="2c954-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="2c954-123">사용자의 장치가 정책을 설정하는 방법에 따라 정책을 따르지 않는 경우 사용자가 이러한 앱의 Microsoft 365 리소스에 액세스하지 못하게 차단되거나 액세스 권한이 있지만 정책 위반을 보고하지 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="2c954-124">**제품**</span><span class="sxs-lookup"><span data-stu-id="2c954-124">**Product**</span></span>|<span data-ttu-id="2c954-125">**iOS 10.0 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="2c954-126">**Android 5.0 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c954-127">**Exchange** Exchange ActiveSync 버전 14.1 이상을 사용하는 TouchDown과 같은 기본 제공 전자 메일 및 타사 Exchange ActiveSync 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="2c954-128">메일</span><span class="sxs-lookup"><span data-stu-id="2c954-128">Mail</span></span> |<span data-ttu-id="2c954-129">전자 메일</span><span class="sxs-lookup"><span data-stu-id="2c954-129">Email</span></span> |
|<span data-ttu-id="2c954-130">**Office**   및  **비즈니스용 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="2c954-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="2c954-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="2c954-131">Outlook</span></span> </br><span data-ttu-id="2c954-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2c954-132">OneDrive</span></span> </br><span data-ttu-id="2c954-133">Word</span><span class="sxs-lookup"><span data-stu-id="2c954-133">Word</span></span> </br><span data-ttu-id="2c954-134">Excel</span><span class="sxs-lookup"><span data-stu-id="2c954-134">Excel</span></span> </br><span data-ttu-id="2c954-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2c954-135">PowerPoint</span></span>|<span data-ttu-id="2c954-136">**휴대폰 및 태블릿의 경우**:</span><span class="sxs-lookup"><span data-stu-id="2c954-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="2c954-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="2c954-137">Outlook</span></span> <br/> <span data-ttu-id="2c954-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2c954-138">OneDrive</span></span> <br/> <span data-ttu-id="2c954-139">Word</span><span class="sxs-lookup"><span data-stu-id="2c954-139">Word</span></span> <br/> <span data-ttu-id="2c954-140">Excel</span><span class="sxs-lookup"><span data-stu-id="2c954-140">Excel</span></span> <br/> <span data-ttu-id="2c954-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2c954-141">PowerPoint</span></span> <br/> <span data-ttu-id="2c954-142">**휴대폰만 해당:**</span><span class="sxs-lookup"><span data-stu-id="2c954-142">**On phones only:**</span></span> <br/> <span data-ttu-id="2c954-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="2c954-143">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="2c954-144">iOS 10.0 이상 버전에 대한 지원에는 iPhone 및 iPad 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="2c954-145">BlackBerry OS 디바이스 관리는 기본 보안 및 모바일에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="2c954-146">BlackBerry의 BBCS(BlackBerry Business Cloud Services)를 사용하여 BlackBerry OS 장치를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="2c954-147">Android OS를 실행하는 Blackberry 디바이스는 표준 Android 장치로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="2c954-148">사용자가 모바일 브라우저를 사용하여 Microsoft 365 SharePoint 사이트, Office Online의 문서 또는 전자 메일에 액세스하는 경우 사용자에게 등록하라는 메시지가 표시되거나 정책 위반에 대해 차단되거나 Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="2c954-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="2c954-149">다음 다이어그램은 새 장치를 사용하는 사용자가 기본 Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인할 때 발생하는 일과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="2c954-150">사용자가 디바이스를 등록할 때까지 Microsoft 365 리소스에 액세스하지 못하도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="기본 모바일 및 보안 액세스 제어":::

> [!NOTE]
> <span data-ttu-id="2c954-152">기본 모바일 및 보안 for Microsoft 365 Business Standard 정책 및 액세스 규칙은 Exchange ActiveSync 관리 센터에서 만든 모바일 장치 사서함 정책 및 장치 액세스 Exchange 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="2c954-153">기본 모바일 및 보안에 장치를 등록한 Microsoft 365 Business Standard 장치에 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="2c954-154">자세한 내용은 Exchange ActiveSync 에서 Exchange ActiveSync [Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="2c954-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="2c954-155">모바일 장치에 대한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="2c954-156">특정 설정이 켜져 있는 액세스를 차단하는 정책을 만들면 [Microsoft 365](capabilities.md)전자 메일 및 문서에 대한 액세스 제어에 나열된 지원되는 앱을 사용할 때 사용자가 Microsoft 365 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="2c954-157">사용자가 리소스에 액세스하지 Microsoft 365 수 있는 설정은 다음 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="2c954-158">보안</span><span class="sxs-lookup"><span data-stu-id="2c954-158">Security</span></span>

- <span data-ttu-id="2c954-159">암호화</span><span class="sxs-lookup"><span data-stu-id="2c954-159">Encryption</span></span>

- <span data-ttu-id="2c954-160">암호 해독</span><span class="sxs-lookup"><span data-stu-id="2c954-160">Jail broken</span></span>

- <span data-ttu-id="2c954-161">관리되는 전자 메일 프로필</span><span class="sxs-lookup"><span data-stu-id="2c954-161">Managed email profile</span></span>  

<span data-ttu-id="2c954-162">예를 들어 다음 다이어그램에는 등록된 장치를 사용하는 사용자가 장치에 적용되는 모바일 장치 관리 정책의 보안 설정을 준수하지 않는 경우 수행되는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="2c954-163">사용자는 Basic Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="2c954-164">디바이스가 보안 설정을 준수할 때까지 Microsoft 365 리소스에 액세스하지 못하게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="기본 모바일 및 보안 준수 메시지":::

<span data-ttu-id="2c954-166">다음 섹션에는 조직 리소스에 연결하는 모바일 장치를 보호하고 관리하는 데 사용할 수 있는 정책 Microsoft 365 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="2c954-167">보안 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-167">Security settings</span></span>

|<span data-ttu-id="2c954-168">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-168">**Setting name**</span></span>|<span data-ttu-id="2c954-169">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-170">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-170">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-172">암호 필요</span><span class="sxs-lookup"><span data-stu-id="2c954-172">Require a password</span></span>|<span data-ttu-id="2c954-173">예</span><span class="sxs-lookup"><span data-stu-id="2c954-173">Yes</span></span>|<span data-ttu-id="2c954-174">예</span><span class="sxs-lookup"><span data-stu-id="2c954-174">Yes</span></span>|<span data-ttu-id="2c954-175">예</span><span class="sxs-lookup"><span data-stu-id="2c954-175">Yes</span></span>|
|<span data-ttu-id="2c954-176">단순한 암호 금지</span><span class="sxs-lookup"><span data-stu-id="2c954-176">Prevent simple password</span></span>|<span data-ttu-id="2c954-177">예</span><span class="sxs-lookup"><span data-stu-id="2c954-177">Yes</span></span>|<span data-ttu-id="2c954-178">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-178">No</span></span>|<span data-ttu-id="2c954-179">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-179">No</span></span>|
|<span data-ttu-id="2c954-180">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="2c954-180">Require an alphanumeric password</span></span>|<span data-ttu-id="2c954-181">예</span><span class="sxs-lookup"><span data-stu-id="2c954-181">Yes</span></span>|<span data-ttu-id="2c954-182">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-182">No</span></span>|<span data-ttu-id="2c954-183">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-183">No</span></span>|
|<span data-ttu-id="2c954-184">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="2c954-184">Minimum password length</span></span> |<span data-ttu-id="2c954-185">예</span><span class="sxs-lookup"><span data-stu-id="2c954-185">Yes</span></span>|<span data-ttu-id="2c954-186">예</span><span class="sxs-lookup"><span data-stu-id="2c954-186">Yes</span></span>|<span data-ttu-id="2c954-187">예</span><span class="sxs-lookup"><span data-stu-id="2c954-187">Yes</span></span>|
|<span data-ttu-id="2c954-188">장치 데이터를 지우기 전 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="2c954-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="2c954-189">예</span><span class="sxs-lookup"><span data-stu-id="2c954-189">Yes</span></span>|<span data-ttu-id="2c954-190">예</span><span class="sxs-lookup"><span data-stu-id="2c954-190">Yes</span></span>|<span data-ttu-id="2c954-191">예</span><span class="sxs-lookup"><span data-stu-id="2c954-191">Yes</span></span>|
|<span data-ttu-id="2c954-192">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="2c954-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="2c954-193">예</span><span class="sxs-lookup"><span data-stu-id="2c954-193">Yes</span></span>|<span data-ttu-id="2c954-194">예</span><span class="sxs-lookup"><span data-stu-id="2c954-194">Yes</span></span>|<span data-ttu-id="2c954-195">예</span><span class="sxs-lookup"><span data-stu-id="2c954-195">Yes</span></span>|
|<span data-ttu-id="2c954-196">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="2c954-196">Password expiration (days)</span></span> |<span data-ttu-id="2c954-197">예</span><span class="sxs-lookup"><span data-stu-id="2c954-197">Yes</span></span>|<span data-ttu-id="2c954-198">예</span><span class="sxs-lookup"><span data-stu-id="2c954-198">Yes</span></span>|<span data-ttu-id="2c954-199">예</span><span class="sxs-lookup"><span data-stu-id="2c954-199">Yes</span></span>|
|<span data-ttu-id="2c954-200">암호 기록 기억 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="2c954-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="2c954-201">예</span><span class="sxs-lookup"><span data-stu-id="2c954-201">Yes</span></span>|<span data-ttu-id="2c954-202">예</span><span class="sxs-lookup"><span data-stu-id="2c954-202">Yes</span></span>|<span data-ttu-id="2c954-203">예</span><span class="sxs-lookup"><span data-stu-id="2c954-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="2c954-204">암호화 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-204">Encryption settings</span></span>

|<span data-ttu-id="2c954-205">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-205">**Setting name**</span></span>|<span data-ttu-id="2c954-206">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-207">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-207">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-209">디바이스<sup>1에서</sup> 데이터 암호화 필요</span><span class="sxs-lookup"><span data-stu-id="2c954-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="2c954-210">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-210">No</span></span>|<span data-ttu-id="2c954-211">예</span><span class="sxs-lookup"><span data-stu-id="2c954-211">Yes</span></span>|<span data-ttu-id="2c954-212">예</span><span class="sxs-lookup"><span data-stu-id="2c954-212">Yes</span></span>|

<span data-ttu-id="2c954-213"><sup>1</sup> Samsung Knox를 사용하면 저장소 카드에 암호화를 요구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="2c954-214">암호 해독 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-214">Jail broken setting</span></span> 

|<span data-ttu-id="2c954-215">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-215">**Setting name**</span></span>|<span data-ttu-id="2c954-216">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-217">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-217">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-219">장치의 암호를 해독하거나 장치를 루트 경로로 지정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="2c954-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="2c954-220">예</span><span class="sxs-lookup"><span data-stu-id="2c954-220">Yes</span></span>|<span data-ttu-id="2c954-221">예</span><span class="sxs-lookup"><span data-stu-id="2c954-221">Yes</span></span>|<span data-ttu-id="2c954-222">예</span><span class="sxs-lookup"><span data-stu-id="2c954-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="2c954-223">관리되는 전자 메일 프로필 옵션</span><span class="sxs-lookup"><span data-stu-id="2c954-223">Managed email profile option</span></span> 

<span data-ttu-id="2c954-224">다음 옵션은 사용자가 수동으로 만든 전자 메일 Microsoft 365 전자 메일에 액세스하지 못하게 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="2c954-225">전자 메일에 액세스하려면 iOS 장치의 사용자가 수동으로 만든 전자 메일 프로필을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="2c954-226">프로필을 삭제하면 디바이스에 새 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="2c954-227">최종 사용자가 규정을 준수하는 방법에 대한 지침은 기존 전자 메일 계정을 [찾은 을 참조하세요.](/intune-user-help/existing-company-email-account-found)</span><span class="sxs-lookup"><span data-stu-id="2c954-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="2c954-228">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-228">**Setting name**</span></span>|<span data-ttu-id="2c954-229">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-230">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-230">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-232">전자 메일 프로필이 관리됨</span><span class="sxs-lookup"><span data-stu-id="2c954-232">Email profile is managed</span></span> |<span data-ttu-id="2c954-233">예</span><span class="sxs-lookup"><span data-stu-id="2c954-233">Yes</span></span>|<span data-ttu-id="2c954-234">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-234">No</span></span>|<span data-ttu-id="2c954-235">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="2c954-236">클라우드 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-236">Cloud settings</span></span>

|<span data-ttu-id="2c954-237">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-237">**Setting name**</span></span>|<span data-ttu-id="2c954-238">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-239">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-239">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-241">암호화된 백업 필요</span><span class="sxs-lookup"><span data-stu-id="2c954-241">Require encrypted backup</span></span> |<span data-ttu-id="2c954-242">예</span><span class="sxs-lookup"><span data-stu-id="2c954-242">Yes</span></span>|<span data-ttu-id="2c954-243">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-243">No</span></span>|<span data-ttu-id="2c954-244">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-244">No</span></span>|
|<span data-ttu-id="2c954-245">클라우드 백업 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-245">Block cloud backup</span></span> |<span data-ttu-id="2c954-246">예</span><span class="sxs-lookup"><span data-stu-id="2c954-246">Yes</span></span>|<span data-ttu-id="2c954-247">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-247">No</span></span>|<span data-ttu-id="2c954-248">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-248">No</span></span>|
|<span data-ttu-id="2c954-249">문서 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-249">Block document synchronization</span></span> |<span data-ttu-id="2c954-250">예</span><span class="sxs-lookup"><span data-stu-id="2c954-250">Yes</span></span>|<span data-ttu-id="2c954-251">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-251">No</span></span>|<span data-ttu-id="2c954-252">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-252">No</span></span>|
|<span data-ttu-id="2c954-253">사진 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-253">Block photo synchronization</span></span>  |<span data-ttu-id="2c954-254">예</span><span class="sxs-lookup"><span data-stu-id="2c954-254">Yes</span></span>|<span data-ttu-id="2c954-255">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-255">No</span></span>|<span data-ttu-id="2c954-256">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-256">No</span></span>|
|<span data-ttu-id="2c954-257">Google 백업 허용</span><span class="sxs-lookup"><span data-stu-id="2c954-257">Allow Google backup</span></span>  |<span data-ttu-id="2c954-258">해당 없음</span><span class="sxs-lookup"><span data-stu-id="2c954-258">N/A</span></span>|<span data-ttu-id="2c954-259">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-259">No</span></span>|<span data-ttu-id="2c954-260">예</span><span class="sxs-lookup"><span data-stu-id="2c954-260">Yes</span></span>|
|<span data-ttu-id="2c954-261">Google 계정 자동 동기화 허용</span><span class="sxs-lookup"><span data-stu-id="2c954-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="2c954-262">해당 없음</span><span class="sxs-lookup"><span data-stu-id="2c954-262">N/A</span></span>|<span data-ttu-id="2c954-263">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-263">No</span></span>|<span data-ttu-id="2c954-264">예</span><span class="sxs-lookup"><span data-stu-id="2c954-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="2c954-265">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-265">System settings</span></span>

|<span data-ttu-id="2c954-266">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-266">**Setting name**</span></span>|<span data-ttu-id="2c954-267">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-268">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-268">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-270">화면 캡처 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-270">Block screen capture</span></span> |<span data-ttu-id="2c954-271">예</span><span class="sxs-lookup"><span data-stu-id="2c954-271">Yes</span></span>|<span data-ttu-id="2c954-272">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-272">No</span></span>|<span data-ttu-id="2c954-273">예</span><span class="sxs-lookup"><span data-stu-id="2c954-273">Yes</span></span>|
|<span data-ttu-id="2c954-274">장치에서 진단 데이터 전송 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="2c954-275">예</span><span class="sxs-lookup"><span data-stu-id="2c954-275">Yes</span></span>|<span data-ttu-id="2c954-276">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-276">No</span></span>|<span data-ttu-id="2c954-277">예</span><span class="sxs-lookup"><span data-stu-id="2c954-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="2c954-278">응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-278">Application settings</span></span>

|<span data-ttu-id="2c954-279">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-279">**Setting name**</span></span>|<span data-ttu-id="2c954-280">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-281">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-281">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-283">장치에서 비디오 회의 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-283">Block video conferences on device</span></span> |<span data-ttu-id="2c954-284">예</span><span class="sxs-lookup"><span data-stu-id="2c954-284">Yes</span></span>|<span data-ttu-id="2c954-285">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-285">No</span></span>|<span data-ttu-id="2c954-286">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-286">No</span></span>|
|<span data-ttu-id="2c954-287">응용 프로그램 저장소에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-287">Block access to application store</span></span> |<span data-ttu-id="2c954-288">예</span><span class="sxs-lookup"><span data-stu-id="2c954-288">Yes</span></span>|<span data-ttu-id="2c954-289">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-289">No</span></span>|<span data-ttu-id="2c954-290">예</span><span class="sxs-lookup"><span data-stu-id="2c954-290">Yes</span></span>|
|<span data-ttu-id="2c954-291">응용 프로그램 저장소에 액세스할 때 암호 필요</span><span class="sxs-lookup"><span data-stu-id="2c954-291">Require password when accessing application store</span></span> |<span data-ttu-id="2c954-292">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-292">No</span></span>|<span data-ttu-id="2c954-293">예</span><span class="sxs-lookup"><span data-stu-id="2c954-293">Yes</span></span>|<span data-ttu-id="2c954-294">예</span><span class="sxs-lookup"><span data-stu-id="2c954-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="2c954-295">장치 기능 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-295">Device capabilities settings</span></span>

|<span data-ttu-id="2c954-296">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-296">**Setting name**</span></span>|<span data-ttu-id="2c954-297">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-298">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-298">**Android 5 and later**</span></span>|<span data-ttu-id="2c954-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2c954-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c954-300">이동식 저장소와 연결 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-300">Block connection with removable storage</span></span> |<span data-ttu-id="2c954-301">예</span><span class="sxs-lookup"><span data-stu-id="2c954-301">Yes</span></span>|<span data-ttu-id="2c954-302">예</span><span class="sxs-lookup"><span data-stu-id="2c954-302">Yes</span></span>|<span data-ttu-id="2c954-303">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-303">No</span></span>|
|<span data-ttu-id="2c954-304">Bluetooth 연결 차단</span><span class="sxs-lookup"><span data-stu-id="2c954-304">Block Bluetooth connection</span></span> |<span data-ttu-id="2c954-305">예</span><span class="sxs-lookup"><span data-stu-id="2c954-305">Yes</span></span>|<span data-ttu-id="2c954-306">예</span><span class="sxs-lookup"><span data-stu-id="2c954-306">Yes</span></span>|<span data-ttu-id="2c954-307">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="2c954-308">추가 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-308">Additional settings</span></span>

<span data-ttu-id="2c954-309">보안 및 준수 센터 PowerShell cmdlet을 사용하여 다음과 같은 추가 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="2c954-310">자세한 내용은 보안 및 [준수 & PowerShell을 참조하세요.](/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="2c954-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="2c954-311">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="2c954-311">**Setting name**</span></span>|<span data-ttu-id="2c954-312">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2c954-313">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="2c954-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c954-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="2c954-314">CameraEnabled</span></span>|<span data-ttu-id="2c954-315">예</span><span class="sxs-lookup"><span data-stu-id="2c954-315">Yes</span></span>|<span data-ttu-id="2c954-316">예</span><span class="sxs-lookup"><span data-stu-id="2c954-316">Yes</span></span>|
|<span data-ttu-id="2c954-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="2c954-317">RegionRatings</span></span>|<span data-ttu-id="2c954-318">예</span><span class="sxs-lookup"><span data-stu-id="2c954-318">Yes</span></span>|<span data-ttu-id="2c954-319">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-319">No</span></span>|
|<span data-ttu-id="2c954-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="2c954-320">MoviesRatings</span></span>|<span data-ttu-id="2c954-321">예</span><span class="sxs-lookup"><span data-stu-id="2c954-321">Yes</span></span>|<span data-ttu-id="2c954-322">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-322">No</span></span>|
|<span data-ttu-id="2c954-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="2c954-323">TVShowsRating</span></span> |<span data-ttu-id="2c954-324">예</span><span class="sxs-lookup"><span data-stu-id="2c954-324">Yes</span></span>|<span data-ttu-id="2c954-325">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-325">No</span></span>|
|<span data-ttu-id="2c954-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="2c954-326">AppsRatings</span></span> |<span data-ttu-id="2c954-327">예</span><span class="sxs-lookup"><span data-stu-id="2c954-327">Yes</span></span>|<span data-ttu-id="2c954-328">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-328">No</span></span>|
|<span data-ttu-id="2c954-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="2c954-329">AllowVoiceDialing</span></span> |<span data-ttu-id="2c954-330">예</span><span class="sxs-lookup"><span data-stu-id="2c954-330">Yes</span></span>|<span data-ttu-id="2c954-331">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-331">No</span></span>|
|<span data-ttu-id="2c954-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="2c954-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="2c954-333">예</span><span class="sxs-lookup"><span data-stu-id="2c954-333">Yes</span></span>|<span data-ttu-id="2c954-334">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-334">No</span></span>|
|<span data-ttu-id="2c954-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="2c954-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="2c954-336">예</span><span class="sxs-lookup"><span data-stu-id="2c954-336">Yes</span></span>|<span data-ttu-id="2c954-337">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-337">No</span></span>|
|<span data-ttu-id="2c954-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="2c954-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="2c954-339">예</span><span class="sxs-lookup"><span data-stu-id="2c954-339">Yes</span></span>|<span data-ttu-id="2c954-340">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-340">No</span></span>|
|<span data-ttu-id="2c954-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="2c954-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="2c954-342">예</span><span class="sxs-lookup"><span data-stu-id="2c954-342">Yes</span></span>|<span data-ttu-id="2c954-343">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-343">No</span></span>|
|<span data-ttu-id="2c954-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="2c954-344">PasswordQuality</span></span> |<span data-ttu-id="2c954-345">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-345">No</span></span>|<span data-ttu-id="2c954-346">예</span><span class="sxs-lookup"><span data-stu-id="2c954-346">Yes</span></span>|
|<span data-ttu-id="2c954-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="2c954-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="2c954-348">예</span><span class="sxs-lookup"><span data-stu-id="2c954-348">Yes</span></span>|<span data-ttu-id="2c954-349">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-349">No</span></span>|
|<span data-ttu-id="2c954-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="2c954-350">WLANEnabled</span></span>  |<span data-ttu-id="2c954-351">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-351">No</span></span>|<span data-ttu-id="2c954-352">아니요</span><span class="sxs-lookup"><span data-stu-id="2c954-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="2c954-353">설정 지원되는 Windows</span><span class="sxs-lookup"><span data-stu-id="2c954-353">Settings supported by Windows</span></span>

<span data-ttu-id="2c954-354">모바일 장치로 Windows 10 등록하여 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="2c954-355">적용 가능한 정책을 배포한 후 Windows 10 장치를 사용하는 사용자는 기본 제공 전자 메일 앱을 처음 사용하여 Microsoft 365 전자 메일에 액세스할 때 기본 이동성 및 보안에 등록해야 합니다(Azure AD Premium 구독 필요).</span><span class="sxs-lookup"><span data-stu-id="2c954-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="2c954-356">모바일 장치로 등록된 Windows 10 다음 설정이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="2c954-357">이러한 설정은 사용자가 리소스에 액세스하는 Microsoft 365 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="2c954-358">보안 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-358">Security settings</span></span>

- <span data-ttu-id="2c954-359">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="2c954-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="2c954-360">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="2c954-360">Minimum password length</span></span>

- <span data-ttu-id="2c954-361">장치 데이터가 지워지기 전 로그인 오류 횟수</span><span class="sxs-lookup"><span data-stu-id="2c954-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="2c954-362">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="2c954-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="2c954-363">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="2c954-363">Password expiration (days)</span></span>

- <span data-ttu-id="2c954-364">암호 기록 저장 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="2c954-364">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="2c954-365">암호를 제어하는 다음 설정은 로컬 계정만 Windows 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="2c954-366">Windows 또는 도메인 가입을 통해 제공된 Azure Active Directory 이러한 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="2c954-367">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-367">System settings</span></span>

<span data-ttu-id="2c954-368">장치에서 진단 데이터 전송을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="2c954-369">추가 설정</span><span class="sxs-lookup"><span data-stu-id="2c954-369">Additional settings</span></span>

<span data-ttu-id="2c954-370">PowerShell cmdlet을 사용하여 이러한 추가 정책 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="2c954-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="2c954-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="2c954-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="2c954-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="2c954-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="2c954-373">FirewallStatus</span></span>

- <span data-ttu-id="2c954-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="2c954-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="2c954-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="2c954-375">AntiVirusStatus</span></span>

- <span data-ttu-id="2c954-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="2c954-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="2c954-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="2c954-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="2c954-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="2c954-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="2c954-379">원격으로 모바일 장치의 데이터 지우기</span><span class="sxs-lookup"><span data-stu-id="2c954-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="2c954-380">장치를 분실하거나 도난당한 경우 보안 및 준수 센터의 데이터 손실 방지 장치 관리에서 Microsoft 365 & 데이터 손실 방지 > 데이터 지우기를 수행하여 중요한 조직 데이터를 제거하고 Microsoft 365 조직 리소스에 대한 액세스를 방지할 수   >  있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="2c954-381">선택적 지우기를 수행하여 조직 데이터만 제거하거나, 전체 지우기를 수행하여 장치에서 모든 정보를 삭제하고 장치를 처음 출시될 때의 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2c954-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="2c954-382">자세한 내용은 Basic Mobility and Security에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="2c954-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="2c954-383">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="2c954-383">Related content</span></span>

<span data-ttu-id="2c954-384">[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)</span><span class="sxs-lookup"><span data-stu-id="2c954-384">[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)</span></span>\
<span data-ttu-id="2c954-385">[기본 모바일 및 보안에서](create-device-security-policies.md) 장치 보안 정책 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="2c954-385">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>