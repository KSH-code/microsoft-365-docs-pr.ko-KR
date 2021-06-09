---
title: 기본 연결 필터 정책 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 전자 메일 서버에서 전자 메일을 허용하거나 차단하도록 EOP(Exchange Online Protection)에서 연결 필터링을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5eb24377dd9f9ac304e1df7b2902d29e4a738b9
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821964"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="83930-103">연결 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="83930-103">Configure connection filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83930-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="83930-104">**Applies to**</span></span>
- [<span data-ttu-id="83930-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="83930-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="83930-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="83930-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="83930-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83930-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="83930-108">Exchange Online 사서함이 있는 Microsoft 365 고객 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(독립 실행형 Exchange Online Protection) 고객인 경우 EOP의 연결 필터링(특히 기본 연결 필터 정책)을 사용하여 해당 IP 주소로 양호하거나 잘못된 원본 전자 메일 서버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="83930-109">기본 연결 필터 정책의 주요 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-109">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="83930-110">**IP 허용 목록: IP** 주소 또는 IP 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 모든 메시지에 대해 스팸 필터링을 건너뜁습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-110">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="83930-111">이러한 원본의 메시지에서 스팸 필터링이 계속 발생할 수 있는 시나리오는 이 문서 의 부분에 있는 [IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 허용 목록의 원본에서 보낸 메시지가 여전히 필터링되는 시나리오 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83930-111">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this article.</span></span> <span data-ttu-id="83930-112">IP 허용 목록이 전반적인 수신 허용 - 보낸 사람 전략에 적합한 방법에 대한 자세한 내용은 EOP에서 수신 허용 - 보낸 사람 목록 [만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="83930-112">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="83930-113">**IP 차단 목록:** IP 주소 또는 IP 주소 범위로 지정한 원본 전자 메일 서버에서 들어오는 모든 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-113">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="83930-114">들어오는 메시지는 거부되어 스팸으로 표시되지 않습니다. 추가 필터링이 일어나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-114">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="83930-115">IP 차단 목록이 전체 수신 차단된 보낸 사람 전략에 적합한 방법에 대한 자세한 내용은 EOP에서 차단 보낸 사람 목록 [만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="83930-115">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="83930-116">**안전한 목록:** 안전한 *목록은* 고객 구성이 필요 없는 Microsoft 데이터 센터의 동적 허용 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="83930-116">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="83930-117">Microsoft는 구독에서 다양한 타사 목록으로의 이러한 신뢰할 수 있는 전자 메일 원본을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-117">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="83930-118">안전한 목록의 사용을 활성화 또는 비활성화합니다. 수신 확인 목록에 원본 전자 메일 서버를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-118">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="83930-119">스팸 필터링은 수신 확인 목록의 전자 메일 서버에서 들어오는 메시지에서 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="83930-119">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="83930-120">이 문서에서는 Microsoft 365 보안 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 기본 연결 필터 정책을 구성하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-120">This article describes how to configure the default connection filter policy in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="83930-121">EOP에서 연결 필터링을 사용하는 방법에 대한 자세한 내용은 스팸 방지 보호를 [참조하세요.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="83930-121">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="83930-122">IP 허용 목록, 수신 허용 목록 및 IP 차단 목록은 조직의 전자 메일을 허용하거나 차단하는 전체 전략의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="83930-122">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="83930-123">자세한 내용은 [수신이](create-safe-sender-lists-in-office-365.md) 가능한 보낸 사람 목록 만들기 및 수신이 차단된 보낸 [사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="83930-123">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="83930-124">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="83930-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="83930-125"><https://security.microsoft.com>에서 보안 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83930-125">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="83930-126">**스팸 방지 정책** 페이지로 직접 이동하려면 <https://security.microsoft.com/antispam>을(를) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-126">To go directly to the **Anti-spam policies** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="83930-127">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83930-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="83930-128">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83930-128">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="83930-129">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-129">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="83930-130">기본 연결 필터 정책을 수정하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-130">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="83930-131">기본 연결 필터 정책에 대한 읽기 전용 액세스의 경우  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83930-131">For read-only access to the default connection filter policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="83930-132">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83930-132">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="83930-133">**참고**:</span><span class="sxs-lookup"><span data-stu-id="83930-133">**Notes**:</span></span>

  - <span data-ttu-id="83930-134">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="83930-134">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="83930-135">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83930-135">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="83930-136">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-136">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="83930-137">허용하거나 차단할 전자 메일 서버(보낸 사람)의 원본 IP 주소를 찾으면 메시지 헤더에서 연결 **IP(CIP)** 헤더 필드를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-137">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="83930-138">다양한 전자 메일 클라이언트에서 메시지 헤더를 확인하려면 에서 인터넷 메시지 [헤더 보기를 Outlook.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)</span><span class="sxs-lookup"><span data-stu-id="83930-138">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="83930-139">IP 허용 목록이 IP 차단 목록보다 우선합니다(두 목록의 주소가 모두 차단되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="83930-139">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="83930-140">IP 허용 목록 및 IP 차단 목록은 각각 하나의 IP 주소, IP 주소 범위 또는 CIDR(Classless InterDomain Routing) IP인 최대 1273 항목을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-140">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="83930-141">보안 센터를 사용하여 기본 연결 필터 정책 수정</span><span class="sxs-lookup"><span data-stu-id="83930-141">Use the security center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="83930-142">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-142">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="83930-143">스팸 **방지 정책 페이지의** 정책  이름을 클릭하여 목록에서 연결 필터 정책(기본값)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-143">On the **Anti-spam policies** page, select **Connection filter policy (Default)** from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="83930-144">정책 세부 정보 플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-144">In the policy details flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="83930-145">**설명** 섹션: 이름 **및 설명 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="83930-145">**Description** section: Click **Edit name and description**.</span></span> <span data-ttu-id="83930-146">나타나는 **이름 및** 설명 편집 플라이아웃에서 설명 상자에 선택적 설명 텍스트를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="83930-146">In the **Edit name and description** flyout that appears, enter optional descriptive text in the **Description** box.</span></span>

     <span data-ttu-id="83930-147">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-147">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="83930-148">**연결 필터링 섹션:** 연결 **필터 정책 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="83930-148">**Connection filtering section**: Click **Edit connection filter policy**.</span></span> <span data-ttu-id="83930-149">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-149">In the flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="83930-150">**항상 다음 IP 주소** 또는 주소 범위의 메시지를 허용합니다. IP 허용 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="83930-150">**Always allow messages from the following IP addresses or address range**: This is the IP Allow list.</span></span> <span data-ttu-id="83930-151">상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 전체 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-151">Click in the box, enter a value, and then press Enter or select the complete value that's displayed below the box.</span></span> <span data-ttu-id="83930-152">유효한 값:</span><span class="sxs-lookup"><span data-stu-id="83930-152">Valid values are</span></span>
       - <span data-ttu-id="83930-153">단일 IP: 예: 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="83930-153">Single IP: For example, 192.168.1.1.</span></span>
       - <span data-ttu-id="83930-154">IP 범위: 예: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="83930-154">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
       - <span data-ttu-id="83930-155">CIDR IP: 예: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="83930-155">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="83930-156">유효한 서브넷 마스크 값은 /24에서 /32까지입니다.</span><span class="sxs-lookup"><span data-stu-id="83930-156">Valid subnet mask values are /24 through /32.</span></span> <span data-ttu-id="83930-157">/1 ~ /23에 대한 스팸 필터링을 건너뛰기 위해 이 문서 의 부분에 있는 사용 가능한 범위 밖에 있는 [CIDR IP에](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 대한 스팸 필터링 건너뛰기 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83930-157">To skip spam filtering for /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this article.</span></span>

       <span data-ttu-id="83930-158">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-158">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="83930-159">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-159">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="83930-161">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-161">next to the value.</span></span>

     <span data-ttu-id="83930-162">IP 주소 또는 주소 범위를 추가하려면 상자를 클릭하고  추가 아이콘 추가 를 ![ ](../../media/ITPro-EAC-AddIcon.png) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-162">To add the IP address or address range, click in the box and type itclick **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="83930-163">항목을 제거하려면 **허용된 IP** 주소의 항목을 선택한 다음 제거 **를** ![ ](../../media/scc-remove-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-163">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="83930-164">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-164">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="83930-165">**항상 다음 IP 주소** 또는 주소 범위의 메시지를 차단합니다. IP 차단 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="83930-165">**Always block messages from the following IP addresses or address range**: This is the IP Block List.</span></span> <span data-ttu-id="83930-166">다음 IP 주소 또는 주소 범위의 메시지 항상 허용 설정에 설명된 바와 같이 상자에 단일 IP, IP 범위 또는 CIDR **IP를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="83930-166">Enter a single IP, IP range, or CIDR IP in the box as previously described in the **Always allow messages from the following IP addresses or address range** setting.</span></span>

   - <span data-ttu-id="83930-167">**수신 가능 목록 켜기**: 수신 가능 목록을 사용하여 스팸 필터링을 건너뛰는 알려진 좋은 보낸 사람 식별을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="83930-167">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span> <span data-ttu-id="83930-168">안전한 목록을 사용하려면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-168">To use the safe list, select the check box.</span></span>

   <span data-ttu-id="83930-169">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-169">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="83930-170">정책 세부 정보 플라이아웃으로 돌아와 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-170">Back on the policy details flyout, click **Close**.</span></span>

## <a name="use-the-security-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="83930-171">보안 센터를 사용하여 기본 연결 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="83930-171">Use the security center to view the default connection filter policy</span></span>

1. <span data-ttu-id="83930-172">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-172">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="83930-173">스팸 **방지 정책 페이지에는** 정책 목록에 다음 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83930-173">On the **Anti-spam policies** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="83930-174">**이름:** 이 값은 기본 연결 필터 정책에 대한 연결 필터 정책(기본값)입니다. </span><span class="sxs-lookup"><span data-stu-id="83930-174">**Name**: This value is **Connection filter policy (Default)** for the default connection filter policy.</span></span>
   - <span data-ttu-id="83930-175">**Status:** 이 값은 **기본** 연결 필터 정책에 대해 항상 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-175">**Status**: This value is **Always on** for the default connection filter policy.</span></span>
   - <span data-ttu-id="83930-176">**우선** 순위: 기본 연결 필터 정책의 경우 **이** 값은 가장 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-176">**Priority**: This value is **Lowest** for the default connection filter policy.</span></span>
   - <span data-ttu-id="83930-177">**Type**: 이 값은 기본 연결 필터 정책에 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-177">**Type**: This value is blank for the default connection filter policy.</span></span>

3. <span data-ttu-id="83930-178">기본 연결 필터 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83930-178">When you select the default connection filter policy, the policy settings are displayed in a flyout.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="83930-179">PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 기본 연결 필터 정책 수정</span><span class="sxs-lookup"><span data-stu-id="83930-179">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="83930-180">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-180">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="83930-181">**참고:**</span><span class="sxs-lookup"><span data-stu-id="83930-181">**Notes**:</span></span>

- <span data-ttu-id="83930-182">유효한 IP 주소 또는 주소 범위 값은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-182">Valid IP address or address range values are:</span></span>
  - <span data-ttu-id="83930-183">단일 IP: 예: 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="83930-183">Single IP: For example, 192.168.1.1.</span></span>
  - <span data-ttu-id="83930-184">IP 범위: 예: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="83930-184">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
  - <span data-ttu-id="83930-185">CIDR IP: 예: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="83930-185">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="83930-186">유효한 네트워크 마스크 값은 /24 ~/32입니다.</span><span class="sxs-lookup"><span data-stu-id="83930-186">Valid network mask values are /24 through /32.</span></span>
- <span data-ttu-id="83930-187">지정한 *값으로* 기존 항목을 덮어치기 위해 다음 구문을 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-187">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>
- <span data-ttu-id="83930-188">다른 *기존 항목에 영향을* 주지 않고 IP 주소 또는 주소 범위를 추가하거나 제거하려면 다음 구문을 `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 사용합니다. .</span><span class="sxs-lookup"><span data-stu-id="83930-188">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>
- <span data-ttu-id="83930-189">IP 허용 목록 또는 IP 차단 목록을 비우기 위해 값을 `$null` 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="83930-189">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="83930-190">이 예에서는 지정된 IP 주소 및 주소 범위를 사용하여 IP 허용 목록 및 IP 차단 목록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-190">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="83930-191">이 예에서는 IP 허용 목록에서 지정된 IP 주소 및 주소 범위를 추가하고 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-191">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="83930-192">구문과 매개 변수에 대한 자세한 내용은 [Set-HostedConnectionFilterPolicy를 참조하십시오.](/powershell/module/exchange/set-hostedconnectionfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="83930-192">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="83930-193">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="83930-193">How do you know this worked?</span></span>

<span data-ttu-id="83930-194">기본 연결 필터 정책이 성공적으로 수정되어 있는지 확인하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-194">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="83930-195">보안 센터에서 전자 메일 **&** 공동 작업 정책 & 규칙 위협 정책 섹션 정책 이름을 클릭하여 목록에서 연결 필터 정책(기본값)을 선택하고 설정을 \>  \>  \>  \>  \> 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="83930-195">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam** \> select **Connection filter policy (Default)** from the list by clicking on the name of the policy, and verify the settings.</span></span>

- <span data-ttu-id="83930-196">PowerShell Exchange Online 독립 실행형 EOP PowerShell에서 다음 명령을 실행하고 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-196">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="83930-197">IP 허용 목록의 항목에서 테스트 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-197">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="83930-198">IP 허용 목록에 대한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="83930-198">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="83930-199">다음 섹션에서는 IP 허용 목록을 구성할 때 알아야 할 추가 항목을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-199">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="83930-200">사용 가능한 범위를 밖 CIDR IP에 대한 스팸 필터링 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="83930-200">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="83930-201">이 문서의 앞부분에서 설명한 대로 IP 허용 목록에서 네트워크 마스크 /24 ~ /32가 있는 CIDR IP만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-201">As described earlier in this article, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="83930-202">/1에서 /23 범위의 원본 전자 메일 서버에서 보낸 메시지에 대해 스팸 필터링을 건너뛰기 위해 전송 규칙 Exchange 메일 흐름 규칙(전송 규칙)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-202">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="83930-203">그러나 /1 ~ /23 CIDR IP 범위의 IP 주소가 Microsoft의 독점 또는 타사 차단 목록에 나타나는 경우 메시지가 차단될 것이기 때문에 가능한 경우 이 작업을 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-203">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="83930-204">이제 잠재적인 문제를 완전히 인식했기 때문에 최소한 다음 설정을 사용하여 메일 흐름 규칙을 만들어 이러한 IP 주소의 메시지가 스팸 필터링을 건너뛰게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-204">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="83930-205">규칙 **조건:** 보낸 사람 IP 주소가 이러한 범위에 있는 경우 또는 정확히 일치하는 경우 이 규칙을 적용합니다(/1 ~ /23 네트워크 마스크를 사용하여 \>  \>  \> CIDR IP 입력).</span><span class="sxs-lookup"><span data-stu-id="83930-205">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>
- <span data-ttu-id="83930-206">규칙 작업: **메시지 속성 수정** \> **SCL(스팸 지수)** 스팸 필터링 무시를 \> **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="83930-206">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="83930-207">규칙을 감사하고, 규칙을 테스트하고, 특정 기간 동안 규칙을 활성화하는 등 기타 선택을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-207">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="83930-208">옵션을 적용하기 전에 규칙을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-208">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="83930-209">자세한 내용은 [Manage mail flow rules in Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="83930-209">For more information, see [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="83930-210">동일한 원본에서 선택적 전자 메일 도메인에 대한 스팸 필터링 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="83930-210">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="83930-211">일반적으로 IP 허용 목록에 IP 주소 또는 주소 범위를 추가하면 해당 전자 메일 원본에서 들어오는 모든 메시지를 신뢰하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83930-211">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="83930-212">그러나 해당 원본이 여러 도메인에서 전자 메일을 보내고 해당 도메인 중 일부에 대해 스팸 필터링을 건너뛰고 다른 도메인은 건너뛰고 싶은 경우에는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="83930-212">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="83930-213">IP 허용 목록만 사용하여 이 작업을 할 수 없지만 메일 흐름 규칙과 함께 IP 허용 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-213">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="83930-214">예를 들어 원본 전자 메일 서버 192.168.1.25는 도메인 contoso.com, fabrikam.com 및 tailspintoys.com 에서 전자 메일을 보내지만 도메인의 보낸 사람이 보낸 메시지에 대한 스팸 필터링만 건너뛰 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="83930-214">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="83930-215">이 작업을 수행하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-215">To do this, use the following steps:</span></span>

1. <span data-ttu-id="83930-216">IP 허용 목록에 192.168.1.25를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-216">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="83930-217">최소한 다음 설정을 사용하여 메일 흐름 규칙을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-217">Configure a mail flow rule with the following settings (at a minimum):</span></span>
   - <span data-ttu-id="83930-218">규칙 **조건:** 보낸 사람 IP 주소가 이러한 범위에 있는 경우 또는 \>  \>  \> 정확히 192.168.1.25(이전 단계에서 IP 허용 목록에 추가한 IP 주소 또는 주소 범위)가 정확히 일치하는 경우 이 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-218">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>
   - <span data-ttu-id="83930-219">규칙 작업: **메시지 속성 수정** \> **SCL(스팸 지수)** \> **0을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="83930-219">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>
   - <span data-ttu-id="83930-220">규칙 예외: **보낸** 사람 도메인이 fabrikam.com(스팸 필터링을 건너뛰는 도메인만 해당) \>  \></span><span class="sxs-lookup"><span data-stu-id="83930-220">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="83930-221">IP 허용 목록의 원본에서 보낸 메시지가 여전히 필터링되는 시나리오</span><span class="sxs-lookup"><span data-stu-id="83930-221">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="83930-222">IP 허용 목록의 전자 메일 서버에서 보낸 메시지는 다음과 같은 시나리오에서 여전히 스팸 필터링이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-222">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="83930-223">IP 허용 목록의 IP 주소는 Microsoft 365(이 테넌트 A를 호출)  테넌트의 모든 테넌트의 IP 기반 인바운드 커넥터와 Microsoft 데이터 센터의 동일한 *Active* Directory 포리스트에 있는 테넌트 A 및 EOP 서버에서도 구성됩니다. </span><span class="sxs-lookup"><span data-stu-id="83930-223">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="83930-224">이 시나리오에서는 **IPV:CAL이**  메시지의 스팸 [](anti-spam-message-headers.md) 방지 메시지 헤더에 추가되지만(메시지가 스팸 필터링을 무시한 경우) 여전히 스팸 필터링이 적용되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-224">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="83930-225">IP 허용 목록과 메시지를 처음 접하는 EOP 서버를 포함하는 테넌트는 모두 Microsoft 데이터 센터의 다른 *Active* Directory 포리스트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-225">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="83930-226">이 시나리오에서는 **IPV:CAL이**  메시지 헤더에 추가되지 않습니다. 따라서 메시지에는 여전히 스팸 필터링이 적용되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-226">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="83930-227">이러한 시나리오 중 하나에 해당되는 경우 최소한 다음 설정을 사용하여 메일 흐름 규칙을 만들어 문제가 있는 IP 주소의 메시지가 스팸 필터링을 건너뛰게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83930-227">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="83930-228">규칙 조건: **보낸** 사람 IP 주소가 이러한 범위에 있는 경우 또는 정확히 일치하는 경우(IP 주소 또는 주소) 이 \>  \>  \> 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-228">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>
- <span data-ttu-id="83930-229">규칙 작업: **메시지 속성 수정** \> **SCL(스팸 지수)** 스팸 필터링 무시를 \> **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="83930-229">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="83930-230">새 Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="83930-230">New to Microsoft 365?</span></span>

****

<span data-ttu-id="83930-231">![LinkedIn Learning의 짧은 아이콘을 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="83930-231">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="83930-232">LinkedIn **Learning에서** 제공한 Microsoft 365 관리자 및 IT 프로를 위한 무료 비디오 과정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="83930-232">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
