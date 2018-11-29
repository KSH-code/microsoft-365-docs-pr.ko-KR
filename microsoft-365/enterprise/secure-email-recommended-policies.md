---
title: 보안 메일 권장 정책 - Microsoft 365 Enterprise | Microsoft Docs
description: 메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: dd1504ac11f0e2eefa56572af24de14b5f87830e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869729"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="96daa-103">메일을 보호하기 위한 정책 권장 사항</span><span class="sxs-lookup"><span data-stu-id="96daa-103">Policy recommendations for securing email</span></span>
<span data-ttu-id="96daa-p101">이 문서에서는 권장된 id 및 조직 내 전자 메일 및 현대 인증 및 조건부 액세스를 지 원하는 전자 메일 클라이언트를 보호 하기 위해 장치 액세스 정책을 구현 하는 방법에 설명 합니다. 이 설명서 [일반적인 id 및 장치에 대 한 액세스 정책](identity-access-policies.md) 에 기반 하 고도 몇가지 추가 권장 사항이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p101">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support Modern Authentication and Conditional Access. This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>


<span data-ttu-id="96daa-p102">이러한 권장 사항을 기반으로 세 다른 계층의 보안 및 보호 적용 될 수 있는 사용자의 요구의 세분성에 따라: **초기 계획**, **중요 한**및 **규제 된 매우**합니다. 이러한 보안 계층 및 [권장 보안 정책 및 구성 소개 (영문)](microsoft-365-policies-configurations.md)에서 이러한 권장 사항으로 참조 되는 권장된 클라이언트 운영 체제에 대 한 자세한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p102">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**. You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="96daa-p103">이러한 권장 사항에는 iOS에 대 한 Outlook 및 Android를 포함 하 여 모바일 장치에서 현대 전자 메일 클라이언트를 사용 하 여 사용자가 필요 합니다. IOS와 Android에 대 한 outlook Office 365의 최상의 기능에 대 한 지원을 제공 합니다. 이러한 모바일 Outlook 응용 프로그램은도 지 원하는 모바일 기능을 사용 하 고 다른 Microsoft 클라우드 보안 기능와 함께 사용 하는 보안 설계 됩니다. 자세한 내용은 [iOS와 Android FAQ에 대 한 Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96daa-p103">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices. Outlook for iOS and Android provide support for the best features of Office 365. These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities. For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="updating-common-policies-to-include-email"></a><span data-ttu-id="96daa-112">전자 메일을 포함 하는 일반적인 정책을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-112">Updating common policies to include email</span></span>
<span data-ttu-id="96daa-p104">다음 다이어그램은 일반적인 id 및 장치 액세스 정책 및 정책의 전자 메일을 보호 하기 위해 업데이트 필요성을 나타냅니다. Note ActiveSync 클라이언트를 차단 하도록 Exchange Online에 대 한 새 규칙을 추가 합니다. 이렇게 하면 Outlook 사용 하 여 모바일 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p104">The following diagram illustrates the common identity and device access policies and indicates which policies need to be updated to protect email. Note the addition of a new rule for Exchange Online to block ActiveSync clients. This forces the use of Outlook mobile.</span></span>

![전자 메일을 보호 하기 위해 정책 업데이트 요약](../images/identity-access-ruleset-mail.png)

<span data-ttu-id="96daa-p105">포함 한 경우 Exchange Online 및 Outlook에서 정책 범위를 설정할 때, ActiveSync 클라이언트를 차단 하도록 새 정책을 만들려면 하기만 하면 됩니다. 다음 표에 나열 된 정책을 검토 하 고 권장된 추가 항목을 확인 하거나 하거나 이러한가 이미 포함 되었음을 확인 합니다. 각 규칙은 [일반적인 id 및 장치 액세스 정책](identity-access-policies.md) 문서에 연결 된 구성 지침에 대 한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p105">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients. Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included. Each rule links to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span> 

