---
title: 보안 메일 권장 정책 - Microsoft 365 Enterprise | Microsoft Docs
description: 메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: aea95dae0165eb23331b2fa24d5fc752df3f4345
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084315"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="cfcaf-103">메일을 보호하기 위한 정책 권장 사항</span><span class="sxs-lookup"><span data-stu-id="cfcaf-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="cfcaf-104">이 문서에서는 최신 인증 및 조건부 액세스를 지 원하는 조직 전자 메일 및 전자 메일 클라이언트를 보호 하기 위해 권장 되는 id 및 장치 액세스 정책을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="cfcaf-105">이 지침은 [일반 id 및 장치 액세스 정책](identity-access-policies.md) 에 대해 구축 되며 몇 가지 추가 권장 사항도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="cfcaf-106">이러한 권장 사항은 **기본**, **중요**및 **높은 규제**의 요구 사항에 따라 적용할 수 있는 세 가지 다른 보안 및 보호 계층을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="cfcaf-107">[권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="cfcaf-108">이러한 권장 사항을 적용 하려면 사용자가 모바일 장치에서 iOS 및 Android 용 Outlook을 비롯 한 최신 전자 메일 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="cfcaf-109">IOS 및 Android 용 Outlook에서는 Office 365의 최상의 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="cfcaf-110">이러한 모바일 Outlook 앱은 모바일 사용을 지원 하 고 다른 Microsoft 클라우드 보안 기능과 함께 사용할 수 있는 보안 기능으로도 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="cfcaf-111">자세한 내용은 [iOS 및 Android 용 OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="updating-common-policies-to-include-email"></a><span data-ttu-id="cfcaf-112">전자 메일을 포함 하도록 일반 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="cfcaf-112">Updating common policies to include email</span></span>

<span data-ttu-id="cfcaf-113">다음 다이어그램에서는 일반 id 및 장치 액세스 정책을 보여주고 전자 메일을 보호 하기 위해 업데이트 해야 하는 정책을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-113">The following diagram illustrates the common identity and device access policies and indicates which policies need to be updated to protect email.</span></span> <span data-ttu-id="cfcaf-114">Exchange Online에 대 한 새 규칙을 추가 하 여 ActiveSync 클라이언트를 차단 하는 방법에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-114">Note the addition of a new rule for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="cfcaf-115">이렇게 하면 Outlook mobile을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-115">This forces the use of Outlook mobile.</span></span>

![전자 메일을 보호 하기 위한 정책 업데이트 요약](../media/identity-access-ruleset-mail.png)

<span data-ttu-id="cfcaf-117">정책을 설정할 때 정책 범위에 Exchange Online과 Outlook을 포함 한 경우에는 ActiveSync 클라이언트를 차단 하는 새 정책만 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-117">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="cfcaf-118">다음 표에 나와 있는 정책 들을 검토 하 고 권장 되는 추가 내용을 확인 하거나 이미 포함 되어 있는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-118">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="cfcaf-119">각 규칙은 [일반 id 및 장치 액세스 정책](identity-access-policies.md) 문서의 관련 구성 지침에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-119">Each rule links to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="cfcaf-120">보호 수준</span><span class="sxs-lookup"><span data-stu-id="cfcaf-120">Protection level</span></span>|<span data-ttu-id="cfcaf-121">정책도</span><span class="sxs-lookup"><span data-stu-id="cfcaf-121">Policies</span></span>|<span data-ttu-id="cfcaf-122">추가 정보</span><span class="sxs-lookup"><span data-stu-id="cfcaf-122">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="cfcaf-123">**기준선**</span><span class="sxs-lookup"><span data-stu-id="cfcaf-123">**Baseline**</span></span>|[<span data-ttu-id="cfcaf-124">로그인 위험이 *보통* 또는 *높을* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="cfcaf-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="cfcaf-125">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="cfcaf-125">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="cfcaf-126">최신 인증을 지원하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="cfcaf-126">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="cfcaf-127">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="cfcaf-127">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="cfcaf-128">앱 보호 정책 정의</span><span class="sxs-lookup"><span data-stu-id="cfcaf-128">Define app protection policies</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="cfcaf-129">Outlook이 앱 목록에 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-129">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="cfcaf-130">각 플랫폼의 정책 (iOS, Android, Windows)을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-130">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="cfcaf-131">승인 된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="cfcaf-131">Require approved apps</span></span>](identity-access-policies.md#require-approved-apps)|<span data-ttu-id="cfcaf-132">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="cfcaf-132">Include Exchange Online in the list of cloud apps</span></span>|
|        |[<span data-ttu-id="cfcaf-133">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="cfcaf-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="cfcaf-134">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="cfcaf-134">Include Exchange Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="cfcaf-135">ActiveSync 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="cfcaf-135">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="cfcaf-136">새 정책 추가</span><span class="sxs-lookup"><span data-stu-id="cfcaf-136">Add this new policy</span></span>| 
|<span data-ttu-id="cfcaf-137">**중요**</span><span class="sxs-lookup"><span data-stu-id="cfcaf-137">**Sensitive**</span></span>|[<span data-ttu-id="cfcaf-138">로그인 위험이 *낮은* *경우 MFA* 필요 \*\*</span><span class="sxs-lookup"><span data-stu-id="cfcaf-138">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="cfcaf-139">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="cfcaf-139">Include Exchange Online in the assignment of cloud apps</span></span>|
|         |[<span data-ttu-id="cfcaf-140">준수 Pc *및* 모바일 장치 요구</span><span class="sxs-lookup"><span data-stu-id="cfcaf-140">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="cfcaf-141">클라우드 앱 목록에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="cfcaf-141">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="cfcaf-142">**높은 규제**</span><span class="sxs-lookup"><span data-stu-id="cfcaf-142">**Highly regulated**</span></span>|[<span data-ttu-id="cfcaf-143">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="cfcaf-143">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="cfcaf-144">클라우드 앱 할당에 Exchange Online 포함</span><span class="sxs-lookup"><span data-stu-id="cfcaf-144">Include Exchange Online in the assignment of cloud apps</span></span>|

## <a name="block-activesync-clients"></a><span data-ttu-id="cfcaf-145">ActiveSync 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="cfcaf-145">Block ActiveSync clients</span></span>

<span data-ttu-id="cfcaf-146">이 정책은 ActiveSync 클라이언트가 다른 조건부 액세스 규칙을 무시할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-146">This policy prevents ActiveSync clients from bypassing other conditional access rules.</span></span> <span data-ttu-id="cfcaf-147">규칙 구성은 ActiveSync 클라이언트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-147">The rule configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="cfcaf-148">승인 된 **클라이언트 앱 필요**를 선택 하면이 정책은 ActiveSync 클라이언트를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-148">By selecting **Require approved client app**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="cfcaf-149">이 정책을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-149">To configure this policy:</span></span>

1. <span data-ttu-id="cfcaf-150">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-150">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="cfcaf-151">성공적으로 로그인 하면 Azure 대시보드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-151">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="cfcaf-152">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-152">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="cfcaf-153">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-153">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="cfcaf-154">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-154">Choose **New policy**.</span></span>

5. <span data-ttu-id="cfcaf-155">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-155">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="cfcaf-156">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-156">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="cfcaf-157">**앱 선택을**선택 하 고 **Office 365 Exchange Online**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-157">Choose **Select apps**, select **Office 365 Exchange Online**.</span></span> <span data-ttu-id="cfcaf-158">**선택** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-158">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="cfcaf-159">**조건을**선택 하 고 **클라이언트 앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-159">Choose **Conditions**, and then choose **Client apps**.</span></span>

9. <span data-ttu-id="cfcaf-160">**구성**하려면 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-160">For **Configure**, select **Yes**.</span></span> <span data-ttu-id="cfcaf-161">**모바일 앱 및 데스크톱 클라이언트** 및 **Exchange ActiveSync 클라이언트만**확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-161">Check only the following: **Mobile apps and desktop clients** and **Exchange ActiveSync clients**.</span></span> <span data-ttu-id="cfcaf-162">**완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-162">Choose **Done**.</span></span>

10. <span data-ttu-id="cfcaf-163">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-163">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="cfcaf-164">**액세스 부여**를 선택 하 고 **승인 된 클라이언트 앱 필요**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-164">Choose **Grant access**, select **Require approved client app**.</span></span>  <span data-ttu-id="cfcaf-165">여러 컨트롤에 대해 **선택한 컨트롤 필요**를 선택한 다음 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-165">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span>

12. <span data-ttu-id="cfcaf-166">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-166">Choose **Create**.</span></span>

## <a name="setup-office-365-message-encryption"></a><span data-ttu-id="cfcaf-167">Office 365 메시지 암호화 설정</span><span class="sxs-lookup"><span data-stu-id="cfcaf-167">Setup Office 365 message encryption</span></span>

<span data-ttu-id="cfcaf-168">Azure Information Protection의 보호 기능을 활용 하는 새로운 Office 365 메시지 암호화 (OME) 기능을 사용 하면 조직에서 모든 장치에 있는 모든 사용자와 보호 된 전자 메일을 쉽게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-168">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="cfcaf-169">사용자는 Outlook.com, Gmail 및 기타 전자 메일 서비스를 사용 하는 Office 365 이외의 다른 Office 365 조직과 보호 된 메시지를 주고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-169">Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="cfcaf-170">자세한 내용은 [Set Up Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfcaf-170">For more information, see [Set up new Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cfcaf-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cfcaf-171">Next steps</span></span>

[<span data-ttu-id="cfcaf-172">SharePoint 사이트 및 파일을 보호하기 위한 정책 권장 사항 알아보기</span><span class="sxs-lookup"><span data-stu-id="cfcaf-172">Learn about policy recommendations for securing SharePoint Sites and files</span></span>](sharepoint-file-access-policies.md)
