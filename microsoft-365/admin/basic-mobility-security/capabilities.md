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
ms.openlocfilehash: 746131e90e207d7b888a3ddcaf4ff0656606a2c7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877119"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="841bc-103">기본 이동성 및 보안 기능</span><span class="sxs-lookup"><span data-stu-id="841bc-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="841bc-104">기본 모바일 및 보안을 사용하면 조직의 라이선스가 부여된 Microsoft 365 사용자가 사용하는 iPhone, iPad, Android 및 Windows Phone과 같은 모바일 장치를 보호하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="841bc-105">지원되는 모바일 장치 및 앱에 대한 조직의 Microsoft 365 전자 메일 및 문서에 대한 액세스를 제어하는 데 도움이 되는 설정을 사용하여 모바일 장치 관리 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="841bc-106">장치를 분실하거나 도난 당한 경우 장치의 데이터를 원격으로 지워 중요한 조직 정보를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="841bc-107">지원되는 장치</span><span class="sxs-lookup"><span data-stu-id="841bc-107">Supported devices</span></span>

<span data-ttu-id="841bc-108">기본 이동성 및 보안을 사용하여 다음 장치를 보호하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="841bc-109">iOS 11.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="841bc-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="841bc-110">Android 5.0 이상 버전<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="841bc-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="841bc-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="841bc-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="841bc-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="841bc-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="841bc-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="841bc-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="841bc-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="841bc-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="841bc-115"><sup>1</sup> Windows 8.1 RT 장치에 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="841bc-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="841bc-116"><sup>2</sup> Windows 8.1 RT 장치에 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="841bc-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="841bc-117">Windows 10에 대한 액세스 제어를 사용하려면 Azure AD Premium을 포함하는 구독이 필요하며 디바이스를 Azure Active Directory에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="841bc-118"><sup>3</sup> Windows 8.1 RT 장치에 대한 액세스 제어는 Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="841bc-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="841bc-119">2020년 6월 이후의 Android 버전은 Samsung Knox 장치를 제외한 암호 설정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="841bc-120">이전 OS 버전에 이미 등록된 장치는 예고 없이 기능이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="841bc-121">조직의 사용자가 기본 이동성 및 보안에서 지원되지 않는 모바일 장치를 사용하는 경우 조직의 데이터를 더 안전하게 Exchange ActiveSync Microsoft 365 전자 메일에 대한 Exchange ActiveSync 앱 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="841bc-122">모바일 기능을 차단하는 Exchange ActiveSync 기본 이동성 및 보안에서 장치 액세스 설정 [관리를 참조하세요.](manage-device-access-settings.md)</span><span class="sxs-lookup"><span data-stu-id="841bc-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="841bc-123">Microsoft 365 전자 메일 및 문서에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="841bc-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="841bc-124">다음 표에 있는 다양한 유형의 모바일 장치에 대해 지원되는 앱은 사용자의 장치에 적용되는 새로운 모바일 장치 관리 정책이 있으며 사용자가 이전에 장치를 등록하지 않은 경우 기본 이동성 및 보안에 등록하라는 메시지를 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="841bc-125">사용자의 장치가 정책을 설정한 방법에 따라 정책을 준수하지 않는 경우 사용자가 이러한 앱의 Microsoft 365 리소스에 액세스하지 못하게 차단되거나 액세스 권한이 있지만 Microsoft 365에서 정책 위반을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="841bc-126">**제품**</span><span class="sxs-lookup"><span data-stu-id="841bc-126">**Product**</span></span>|<span data-ttu-id="841bc-127">**iOS 10.0 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="841bc-128">**Android 5.0 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="841bc-129">**Exchange** Exchange ActiveSync 버전 14.1 이상을 사용하는 터치다운과 같은 기본 제공 전자 메일 및 타사 Exchange ActiveSync 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="841bc-130">메일</span><span class="sxs-lookup"><span data-stu-id="841bc-130">Mail</span></span> |<span data-ttu-id="841bc-131">전자 메일</span><span class="sxs-lookup"><span data-stu-id="841bc-131">Email</span></span> |
|<span data-ttu-id="841bc-132">**Office**   및  **비즈니스용 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="841bc-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="841bc-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="841bc-133">Outlook</span></span> </br><span data-ttu-id="841bc-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="841bc-134">OneDrive</span></span> </br><span data-ttu-id="841bc-135">Word</span><span class="sxs-lookup"><span data-stu-id="841bc-135">Word</span></span> </br><span data-ttu-id="841bc-136">Excel</span><span class="sxs-lookup"><span data-stu-id="841bc-136">Excel</span></span> </br><span data-ttu-id="841bc-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="841bc-137">PowerPoint</span></span>|<span data-ttu-id="841bc-138">**휴대폰 및 태블릿:**</span><span class="sxs-lookup"><span data-stu-id="841bc-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="841bc-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="841bc-139">Outlook</span></span> <br/> <span data-ttu-id="841bc-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="841bc-140">OneDrive</span></span> <br/> <span data-ttu-id="841bc-141">Word</span><span class="sxs-lookup"><span data-stu-id="841bc-141">Word</span></span> <br/> <span data-ttu-id="841bc-142">Excel</span><span class="sxs-lookup"><span data-stu-id="841bc-142">Excel</span></span> <br/> <span data-ttu-id="841bc-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="841bc-143">PowerPoint</span></span> <br/> <span data-ttu-id="841bc-144">**휴대폰만 해당:**</span><span class="sxs-lookup"><span data-stu-id="841bc-144">**On phones only:**</span></span> <br/> <span data-ttu-id="841bc-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="841bc-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="841bc-146">iOS 10.0 이상 버전에 대한 지원에는 iPhone 및 iPad 장치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="841bc-147">BlackBerry OS 디바이스 관리는 기본 보안 및 모바일 기능에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-147">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="841bc-148">BlackBerry의 BBCS(BlackBerry Business Cloud Services)를 사용하여 BlackBerry OS 장치를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="841bc-149">Android OS를 실행하는 Blackberry 장치는 표준 Android 장치로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="841bc-150">사용자가 모바일 브라우저를 사용하여 Microsoft 365 SharePoint 사이트, Office Online의 문서 또는 Office Online의 전자 메일에 액세스하는 경우 등록하라는 메시지가 표시되거나 정책 위반에 대해 차단되거나 Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="841bc-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="841bc-151">다음 다이어그램은 새 장치를 사용하는 사용자가 기본 이동성 및 보안으로 액세스 제어를 지원하는 앱에 로그인할 때 발생하는 일과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="841bc-152">사용자가 디바이스를 등록할 때까지 앱에서 Microsoft 365 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="기본 이동성 및 보안 액세스 제어":::

