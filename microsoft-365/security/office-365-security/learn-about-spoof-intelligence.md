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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 특정 스푸핑된 보낸 사람을 허용하거나 차단할 수 있는 EOP(Exchange Online Protection)에서 스푸핑 인텔리전스에 대해 자세히 설명할 수 있습니다.
ms.openlocfilehash: 66cfc419c3e2f3a5dd8ad45cdb9fe651b613679b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826580"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="bc6cd-103">EOP에서 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="bc6cd-103">Configure spoof intelligence in EOP</span></span>

<span data-ttu-id="bc6cd-104">Exchange Online 사서함이 없는 사서함 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직이 있는 Microsoft 365 조직에서는 2018년 10월이전 시 EOP의 스푸핑으로부터 인바운드 전자 메일 메시지가 자동으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="bc6cd-105">EOP는 피싱에 대한 조직의 전반적인 방어의 일부로 스푸핑 인텔리전스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="bc6cd-106">자세한 내용은 [EOP에서 스푸핑 방지 보호 기능을 참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="bc6cd-107">보낸 사람이 전자 메일 주소를 스푸핑하면 이는 조직의 도메인 중 하나 또는 조직으로 전자 메일을 보내는 외부 도메인의 사용자에게 표시되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="bc6cd-108">스팸 또는 피싱 전자 메일을 보내도록 위장된 발신자는 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="bc6cd-109">하지만 합법적 보낸 사람을 스푸핑하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="bc6cd-110">예제:</span><span class="sxs-lookup"><span data-stu-id="bc6cd-110">For example:</span></span>

- <span data-ttu-id="bc6cd-111">내부 도메인 스푸핑에 대한 합법적 시나리오:</span><span class="sxs-lookup"><span data-stu-id="bc6cd-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="bc6cd-112">타사 보낸 사람은 도메인을 사용하여 회사 폴링을 위해 사용자의 직원에게 대량 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="bc6cd-113">외부 회사는 사용자 대신 광고 또는 제품 업데이트를 생성하고 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="bc6cd-114">도우미는 정기적으로 조직 내 다른 사람의 전자 메일을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="bc6cd-115">내부 응용 프로그램은 전자 메일 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="bc6cd-116">외부 도메인 스푸핑에 대한 합법적 시나리오:</span><span class="sxs-lookup"><span data-stu-id="bc6cd-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="bc6cd-117">보낸 사람이 메일 목록에 있고(토론 목록이라고도 함) 메일링 목록은 전자 메일을 원래 보낸 사람에서 우편 참가자 모두에게 릴레이합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="bc6cd-118">외부 회사가 다른 회사(예: 자동화된 보고서 또는 software-as-a-service 회사)를 대신하여 이메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="bc6cd-119">스푸핑 인텔리전스, 특히 기본 스푸핑 인텔리전스 정책은 정상적인 보낸 사람이 보낸 스푸핑된 전자 메일이 EOP 스팸 필터 또는 외부 전자 메일 시스템에서 조용되지 않도록 하면서 스팸 또는 피싱 공격으로부터 사용자를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="bc6cd-120">사용자는 보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직의 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 스푸핑 인텔리전스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bc6cd-121">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc6cd-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bc6cd-122"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bc6cd-123">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="bc6cd-124">피싱 방지 **페이지로 직접 이동하려면 을** 사용합니다. <https://protection.office.com/antiphishing></span><span class="sxs-lookup"><span data-stu-id="bc6cd-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="bc6cd-125">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bc6cd-126">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bc6cd-127">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-127">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="bc6cd-128">스푸핑 인텔리전스 정책을 수정하거나 스푸핑 인텔리전스를 사용하거나 사용하지 않도록 설정하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="bc6cd-129">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="bc6cd-130">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-130">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="bc6cd-131">스푸핑 인텔리전스 정책에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-131">For read-only access to the spoof intelligence policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="bc6cd-132">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-132">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="bc6cd-133">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-133">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="bc6cd-134">스푸핑 인텔리전스에 대한 권장 설정은 [EOP 기본 피싱 방지 정책 설정을 참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-134">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="bc6cd-135">보안 서비스 & 사용하여 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="bc6cd-135">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="bc6cd-136">Microsoft 365 Enterprise E5를 구독하는 경우 또는 Office 365 ATP(Advanced Threat Protection) 추가 기능을 별도로 구입한 경우 스푸핑 인텔리전스 인사이트를 통해 도메인을 스푸핑하는 [보낸 사람도 관리할 수 있습니다.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-136">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Office 365 Advanced Threat Protection (Office 365 ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="bc6cd-137">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="bc6cd-138">스팸 방지 **설정 페이지에서 확장 아이콘을** ![ 클릭하여 ](../../media/scc-expand-icon.png) 스푸핑 **인텔리전스 정책을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-138">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![스푸핑 인텔리전스 정책 선택](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="bc6cd-140">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-140">Make one of the following selections:</span></span>

   - <span data-ttu-id="bc6cd-141">**새 보낸 사람 검토**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-141">**Review new senders**</span></span>
   - <span data-ttu-id="bc6cd-142">**Show me senders I already reviewed**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-142">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="bc6cd-143">이러한 보낸 **사람이 표시되는 사용자 플라이아웃을** 스푸핑할 수 있는지 여부를 결정할 시 다음 탭 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-143">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="bc6cd-144">**도메인:** 보낸 사람: 내부 도메인의 사용자를 스푸핑합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-144">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="bc6cd-145">**외부 도메인:** 외부 도메인의 사용자를 스푸핑하는 보낸 사람</span><span class="sxs-lookup"><span data-stu-id="bc6cd-145">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="bc6cd-146">![ ](../../media/scc-expand-icon.png) 스푸핑하도록 **허용되는 첫 추가 아이콘을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-146">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="bc6cd-147">**스푸핑된** 보낸 사람을 허용하려면 **예를** 선택하거나 메시지를 스푸핑된 것으로 표시하려면 아니요를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-147">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="bc6cd-148">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 ATP 피싱 방지 정책을 사용하여 제어합니다(기본값은 **정크 메일 폴더로 메시지 이동).**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-148">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="bc6cd-149">자세한 내용은 [피싱 방지 정책의 스푸핑 설정을 참조하십시오.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-149">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![스푸핑된 보낸 사람 플라이아웃 및 보낸 사람이 스푸핑하도록 허용되는지를 보여 주는 스크린샷](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="bc6cd-151">다음 목록에서는 열과 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-151">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="bc6cd-152">**스푸핑된**사용자: 스푸핑되는 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-152">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="bc6cd-153">전자 메일 클라이언트에 표시되는 보낸 사람 `5322.From` 주소(주소라고도 함)의 메시지 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-153">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="bc6cd-154">이 주소의 유효성은 SPF에서 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-154">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="bc6cd-155">도메인 **탭의 값에는** 단일 전자 메일 주소가 포함됩니다. 원본 전자 메일 서버가 여러 사용자 계정을 스푸핑하고 있는 경우 둘 **이상의 계정이 포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-155">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="bc6cd-156">외부 도메인 **탭의** 값에는 전체 전자 메일 주소가 없는 스푸핑된 사용자 도메인이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-156">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="bc6cd-157">**보내는 인프라:** 원본 전자 메일 서버 IP 주소의 역방향 DNS 조회(PTR 레코드)에 있는 도메인입니다. 또는 원본에 PTR 레코드가 없는 경우에는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-157">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="bc6cd-158">메시지 원본 및 메시지 보낸 사람에 대한 자세한 내용은 전자 [메일 메시지 표준의 개요를 참조하십시오.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-158">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="bc6cd-159">**메시지 수**: 지난 30일 이내에 지정된 스푸핑된 보낸 사람 또는 보낸 사람을 포함하는 조직으로 전송 인프라에서 조직에 전송된 메시지의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-159">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="bc6cd-160">**사용자 기대 용도 : 지난**30일 이내에 이 보낸 사람에게 대해 사용자가 차단한 비상 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-160">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="bc6cd-161">보상은 일반적으로 Microsoft로의 정크 제출 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-161">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="bc6cd-162">**인증 결과:** 다음 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="bc6cd-162">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="bc6cd-163">**통과됨**: 보낸 사람이 보낸 사람 의사 전자 메일 인증 검사(SPF 또는 DKIM)를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-163">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="bc6cd-164">**실패**: 보낸 사람이 EOP 보낸 사람 인증 검사에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-164">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="bc6cd-165">**알 수**없음: 이러한 검사 결과를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-165">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="bc6cd-166">**의사 결정**집합: 송신 인프라가 사용자 스푸핑을 허용할지 결정한 사람을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-166">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="bc6cd-167">**스푸핑 인텔리전스** 정책(자동)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-167">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="bc6cd-168">**Admin** Admin(수동)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-168">**Admin** (manual)</span></span>

   - <span data-ttu-id="bc6cd-169">**마지막 시드:** 스푸핑된 사용자를 포함하는 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-169">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="bc6cd-170">**스푸핑 허용되는 값:** 아래에 나와 있는 값:</span><span class="sxs-lookup"><span data-stu-id="bc6cd-170">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="bc6cd-171">**예:** 스푸핑된 사용자와 보내는 인프라가 조합되어 있는 메시지는 허용되고 스푸핑된 전자 메일로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-171">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="bc6cd-172">**아니요:** 스푸핑된 사용자 및 전송 인프라가 결합된 메시지는 스푸핑으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-172">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="bc6cd-173">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 ATP 피싱 방지 정책을 사용하여 제어합니다(기본값은 **정크 메일 폴더로 메시지 이동).**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-173">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="bc6cd-174">자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-174">See the next section for more information.</span></span>

     - <span data-ttu-id="bc6cd-175">**Some users** **(Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-175">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="bc6cd-176">자세한 **탭을** 사용하여 특정 주소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-176">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="bc6cd-177">페이지 맨 아래에서 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-177">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="bc6cd-178">PowerShell을 사용하여 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="bc6cd-178">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="bc6cd-179">스푸핑 인텔리전스에서 허용되고 수신 거부를 확인하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-179">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="bc6cd-180">이 예에서는 도메인의 사용자를 스푸핑할 수 있는 모든 보낸 사람에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-180">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="bc6cd-181">구문과 매개 변수에 대한 자세한 내용은 [Get-PhishFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-181">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="bc6cd-182">스푸핑 인텔리전스에서 허용되고 수신 거부를 구성하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-182">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="bc6cd-183">**Get-PhishFilterPolicy** cmdlet의 출력을 CSV 파일에 작성하여 검색된 발신자의 현재 목록을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-183">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="bc6cd-184">CSV 파일을 편집하여 **SpoofedUser(전자** 메일 주소) 및 **AllowedToSpoof(예 또는 아니요)** 값을 추가하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-184">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="bc6cd-185">파일을 저장하고 파일을 읽고 콘텐츠를 다음변수로 `$UpdateSpoofedSenders` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-185">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="bc6cd-186">다음 `$UpdateSpoofedSenders` 변수를 사용하여 스푸핑 인텔리전스 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-186">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="bc6cd-187">구문과 매개 변수에 대한 자세한 내용은 [Set-PhishFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-187">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="bc6cd-188">보안 그룹 규정 & 사용하여 스푸핑 인텔리전스 구성</span><span class="sxs-lookup"><span data-stu-id="bc6cd-188">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="bc6cd-189">스푸핑 인텔리전스의 구성 옵션은 피싱 방지 [정책의 스푸핑 설정에 설명되어 있습니다.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-189">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="bc6cd-190">기본 피싱 방지 정책및 사용자 지정 정책에서 스푸핑 인텔리전스 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-190">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="bc6cd-191">구독에 따른 지침은 다음 항목 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-191">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="bc6cd-192">[EOP에서 피싱 방지 정책을 구성합니다.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-192">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="bc6cd-193">[Microsoft 365에서 ATP 피싱 방지 정책을 구성합니다.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-193">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bc6cd-194">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="bc6cd-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="bc6cd-195">스푸핑 할 수 있도록 허용되고 허용되지 않는 보낸 사람과 스푸핑 인텔리전스를 구성했는지 확인하려면 다음 단계 중 하나를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-195">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="bc6cd-196">보안 설정 준수 & 센터에서 위협 관리 **Threat management** 정책으로 이동하여 스푸핑 인텔리전스 정책에 있는 스푸핑 인텔리전스 정책을 확장하고 이미 사용자 도메인 또는 외부 도메인 탭을 선택하기를 선택한 후 보낸 사람에 대해 \> **Policy** \> **Anti-spam** \> **Spoof intelligence policy** \> **Show me senders I already reviewed** \> **스푸핑이 허용되는지** 확인합니다. **Your Domains** **External Domains**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="bc6cd-197">PowerShell에서 다음 명령을 실행하여 스푸핑이 허용되고 스푸핑이 허용되지 않는 보낸 사람을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-197">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="bc6cd-198">PowerShell에서 다음 명령을 실행하여 스푸핑된 모든 보낸 사람 목록을 CSV 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-198">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="bc6cd-199">보안 규정 준수 & 서비스에서 위협 관리 **Threat management** 정책 방지 정책 방지 또는 ATP 피싱 방지로 이동한 후 \> **Policy** \> **Anti-phishing** 다음 단계 중 하나를 수행합니다. **ATP anti-phishing**  </span><span class="sxs-lookup"><span data-stu-id="bc6cd-199">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="bc6cd-200">목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-200">Select a policy from the list.</span></span> <span data-ttu-id="bc6cd-201">플라이아웃이 나타나면 스푸핑 섹션에서 **값을 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-201">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="bc6cd-202">기본 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-202">Click **Default policy**.</span></span> <span data-ttu-id="bc6cd-203">플라이아웃이 나타나면 스푸핑 섹션에서 **값을 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-203">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="bc6cd-204">Exchange Online PowerShell에서 \<Name\> Office365 AntiPhish Default 또는 사용자 지정 정책의 이름으로 바꾸고 다음 명령을 실행하여 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-204">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="bc6cd-205">스푸핑 및 피싱을 관리하는 다른 방법</span><span class="sxs-lookup"><span data-stu-id="bc6cd-205">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="bc6cd-206">스푸핑 및 피싱 방지에 대해 고지하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-206">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="bc6cd-207">다음은 보낸 사람이 도메인을 스푸핑하고 조직을 어드로운 것을 방지하는 데 도움이 되는 관련 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-207">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="bc6cd-208">**스푸핑 메일 보고서를 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc6cd-208">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="bc6cd-209">이 보고서를 통해 스푸핑된 보낸 사람을 확인하고 관리하는 데 도움이 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-209">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="bc6cd-210">자세한 내용은 [스푸핑 탐지 보고서를 참조하십시오.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-210">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="bc6cd-211">SPF(Sender Policy Framework) 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-211">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="bc6cd-212">SPF를 빠르게 도입하여 신속하게 구성하려면 [스푸핑 방지를 위해 Microsoft 365에서 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-212">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="bc6cd-213">Office 365에서 SPF를 사용하는 방법이나 문제 해결 또는 비표준 배포(예: 하이브리드 배포)에 대한 자세한 내용은 [Office 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 차단하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-213">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="bc6cd-214">DKIM(DomainKeys 식별 메일) 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-214">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="bc6cd-215">SPF 및 DMARC와 함께 DKIM을 사용하여 공격자가 사용자의 도메인에서 오는 것처럼 보이는 메시지를 보내지 못하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-215">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="bc6cd-216">DKIM을 사용하면 메시지 머리글에 있는 전자 메일 메시지에 디지털 서명을 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-216">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="bc6cd-217">자세한 내용은 [DKIM을 사용하여 Office 365의 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성을 검사하는 데 DKIM을 참조하세요.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-217">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="bc6cd-218">DMARC(도메인 기반 메시지 인증, 보고 및 적정) 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-218">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="bc6cd-219">SPF 및 DKIM과 함께 DMARC를 구현하면 스푸핑 및 피싱 전자 메일에 대한 추가 보호 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-219">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="bc6cd-220">DMARC는 수신 메일 시스템이 사용자의 도메인에서 보낸 SPF 또는 DKIM 확인에 실패한 메시지에 대해 수행할 작업을 결정하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc6cd-220">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="bc6cd-221">자세한 내용은 [Office 365에서 DMARC를 사용하여 전자 메일 유효성을 검사하세요.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="bc6cd-221">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
