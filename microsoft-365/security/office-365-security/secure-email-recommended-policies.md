---
title: 보안 전자 메일 권장 정책-엔터프라이즈에 대 한 Microsoft 365 | Microsoft Docs
description: 메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c8a1609bed124789229c6ae6d1f80b7d9c70bb66
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646814"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="914b3-103">메일을 보호하기 위한 정책 권장 사항</span><span class="sxs-lookup"><span data-stu-id="914b3-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="914b3-104">이 문서에서는 최신 인증 및 조건부 액세스를 지 원하는 조직 전자 메일 및 전자 메일 클라이언트를 보호 하기 위해 권장 되는 id 및 장치 액세스 정책을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="914b3-105">이 지침은 [일반 id 및 장치 액세스 정책](identity-access-policies.md) 에 대해 구축 되며 몇 가지 추가 권장 사항도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="914b3-106">이러한 권장 사항은 **기본**, **중요**및 **높은 규제**의 요구 사항에 따라 적용할 수 있는 세 가지 다른 보안 및 보호 계층을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="914b3-107">[권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="914b3-108">이러한 권장 사항을 적용 하려면 사용자가 모바일 장치에서 iOS 및 Android 용 Outlook을 비롯 한 최신 전자 메일 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="914b3-109">IOS 및 Android 용 Outlook에서는 Office 365의 최상의 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="914b3-110">이러한 모바일 Outlook 앱은 모바일 사용을 지원 하 고 다른 Microsoft 클라우드 보안 기능과 함께 사용할 수 있는 보안 기능으로도 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="914b3-111">자세한 내용은 [iOS 및 Android 용 OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="914b3-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="914b3-112">전자 메일을 포함 하도록 일반 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="914b3-112">Update common policies to include email</span></span>

<span data-ttu-id="914b3-113">다음 다이어그램에서는 전자 메일을 보호 하기 위해 일반 id 및 장치 액세스 정책에서 업데이트할 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-113">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="914b3-114">[![팀 및 해당 종속 서비스에 대 한 액세스를 보호 하기 위한 정책 업데이트 요약](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="914b3-114">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="914b3-115">이 이미지의 더 큰 버전 보기</span><span class="sxs-lookup"><span data-stu-id="914b3-115">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="914b3-116">Exchange Online에 대 한 새 정책을 추가 하 여 ActiveSync 클라이언트를 차단 하는 방법에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="914b3-116">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="914b3-117">이렇게 하면 Outlook mobile을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-117">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="914b3-118">정책을 설정할 때 정책 범위에 Exchange Online과 Outlook을 포함 한 경우에는 ActiveSync 클라이언트를 차단 하는 새 정책만 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-118">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="914b3-119">다음 표에 나와 있는 정책 들을 검토 하 고 권장 되는 추가 내용을 확인 하거나 이미 포함 되어 있는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-119">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="914b3-120">각 정책은 [일반 id 및 장치 액세스 정책의](identity-access-policies.md)관련 구성 지침에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-120">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="914b3-121">보호 수준</span><span class="sxs-lookup"><span data-stu-id="914b3-121">Protection level</span></span>|<span data-ttu-id="914b3-122">정책</span><span class="sxs-lookup"><span data-stu-id="914b3-122">Policies</span></span>|<span data-ttu-id="914b3-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="914b3-123">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="914b3-124">**기준**</span><span class="sxs-lookup"><span data-stu-id="914b3-124">**Baseline**</span></span>|[<span data-ttu-id="914b3-125">로그인 위험이 *보통* 또는 *높을* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="914b3-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="914b3-126">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="914b3-126">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="914b3-127">최신 인증을 지원하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="914b3-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="914b3-128">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="914b3-128">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="914b3-129">앱 데이터 보호 정책 적용</span><span class="sxs-lookup"><span data-stu-id="914b3-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="914b3-130">Outlook이 앱 목록에 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-130">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="914b3-131">각 플랫폼의 정책 (iOS, Android, Windows)을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-131">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="914b3-132">승인 된 앱 및 앱 보호 필요</span><span class="sxs-lookup"><span data-stu-id="914b3-132">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="914b3-133">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="914b3-133">Include Exchange Online in the list of cloud apps</span></span>|
|        |[<span data-ttu-id="914b3-134">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="914b3-134">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="914b3-135">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="914b3-135">Include Exchange Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="914b3-136">ActiveSync 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="914b3-136">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="914b3-137">새 정책 추가</span><span class="sxs-lookup"><span data-stu-id="914b3-137">Add this new policy</span></span>| 
|<span data-ttu-id="914b3-138">**중요**</span><span class="sxs-lookup"><span data-stu-id="914b3-138">**Sensitive**</span></span>|[<span data-ttu-id="914b3-139">로그인 위험이 *낮은* *경우 MFA* 필요 *high*</span><span class="sxs-lookup"><span data-stu-id="914b3-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="914b3-140">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="914b3-140">Include Exchange Online in the assignment of cloud apps</span></span>|
|         |[<span data-ttu-id="914b3-141">준수 Pc *및* 모바일 장치 요구</span><span class="sxs-lookup"><span data-stu-id="914b3-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="914b3-142">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="914b3-142">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="914b3-143">**매우 엄격한 규제**</span><span class="sxs-lookup"><span data-stu-id="914b3-143">**Highly regulated**</span></span>|[<span data-ttu-id="914b3-144">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="914b3-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="914b3-145">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="914b3-145">Include Exchange Online in the assignment of cloud apps</span></span>|

## <a name="block-activesync-clients"></a><span data-ttu-id="914b3-146">ActiveSync 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="914b3-146">Block ActiveSync clients</span></span>

<span data-ttu-id="914b3-147">이 정책은 ActiveSync 클라이언트가 다른 조건부 액세스 정책을 무시할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-147">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="914b3-148">정책 구성은 ActiveSync 클라이언트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-148">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="914b3-149">이 정책은 **[앱 보호 정책 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** 를 선택 하 여 ActiveSync 클라이언트를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-149">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="914b3-150">이 정책 만들기에 대 한 자세한 내용은 [조건부 액세스를 사용한 클라우드 앱 액세스에 대 한 앱 보호 정책 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="914b3-150">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="914b3-151">시나리오 1의 "2 단계: ActiveSync를 사용 하 여 Azure AD 조건부 액세스 정책 구성 (EAS)" [: Office 365 앱은 앱 보호 정책과 함께 승인 된 앱이 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)하므로 기본 인증을 사용 하는 exchange ActiveSync 클라이언트에서 exchange Online에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-151">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="914b3-152">인증 정책을 사용 하 여 [기본 인증을 사용 하지 않도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)하 여 모든 클라이언트 액세스 요청이 최신 인증을 사용 하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-152">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="914b3-153">웹용 Outlook에서 Exchange Online에 대 한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="914b3-153">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="914b3-154">사용자가 umnanaged 장치에서 웹에 있는 첨부 파일을 다운로드 하는 기능이 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-154">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="914b3-155">이러한 장치에서 사용자는 파일을 누설 및 저장 하지 않고 Office Online을 사용 하 여 이러한 파일을 보고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-155">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="914b3-156">또한 사용자가 관리 되지 않는 장치에서 첨부 파일을 볼 수 없도록 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-156">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="914b3-157">단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-157">Here are the steps:</span></span>

1. <span data-ttu-id="914b3-158">[Exchange Online 원격 PowerShell 세션에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-158">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="914b3-159">아직 OWA 사서함 정책이 없는 경우에는 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet을 사용 하 여 하나를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-159">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="914b3-160">다운로드 하지 않고 첨부 파일을 볼 수 있도록 허용 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-160">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="914b3-161">첨부 파일을 차단 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-161">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

4. <span data-ttu-id="914b3-162">Azure portal에서 다음 설정을 사용 하 여 새 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-162">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="914b3-163">**사용자 및 그룹 > 할당**: 포함 하거나 제외할 적절 한 사용자 및 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-163">**Assignments > Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="914b3-164">클라우드 앱 **또는 작업 > 할당 > 클라우드 앱 > 포함 > 앱 선택**: **Office 365 Exchange Online** 선택</span><span class="sxs-lookup"><span data-stu-id="914b3-164">**Assignments > Cloud apps or actions > Cloud apps > Include > Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="914b3-165">**세션 > 액세스 제어**: **앱 적용 제한 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-165">**Access controls > Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="914b3-166">IOS 및 Android 장치에서 Outlook을 사용 해야 함</span><span class="sxs-lookup"><span data-stu-id="914b3-166">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="914b3-167">IOS 및 Android 장치 사용자가 iOS 및 Android 용 Outlook을 사용 하 여 회사 또는 학교 콘텐츠에만 액세스할 수 있도록 하려면 이러한 잠재적 사용자를 대상으로 하는 조건부 액세스 정책이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-167">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="914b3-168">[IOS 및 Android 용 Outlook을 사용 하 여 메시징 공동 작업 액세스 관리]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)에서이 정책을 구성 하는 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="914b3-168">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>


## <a name="set-up-message-encryption"></a><span data-ttu-id="914b3-169">메시지 암호화 설정</span><span class="sxs-lookup"><span data-stu-id="914b3-169">Set up message encryption</span></span>

<span data-ttu-id="914b3-170">Azure Information Protection의 보호 기능을 활용 하는 새로운 Office 365 메시지 암호화 (OME) 기능을 사용 하면 조직에서 모든 장치에 있는 모든 사용자와 보호 된 전자 메일을 쉽게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-170">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="914b3-171">사용자는 Outlook.com, Gmail 및 기타 전자 메일 서비스를 사용 하는 고객 뿐만 아니라 다른 Microsoft 365 조직과의 보호 된 메시지를 주고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914b3-171">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="914b3-172">자세한 내용은 [Set Up Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="914b3-172">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="914b3-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="914b3-173">Next steps</span></span>

![4 단계: Microsoft 365 클라우드 앱에 대 한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="914b3-175">다음에 대 한 조건부 액세스 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="914b3-175">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="914b3-176">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="914b3-176">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="914b3-177">SharePoint</span><span class="sxs-lookup"><span data-stu-id="914b3-177">SharePoint</span></span>](sharepoint-file-access-policies.md)