> [!NOTE]
> <span data-ttu-id="841bc-154">Microsoft 365 Business Standard의 기본 이동성 및 보안에서 만든 정책 및 액세스 규칙은 Exchange 관리 센터에서 Exchange ActiveSync 모바일 장치 사서함 정책 및 장치 액세스 규칙에 대해 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-154">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="841bc-155">장치가 Microsoft 365 Business Standard의 기본 이동성 및 보안에 등록된 후 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치에 적용된 장치 액세스 규칙은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-155">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="841bc-156">Exchange Online의 Exchange ActiveSync 자세한 내용은 [Exchange ActiveSync 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=524380)</span><span class="sxs-lookup"><span data-stu-id="841bc-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="841bc-157">모바일 장치에 대한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="841bc-158">특정 설정이 켜져 있는 액세스를 차단하는 정책을 만들면 Microsoft 365 전자 메일 및 문서에 대한 액세스 제어에 나열된 지원되는 앱을 사용할 때 사용자가 [Microsoft 365](capabilities.md)리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="841bc-159">사용자가 Microsoft 365 리소스에 액세스하지 수 없는 설정은 다음 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="841bc-160">보안</span><span class="sxs-lookup"><span data-stu-id="841bc-160">Security</span></span>

- <span data-ttu-id="841bc-161">암호화</span><span class="sxs-lookup"><span data-stu-id="841bc-161">Encryption</span></span>

- <span data-ttu-id="841bc-162">암호 해독</span><span class="sxs-lookup"><span data-stu-id="841bc-162">Jail broken</span></span>

- <span data-ttu-id="841bc-163">관리되는 전자 메일 프로필</span><span class="sxs-lookup"><span data-stu-id="841bc-163">Managed email profile</span></span>  

<span data-ttu-id="841bc-164">예를 들어 다음 다이어그램에는 등록된 장치를 사용하는 사용자가 장치에 적용되는 모바일 장치 관리 정책의 보안 설정을 준수하지 않는 경우 수행되는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="841bc-165">사용자는 기본 이동성 및 보안으로 액세스 제어를 지원하는 앱에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="841bc-166">디바이스가 보안 설정을 준수할 때까지 앱에서 Microsoft 365 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="기본 이동성 및 보안 준수 메시지":::

