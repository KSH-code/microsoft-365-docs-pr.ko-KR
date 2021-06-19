---
title: 스푸핑 인텔리전스 정책 및 스푸핑 인텔리전스 정보를 사용하여 스푸핑된 보낸 사람 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 관리자는 스푸핑 인텔리전스 정책 및 스푸핑 인텔리전스 인사이트를 사용하여 검색된 스푸핑된 보낸 사람 허용 또는 차단 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a683ed93e4e483e63fe01281b32661f0b803d1ce
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029300"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="730a6-103">EOP에서 스푸핑 인텔리전스 정책 및 스푸핑 인텔리전스 인사이트를 사용하여 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="730a6-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="730a6-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="730a6-104">**Applies to**</span></span>
- [<span data-ttu-id="730a6-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="730a6-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="730a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="730a6-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="730a6-107">이 문서에서는 대체되는 이전 스푸핑된 보낸 사람 관리 환경을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="730a6-108">새 경험에 대한 자세한 내용은 [EOP의 스푸핑 인텔리전스 인사이트를 참조하세요.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="730a6-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="730a6-109">Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 인바운드 전자 메일 메시지는 Exchange Online 2018년 10월부로 EOP의 스푸핑으로부터 자동으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="730a6-110">EOP는 피싱에 **대한** 조직의 전반적인 방어의 일부로 스푸핑 인텔리전스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="730a6-111">자세한 내용은 EOP의 스푸핑 방지 보호 [기능을 참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="730a6-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="730a6-112">기본(유일한)  스푸핑 인텔리전스 정책은 합법적인 보낸 사람이 보낸 스푸핑된 전자 메일이 스팸 또는 피싱 공격으로부터 사용자를 보호하면서 EOP 스팸 필터에 걸려오지 않도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="730a6-113">또한 스푸핑  인텔리전스 정보를 사용하여 외부 보낸 사람이 사용자에게 합법적으로 확인되지 않은 전자 메일(SPF, DKIM 또는 DMARC 검사를 통과하지 않은 도메인의 메시지)을 빠르게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="730a6-114">보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online, 사서함이 없는 조직의 독립 실행형 EOP PowerShell Exchange Online PowerShell)에서 스푸핑 인텔리전스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="730a6-115">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="730a6-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="730a6-116"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="730a6-117">스푸핑 인텔리전스 정책에 대한 스팸 방지 설정 페이지로 직접 이동하려면 를  <https://protection.office.com/antispam> 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="730a6-118">스푸핑 **인텔리전스** 인사이트를 위해 보안 대시보드 페이지로 직접 이동하기 위해 를 <https://protection.office.com/searchandinvestigation/dashboard> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="730a6-119">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="730a6-120">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="730a6-121">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="730a6-122">스푸핑 인텔리전스 정책을 수정하거나 스푸핑 인텔리전스를 사용하거나  사용하지 않도록 설정하려면 조직 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="730a6-123">스푸핑 인텔리전스 정책에 대한 읽기 전용 액세스 권한을  사용하려면 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="730a6-124">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="730a6-125">**참고**:</span><span class="sxs-lookup"><span data-stu-id="730a6-125">**Notes**:</span></span>

  - <span data-ttu-id="730a6-126">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="730a6-127">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="730a6-128">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="730a6-129">스푸핑 인텔리전스에 대한 옵션은 피싱 방지 정책의 스푸핑 설정에 [설명되어 있습니다.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="730a6-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="730a6-130">피싱 방지 정책에서 스푸핑 인텔리전스 설정을 사용하도록 설정, 비활성화 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="730a6-131">구독에 기반한 지침은 다음 항목 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="730a6-132">[EOP에서 피싱 방지 정책을 구성합니다.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="730a6-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="730a6-133">[Microsoft Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="730a6-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="730a6-134">스푸핑 인텔리전스에 대한 권장 설정은 EOP 피싱 방지 정책 [설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="730a6-134">For our recommended settings for spoof intelligence, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="730a6-135">스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="730a6-135">Manage spoofed senders</span></span>

<span data-ttu-id="730a6-136">스푸핑된 보낸 사람은 다음 두 가지 방법으로 허용하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="730a6-137">스푸핑 인텔리전스 정책 사용</span><span class="sxs-lookup"><span data-stu-id="730a6-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="730a6-138">스푸핑 인텔리전스 인사이트 사용</span><span class="sxs-lookup"><span data-stu-id="730a6-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="730a6-139">스푸핑 인텔리전스 정책에서 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="730a6-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="730a6-140">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="730a6-141">스팸 **방지 설정 페이지에서** 확장 아이콘을 ![ 클릭하여 스푸핑 인텔리전스 정책을 ](../../media/scc-expand-icon.png) **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![스푸핑 인텔리전스 정책 선택](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="730a6-143">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="730a6-144">**새 보낸 사람 검토**</span><span class="sxs-lookup"><span data-stu-id="730a6-144">**Review new senders**</span></span>
   - <span data-ttu-id="730a6-145">**이미 검토한 보낸 사람 표시**</span><span class="sxs-lookup"><span data-stu-id="730a6-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="730a6-146">이러한 **보낸 사람이** 나타나는 사용자 플라이아웃을 스푸핑할 수 있도록 허용할지 결정에서 다음 탭 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="730a6-147">**도메인:** 보낸 사람이 내부 도메인의 사용자를 스푸핑합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="730a6-148">**외부 도메인:** 보낸 사람이 외부 도메인의 사용자를 스푸핑합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="730a6-149">스푸핑 허용 여부 열에서 확장 ![ ](../../media/scc-expand-icon.png) **아이콘을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="730a6-150">예를 **선택하면** 스푸핑된 보낸 사람이 허용되거나 아니요를 선택하고 메시지를 스푸핑된 메시지로 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="730a6-150">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="730a6-151">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책(기본값은 정크 메일 폴더로 메시지 이동)에 의해 **제어됩니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="730a6-152">자세한 내용은 [피싱 방지 정책의 스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![스푸핑된 보낸 사람 플라이아웃 및 보낸 사람이 스푸핑할 수 있는지 여부를 보여 주는 스크린샷](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="730a6-154">다음 목록에는 열과 값이 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="730a6-155">**스푸핑된 사용자:** 스푸핑되는 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="730a6-156">전자 메일 클라이언트에 표시된 보낸 사람 주소(주소라고도 알려지음)의 메시지 보낸 `5322.From` 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="730a6-157">SPF에서 이 주소의 유효성을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="730a6-158">도메인 **탭에서** 값에 단일 전자 메일 주소가 포함되어 있습니다. 또는 원본 전자 메일 서버가 여러 사용자 계정을 스푸핑하는 경우 이 값에는 두 개 **이상이 포함되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="730a6-159">외부 **도메인 탭의** 값에는 스푸핑된 사용자의 도메인이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="730a6-160">**보내는 인프라:** 원본 전자 메일 서버의 IP 주소에 대한 역방향 DNS 검색(PTR 레코드)에 있는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="730a6-161">원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="730a6-162">메시지 원본 및 메시지 보낸 사람에 대한 자세한 내용은 전자 메일 메시지 표준 [개요를 참조하세요.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="730a6-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="730a6-163">**메시지** 수: 지난 30일 이내에 지정된 스푸핑된 보낸 사람 또는 보낸 사람이 포함된 조직으로 보내는 인프라에서 보내는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="730a6-164">**# of user complaints:** 지난 30일 이내에 이 보낸 사람에 대해 사용자가 제출한 불만 사항</span><span class="sxs-lookup"><span data-stu-id="730a6-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="730a6-165">불만은 일반적으로 Microsoft에 대한 정크 제출 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="730a6-166">**인증 결과:** 다음 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="730a6-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="730a6-167">**통과:** 보낸 사람이 SPF 또는 DKIM(보낸 사람 전자 메일 인증 검사)을 통과했습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="730a6-168">**실패:** 보낸 사람이 EOP 보낸 사람 인증 검사를 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="730a6-169">**알** 수 없음: 이러한 검사의 결과를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="730a6-170">**다음에 의해 설정된 결정**: 보내는 인프라가 사용자를 스푸핑할 수 있도록 허용할지 결정한 사용자를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="730a6-171">**스푸핑 인텔리전스** 정책(자동)</span><span class="sxs-lookup"><span data-stu-id="730a6-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="730a6-172">**관리자(수동)**</span><span class="sxs-lookup"><span data-stu-id="730a6-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="730a6-173">**마지막 확인** 날짜: 스푸핑된 사용자가 포함된 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="730a6-174">**스푸핑이 허용되는 경우:** 여기에 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="730a6-175">**예:** 스푸핑된 사용자와 보내는 인프라의 조합에서 보낸 메시지는 허용될 수 있으며 스푸핑된 전자 메일로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="730a6-176">**No:** 스푸핑된 사용자와 보내는 인프라의 조합에서 보낸 메시지가 스푸핑된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="730a6-177">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책(기본값은 정크 메일 폴더로 메시지 이동)에 의해 **제어됩니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="730a6-178">자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="730a6-178">See the next section for more information.</span></span>

     - <span data-ttu-id="730a6-179">**일부 사용자(** **도메인** 탭에만 해당): 보내는 인프라가 여러 사용자를 스푸핑하고, 일부 스푸핑된 사용자가 허용되는 경우 및 다른 사용자는 스푸핑되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="730a6-180">자세한 **탭을 사용하여** 특정 주소를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="730a6-181">페이지 아래쪽에서 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="730a6-182">PowerShell을 사용하여 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="730a6-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="730a6-183">허용 및 차단된 보낸 사람이 스푸핑 인텔리전스에서 볼 수 있도록 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="730a6-184">이 예에서는 도메인의 사용자를 스푸핑할 수 있는 모든 보낸 사람에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="730a6-185">구문과 매개 변수에 대한 자세한 내용은 [Get-PhishFilterPolicy를 참조하십시오.](/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="730a6-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="730a6-186">스푸핑 인텔리전스에서 허용 및 차단된 보낸 사람 구성을 구성하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="730a6-187">다음 명령을 실행하여 **Get-PhishFilterPolicy** cmdlet의 출력을 CSV 파일에 기록하여 검색된 스푸핑된 보낸 사람의 현재 목록을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="730a6-188">CSV 파일을 편집하여 다음 값을 추가하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="730a6-189">**보낸 사람(원본** 서버의 PTR 레코드 또는 IP/24 주소의 도메인)</span><span class="sxs-lookup"><span data-stu-id="730a6-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="730a6-190">**SpoofedUser**: 다음 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="730a6-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="730a6-191">내부 사용자의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-191">The internal user's email address.</span></span>
     - <span data-ttu-id="730a6-192">외부 사용자의 전자 메일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-192">The external user's email domain.</span></span>
     - <span data-ttu-id="730a6-193">스푸핑된 전자 메일 주소에 관계없이 지정된 보낸 사람이 보낸 모든 스푸핑 메시지를 차단하거나 허용할지 나타내는 빈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="730a6-194">**AllowedToSpoof(예** 또는 아니요)</span><span class="sxs-lookup"><span data-stu-id="730a6-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="730a6-195">**SpoofType(내부** 또는 외부)</span><span class="sxs-lookup"><span data-stu-id="730a6-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="730a6-196">다음 명령을 실행하여 파일을 저장하고 파일을 읽은 다음 이름을 지정한 변수로 `$UpdateSpoofedSenders` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="730a6-197">변수를 사용하여 다음 명령을 실행하여 스푸핑 인텔리전스 `$UpdateSpoofedSenders` 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="730a6-198">구문과 매개 변수에 대한 자세한 내용은 [Set-PhishFilterPolicy를 참조하십시오.](/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="730a6-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="730a6-199">스푸핑 인텔리전스 인사이트에서 스푸핑된 보낸 사람 관리</span><span class="sxs-lookup"><span data-stu-id="730a6-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="730a6-200">보안 및 & 센터에서 위협 관리 **대시보드로** \> **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="730a6-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="730a6-201">Insights **행에서** 다음 항목 중 하나를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="730a6-202">**지난 7일** 동안의 스푸핑된 도메인 가능성 : 이 인사이트는 스푸핑 인텔리전스가 활성화되어 있는 것으로 나타냅니다(기본적으로 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="730a6-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="730a6-203">**스푸핑** 보호 사용 : 이 인사이트는 스푸핑 인텔리전스가 사용되지 않도록 설정되어 있으며, 정보를 클릭하면 스푸핑 인텔리전스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="730a6-204">대시보드의 인사이트에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-204">The insight on the dashboard shows you information like this:</span></span>

   ![스푸핑 인텔리전스 정보의 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="730a6-206">이 인사이트에는 두 가지 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-206">This insight has two modes:</span></span>

   - <span data-ttu-id="730a6-207">**인사이트** 모드: 스푸핑 인텔리전스를 사용하도록 설정하면 지난 7일 동안의 스푸핑 인텔리전스 기능에 영향을 미치게 된 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="730a6-208">**모드인 경우:** 스푸핑 인텔리전스를 사용하지 않도록 설정하면  지난 7일 동안의 스푸핑 인텔리전스 기능에 의해 영향을 났을 메시지 수가 인사이트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="730a6-209">어느 경우든 인사이트에 표시되는 스푸핑된 도메인은 의심스러운  도메인과 의심하지 않는 도메인의 두 가지 범주로 **구분됩니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="730a6-210">**의심스러운 도메인**:</span><span class="sxs-lookup"><span data-stu-id="730a6-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="730a6-211">**높은** 신뢰도 스푸핑: 이전 전송 패턴 및 도메인의 신뢰도 점수에 따라 도메인이 스푸핑하고 이러한 도메인의 메시지가 악의적일 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="730a6-212">**보통** 신뢰도 스푸핑: 이전 전송 패턴과 도메인의 신뢰도 점수를 기반으로 도메인이 스푸핑하고 이러한 도메인에서 보낸 메시지가 합법적이라고 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="730a6-213">가음성은 높은 신뢰도 스푸핑보다 이 범주에서 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="730a6-214">**의심스러운** 도메인이 아닌 도메인: 도메인이 명시적 전자 메일 인증 검사 [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC를](use-dmarc-to-validate-email.md)확인하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="730a6-215">그러나 도메인이 암시적 전자 메일 인증[확인(복합 인증)을 통과했습니다.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="730a6-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="730a6-216">따라서 메시지에 대한 스푸핑 방지 작업이 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="730a6-217">의심스러우며 의심스러운 도메인에 대한 자세한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="730a6-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="730a6-218">스푸핑 인텔리전스  인사이트에서 의심스러운  도메인 또는 의심스러운 도메인을 클릭하여 스푸핑 인텔리전스 인사이트 **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="730a6-219">**스푸핑 인텔리전스 인사이트 페이지에는** 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="730a6-220">**스푸핑된 도메인**: 전자 메일 클라이언트의 시작 상자에  표시되는 스푸핑된 사용자의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="730a6-221">이 주소를 `5322.From` 주소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="730a6-222">**인프라:** 보내는 _인프라라고도 합니다._</span><span class="sxs-lookup"><span data-stu-id="730a6-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="730a6-223">원본 전자 메일 서버의 IP 주소에 대한 역방향 DNS 검색(PTR 레코드)에 있는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="730a6-224">원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="730a6-225">**메시지 수:** 지난 7일 이내에 지정된 스푸핑된 도메인을 포함하는 조직으로 보내는 인프라에서 조직으로 보내는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="730a6-226">**마지막으로 확인한** 날짜: 스푸핑된 도메인이 포함된 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="730a6-227">**스푸핑 유형**: 이 값은 **External입니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="730a6-228">**스푸핑이 허용되는 경우:** 여기에 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="730a6-229">**예:** 스푸핑된 사용자의 도메인과 보내는 인프라의 조합에서 보낸 메시지는 허용될 수 있으며 스푸핑된 전자 메일로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="730a6-230">**No:** 스푸핑된 사용자의 도메인과 보내는 인프라의 조합에서 보낸 메시지가 스푸핑된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="730a6-231">이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책(기본값은 정크 메일 폴더로 메시지 이동)에 의해 **제어됩니다.**</span><span class="sxs-lookup"><span data-stu-id="730a6-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="730a6-232">플라이아웃에서 도메인/보내는 인프라 쌍에 대한 세부 정보를 확인하려면 목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="730a6-233">이 정보에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-233">The information includes:</span></span>
   - <span data-ttu-id="730a6-234">이 경우 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-234">Why we caught this.</span></span>
   - <span data-ttu-id="730a6-235">해야 할 일.</span><span class="sxs-lookup"><span data-stu-id="730a6-235">What you need to do.</span></span>
   - <span data-ttu-id="730a6-236">도메인 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-236">A domain summary.</span></span>
   - <span data-ttu-id="730a6-237">보낸 사람에 대한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="730a6-238">동일한 보낸 사람으로부터 테넌트에 비슷한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="730a6-239">여기에서 허용된 보낸 사람 스푸핑 허용 목록에서 도메인/보내는 인프라 쌍을 추가하거나 제거하도록 선택할 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="730a6-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="730a6-240">그에 따라 토글을 설정하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-240">Simply set the toggle accordingly.</span></span>

   ![스푸핑 인텔리전스 인사이트 세부 정보 창의 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="730a6-242">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="730a6-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="730a6-243">스푸핑이 허용 및 스푸핑이 허용되지 않는 보낸 사람에 대해 스푸핑 인텔리전스를 구성해야 하는지 확인을 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="730a6-244">보안 & 준수 센터에서 위협 관리  정책 스팸 방지 확장 스푸핑 \>  \>  \> **인텔리전스** \>  \>    정책으로 이동하여 이미 검토한 보낸 사람 표시를 선택하고 사용자의 도메인 또는 외부 도메인 탭을 선택하고 보낸 사람에 대해 스푸핑 허용 여부 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="730a6-245">PowerShell에서 다음 명령을 실행하여 스푸핑이 허용 및 허용되지 않은 보낸 사람 보기</span><span class="sxs-lookup"><span data-stu-id="730a6-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="730a6-246">PowerShell에서 다음 명령을 실행하여 스푸핑된 모든 보낸 사람 목록을 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730a6-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
