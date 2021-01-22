---
title: 보안 전자 메일 권장 정책 - 엔터프라이즈용 Microsoft 365 | Microsoft Docs
description: 메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: f3654762bf4d4c28a82b1e93829094b9e0386a60
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926525"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="2de53-103">메일을 보호하기 위한 정책 권장 사항</span><span class="sxs-lookup"><span data-stu-id="2de53-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="2de53-104">이 문서에서는 최신 인증 및 조건부 액세스를 지원하는 조직 전자 메일 및 전자 메일 클라이언트를 보호하기 위해 권장되는 ID 및 장치 액세스 정책을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="2de53-105">이 지침은 [일반 ID](identity-access-policies.md) 및 장치 액세스 정책을 구축하며 몇 가지 추가 권장 사항도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="2de53-106">이러한 권장 사항은 기준, 중요 및 높은 규제의 세분성에 따라 적용할 수 있는 세 가지 보안 및 보호 계층을 **기반으로 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2de53-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="2de53-107">[권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="2de53-108">이러한 권장 사항을 사용하려면 사용자가 모바일 장치에서 iOS 및 Android용 Outlook을 포함하여 최신 전자 메일 클라이언트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="2de53-109">iOS 및 Android용 Outlook에서는 Office 365의 최상의 기능을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="2de53-110">이러한 모바일 Outlook 앱은 모바일 사용을 지원하고 다른 Microsoft 클라우드 보안 기능과 함께 작동할 수 있는 보안 기능도 사용하여 설계됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="2de53-111">자세한 내용은 iOS 및 [Android용 Outlook FAQ를 참조하세요.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)</span><span class="sxs-lookup"><span data-stu-id="2de53-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="2de53-112">전자 메일을 포함 하게 일반적인 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="2de53-112">Update common policies to include email</span></span>

<span data-ttu-id="2de53-113">다음 다이어그램에서는 전자 메일을 보호하기 위해 공통 ID 및 장치 액세스 정책에서 업데이트할 정책을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-113">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="2de53-114">[![Teams 및 해당 종속 서비스에 대한 액세스를 보호하기 위한 정책 업데이트 요약](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="2de53-114">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="2de53-115">이 이미지의 더 큰 버전 보기</span><span class="sxs-lookup"><span data-stu-id="2de53-115">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="2de53-116">ActiveSync 클라이언트를 차단하는 Exchange Online에 대한 새 정책이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-116">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="2de53-117">그러면 Outlook 모바일이 강제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-117">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="2de53-118">정책을 설정할 때 정책 범위에 Exchange Online 및 Outlook을 포함한 경우 ActiveSync 클라이언트를 차단하는 새 정책만 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-118">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="2de53-119">다음 표에 나열된 정책을 검토하고 권장되는 추가를 작성하거나 이러한 정책이 이미 포함되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-119">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="2de53-120">각 정책은 일반 ID 및 장치 액세스 정책의 관련 구성 [지침에 연결됩니다.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2de53-120">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="2de53-121">보호 수준</span><span class="sxs-lookup"><span data-stu-id="2de53-121">Protection level</span></span>|<span data-ttu-id="2de53-122">정책</span><span class="sxs-lookup"><span data-stu-id="2de53-122">Policies</span></span>|<span data-ttu-id="2de53-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2de53-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="2de53-124">**기준**</span><span class="sxs-lookup"><span data-stu-id="2de53-124">**Baseline**</span></span>|[<span data-ttu-id="2de53-125">로그인 위험이 중간 또는 높음인 경우 MFA *필요*</span><span class="sxs-lookup"><span data-stu-id="2de53-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2de53-126">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="2de53-126">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="2de53-127">최신 인증을 지원하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="2de53-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="2de53-128">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="2de53-128">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="2de53-129">APP 데이터 보호 정책 적용</span><span class="sxs-lookup"><span data-stu-id="2de53-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="2de53-130">Outlook이 앱 목록에 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="2de53-130">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="2de53-131">각 플랫폼(iOS, Android, Windows)에 대한 정책을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-131">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="2de53-132">승인된 앱 및 APP 보호 필요</span><span class="sxs-lookup"><span data-stu-id="2de53-132">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="2de53-133">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="2de53-133">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="2de53-134">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="2de53-134">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2de53-135">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="2de53-135">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="2de53-136">ActiveSync 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="2de53-136">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="2de53-137">이 새 정책 추가</span><span class="sxs-lookup"><span data-stu-id="2de53-137">Add this new policy</span></span>|
|<span data-ttu-id="2de53-138">**중요**</span><span class="sxs-lookup"><span data-stu-id="2de53-138">**Sensitive**</span></span>|[<span data-ttu-id="2de53-139">로그인 위험이 낮음, 보통  *또는* 높음인 경우 MFA *필요*</span><span class="sxs-lookup"><span data-stu-id="2de53-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2de53-140">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="2de53-140">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="2de53-141">호환 PC 및 *모바일* 장치 필요</span><span class="sxs-lookup"><span data-stu-id="2de53-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="2de53-142">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="2de53-142">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="2de53-143">**매우 엄격한 규제**</span><span class="sxs-lookup"><span data-stu-id="2de53-143">**Highly regulated**</span></span>|[<span data-ttu-id="2de53-144">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="2de53-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2de53-145">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="2de53-145">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="2de53-146">ActiveSync 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="2de53-146">Block ActiveSync clients</span></span>

<span data-ttu-id="2de53-147">이 정책은 ActiveSync 클라이언트가 다른 조건부 액세스 정책을 무시하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-147">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="2de53-148">정책 구성은 ActiveSync 클라이언트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-148">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="2de53-149">앱 보호 필요 **[정책을](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** 선택하면 이 정책은 ActiveSync 클라이언트를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-149">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="2de53-150">이 정책을 만드는 데 대한 자세한 내용은 조건부 액세스를 사용하여 클라우드 앱 액세스에 대한 앱 보호 [필요 정책에서 찾을 수 있습니다.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="2de53-150">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="2de53-151">시나리오 1의 "2단계: EAS(ActiveSync)를 사용하여 Exchange Online에 대한 Azure AD 조건부 액세스 정책 [구성"을 따르기: Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)앱에는 기본 인증을 활용하는 Exchange ActiveSync 클라이언트가 Exchange Online에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-151">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="2de53-152">또한 인증 정책을 사용하여 [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)기본 인증을 사용하지 않도록 설정할 수 있습니다. 이 경우 모든 클라이언트 액세스 요청에서 최신 인증을 강제로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-152">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="2de53-153">웹에서 Outlook에서 Exchange Online에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="2de53-153">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="2de53-154">사용자가 웹용 Outlook에서 umnanaged 장치에서 첨부 파일을 다운로드하는 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-154">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="2de53-155">이러한 장치의 사용자는 장치에서 파일을 누출하고 저장하지 않고도 Office Online을 사용하여 이러한 파일을 보고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-155">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="2de53-156">관리되지 않는 장치에서 사용자가 첨부 파일을 볼 수 없는 경우를 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-156">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="2de53-157">단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-157">Here are the steps:</span></span>

1. <span data-ttu-id="2de53-158">[Exchange Online 원격 PowerShell 세션에 연결합니다.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="2de53-158">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="2de53-159">OWA 사서함 정책이 아직 없는 경우 [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet을 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-159">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="2de53-160">첨부 파일을 볼 수 있지만 다운로드할 수 없는 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-160">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="2de53-161">첨부 파일을 차단하려는 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-161">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="2de53-162">Azure Portal에서 다음 설정을 사용하여 새 조건부 액세스 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-162">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="2de53-163">**배정** \> **사용자 및 그룹:** 포함 및 제외할 적절한 사용자 및 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-163">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="2de53-164">**배정** \> **클라우드 앱 또는 작업** \> **클라우드 앱** \> **포함** \> **앱 선택:** **Office 365 Exchange Online 선택**</span><span class="sxs-lookup"><span data-stu-id="2de53-164">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="2de53-165">**액세스 컨트롤** \> **세션**: 앱 **적용 제한 사용 선택**</span><span class="sxs-lookup"><span data-stu-id="2de53-165">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="2de53-166">iOS 및 Android 장치에서 Outlook을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-166">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="2de53-167">iOS 및 Android 장치의 사용자가 iOS 및 Android용 Outlook을 사용하여 직장 또는 학교 콘텐츠에만 액세스할 수 있도록 허용하려면 이러한 잠재적 사용자를 대상으로 하는 조건부 액세스 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-167">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="2de53-168">iOS 및 Android용 Outlook을 사용하여 메시징 공동 작업 액세스 관리에서 이 정책을 [구성하는 단계를 참조하세요.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="2de53-168">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="2de53-169">메시지 암호화 설정</span><span class="sxs-lookup"><span data-stu-id="2de53-169">Set up message encryption</span></span>

<span data-ttu-id="2de53-170">Azure Information Protection의 보호 기능을 활용하는 새로운 Office 365 메시지 암호화(OME) 기능을 사용하여 조직은 모든 디바이스의 모든 사용자와 보호된 전자 메일을 쉽게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-170">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="2de53-171">사용자는 다른 Microsoft 365 조직과 함께 보호된 메시지를 보내고 받을 수 있으며, Outlook.com, Gmail 및 기타 전자 메일 서비스를 사용하는 고객도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de53-171">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="2de53-172">자세한 내용은 새 Office 365 메시지 암호화 기능 [설정을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)</span><span class="sxs-lookup"><span data-stu-id="2de53-172">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2de53-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2de53-173">Next steps</span></span>

![4단계: Microsoft 365 클라우드 앱에 대한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="2de53-175">조건부 액세스 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="2de53-175">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="2de53-176">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2de53-176">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="2de53-177">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2de53-177">SharePoint</span></span>](sharepoint-file-access-policies.md)