<span data-ttu-id="841bc-168">다음 섹션에는 Microsoft 365 조직 리소스에 연결하는 모바일 장치를 보호하고 관리하는 데 사용할 수 있는 정책 설정이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="841bc-169">보안 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-169">Security settings</span></span>

|<span data-ttu-id="841bc-170">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-170">**Setting name**</span></span>|<span data-ttu-id="841bc-171">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-172">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-172">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-174">암호 필요</span><span class="sxs-lookup"><span data-stu-id="841bc-174">Require a password</span></span>|<span data-ttu-id="841bc-175">예</span><span class="sxs-lookup"><span data-stu-id="841bc-175">Yes</span></span>|<span data-ttu-id="841bc-176">예</span><span class="sxs-lookup"><span data-stu-id="841bc-176">Yes</span></span>|<span data-ttu-id="841bc-177">예</span><span class="sxs-lookup"><span data-stu-id="841bc-177">Yes</span></span>|
|<span data-ttu-id="841bc-178">단순한 암호 금지</span><span class="sxs-lookup"><span data-stu-id="841bc-178">Prevent simple password</span></span>|<span data-ttu-id="841bc-179">예</span><span class="sxs-lookup"><span data-stu-id="841bc-179">Yes</span></span>|<span data-ttu-id="841bc-180">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-180">No</span></span>|<span data-ttu-id="841bc-181">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-181">No</span></span>|
|<span data-ttu-id="841bc-182">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="841bc-182">Require an alphanumeric password</span></span>|<span data-ttu-id="841bc-183">예</span><span class="sxs-lookup"><span data-stu-id="841bc-183">Yes</span></span>|<span data-ttu-id="841bc-184">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-184">No</span></span>|<span data-ttu-id="841bc-185">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-185">No</span></span>|
|<span data-ttu-id="841bc-186">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="841bc-186">Minimum password length</span></span> |<span data-ttu-id="841bc-187">예</span><span class="sxs-lookup"><span data-stu-id="841bc-187">Yes</span></span>|<span data-ttu-id="841bc-188">예</span><span class="sxs-lookup"><span data-stu-id="841bc-188">Yes</span></span>|<span data-ttu-id="841bc-189">예</span><span class="sxs-lookup"><span data-stu-id="841bc-189">Yes</span></span>|
|<span data-ttu-id="841bc-190">장치 데이터를 지우기 전 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="841bc-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="841bc-191">예</span><span class="sxs-lookup"><span data-stu-id="841bc-191">Yes</span></span>|<span data-ttu-id="841bc-192">예</span><span class="sxs-lookup"><span data-stu-id="841bc-192">Yes</span></span>|<span data-ttu-id="841bc-193">예</span><span class="sxs-lookup"><span data-stu-id="841bc-193">Yes</span></span>|
|<span data-ttu-id="841bc-194">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="841bc-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="841bc-195">예</span><span class="sxs-lookup"><span data-stu-id="841bc-195">Yes</span></span>|<span data-ttu-id="841bc-196">예</span><span class="sxs-lookup"><span data-stu-id="841bc-196">Yes</span></span>|<span data-ttu-id="841bc-197">예</span><span class="sxs-lookup"><span data-stu-id="841bc-197">Yes</span></span>|
|<span data-ttu-id="841bc-198">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="841bc-198">Password expiration (days)</span></span> |<span data-ttu-id="841bc-199">예</span><span class="sxs-lookup"><span data-stu-id="841bc-199">Yes</span></span>|<span data-ttu-id="841bc-200">예</span><span class="sxs-lookup"><span data-stu-id="841bc-200">Yes</span></span>|<span data-ttu-id="841bc-201">예</span><span class="sxs-lookup"><span data-stu-id="841bc-201">Yes</span></span>|
|<span data-ttu-id="841bc-202">암호 기록 기억 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="841bc-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="841bc-203">예</span><span class="sxs-lookup"><span data-stu-id="841bc-203">Yes</span></span>|<span data-ttu-id="841bc-204">예</span><span class="sxs-lookup"><span data-stu-id="841bc-204">Yes</span></span>|<span data-ttu-id="841bc-205">예</span><span class="sxs-lookup"><span data-stu-id="841bc-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="841bc-206">암호화 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-206">Encryption settings</span></span>

