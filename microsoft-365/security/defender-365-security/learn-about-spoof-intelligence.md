---
title: 스푸핑 인텔리전스 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 스푸핑된 특정 보낸 사람에 대해 허용하거나 차단할 수 있는 EOP(Exchange Online Protection)의 스푸핑 인텔리전스에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c13c080829236b9a27b6a1a82e1c27256749b5c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073263"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="9ca07-103">EOP에서 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="9ca07-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9ca07-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="9ca07-104">**Applies to**</span></span>
- [<span data-ttu-id="9ca07-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9ca07-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9ca07-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="9ca07-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9ca07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ca07-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9ca07-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 전자 메일 메시지는 2018년 10월부터 EOP의 스푸핑으로부터 자동으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="9ca07-109">EOP는 피싱에 대한 조직의 전반적인 방어의 일부로 스푸핑 인텔리전스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="9ca07-110">자세한 내용은 EOP의 스푸핑 방지 보호 [기능을 참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9ca07-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="9ca07-111">보낸 사람이 전자 메일 주소를 스푸핑하면 조직의 도메인 중 하나에 있는 사용자 또는 조직에 전자 메일을 보내는 외부 도메인의 사용자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="9ca07-112">스팸 또는 피싱 전자 메일을 보내기 위해 보낸 사람 스푸핑하는 공격자는 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="9ca07-113">그러나 합법적인 보낸 사람이 스푸핑하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="9ca07-114">예시:</span><span class="sxs-lookup"><span data-stu-id="9ca07-114">For example:</span></span>

- <span data-ttu-id="9ca07-115">내부 도메인을 스푸핑하기 위한 합법적인 시나리오:</span><span class="sxs-lookup"><span data-stu-id="9ca07-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="9ca07-116">타사 보낸 사람이 도메인을 사용하여 회사 설문 조사를 위해 직원에게 대량 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="9ca07-117">외부 회사에서 사용자 대신 광고 또는 제품 업데이트를 생성하고 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="9ca07-118">도우미는 정기적으로 조직 내의 다른 사용자에 대한 전자 메일을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="9ca07-119">내부 응용 프로그램에서 전자 메일 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="9ca07-120">외부 도메인을 스푸핑하기 위한 합법적인 시나리오:</span><span class="sxs-lookup"><span data-stu-id="9ca07-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="9ca07-121">보낸 사람이 메일링 목록(토론 목록)에 있으며, 메일링 목록은 원래 보낸 사람으로부터 메일링 목록의 모든 참가자에게 전자 메일을 릴레이합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="9ca07-122">외부 회사가 다른 회사를 대신하여 전자 메일을 전송합니다(예: 자동화된 보고서 또는 소프트웨어 as-a-service 회사).</span><span class="sxs-lookup"><span data-stu-id="9ca07-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="9ca07-123">스푸핑 인텔리전스 및 특히 기본(유일한) 스푸핑 인텔리전스 정책은 합법적인 보낸 사람이 보낸 스푸핑된 전자 메일이 EOP 스팸 필터 또는 외부 전자 메일 시스템에 걸려오지 않도록 하는 동시에 스팸 또는 피싱 공격으로부터 사용자를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="9ca07-124">보안 및 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 스푸핑 인텔리전스를 관리할 수 있습니다. &</span><span class="sxs-lookup"><span data-stu-id="9ca07-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9ca07-125">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="9ca07-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9ca07-126"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9ca07-127">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="9ca07-128">피싱 방지 페이지로 직접 **이동하기** 위해 를 <https://protection.office.com/antiphishing> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="9ca07-129">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9ca07-130">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9ca07-131">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-131">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9ca07-132">스푸핑 인텔리전스 정책을 수정하거나 스푸핑 인텔리전스를 사용하거나  사용하지 않도록 설정하려면 조직 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9ca07-133">스푸핑 인텔리전스 정책에 대한 읽기 전용 액세스 권한을  사용하려면 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="9ca07-134">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-134">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="9ca07-135">**참고**:</span><span class="sxs-lookup"><span data-stu-id="9ca07-135">**Notes**:</span></span>

  - <span data-ttu-id="9ca07-136">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9ca07-137">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="9ca07-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="9ca07-139">스푸핑 인텔리전스에 대한 권장 설정은 EOP 기본 피싱 방지 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="9ca07-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="9ca07-140">보안 및 & 센터를 사용하여 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="9ca07-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="9ca07-141">Microsoft 365 Enterprise E5 구독이 있는 경우 또는 Office 365용 Microsoft Defender 추가 기능을 별도로 구입한 경우 스푸핑 인텔리전스 인사이트를 통해 도메인을 스푸핑하는 보낸 사람도 관리할 수 [있습니다.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="9ca07-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="9ca07-142">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="9ca07-143">스팸 **방지 설정 페이지에서** 확장 아이콘을 ![ 클릭하여 스푸핑 인텔리전스 정책을 ](../../media/scc-expand-icon.png) **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![스푸핑 인텔리전스 정책 선택](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="9ca07-145">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="9ca07-146">**새 보낸 사람 검토**</span><span class="sxs-lookup"><span data-stu-id="9ca07-146">**Review new senders**</span></span>
   - <span data-ttu-id="9ca07-147">**이미 검토한 보낸 사람 표시**</span><span class="sxs-lookup"><span data-stu-id="9ca07-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="9ca07-148">이러한 **보낸 사람이** 나타나는 사용자 플라이아웃을 스푸핑할 수 있도록 허용할지 결정에서 다음 탭 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="9ca07-149">**도메인:** 보낸 사람이 내부 도메인의 사용자를 스푸핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="9ca07-150">**외부 도메인:** 보낸 사람이 외부 도메인의 사용자를 스푸핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="9ca07-151">스푸핑 허용 여부 열에서 확장 ![ ](../../media/scc-expand-icon.png) **아이콘을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="9ca07-152">예를 **선택하면** 스푸핑된 보낸 사람이 허용되거나 아니요를 선택하고 메시지를 스푸핑된 메시지로 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="9ca07-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="9ca07-153">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책(기본값은 정크 메일 폴더로 메시지 이동)에 의해 **제어됩니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="9ca07-154">자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="9ca07-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![스푸핑된 보낸 사람 플라이아웃 및 보낸 사람이 스푸핑할 수 있는지 여부를 보여 주는 스크린샷](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="9ca07-156">다음 목록에는 열과 값이 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="9ca07-157">**스푸핑된 사용자:** 스푸핑되는 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="9ca07-158">전자 메일 클라이언트에 표시된 보낸 사람 주소(주소라고도 알려지음)의 메시지 보낸 `5322.From` 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="9ca07-159">SPF에서 이 주소의 유효성을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="9ca07-160">도메인 **탭에서** 값에 단일 전자 메일 주소가 포함되어 있습니다. 또는 원본 전자 메일 서버가 여러 사용자 계정을 스푸핑하는 경우 이 값에는 두 개 **이상이 포함되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="9ca07-161">외부 **도메인 탭의** 값에는 스푸핑된 사용자의 도메인이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="9ca07-162">**보내는 인프라:** 원본 전자 메일 서버의 IP 주소에 대한 역방향 DNS 검색(PTR 레코드)에 있는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="9ca07-163">원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="9ca07-164">메시지 원본 및 메시지 보낸 사람에 대한 자세한 내용은 전자 메일 메시지 표준 [개요를 참조하세요.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="9ca07-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="9ca07-165">**메시지** 수: 지난 30일 이내에 지정된 스푸핑된 보낸 사람 또는 보낸 사람이 포함된 조직으로 보내는 인프라에서 보내는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="9ca07-166">**# of user complaints:** 지난 30일 이내에 이 보낸 사람에 대해 사용자가 제출한 불만 사항</span><span class="sxs-lookup"><span data-stu-id="9ca07-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="9ca07-167">불만은 일반적으로 Microsoft에 대한 정크 제출 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="9ca07-168">**인증 결과:** 다음 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="9ca07-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="9ca07-169">**통과:** 보낸 사람이 SPF 또는 DKIM(보낸 사람 전자 메일 인증 검사)을 통과했습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="9ca07-170">**실패:** 보낸 사람이 EOP 보낸 사람 인증 검사를 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="9ca07-171">**알** 수 없음: 이러한 검사의 결과를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="9ca07-172">**다음에 의해 설정된 결정**: 보내는 인프라가 사용자를 스푸핑할 수 있도록 허용할지 결정한 사용자를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="9ca07-173">**스푸핑 인텔리전스** 정책(자동)</span><span class="sxs-lookup"><span data-stu-id="9ca07-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="9ca07-174">**관리자(수동)**</span><span class="sxs-lookup"><span data-stu-id="9ca07-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="9ca07-175">**마지막 확인** 날짜: 스푸핑된 사용자가 포함된 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="9ca07-176">**스푸핑이 허용되는 경우:** 여기에 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="9ca07-177">**예:** 스푸핑된 사용자와 보내는 인프라의 조합에서 보낸 메시지는 허용될 수 있으며 스푸핑된 전자 메일로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="9ca07-178">**No:** 스푸핑된 사용자와 보내는 인프라의 조합에서 보낸 메시지가 스푸핑된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="9ca07-179">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책(기본값은 정크 메일 폴더로 메시지 이동)에 의해 **제어됩니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="9ca07-180">자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-180">See the next section for more information.</span></span>

     - <span data-ttu-id="9ca07-181">**일부 사용자(** **도메인** 탭에만 해당): 보내는 인프라가 여러 사용자를 스푸핑하고, 일부 스푸핑된 사용자가 허용되는 경우 및 다른 사용자는 스푸핑되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="9ca07-182">자세한 **탭을 사용하여** 특정 주소를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="9ca07-183">페이지 아래쪽에서 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="9ca07-184">PowerShell을 사용하여 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="9ca07-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="9ca07-185">허용 및 차단된 보낸 사람이 스푸핑 인텔리전스에서 볼 수 있도록 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="9ca07-186">이 예에서는 도메인의 사용자를 스푸핑할 수 있는 모든 보낸 사람에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="9ca07-187">구문과 매개 변수에 대한 자세한 내용은 [Get-PhishFilterPolicy를 참조하십시오.](/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="9ca07-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="9ca07-188">스푸핑 인텔리전스에서 허용 및 차단된 보낸 사람 구성을 구성하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="9ca07-189">**Get-PhishFilterPolicy** cmdlet의 출력을 CSV 파일에 기록하여 검색된 스푸핑된 보낸 사람의 현재 목록을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="9ca07-190">CSV 파일을 편집하여 **SpoofedUser(전자** 메일 주소) 및 **AllowedToSpoof(예** 또는 아니요) 값을 추가하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="9ca07-191">파일을 저장하고, 파일을 읽고, 이라는 변수로 내용을 `$UpdateSpoofedSenders` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="9ca07-192">변수를 사용하여 스푸핑 인텔리전스 `$UpdateSpoofedSenders` 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="9ca07-193">구문과 매개 변수에 대한 자세한 내용은 [Set-PhishFilterPolicy를 참조하십시오.](/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="9ca07-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="9ca07-194">보안 및 준수 & 사용하여 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="9ca07-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="9ca07-195">스푸핑 인텔리전스에 대한 구성 옵션은 피싱 방지 정책의 스푸핑 설정에 [설명되어 있습니다.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="9ca07-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="9ca07-196">기본 피싱 방지 정책 및 사용자 지정 정책에서 스푸핑 인텔리전스 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="9ca07-197">구독에 기반한 지침은 다음 항목 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="9ca07-198">[EOP에서 피싱 방지 정책을 구성합니다.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="9ca07-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="9ca07-199">[Microsoft Defender for Office 365에서 피싱 방지 정책을 구성합니다.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9ca07-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9ca07-200">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="9ca07-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="9ca07-201">스푸핑이 허용 및 허용되지 않는 보낸 사람에 대해 스푸핑 인텔리전스를 구성하고 스푸핑 인텔리전스 설정을 구성한지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="9ca07-202">보안 & 준수 센터에서 위협 관리  정책 스팸 방지 확장 스푸핑 \>  \>  \> **인텔리전스** \>  \>    정책으로 이동하여 이미 검토한 보낸 사람 표시를 선택하고 사용자의 도메인 또는 외부 도메인 탭을 선택하고 보낸 사람에 대해 스푸핑 허용 여부 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="9ca07-203">PowerShell에서 다음 명령을 실행하여 스푸핑이 허용 및 허용되지 않은 보낸 사람 보기</span><span class="sxs-lookup"><span data-stu-id="9ca07-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="9ca07-204">PowerShell에서 다음 명령을 실행하여 스푸핑된 모든 보낸 사람 목록을 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="9ca07-205">보안 & 준수 센터에서 위협  관리 정책 피싱 방지 또는 ATP 피싱 방지로 이동한 후 다음 단계 중 \>  \>  하나를 수행합니다.   </span><span class="sxs-lookup"><span data-stu-id="9ca07-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="9ca07-206">목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-206">Select a policy from the list.</span></span> <span data-ttu-id="9ca07-207">플라이아웃이 나타나면 스푸핑 섹션의 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="9ca07-208">기본 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-208">Click **Default policy**.</span></span> <span data-ttu-id="9ca07-209">플라이아웃이 나타나면 스푸핑 섹션의 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="9ca07-210">Exchange Online PowerShell에서 Office365 AntiPhish Default 또는 사용자 지정 정책의 이름으로 바꾸고 다음 명령을 실행하여 설정을 \<Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="9ca07-211">스푸핑 및 피싱을 관리하는 다른 방법</span><span class="sxs-lookup"><span data-stu-id="9ca07-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="9ca07-212">스푸핑 및 피싱 보호에 대해 신각해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="9ca07-213">다음은 도메인을 스푸핑하는 보낸 사람이 조직을 손상하지 않도록 하는 관련 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="9ca07-214">**스푸핑 메일 보고서를 검사합니다.**</span><span class="sxs-lookup"><span data-stu-id="9ca07-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="9ca07-215">이 보고서를 자주 사용하여 스푸핑된 보낸 사람 관리를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="9ca07-216">자세한 내용은 [스푸핑 검색 보고서를 참조하세요.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="9ca07-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="9ca07-217">SPF(Sender Policy Framework) 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="9ca07-218">SPF를 빠르게 도입하여 신속하게 구성하려면 [스푸핑 방지를 위해 Microsoft 365에서 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="9ca07-219">Office 365에서 SPF를 사용하는 방법이나 문제 해결 또는 비표준 배포(예: 하이브리드 배포)에 대한 자세한 내용은 [Office 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 차단하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="9ca07-220">DomainKeys 식별 메일(DKIM) 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="9ca07-221">SPF 및 DMARC 외에도 DKIM을 사용하여 공격자가 도메인에서 보낸 것 같은 메시지를 보내지 못하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="9ca07-222">DKIM을 사용하면 메시지 머리글에 있는 전자 메일 메시지에 디지털 서명을 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="9ca07-223">자세한 내용은 [DKIM을 사용하여 Office 365의](use-dkim-to-validate-outbound-email.md)사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성 검사를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="9ca07-224">도메인 기반 메시지 인증, 보고 및 적합성(DMARC) 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="9ca07-225">SPF 및 DKIM과 함께 DMARC를 구현하면 스푸핑 및 피싱 전자 메일에 대한 추가 보호 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="9ca07-226">DMARC는 수신 메일 시스템이 사용자의 도메인에서 보낸 SPF 또는 DKIM 확인에 실패한 메시지에 대해 수행할 작업을 결정하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ca07-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="9ca07-227">자세한 내용은 [DMARC를 사용하여 Office 365에서](use-dmarc-to-validate-email.md)전자 메일 유효성 검사를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca07-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>