|<span data-ttu-id="96daa-120">보호 수준</span><span class="sxs-lookup"><span data-stu-id="96daa-120">Protection level</span></span>|<span data-ttu-id="96daa-121">Policies(정책)</span><span class="sxs-lookup"><span data-stu-id="96daa-121">Policies</span></span>|<span data-ttu-id="96daa-122">추가 정보</span><span class="sxs-lookup"><span data-stu-id="96daa-122">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="96daa-123">**기준**</span><span class="sxs-lookup"><span data-stu-id="96daa-123">**Baseline**</span></span>|[<span data-ttu-id="96daa-124">로그인 위험 *보통* 또는 *높음* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="96daa-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="96daa-125">클라우드 앱의 할당에서 Exchange Online을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-125">Include Exchange Online in the assignments of cloud apps.</span></span>|
|        |[<span data-ttu-id="96daa-126">현대 인증을 지원 하지 않는 블록 클라이언트</span><span class="sxs-lookup"><span data-stu-id="96daa-126">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="96daa-127">클라우드 앱의 할당에서 Exchange Online을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-127">Include Exchange Online in the assignments of cloud apps.</span></span>|
|        |[<span data-ttu-id="96daa-128">응용 프로그램 보호 정책 정의</span><span class="sxs-lookup"><span data-stu-id="96daa-128">Define app protection policies</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="96daa-p106">Outlook 응용 프로그램의 목록에 포함 되어 있어야 합니다. 각 플랫폼 (iOS, Android, Windows)에 대 한 정책을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p106">Be sure Outlook is included in the list of apps. Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="96daa-131">승인 된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="96daa-131">Require approved apps</span></span>](identity-access-policies.md#require-approved-apps)|<span data-ttu-id="96daa-132">클라우드 앱 목록에서 Exchange Online을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-132">Include Exchange Online in the list of cloud apps.</span></span>|
|        |[<span data-ttu-id="96daa-133">호환 Pc 필요</span><span class="sxs-lookup"><span data-stu-id="96daa-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="96daa-134">클라우드 앱 목록에서 Exchange Online을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-134">Include Exchange Online in list of cloud apps.</span></span>|
|        |[<span data-ttu-id="96daa-135">블록 ActiveSync 클라이언트</span><span class="sxs-lookup"><span data-stu-id="96daa-135">Block ActiveSync clients</span></span>](#block-activesync)|<span data-ttu-id="96daa-136">이 새 정책을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-136">Add this new policy.</span></span> 
|<span data-ttu-id="96daa-137">**중요**</span><span class="sxs-lookup"><span data-stu-id="96daa-137">**Sensitive**</span></span>|[<span data-ttu-id="96daa-138">로그인 위험 *낮음*, *보통* , *높음* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="96daa-138">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="96daa-139">클라우드 앱의 할당에서 Exchange Online을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-139">Include Exchange Online in the assignments of cloud apps.</span></span>|
|         |[<span data-ttu-id="96daa-140">준수 Pc *및* 모바일 장치 필요</span><span class="sxs-lookup"><span data-stu-id="96daa-140">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="96daa-141">클라우드 앱 목록에서 Exchange Online을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-141">Include Exchange Online in the list of cloud apps.</span></span>|
|<span data-ttu-id="96daa-142">**높은 규제**</span><span class="sxs-lookup"><span data-stu-id="96daa-142">**Highly regulated**</span></span>|[<span data-ttu-id="96daa-143">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="96daa-143">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="96daa-144">Exchange Online 클라우드 앱의 할당에 포함</span><span class="sxs-lookup"><span data-stu-id="96daa-144">Include Exchange Online in the assignments of cloud apps</span></span> |

## <a name="block-activesync-clients"></a><span data-ttu-id="96daa-145">블록 ActiveSync 클라이언트</span><span class="sxs-lookup"><span data-stu-id="96daa-145">Block ActiveSync clients</span></span>
<span data-ttu-id="96daa-p107">이 정책에는 다른 조건부 액세스 규칙을 무시에서 ActiveSync 클라이언트 수 없습니다. 규칙 구성을 ActiveSync 클라이언트에만 적용 됩니다. **클라이언트 응용 프로그램을 승인 필요**를 선택 하 여이 정책을 ActiveSync 클라이언트를 차단 합니다. 이 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p107">This policy prevents ActiveSync clients from bypassing other conditional access rules. The rule configuration applies only to ActiveSync clients. By selecting **Require approved client app**, this policy blocks ActiveSync clients. To configure this policy:</span></span>

1. <span data-ttu-id="96daa-p108">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p108">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="96daa-152">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-152">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="96daa-153">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-153">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="96daa-154">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-154">Choose **New policy**.</span></span>

5. <span data-ttu-id="96daa-155">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-155">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="96daa-156">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-156">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="96daa-p109">**앱을**선택 하 고 Office 365 Exchange Online을 선택 합니다. **선택** 하 고 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p109">Choose **Select apps**, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>
8. <span data-ttu-id="96daa-159">**조건**을 선택 하 고 **클라이언트 응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-159">Choose **Conditions**, and then choose **Client apps**.</span></span>
9. <span data-ttu-id="96daa-p110">**구성**대 한 **예**를 선택 합니다. 다음만 확인: **모바일 응용 프로그램 및 데스크톱 클라이언트** 및 **Exchange ActiveSync 클라이언트**입니다. **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p110">For **Configure**, select **Yes**. Check only the following: **Mobile apps and desktop clients** and **Exchange ActiveSync clients**. Click **Done**.</span></span>

10. <span data-ttu-id="96daa-163">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-163">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="96daa-p111">**클라이언트 응용 프로그램을 승인 필요**를 선택, **액세스 권한 부여를**선택 합니다.  여러 컨트롤에 대 한 **선택된 된 컨트롤 필요**를 선택 하 고 **선택**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p111">Choose **Grant access**, select **Require approved client app**.  For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

12. <span data-ttu-id="96daa-166">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-166">Click **Create**.</span></span>

## <a name="setup-office-365-message-encryption"></a><span data-ttu-id="96daa-167">Office 365 메시지 암호화를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-167">Setup Office 365 message encryption</span></span>
<span data-ttu-id="96daa-p112">Azure 정보 보호의 보호 기능을 활용 하는 새로운 Office 365 메시지 암호화 (OME) 기능을 사용 하면 조직 모든 장치에서 모든 사람과 보호 된 전자 메일을 쉽게 공유할 수 있습니다. 사용자가 보내고 Outlook.com, Gmail, 및 기타 전자 메일 서비스를 사용 하 여 Office 365가 아닌 고객은 물론 다른 Office 365 조직으로 보호 된 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96daa-p112">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device. Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="96daa-170">자세한 내용은 [새 Office 365 메시지 암호화 기능을 설정](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96daa-170">For more information, see [Set up new Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span> 

<!---
This article describes recommended policies to help you secure organizational email and email clients that support Modern Authentication and Conditional Access. These recommendations are in addition to the [common identity and access policy recommendations](identity-access-policies.md).

The following recommendations are based on three different layers of security and protection for your email that can be applied based on the granularity of your needs:

- **Baseline**: Microsoft recommends you establish a minimum standard for protecting data, as well as the identities and devices that access your data. Microsoft provides strong default protection that meets the needs of many organizations. Some organizations require additional capabilities to meet their baseline requirements.
- **Sensitive**: Some customers have a subset of data that must be protected at higher levels. You can apply increased protection to specific data sets in your Office 365 environment. Microsoft recommends protecting identities and devices that access sensitive data with comparable levels of security. 
- **Highly regulated**: Some organizations may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

See the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md) topic for more details.

> [!IMPORTANT]
> All security groups created as part of these recommendations must be created with Office features enabled. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.
>
>![Office features enabled for security groups](./media/security-group.png)
>

## Baseline
To create a new conditional access policy: 

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.

2. Choose **Azure Active Directory** from the left menu.

3. Under the **Security** section, choose **Conditional access**.

4. Choose **New policy** as shown in the screen-shot below:

![Baseline CA policy](./media/secure-email/CA-EXO-policy-1.png)

The following tables describe the appropriate settings necessary to express the policies required for each level of protection.

### Medium and above risk requires MFA

The following tables describes the conditional access policy settings to implement for this policy.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users and groups|Include|Select users and groups – Select specific security group containing targeted users|Start with security group including pilot users.|
||Exclude|Exception security group; service accounts (app identities)|Membership modified on an as needed temporary basis|
|Cloud apps|Include|Select apps -  Select Office 365 Exchange Online||
|Conditions|Configured|Yes|Configure specific to your environment and needs|
|Sign-in risk|Risk level|High, medium|Check both|

**Access controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Grant|Grant access|True|Selected|
||Require MFA|True|Check|
||Require compliant devices|False||
||Require domain joined devices|False||
||Require all the selected controls|True|Selected|

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

### Require a compliant or domain joined device

To create a conditional access policy for Exchange Online:

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.

2. Choose **Azure Active Directory** from the left menu.

3. Under the **Security** section, choose **Conditional access**.

4. Choose **New policy**.

5. Enter a policy name, then choose the **Users and groups** you want to apply the policy for.

6. Choose **Cloud apps**.

7. Choose **Select apps**, select **Office 365 Exchange Online** from the **Cloud apps** list, click on **Select**. Once the **Office 365 Exchange Online** app is selected, click **Done**.

8. Choose **Grant** from the **Access controls** section.

9. Choose **Grant access**, select both **Require device to be marked as compliant** and **Require domain joined (Hybrid Azure AD)**, then choose **Select**.

10. Click **Create** to create the Exchange Online conditional access policy.

    > [!NOTE]
    > Beginning with Intune on Azure, you have to create all conditional access policies in the Azure Active Directory workload. Intune provides a link to Azure AD conditional access policies workload from its portal  for convenience.

    > [!IMPORTANT]
    > If you need assistance on migrating conditional access policies previously created in the Intune classic portal to the Intune on Azure portal, see the [reassign conditional access policies from Intune classic portal to the Azure portal](https://docs.microsoft.com/intune/conditional-access-intune-reassign) topic. 

### App-based conditional access for Exchange Online

You can add one more security layer by setting up an app-based conditional access policy for Exchange Online in the Intune on Azure portal. When you apply an app-based conditional access for Exchange Online you require users to use a specific app (E.g. Microsoft Outlook app) to access corporate e-mail.

To add an app-based conditional access policy:

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials. After you've successfully signed in, you see the Azure Dashboard.

2. Choose **More services** from the left menu, then type: "**Intune**".

3. Choose **Intune App Protection**.

4. On the **Intune mobile application management** blade choose **All Settings**.

5. Choose **Exchange Online** under the **Conditional access** section.

6. Select **Allow apps that support Intune app policies**, then choose the app (E.g. Microsoft Outlook).

7. Choose **Restricted user groups**, click **Select groups**, select the user or group you want to apply the policy for, then click **Select**.

## Sensitive

### Low and above risk requires MFA
The following tables describes the conditional access policy settings to implement for low- and above-risk policies.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users and groups|Include|Select users and groups – Select specific security group containing targeted users|Start with security group including pilot users|
||Exclude|Exception security group; service accounts (app identities)|Membership modified on an as needed temporary basis|
|Cloud apps|Include|Select apps -  Select Office 365 Exchange Online||
|Conditions|Configured|Yes|Configure specific to your environment and needs|
|Sign-in risk|Configured|Yes|Configure specific to your environment and needs|
||Risk level|Low, medium, high|Check all three|

**Access controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
||Grant|Grant access|True|Selected|
||Require MFA|True|Check|
||Require compliant devices|False||
||Require domain joined device|False||
||Require all the selected controls|True|Selected|

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

### Require a compliant or domain joined device
(See baseline instructions)

### App-based conditional access for Exchange online

(See baseline instructions)

#### Apply to

Once the pilot project has been completed, these policies should be applied to users in your organization who require access to email considered sensitive.

## Highly regulated
### MFA required

The following tables describes the conditional access policy settings to implement for the highly regulated policy.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users and groups|Include|Select users and groups – Select specific security group containing targeted users|Start with security group including pilot users|
||Exclude|Exception security group; service accounts (app identities)|Membership modified on an as needed temporary basis|
|Cloud apps|Include|Select apps -  Select Office 365 Exchange Online||

**Access controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Grant|Grant access|True|Selected|
||Require MFA|True|Check|
||Require complaint devices|False|Check|
||Require domain joined device|False||
||Require all the selected controls|True|Selected|

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

### Require a compliant or domain joined device
(See baseline instructions)
### App-based conditional access for Exchange online
(See baseline instructions)
#### Apply to
Once the pilot project has been completed, these policies should be applied to users in your organization who require access to email considered highly regulated.

### High risk users policy
To ensure that all high-risk users compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.

Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.

**Assignments**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Users|Include|All users|Selected|
||Exclude|None||
|Conditions|User risk|High|Selected|

**Controls**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
||Access|Allow access|True|Selected|
||Access|Require password change|True|Check|

**Review:** not applicable

> [!NOTE]
> Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy

## Additional configurations
In addition to the above policies, you must configure the following Mobile Application and Device Management settings discussed in this section.

### Intune mobile application management

To ensure email is protected by the policy recommendations stated earlier for each security and data protection tier, you must create Intune app protection policies from within the Azure portal.

To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune App Protection > App policy**.

Add a new policy (+Add) as shown in the following screen shot:

![Intune mobile application management](./media/secure-email/CA-EXO-policy-2.png)

>[!NOTE]
>There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android.
>

The following tables describe the recommended Intune app protection policy settings:

**General**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Email|Name|Secure email policy for Android|Enter a policy name|
||Description||Enter text that describes the policy|
||Platform|Android|There are slight differences in the app protection policy options between iOS and Android; this policy is specifically for Android|

**Apps**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Applications|Apps|Outlook|Selected (list)|

**Settings**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Data relocation|Prevent Android backup|Yes|On iOS this will specifically call out iTunes and iCloud|
|||Allow app to transfer data to other apps|Policy managed apps||
||Allow app to receive data to other apps|Policy managed apps||
||Prevent "Save As"|Yes||
||Restrict cut, copy, and paste with other apps|Policy managed apps||
||Restrict web content to display in the managed browser|No||
||Encrypt app data|Yes|On iOS select option: When device is locked|
||Disable contacts sync|No||
|Access|Require PIN for access|Yes||
||Number of attempts before PIN reset|3||
||Allow simple PIN|No||
||PIN length|6||
||Allow fingerprint instead of PIN|Yes||
||Require Corporate credentials for access|No||
||Block managed apps from running on jailbroken or rooted devices|Yes||
||Recheck the access requirement after (minutes)|30||
||Offline grace period|720||
||Offline interval (days) before app data is wiped|90||
||Block screen capture and Android assistant|No|On iOS this is not an available option|

When complete, remember to click "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.

- See [how to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies) for more details.

### Intune mobile device management
You create the following device configuration profiles and device compliance policies by logging into the [Intune on Azure portal](https://portal.azure.com) with your Intune credentials.

#### iOS email profile
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device configuration profiles at **Device configuration > Profiles > Create Profile > Platform (iOS) > Profile type (E-mail)**.

**Email profile**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Exchange Active Sync|Host (#)|Outlook.office365.com||
||Account Name (#)|SecureEmailAccount|Admini choice|
||Username|User principal name|Selected – Drop down|
||Email address|Primary SMTP address|Selected – Drop down|
||Authentication method|Username and password|Selected – Drop down|
||Use S/MIME|False||
|Synchronization settings|Number of days of email to synchronize|Two weeks|Selected – Drop down|
||Use SSL|True|Check|
||Allow messages to be moved to other email accounts|False||
||Allow email to be sent from third party applications|True||
||Synchronize recently used email addresses|True|Check|

#### Android email profile
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device configuration profiles at **Device configuration > Profiles > Create Profile > Platform (Android) > Profile type (E-mail)**.

**Email profile**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Exchange Active Sync|Host (#)| Outlook.office365.com|
||Account Name (#)|SecureEmailAccount|Admini choice|
||Username|User principal name|Selected – Drop down|
||Email address|Primary SMTP address|Selected – Drop down|
||Authentication method|Username and password|Selected – Drop down|
||Use S/MIME|False||
|Synchronization settings|Number of days of email to synchronize|Two weeks|Selected – Drop down|
||Sync schedule|Not configured|Selected – Drop down|
||Use SSL|True|Check|
||Content type to synchronize|||
||Email|True|Check (locked)|
||Contacts|True|Check|
||Calenadr|True|Check|
||Tasks|True|Check|
||Notes|True|Check|

#### Android for work email profile
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device configuration profiles at **Device configuration > Profiles > Create Profile > Platform (Android for Work) > Profile type (E-mail)**.

**Email profile**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Exchange Active Sync|Host(#)| Outlook.office365.com|
||Account Name(#)|SecureEmailAccount|Admini choice|
||Username|User principal name|Selected – Drop down|
||Email address|Primary SMTP address|Selected – Drop down|
||Authentication method|Username and password|Selected – Drop down|
|Synchronization settings|Number of days of email to synchronize|Two weeks|Selected – Drop down|
||Use SSL|True|Check|

#### Device compliance policy
In the [Intune on Azure portal](https://portal.azure.com), you can create the following device compliance policies at **Device compliance > Policies > Create Policy > Platform (iOS, Android or others) > Settings**.

**System security**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Password|Require a password to unlock mobile devices (...)|Yes|Selected – Drop down|
||Allow simple passwords (...)|No|Selected – Drop down|
||Minimum password length (...)|6|Selected – List|
|Advanced password settings|All|Not configured||
|Encryption|Require encryption on mobile device (...)|Yes|Selected – Drop down|
|Email profiles|Email account must be managed by Intune (iOS 8.0+)|Yes| Selected  – Drop down|
||Select (#)||Must select Email Configuration Policy for iOS: iOS Email Policy (see configuration policies above)|

**Device health**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Windows decide health attestation|Require devices to be reported as healthy (Windows 10 Desktop and Mobile and later)|Yes||
|Device security settings|All|Not configured||
|Device threat protection|All|Not configured||
|Jailbreak|Device must not be jailbroken or rooted (iOS 8.0+, Android 4.0+)|Yes||

**Device properties**
|Type|Properties|Values|Notes|
|:---|:---------|:-----|:----|
|Operating system version|All|Not configured||

For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting Manage Deployment in the Policy section (same level as Add).

## Remediating medium or high risk access events
If a user reports that they are now expected to perform MFA when this was previously not required, support can review their status from a risk perspective.  

Users within the organization with a Global Administrator or Security Administrator role can use Azure AD Identity Protection to review the risky events that contributed to the calculated risk score. If they identify some events that were flagged as suspicious, but are confirmed to be valid (such as a login from an unfamiliar location when an employee is on vacation), the administrator can resolve the event so it no longer contributes to the risk score.
--->

## <a name="next-steps"></a><span data-ttu-id="96daa-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="96daa-171">Next steps</span></span>

[<span data-ttu-id="96daa-172">SharePoint 사이트 및 파일을 보호하기 위한 정책 권장 사항 알아보기</span><span class="sxs-lookup"><span data-stu-id="96daa-172">Learn about policy recommendations for securing SharePoint Sites and files</span></span>](sharepoint-file-access-policies.md)