|<span data-ttu-id="841bc-207">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-207">**Setting name**</span></span>|<span data-ttu-id="841bc-208">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-209">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-209">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-211">디바이스<sup>1에서</sup> 데이터 암호화 필요</span><span class="sxs-lookup"><span data-stu-id="841bc-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="841bc-212">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-212">No</span></span>|<span data-ttu-id="841bc-213">예</span><span class="sxs-lookup"><span data-stu-id="841bc-213">Yes</span></span>|<span data-ttu-id="841bc-214">예</span><span class="sxs-lookup"><span data-stu-id="841bc-214">Yes</span></span>|

<span data-ttu-id="841bc-215"><sup>1</sup> Samsung Knox를 사용하면 저장소 카드에 암호화를 요구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="841bc-216">암호 해독 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-216">Jail broken setting</span></span> 

|<span data-ttu-id="841bc-217">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-217">**Setting name**</span></span>|<span data-ttu-id="841bc-218">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-219">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-219">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-221">장치의 암호를 해독하거나 장치를 루트 경로로 지정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="841bc-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="841bc-222">예</span><span class="sxs-lookup"><span data-stu-id="841bc-222">Yes</span></span>|<span data-ttu-id="841bc-223">예</span><span class="sxs-lookup"><span data-stu-id="841bc-223">Yes</span></span>|<span data-ttu-id="841bc-224">예</span><span class="sxs-lookup"><span data-stu-id="841bc-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="841bc-225">관리되는 전자 메일 프로필 옵션</span><span class="sxs-lookup"><span data-stu-id="841bc-225">Managed email profile option</span></span> 

