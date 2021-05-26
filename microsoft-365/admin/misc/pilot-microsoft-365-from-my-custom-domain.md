---
title: 사용자 지정 도메인에서 Microsoft 365 파일럿
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: 두 개의 테스트 계정만 사용하여 사용자 지정 도메인의 전자 메일 기능을 Microsoft 365 사서함으로 시험해 보는 방법에 대해 알아봅니다.
ms.openlocfilehash: b2017da30aba3b48b51de26b7907167dc5dd3e6e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623648"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="ff4aa-103">사용자 지정 도메인에서 Microsoft 365 파일럿</span><span class="sxs-lookup"><span data-stu-id="ff4aa-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="ff4aa-104">다음 요구 사항 및 제한으로 Microsoft 365를 시험해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="ff4aa-105">현재 전자 메일 공급자가 전자 메일 전달을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="ff4aa-106">Microsoft 365에서 이러한 레코드를 관리하는 것이 아니라 DNS 호스팅 공급자에서 Microsoft 365 DNS 레코드를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="ff4aa-107">자세한 내용은 [DNS 레코드를 추가하여 도메인 연결하기](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-107">To learn more, see [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="ff4aa-108">다른 전자 메일 서버의 사용자에 대한 약속 있음/없음 정보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="ff4aa-109">관리자는 한 위치에서 모든 사용자 계정을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="ff4aa-110">사용자가 Microsoft 365 스팸 필터링을 사용하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="ff4aa-111">이 기능은 매우 적은 수의 사용자에게 권장되며 파일럿용 전자 메일 사용에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="ff4aa-112">Microsoft 365 파일럿 설정하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="ff4aa-113">Microsoft 365 파일럿을 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="ff4aa-114">1단계: Microsoft 365 관리 센터에 로그인하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ff4aa-115">회사 또는 학교 계정으로 [Microsoft 365 관리자 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="ff4aa-116">왼쪽 탐색 창에서 **설정** > **도메인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="ff4aa-117">2단계: 사용하려는 도메인을 소유했는지 확인하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="ff4aa-118">**도메인** 페이지에서 **도메인 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="ff4aa-119">상자에 도메인 이름을 입력하고 **이 도메인 사용** 을 선택한 다음 **계속** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="ff4aa-120">전자 메일 및 인스턴트 메시징과 같이 도메인을 사용하여 테스트하려는 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

4. <span data-ttu-id="ff4aa-121">도메인 **확인** 페이지에서 단계별 지침을 따르고 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="ff4aa-122">DNS 변경 내용이 적용되기까지 몇 분에서 72시간까지 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="ff4aa-123">확인에 성공하면 DNS 레코드를 수정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="ff4aa-124">3단계: 도메인을 Exchange Online에서 공유됨으로 표시하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="ff4aa-125">Exchange 관리 센터의 **메일 흐름** 섹션에서 **허용 도메인** 을 선택한 다음 수정하려는 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="ff4aa-126">창을 두 번 클릭하여 연 다음 **내부 릴레이** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-126">Double-click to open the window, and then select **Internal Relay**.</span></span>

3. <span data-ttu-id="ff4aa-127">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-127">Select **Save**.</span></span>

    <span data-ttu-id="ff4aa-128">이 설정이 적용되는 데 몇 분 정도가 필요할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="ff4aa-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="ff4aa-129">4단계: 기존 전자 메일 서버 차단 해제하기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ff4aa-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="ff4aa-130">Microsoft 365에서는 스팸 방지를 위해 EOP(Exchange Online Protection)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="ff4aa-131">EOP가 현재 메일 서버에서 다량의 스팸 메일이 전달되는 것을 탐지하면 기존 메일 서버를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="ff4aa-132">다른 전자 메일 공급자의 스팸 방지를 신뢰하는 경우 Microsoft 365에서 서버 차단을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="ff4aa-133">기존 전자 메일 서버 차단을 해제하면 원래 서버를 통해 들어오는 모든 스팸이 Microsoft 365 사서함으로 전달되며, Microsoft 365에서 스팸을 얼마나 잘 방지하는지 평가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can't evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="ff4aa-134">Exchange 관리 센터 탐색 창에서 **보호** 를 선택한 다음 **연결 필터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="ff4aa-135">**IP 허용 목록** 에서 **+** 를 선택하고 현재 전자 메일 공급자의 메일 서버 IP 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span>

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="ff4aa-136">5단계: 사용자 계정 만들기 및 기본 회신 주소 설정하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="ff4aa-137">Microsoft 365 관리 센터 왼쪽 탐색에서 **사용자** > **활성 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="ff4aa-138">두 명의 기존 사용자를 추가하여 두 개의 테스트 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="ff4aa-139">각 계정에 대해 **+사용자 추가** 를 선택하고 테스트하려는 암호 방법을 포함하여 필요한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="ff4aa-140">사용자의 전자 메일을 동일하게 유지하려면 **사용자 이름** 필드가 사용자의 현재 전자 메일 주소와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-140">To ensure a user's email stays the same, the **User name** field must match the user's current email address.</span></span>

3. <span data-ttu-id="ff4aa-141">적절한 라이선스를 선택하고 **다음** 을 클릭한 다음 **추가 완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span>

4. <span data-ttu-id="ff4aa-142">**사용자 이름** 옆의 드롭다운 목록에서 사용자 지정 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span>

5. <span data-ttu-id="ff4aa-143">**만들기** > **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="ff4aa-144">6단계: \*\*Microsoft 365 또는 Office 365에서 전자 메일 서버로 전송되는 메일 구성하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="ff4aa-145">해당 작업에는 두 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-145">There are two steps for this:</span></span>

1. <span data-ttu-id="ff4aa-146">Microsoft 365 또는 Office 365 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ff4aa-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="ff4aa-147">Microsoft 365 또는 Office 365에서 전자 메일 서버로 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="ff4aa-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="ff4aa-148">1. Microsoft 365 또는 Office 365 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ff4aa-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="ff4aa-149">Microsoft 365 또는 Office 365에서 다음 사항을 완료했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="ff4aa-150">커넥터를 설정하려면 시작하기 전에 할당된 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="ff4aa-151">필요한 사용 권한을 확인하려면 [Exchange Online의 기능 사용 권한](/exchange/permissions-exo/feature-permissions) 항목에서 Microsoft 365 및 Office 365 커넥터 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in Exchange Online](/exchange/permissions-exo/feature-permissions) topic.</span></span>

2. <span data-ttu-id="ff4aa-152">EOP 또는 Exchange Online이 전자 메일 서버에서 인터넷으로 전자 메일을 릴레이하도록 하려면 다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="ff4aa-153">Microsoft 365 또는 Office 365의 허용 도메인과 일치하는 주체 이름으로 구성된 인증서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ff4aa-154">인증서의 일반 이름 또는 주체 대체 이름은 조직에 대한 기본 SMTP 도메인과 일치시키는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="ff4aa-155">자세한 내용은 [온-프레미스 전자 메일 환경의 필수 구성 요소](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-155">For details, see [Prerequisites for your on-premises email environment](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="ff4aa-156">-또는-</span><span class="sxs-lookup"><span data-stu-id="ff4aa-156">-OR-</span></span>

   - <span data-ttu-id="ff4aa-157">조직의 모든 보낸 사람 도메인과 하위 도메인이 Microsoft 365 또는 Office 365에서 허용 도메인으로 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="ff4aa-158">허용 도메인 정의에 대한 자세한 내용은 [Exchange Online에서 허용 도메인 관리](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 및 [Exchange Online에서 하위 도메인에 대한 메일 흐름 사용](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="ff4aa-159">메일 흐름 규칙(전송 규칙)을 사용할지 또는 도메인 이름을 사용할지 결정하여 Microsoft 365 또는 Office 365에서 전자 메일 서버로 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="ff4aa-160">대부분의 기업은 모든 허용 도메인에 대한 메일을 전송하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="ff4aa-161">자세한 내용은 [시나리오: Exchange Online에서 조건부 메일 라우팅](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="ff4aa-162">[Exchange Online에서 메일 흐름 규칙 동작](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)에 설명된 대로 메일 흐름 규칙을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="ff4aa-163">예를 들어 현재 메일이 메일 그룹을 통해 여러 사이트로 직접 전송되는 경우 커넥터와 함께 메일 흐름 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="ff4aa-164">2. Microsoft 365 또는 Office 365에서 전자 메일 서버로 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="ff4aa-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="ff4aa-165">Microsoft 365 또는 Office 365에서 커넥터를 만들려면 **관리** 를 클릭한 다음 **Exchange** 를 클릭하여 Exchange 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="ff4aa-166">그 다음 **메일 흐름**, **커넥터** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="ff4aa-167">마법사를 사용하여 커넥터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="ff4aa-168">마법사를 시작하려면 더하기 기호 **+** 을(를) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="ff4aa-169">첫 번째 화면에서 Office 365 **에서** 및 조직 메일 서버 **로** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="ff4aa-170">**다음** 을 클릭하고 마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="ff4aa-171">추가 정보가 필요한 경우 **도움말** 또는 **추가 정보** 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="ff4aa-172">마법사가 설정 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="ff4aa-173">완료되면 커넥터 유효성 검사가 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="ff4aa-174">커넥터 유효성 검사가 실행되지 않는 경우 자세한 내용을 보려면 표시된 메시지를 두 번 클릭하고 문제 해결을 위해 [커넥터 유효성 검사](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="ff4aa-175">7단계: DNS 호스팅 공급자에서 DNS 레코드 업데이트하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="ff4aa-176">DNS 호스팅 공급자의 웹 사이트에 로그인하고 [DNS 레코드를 추가하여 도메인 연결하기](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="ff4aa-177">**다음 두 가지 예외를 수행합니다.**</span><span class="sxs-lookup"><span data-stu-id="ff4aa-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="ff4aa-178">새 MX 레코드를 만들거나 기존 MX 레코드를 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="ff4aa-179">이전 전자 메일 공급자에 대해 SPF(Sender Policy Framework) 레코드가 이미 있는 경우에는 Exchange용 SPF(TXT) 레코드를 새로 만드는 대신 현재 TXT 레코드에 "include:spf.protection.outlook.com"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="ff4aa-180">예를 들어 “v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all”과 같이 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="ff4aa-p109">아직 SPF 레코드가 없는 경우에는 Microsoft 365에서 추천하는 레코드를 수정하여 현재 전자 메일 공급자의 도메인을 포함하고 spf.protection.outlook.com을 추가합니다. 이렇게 하면 두 전자 메일 시스템에서 발송되는 메시지에 대한 권한이 승인됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-p109">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com. This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="ff4aa-183">8단계: 현재 공급자에서 전자 메일 전달 설정하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="ff4aa-184">현재 전자 메일 공급자에서 사용자의 전자 메일 계정이 onmicrosoft.com 도메인으로 전달되도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="ff4aa-185">사용자 A 사서함을 usera@yourcompany.onmicrosoft.com으로 전달</span><span class="sxs-lookup"><span data-stu-id="ff4aa-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="ff4aa-186">사용자 B 사서함을 userb@yourcompany.onmicrosoft.com으로 전달</span><span class="sxs-lookup"><span data-stu-id="ff4aa-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="ff4aa-187">이 단계를 완료하면 usera@yourcompany.com 및 userb@yourcompany.com으로 전송된 모든 전자 메일을 Microsoft 365에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="ff4aa-188">전자 메일 전달을 설정하는 정확한 단계에 대해서는 현재 전자 메일 공급자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="ff4aa-189">현재 전자 메일 공급자에 메시지 복사본을 유지할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="ff4aa-190">대부분의 공급자는 보낸 사람의 회신 주소는 그대로 유지하고 전자 메일을 전달하므로, 회신은 원래 보낸 사람에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="ff4aa-191">9단계: 메일 흐름 테스트하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="ff4aa-192">사용자 A의 자격 증명을 사용하여 Outlook Web App에 로그인합니다. </span><span class="sxs-lookup"><span data-stu-id="ff4aa-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="ff4aa-193">다음 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-193">Perform these tests:</span></span>

    - <span data-ttu-id="ff4aa-194">예를 들어 사용자 B에게 전자 메일을 보내 로컬 Microsoft 전자 메일을 테스트합니다. 전자 메일은 즉시 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="ff4aa-195">이 시나리오에서는 Microsoft 365 사서함이 로컬이기 때문에 메시지가 원래 서버에서 사용자 B의 사서함으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="ff4aa-196">예를 들어 사용자 C에게 전자 메일을 보내 기존 전자 메일 시스템에서 전자 메일을 사용자에게 테스트합니다. 전자 메일은 원본 메일 서버에서 사용자 C의 사서함으로 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="ff4aa-197">전달이 외부 계정에서, 기존 전자 메일 시스템의 직원 전자 메일 계정에서 제대로 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="ff4aa-198">예를 들어 사용자 C의 원래 서버 계정 또는 Hotmail 계정에서 사용자 A에게 전자 메일을 보내고 사용자 A의 Microsoft 365 사서함에 도착하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="ff4aa-199">10단계: 사서함 콘텐츠 이동하기</span><span class="sxs-lookup"><span data-stu-id="ff4aa-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="ff4aa-200">두 명의 테스트 사용자만 이동하고 사용자 A와 사용자 B가 모두 Outlook을 사용하고 있으므로, 새 Outlook 프로필에서 이전 .PST 파일을 열고 메시지, 일정 항목, 연락처 등을 복사하여 전자 메일을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="ff4aa-201">자세한 내용은 [Outlook .pst 파일에서 전자 메일, 연락처 및 일정 가져오기](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="ff4aa-202">콘텐츠를 Microsoft 365 사서함의 적절한 위치로 가져온 후에는 모든 장치에서 어디서나 해당 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff4aa-202">After they're imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>
