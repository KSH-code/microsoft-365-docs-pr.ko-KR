---
title: 기본 연결 필터 정책 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)에서 연결 필터링을 구성 하 여 전자 메일 서버에서 받은 메일을 허용 하거나 차단 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 675247ba1764cb928bec967c581083c6365f635a
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656794"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="f42be-103">연결 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="f42be-103">Configure connection filtering</span></span>

<span data-ttu-id="f42be-104">Exchange online 사서함이 없는 Microsoft 365 고객이 나 독립 실행형 EOP (Exchange Online Protection) 고객에 게는 EOP (특히 기본 연결 필터 정책)에서 연결 필터링을 사용 하 여 해당 IP 주소로 양호한 지 나 잘못 된 원본 전자 메일 서버를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="f42be-105">기본 연결 필터 정책의 주요 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-105">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="f42be-106">**Ip 허용 목록**: ip 주소 또는 ip 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 모든 메시지에 대 한 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-106">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="f42be-107">이러한 원본의 메시지에 대 한 스팸 필터링이 계속 발생할 수 있는 시나리오는이 항목 뒷부분의 [IP 허용 목록에 있는 원본의 메시지가 계속 필터링 되는 시나리오](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42be-107">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this topic.</span></span> <span data-ttu-id="f42be-108">IP 허용 목록을 전반적인 수신 허용-보낸 사람 전략에 맞게 조정 하는 방법에 대 한 자세한 내용은 [EOP의 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42be-108">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="f42be-109">**Ip 차단 목록**: ip 주소 또는 ip 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 모든 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-109">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="f42be-110">들어오는 메시지가 거부 되 고 스팸으로 표시 되지 않으며 추가 필터링이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-110">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="f42be-111">IP 차단 목록이 전체 차단 된 보낸 사람 전략에 맞게 조정 되는 방식에 대 한 자세한 내용은 [EOP에서 수신 거부 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42be-111">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="f42be-112">**수신 허용 목록**: *안전한 목록은* Microsoft 데이터 센터의 동적 허용 목록으로, 고객 구성을 필요로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-112">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="f42be-113">Microsoft는 이러한 신뢰할 수 있는 전자 메일 원본을 구독에서 다양 한 타사 목록으로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-113">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="f42be-114">수신 허용 목록을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 수신 허용 목록에는 원본 전자 메일 서버를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-114">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="f42be-115">수신 허용 목록에 있는 전자 메일 서버에서 들어오는 메시지에 대 한 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-115">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="f42be-116">이 항목에서는 보안 & 준수 센터 또는 PowerShell (exchange online 사서함이 없는 조직에 대 한 사서함이 있는 Microsoft 365 조 직의 exchange online PowerShell)에서 기본 연결 필터 정책을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-116">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="f42be-117">EOP가 연결 필터링을 사용 하는 방법에 대 한 자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42be-117">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f42be-118">IP 허용 목록, 안전한 목록 및 IP 차단 목록은 조직의 전자 메일을 허용 하거나 차단 하는 전체 전략의 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-118">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="f42be-119">자세한 내용은 [수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md) 및 [차단 된 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f42be-119">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f42be-120">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f42be-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f42be-121"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f42be-122">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f42be-122">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="f42be-123">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f42be-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f42be-124">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f42be-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f42be-125">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-125">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f42be-126">기본 연결 필터 정책을 수정 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-126">To modify the default connection filter policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f42be-127">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="f42be-127">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f42be-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="f42be-128">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f42be-129">기본 연결 필터 정책에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-129">For read-only access to the default connection filter policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f42be-130">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="f42be-130">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f42be-131">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="f42be-131">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="f42be-132">허용 하거나 차단할 전자 메일 서버 (보낸 사람)의 원본 IP 주소를 찾으려면 메시지 헤더에서 연결 IP (**CIP**) 헤더 필드를 확인 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-132">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="f42be-133">다양 한 전자 메일 클라이언트에서 메시지 헤더를 보려면 [Outlook에서 internet 메시지 헤더 보기](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f42be-133">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="f42be-134">Ip 허용 목록은 IP 차단 목록 보다 우선 합니다 (두 목록의 주소가 차단 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="f42be-134">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="f42be-135">각 IP 허용 목록 및 IP 차단 목록은 항목이 단일 IP 주소, IP 주소 범위 또는 CIDR (도메인간 라우팅) IP 인 최대 1273 항목을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-135">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="f42be-136">보안 & 준수 센터를 사용 하 여 기본 연결 필터 정책 수정</span><span class="sxs-lookup"><span data-stu-id="f42be-136">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="f42be-137">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-137">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="f42be-138">**스팸 방지 설정** 페이지에서 확장 아이콘을 클릭 하 여 **연결 필터 정책을** 확장 한 ![ ](../../media/scc-expand-icon.png) 다음 **정책 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-138">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="f42be-139">**기본** 플라이 아웃이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-139">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="f42be-140">**설명**: 선택적 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-140">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="f42be-141">**IP 허용 목록**: **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-141">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="f42be-142">**IP 허용 목록** 플라이 아웃이 나타나면 다음 구문을 사용 하 여 **주소 또는 주소 범위** 상자에 IPV4 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-142">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="f42be-143">단일 IP: (예: 192.168.1.1)</span><span class="sxs-lookup"><span data-stu-id="f42be-143">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="f42be-144">IP 범위 (예: 192.168.0.1-192.168.0.254)</span><span class="sxs-lookup"><span data-stu-id="f42be-144">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="f42be-145">CIDR IP (예: 192.168.0.1/25)</span><span class="sxs-lookup"><span data-stu-id="f42be-145">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="f42be-146">유효한 네트워크 마스크 값은/24에서/32 까지입니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-146">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="f42be-147">CIDR IP 마스크 값/1에서/23에 대 한 스팸 필터링을 건너뛰려면이 항목의 뒷부분에 나오는 [사용 가능한 범위 외부의 CIDR ip에 대 한 스팸 필터링 건너뛰기](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42be-147">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this topic.</span></span>

     <span data-ttu-id="f42be-148">IP 주소 또는 주소 범위를 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-148">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="f42be-149">항목을 제거 하려면 **허용 된 IP 주소** 에서 항목을 선택 하 고 제거 **제거를 클릭** ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-149">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="f42be-150">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-150">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="f42be-151">**IP 차단 목록**: **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-151">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="f42be-152">**Ip 차단 목록** 플라이 아웃이 나타나면 **ip 허용 목록** 설정에 설명 된 대로 **주소 또는 주소 범위** 상자에 단일 IP, ip 범위 또는 CIDR IP를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-152">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="f42be-153">IP 주소 또는 주소 범위를 추가 하려면 추가 아이콘 **추가를 클릭** ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-153">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="f42be-154">항목을 제거 하려면 **차단 된 IP 주소** 에서 항목을 선택 하 고 제거 **제거를 클릭** ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-154">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="f42be-155">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-155">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="f42be-156">**수신 허용 목록 설정**: 수신 허용 목록을 사용 하거나 사용 하지 않도록 설정 하 여 스팸 필터링을 건너뛸 알려진 적절 한 보낸 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-156">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="f42be-157">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-157">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="f42be-158">보안 & 준수 센터를 사용 하 여 기본 연결 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="f42be-158">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="f42be-159">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-159">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="f42be-160">**스팸 방지 설정** 페이지에서 **연결 필터 정책**이라는 기본 정책 옆에 있는 드롭다운을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-160">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="f42be-161">이 정책 설정은 열리는 드롭다운에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-161">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="f42be-162">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 기본 연결 필터 정책 수정</span><span class="sxs-lookup"><span data-stu-id="f42be-162">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="f42be-163">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-163">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="f42be-164">**참고**:</span><span class="sxs-lookup"><span data-stu-id="f42be-164">**Notes**:</span></span>

- <span data-ttu-id="f42be-165">유효한 IP 주소 또는 주소 범위 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-165">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="f42be-166">단일 IP: (예: 192.168.1.1)</span><span class="sxs-lookup"><span data-stu-id="f42be-166">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="f42be-167">IP 범위 (예: 192.168.0.1-192.168.0.254)</span><span class="sxs-lookup"><span data-stu-id="f42be-167">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="f42be-168">CIDR IP (예: 192.168.0.1/25)</span><span class="sxs-lookup"><span data-stu-id="f42be-168">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="f42be-169">유효한 네트워크 마스크 값은/24에서/32 까지입니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-169">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="f42be-170">지정한 값으로 기존 항목을 *덮어쓰려면* 다음 구문을 사용 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-170">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="f42be-171">기존의 다른 항목에 영향을 주지 않고 IP 주소 또는 주소 범위를 *추가 하거나 제거* 하려면 다음 구문을 사용 `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-171">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="f42be-172">IP 허용 목록 또는 IP 차단 목록을 비우려면이 값을 사용 `$null` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-172">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="f42be-173">이 예에서는 지정 된 IP 주소 및 주소 범위를 사용 하 여 IP 허용 목록과 IP 차단 목록을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-173">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="f42be-174">이 예에서는 IP 허용 목록에서 지정 된 IP 주소 및 주소 범위를 추가 하 고 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-174">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="f42be-175">구문 및 매개 변수에 대 한 자세한 내용은 [get-hostedconnectionfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42be-175">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f42be-176">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="f42be-176">How do you know this worked?</span></span>

<span data-ttu-id="f42be-177">기본 연결 필터 정책이 성공적으로 수정 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-177">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="f42be-178">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 에서 \> **연결 필터 정책 (항상 켜기**) 옆에 있는 드롭다운을 클릭 하 고 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-178">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="f42be-179">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 다음 명령을 실행 하 고 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-179">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="f42be-180">IP 허용 목록의 항목에서 테스트 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-180">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="f42be-181">IP 허용 목록에 대 한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f42be-181">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="f42be-182">다음 섹션에서는 IP 허용 목록을 구성할 때 알아야 할 추가 항목을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-182">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="f42be-183">사용 가능한 범위 외부의 CIDR IP에 대 한 스팸 필터링 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="f42be-183">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="f42be-184">이 항목의 앞부분에서 설명한 것 처럼 IP 허용 목록에는 네트워크 마스크/24 ~/32의 CIDR IP만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-184">As described earlier in this topic, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="f42be-185">/1 ~/23 범위의 원본 전자 메일 서버에서 메시지에 대 한 스팸 필터링을 건너뛰려면 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-185">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="f42be-186">그러나/1 ~/23 CIDR IP 범위의 IP 주소가 Microsoft의 독점 또는 타사 차단 목록에 표시 되는 경우에는 가능한 경우에는이 방법을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-186">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="f42be-187">잠재적인 문제를 완벽 하 게 알게 되었으므로 다음 설정 (최소)을 사용 하 여 메일 흐름 규칙을 만들어 이러한 IP 주소의 메시지가 스팸 필터링을 건너뛰도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-187">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="f42be-188">규칙 조건: **Apply this rule if** \> **보낸 사람** \> **ip 주소가 이러한 범위에 있거나 정확 하 게 일치 하** 는 경우이 규칙을 적용 합니다 \> (/1과/23 사이의 네트워크 마스크를 사용 하 여 CIDR ip 입력).</span><span class="sxs-lookup"><span data-stu-id="f42be-188">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="f42be-189">규칙 동작: **메시지 속성 수정** \> **SCL (스팸** 지 수) 사용 \> **안 함 스팸 필터링**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-189">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="f42be-190">규칙을 감사 하 고 규칙을 테스트 하며 특정 기간 동안 규칙을 활성화 하 고 기타 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-190">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="f42be-191">옵션을 적용하기 전에 규칙을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-191">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="f42be-192">자세한 내용은 [Exchange Online에서 메일 흐름 규칙 관리](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f42be-192">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="f42be-193">같은 원본에서 선택 된 전자 메일 도메인에 대 한 스팸 필터링 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="f42be-193">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="f42be-194">대개 ip 주소 또는 주소 범위를 IP 허용 목록에 추가 하는 것은 해당 전자 메일 원본에서 들어오는 모든 메시지를 신뢰 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-194">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="f42be-195">하지만 해당 원본에서 여러 도메인의 전자 메일을 전송 하는 경우 해당 도메인 중 일부에 대해서는 스팸 필터링을 건너뛰시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="f42be-195">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="f42be-196">IP 허용 목록만 사용 하 여이 작업을 수행할 수는 없지만, 메일 흐름 규칙과 함께 IP 허용 목록을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-196">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="f42be-197">예를 들어 원본 전자 메일 서버 192.168.1.25는 contoso.com, fabrikam.com 및 tailspintoys.com 도메인의 전자 메일을 보내며, fabrikam.com의 보낸 사람 으로부터 메시지에 대 한 스팸 필터링은 건너뛰도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-197">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="f42be-198">이 작업을 수행 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-198">To do this, use the following steps:</span></span>

1. <span data-ttu-id="f42be-199">IP 허용 목록에 192.168.1.25을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-199">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="f42be-200">다음 설정을 사용 하 여 메일 흐름 규칙을 구성 합니다 (최소한).</span><span class="sxs-lookup"><span data-stu-id="f42be-200">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="f42be-201">규칙 조건: **Apply this rule if** \> **보낸 사람** \> **IP 주소가 이러한 범위에 있거나,** \> 이전 단계에서 ip 허용 목록에 추가한 것과 같은 ip 주소 또는 주소 범위에 있는 192.168.1.25와 정확 하 게 일치 하는 경우이 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-201">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="f42be-202">규칙 동작: **메시지 속성 수정** \> **SCL (스팸 지 수) 0을 설정** 합니다 \> **0**.</span><span class="sxs-lookup"><span data-stu-id="f42be-202">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="f42be-203">규칙 예외: **보낸 사람** \> **도메인이** \> fabrikam.com (스팸 필터링을 건너뛰도록 하려는 도메인)입니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-203">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="f42be-204">IP 허용 목록에 있는 원본의 메시지가 계속 필터링 되는 시나리오</span><span class="sxs-lookup"><span data-stu-id="f42be-204">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="f42be-205">IP 허용 목록에 있는 전자 메일 서버의 메시지는 여전히 다음과 같은 경우에 스팸 필터링의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-205">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="f42be-206">또한 IP 허용 목록의 IP 주소는 Microsoft 365의 *모든* 테 넌 트에 있는 온-프레미스의 ip 기반 인바운드 커넥터, 즉이 테 넌 트 a를 호출 하 **고** , 테 넌 트 a 및 메시지를 처음으로 실행 하는 EOP 서버에서 microsoft 데이터 센터의 *동일한* Active Directory 포리스트에 있는 것 처럼 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-206">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="f42be-207">이 시나리오에서는 **IPV: CAL** *이 메시지* 의 [스팸 방지 메시지 헤더](anti-spam-message-headers.md) (스팸 필터링 바이패스 메시지를 나타냄)에 추가 되지만 메시지에 여전히 스팸 필터링이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-207">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="f42be-208">IP 허용 목록을 포함 하는 테 넌 트와 처음에 메시지를 발견 하는 EOP 서버가 Microsoft 데이터 센터의 *서로 다른* Active Directory 포리스트에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-208">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="f42be-209">이 시나리오에서는 **IPV: CAL** *이* 메시지 헤더에 추가 되지 않으므로 메시지에 여전히 스팸 필터링이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-209">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="f42be-210">이러한 시나리오 중 하나에 해당 하는 경우 다음 설정을 사용 하 여 메일 흐름 규칙을 만들어 문제가 발생 한 IP 주소의 메시지가 스팸 필터링을 건너뛰도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-210">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="f42be-211">규칙 조건: **Apply this rule if** \> **보낸 사람** \> **ip 주소가 이러한 범위에 있거나 정확히 일치** 하는 경우 \> (IP 주소 또는 주소)이 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-211">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="f42be-212">규칙 동작: **메시지 속성 수정** \> **SCL (스팸** 지 수) 사용 \> **안 함 스팸 필터링**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-212">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="f42be-213">Microsoft 365의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f42be-213">New to Microsoft 365?</span></span>

|<!-- a -->|
|---|
|<span data-ttu-id="f42be-214">![LinkedIn에 대 한 짧은 아이콘은 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365를 처음으로 학습 하나요?**</span><span class="sxs-lookup"><span data-stu-id="f42be-214">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="f42be-215">LinkedIn 학습을 통해 제공 되는 **관리자 및 IT 전문가**를 위한 무료 비디오 코스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42be-215">Discover free video courses for **Admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
|