<span data-ttu-id="841bc-226">다음 옵션은 사용자가 수동으로 만든 전자 메일 프로필을 사용하는 경우 Microsoft 365 전자 메일에 액세스하지 못하게 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="841bc-227">전자 메일에 액세스하려면 iOS 장치의 사용자가 수동으로 만든 전자 메일 프로필을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="841bc-228">프로필을 삭제하면 디바이스에 새 프로필이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="841bc-229">최종 사용자가 규정을 준수하는 방법에 대한 지침은 기존 전자 메일 계정을 [찾은 것입니다.](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)</span><span class="sxs-lookup"><span data-stu-id="841bc-229">For instructions on how end users can get compliant, see [An existing email account was found](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="841bc-230">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-230">**Setting name**</span></span>|<span data-ttu-id="841bc-231">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-232">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-232">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-234">전자 메일 프로필이 관리됨</span><span class="sxs-lookup"><span data-stu-id="841bc-234">Email profile is managed</span></span> |<span data-ttu-id="841bc-235">예</span><span class="sxs-lookup"><span data-stu-id="841bc-235">Yes</span></span>|<span data-ttu-id="841bc-236">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-236">No</span></span>|<span data-ttu-id="841bc-237">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="841bc-238">클라우드 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-238">Cloud settings</span></span>

|<span data-ttu-id="841bc-239">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-239">**Setting name**</span></span>|<span data-ttu-id="841bc-240">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-241">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-241">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-243">암호화된 백업 필요</span><span class="sxs-lookup"><span data-stu-id="841bc-243">Require encrypted backup</span></span> |<span data-ttu-id="841bc-244">예</span><span class="sxs-lookup"><span data-stu-id="841bc-244">Yes</span></span>|<span data-ttu-id="841bc-245">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-245">No</span></span>|<span data-ttu-id="841bc-246">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-246">No</span></span>|
|<span data-ttu-id="841bc-247">클라우드 백업 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-247">Block cloud backup</span></span> |<span data-ttu-id="841bc-248">예</span><span class="sxs-lookup"><span data-stu-id="841bc-248">Yes</span></span>|<span data-ttu-id="841bc-249">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-249">No</span></span>|<span data-ttu-id="841bc-250">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-250">No</span></span>|
|<span data-ttu-id="841bc-251">문서 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-251">Block document synchronization</span></span> |<span data-ttu-id="841bc-252">예</span><span class="sxs-lookup"><span data-stu-id="841bc-252">Yes</span></span>|<span data-ttu-id="841bc-253">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-253">No</span></span>|<span data-ttu-id="841bc-254">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-254">No</span></span>|
|<span data-ttu-id="841bc-255">사진 동기화 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-255">Block photo synchronization</span></span>  |<span data-ttu-id="841bc-256">예</span><span class="sxs-lookup"><span data-stu-id="841bc-256">Yes</span></span>|<span data-ttu-id="841bc-257">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-257">No</span></span>|<span data-ttu-id="841bc-258">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-258">No</span></span>|
|<span data-ttu-id="841bc-259">Google 백업 허용</span><span class="sxs-lookup"><span data-stu-id="841bc-259">Allow Google backup</span></span>  |<span data-ttu-id="841bc-260">해당 없음</span><span class="sxs-lookup"><span data-stu-id="841bc-260">N/A</span></span>|<span data-ttu-id="841bc-261">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-261">No</span></span>|<span data-ttu-id="841bc-262">예</span><span class="sxs-lookup"><span data-stu-id="841bc-262">Yes</span></span>|
|<span data-ttu-id="841bc-263">Google 계정 자동 동기화 허용</span><span class="sxs-lookup"><span data-stu-id="841bc-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="841bc-264">해당 없음</span><span class="sxs-lookup"><span data-stu-id="841bc-264">N/A</span></span>|<span data-ttu-id="841bc-265">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-265">No</span></span>|<span data-ttu-id="841bc-266">예</span><span class="sxs-lookup"><span data-stu-id="841bc-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="841bc-267">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-267">System settings</span></span>

|<span data-ttu-id="841bc-268">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-268">**Setting name**</span></span>|<span data-ttu-id="841bc-269">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-270">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-270">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-272">화면 캡처 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-272">Block screen capture</span></span> |<span data-ttu-id="841bc-273">예</span><span class="sxs-lookup"><span data-stu-id="841bc-273">Yes</span></span>|<span data-ttu-id="841bc-274">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-274">No</span></span>|<span data-ttu-id="841bc-275">예</span><span class="sxs-lookup"><span data-stu-id="841bc-275">Yes</span></span>|
|<span data-ttu-id="841bc-276">장치에서 진단 데이터 전송 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="841bc-277">예</span><span class="sxs-lookup"><span data-stu-id="841bc-277">Yes</span></span>|<span data-ttu-id="841bc-278">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-278">No</span></span>|<span data-ttu-id="841bc-279">예</span><span class="sxs-lookup"><span data-stu-id="841bc-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="841bc-280">응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-280">Application settings</span></span>

|<span data-ttu-id="841bc-281">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-281">**Setting name**</span></span>|<span data-ttu-id="841bc-282">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-283">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-283">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-285">장치에서 비디오 회의 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-285">Block video conferences on device</span></span> |<span data-ttu-id="841bc-286">예</span><span class="sxs-lookup"><span data-stu-id="841bc-286">Yes</span></span>|<span data-ttu-id="841bc-287">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-287">No</span></span>|<span data-ttu-id="841bc-288">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-288">No</span></span>|
|<span data-ttu-id="841bc-289">응용 프로그램 저장소에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-289">Block access to application store</span></span> |<span data-ttu-id="841bc-290">예</span><span class="sxs-lookup"><span data-stu-id="841bc-290">Yes</span></span>|<span data-ttu-id="841bc-291">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-291">No</span></span>|<span data-ttu-id="841bc-292">예</span><span class="sxs-lookup"><span data-stu-id="841bc-292">Yes</span></span>|
|<span data-ttu-id="841bc-293">응용 프로그램 저장소에 액세스할 때 암호 필요</span><span class="sxs-lookup"><span data-stu-id="841bc-293">Require password when accessing application store</span></span> |<span data-ttu-id="841bc-294">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-294">No</span></span>|<span data-ttu-id="841bc-295">예</span><span class="sxs-lookup"><span data-stu-id="841bc-295">Yes</span></span>|<span data-ttu-id="841bc-296">예</span><span class="sxs-lookup"><span data-stu-id="841bc-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="841bc-297">장치 기능 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-297">Device capabilities settings</span></span>

|<span data-ttu-id="841bc-298">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-298">**Setting name**</span></span>|<span data-ttu-id="841bc-299">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-300">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-300">**Android 5 and later**</span></span>|<span data-ttu-id="841bc-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="841bc-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="841bc-302">이동식 저장소와 연결 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-302">Block connection with removable storage</span></span> |<span data-ttu-id="841bc-303">예</span><span class="sxs-lookup"><span data-stu-id="841bc-303">Yes</span></span>|<span data-ttu-id="841bc-304">예</span><span class="sxs-lookup"><span data-stu-id="841bc-304">Yes</span></span>|<span data-ttu-id="841bc-305">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-305">No</span></span>|
|<span data-ttu-id="841bc-306">Bluetooth 연결 차단</span><span class="sxs-lookup"><span data-stu-id="841bc-306">Block Bluetooth connection</span></span> |<span data-ttu-id="841bc-307">예</span><span class="sxs-lookup"><span data-stu-id="841bc-307">Yes</span></span>|<span data-ttu-id="841bc-308">예</span><span class="sxs-lookup"><span data-stu-id="841bc-308">Yes</span></span>|<span data-ttu-id="841bc-309">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-309">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="841bc-310">추가 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-310">Additional settings</span></span>

<span data-ttu-id="841bc-311">보안 및 준수 센터 PowerShell cmdlet을 사용하여 다음과 같은 추가 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-311">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="841bc-312">자세한 내용은 보안 및 [준수 & PowerShell을 참조하세요.](https://docs.microsoft.com/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="841bc-312">For more information, see [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="841bc-313">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="841bc-313">**Setting name**</span></span>|<span data-ttu-id="841bc-314">**iOS 7.1 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="841bc-315">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="841bc-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="841bc-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="841bc-316">CameraEnabled</span></span>|<span data-ttu-id="841bc-317">예</span><span class="sxs-lookup"><span data-stu-id="841bc-317">Yes</span></span>|<span data-ttu-id="841bc-318">예</span><span class="sxs-lookup"><span data-stu-id="841bc-318">Yes</span></span>|
|<span data-ttu-id="841bc-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="841bc-319">RegionRatings</span></span>|<span data-ttu-id="841bc-320">예</span><span class="sxs-lookup"><span data-stu-id="841bc-320">Yes</span></span>|<span data-ttu-id="841bc-321">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-321">No</span></span>|
|<span data-ttu-id="841bc-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="841bc-322">MoviesRatings</span></span>|<span data-ttu-id="841bc-323">예</span><span class="sxs-lookup"><span data-stu-id="841bc-323">Yes</span></span>|<span data-ttu-id="841bc-324">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-324">No</span></span>|
|<span data-ttu-id="841bc-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="841bc-325">TVShowsRating</span></span> |<span data-ttu-id="841bc-326">예</span><span class="sxs-lookup"><span data-stu-id="841bc-326">Yes</span></span>|<span data-ttu-id="841bc-327">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-327">No</span></span>|
|<span data-ttu-id="841bc-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="841bc-328">AppsRatings</span></span> |<span data-ttu-id="841bc-329">예</span><span class="sxs-lookup"><span data-stu-id="841bc-329">Yes</span></span>|<span data-ttu-id="841bc-330">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-330">No</span></span>|
|<span data-ttu-id="841bc-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="841bc-331">AllowVoiceDialing</span></span> |<span data-ttu-id="841bc-332">예</span><span class="sxs-lookup"><span data-stu-id="841bc-332">Yes</span></span>|<span data-ttu-id="841bc-333">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-333">No</span></span>|
|<span data-ttu-id="841bc-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="841bc-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="841bc-335">예</span><span class="sxs-lookup"><span data-stu-id="841bc-335">Yes</span></span>|<span data-ttu-id="841bc-336">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-336">No</span></span>|
|<span data-ttu-id="841bc-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="841bc-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="841bc-338">예</span><span class="sxs-lookup"><span data-stu-id="841bc-338">Yes</span></span>|<span data-ttu-id="841bc-339">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-339">No</span></span>|
|<span data-ttu-id="841bc-340">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="841bc-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="841bc-341">예</span><span class="sxs-lookup"><span data-stu-id="841bc-341">Yes</span></span>|<span data-ttu-id="841bc-342">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-342">No</span></span>|
|<span data-ttu-id="841bc-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="841bc-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="841bc-344">예</span><span class="sxs-lookup"><span data-stu-id="841bc-344">Yes</span></span>|<span data-ttu-id="841bc-345">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-345">No</span></span>|
|<span data-ttu-id="841bc-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="841bc-346">PasswordQuality</span></span> |<span data-ttu-id="841bc-347">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-347">No</span></span>|<span data-ttu-id="841bc-348">예</span><span class="sxs-lookup"><span data-stu-id="841bc-348">Yes</span></span>|
|<span data-ttu-id="841bc-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="841bc-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="841bc-350">예</span><span class="sxs-lookup"><span data-stu-id="841bc-350">Yes</span></span>|<span data-ttu-id="841bc-351">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-351">No</span></span>|
|<span data-ttu-id="841bc-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="841bc-352">WLANEnabled</span></span>  |<span data-ttu-id="841bc-353">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-353">No</span></span>|<span data-ttu-id="841bc-354">아니요</span><span class="sxs-lookup"><span data-stu-id="841bc-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="841bc-355">Windows에서 지원하는 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-355">Settings supported by Windows</span></span>

<span data-ttu-id="841bc-356">Windows 10 장치를 모바일 장치로 등록하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="841bc-357">적용 가능한 정책을 배포한 후 Windows 10 장치를 사용하는 사용자는 기본 제공 전자 메일 앱을 처음 사용하여 Microsoft 365 전자 메일에 액세스할 때 기본 이동성 및 보안에 등록해야 합니다(Azure AD Premium 구독 필요).</span><span class="sxs-lookup"><span data-stu-id="841bc-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="841bc-358">다음 설정은 모바일 장치로 등록된 Windows 10 장치에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="841bc-359">이러한 설정은 사용자가 Microsoft 365 리소스에 액세스하는 데 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="841bc-360">보안 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-360">Security settings</span></span>

- <span data-ttu-id="841bc-361">영숫자 암호 필요</span><span class="sxs-lookup"><span data-stu-id="841bc-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="841bc-362">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="841bc-362">Minimum password length</span></span>

- <span data-ttu-id="841bc-363">장치 데이터가 지워지기 전 로그인 오류 횟수</span><span class="sxs-lookup"><span data-stu-id="841bc-363">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="841bc-364">장치가 잠기기 전 비활성화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="841bc-364">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="841bc-365">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="841bc-365">Password expiration (days)</span></span>

- <span data-ttu-id="841bc-366">암호 기록 저장 및 재사용 금지</span><span class="sxs-lookup"><span data-stu-id="841bc-366">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="841bc-367">암호를 제어하는 다음 설정은 로컬 Windows 계정만 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="841bc-368">도메인 또는 Azure Active Directory 가입을 통해 제공된 Windows 계정은 이러한 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="841bc-369">시스템 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-369">System settings</span></span>

<span data-ttu-id="841bc-370">장치에서 진단 데이터 전송을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="841bc-371">추가 설정</span><span class="sxs-lookup"><span data-stu-id="841bc-371">Additional settings</span></span>

<span data-ttu-id="841bc-372">PowerShell cmdlet을 사용하여 이러한 추가 정책 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="841bc-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="841bc-373">AllowConvenienceLogon</span></span>

- <span data-ttu-id="841bc-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="841bc-374">UserAccountControlStatus</span></span>

- <span data-ttu-id="841bc-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="841bc-375">FirewallStatus</span></span>

- <span data-ttu-id="841bc-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="841bc-376">AutoUpdateStatus</span></span>

- <span data-ttu-id="841bc-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="841bc-377">AntiVirusStatus</span></span>

- <span data-ttu-id="841bc-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="841bc-378">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="841bc-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="841bc-379">SmartScreenEnabled</span></span>

- <span data-ttu-id="841bc-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="841bc-380">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="841bc-381">원격으로 모바일 장치의 데이터 지우기</span><span class="sxs-lookup"><span data-stu-id="841bc-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="841bc-382">장치를 분실하거나 도난당한 경우 보안 및 준수 센터에서 데이터 손실 방지 장치 관리를 통해 데이터 & 데이터 지우기를 수행하여 중요한 **조직** 데이터를 제거하고 Microsoft 365 조직 리소스에 대한 액세스를 > 수  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="841bc-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="841bc-383">선택적 지우기를 수행하여 조직 데이터만 제거하거나, 전체 지우기를 수행하여 장치에서 모든 정보를 삭제하고 장치를 처음 출시될 때의 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="841bc-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="841bc-384">자세한 내용은 기본 이동성 및 보안에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="841bc-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="841bc-385">관련 항목</span><span class="sxs-lookup"><span data-stu-id="841bc-385">Related topics</span></span>

[<span data-ttu-id="841bc-386">Microsoft 365의 기본 이동성 및 보안 개요</span><span class="sxs-lookup"><span data-stu-id="841bc-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="841bc-387">기본 이동성 및 보안에서 장치 보안 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="841bc-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)