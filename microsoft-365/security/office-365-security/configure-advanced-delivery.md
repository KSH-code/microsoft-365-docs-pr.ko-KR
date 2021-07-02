---
title: 사용자에 대한 타사 피싱 시뮬레이션 및 필터되지 않은 메시지의 SecOps 사서함 배달 구성
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 관리자는 EOP(Exchange Online Protection)의 고급 배달 정책을 사용하여 지원되는 특정 시나리오(타사 피싱 시뮬레이션 및 SecOps(보안 작업) 사서함으로 배달된 메시지)에서 필터링하지 말아야 하는 메시지를 식별하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 053f88da96983b03ad03e75c11a4fa692ac6a850
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256870"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="247e5-103">사용자에 대한 타사 피싱 시뮬레이션 및 필터되지 않은 메시지의 SecOps 사서함 배달 구성</span><span class="sxs-lookup"><span data-stu-id="247e5-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="247e5-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="247e5-104">**Applies to**</span></span>
- [<span data-ttu-id="247e5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="247e5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="247e5-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="247e5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="247e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="247e5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="247e5-108">이 문서에서 설명하는 기능은 미리 보기에 있으며, 모든 사람이 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="247e5-109">기본적으로 조직의 [](secure-by-default.md)보안을 유지하기 위해 EOP(Exchange Online Protection)는 맬웨어 또는 높은 신뢰도 피싱으로 식별된 메시지에 대해 수신 허용 목록 또는 필터링 우회를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="247e5-110">그러나 필터되지 않은 메시지를 배달해야 하는 특정 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="247e5-111">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-111">For example:</span></span>

- <span data-ttu-id="247e5-112">**타사 피싱 시뮬레이션:** 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 취약한 사용자를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="247e5-113">**SecOps(보안 작업)** 사서함: 보안 팀에서 필터되지 않은 메시지를 수집 및 분석하는 데 사용하는 전용 사서함(좋음과 불량 모두)입니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="247e5-114">이러한 특정 _시나리오에서_ 이러한 Microsoft 365 필터링하지 못하도록  하는 고급 배달 정책을 사용할 수 있습니다. <sup>\*</sup> 고급 배달 정책은 이러한 시나리오의 메시지가 다음 결과를 달성하도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="247e5-115">EOP 및 Microsoft Defender for Office 365 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="247e5-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="247e5-116">스팸 및 피싱에 [대한 ZAP(제로](zero-hour-auto-purge.md) 아워 제거)는 이러한 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="247e5-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="247e5-117">[이러한 시나리오에서는](alerts.md) 기본 시스템 알림이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="247e5-118">[Defender for Defender의](office-365-air.md) AIR Office 365 메시지는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="247e5-119">타사 피싱 시뮬레이션을 위한 구체적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="247e5-120">[관리자 제출은](admin-submission.md) 메시지가 피싱 시뮬레이션 캠페인의 일부이자 실제 위협이 아니라는 자동 응답을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="247e5-121">경고와 AIR이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="247e5-122">[금고 Defender for Office 365](safe-links.md) 링크는 이러한 메시지에서 구체적으로 식별된 URL을 차단하거나 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="247e5-123">[금고 For Defender에서](safe-attachments.md) Office 365 메시지의 첨부 파일은 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="247e5-124"><sup>\*</sup> 맬웨어 필터링 또는 맬웨어에 대한 ZAP를 무시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="247e5-125">고급 배달 정책으로 식별된 메시지는 보안 위협이 아니기 때문에 메시지는 시스템 오버라이드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="247e5-126">관리자는 다음 환경의 이러한 시스템 오버라이드를 필터링하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="247e5-127">계획 2용 Defender의 위협 탐색기 Office 365 검색</span><span class="sxs-lookup"><span data-stu-id="247e5-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="247e5-128">위협 [탐색기/실시간](mdo-email-entity-page.md) 검색의 전자 메일 엔터티 페이지</span><span class="sxs-lookup"><span data-stu-id="247e5-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="247e5-129">[위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="247e5-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="247e5-130">끝점용 Microsoft Defender의 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="247e5-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="247e5-131">캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="247e5-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="247e5-132">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="247e5-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="247e5-133"><https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="247e5-134">고급 배달 페이지로 직접 **이동하기 위해** 를 를 니다. <https://security.microsoft.com/advanceddelivery></span><span class="sxs-lookup"><span data-stu-id="247e5-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="247e5-135">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="247e5-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="247e5-136">이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="247e5-137">고급 배달 정책에서 구성된 설정을 만들거나 수정하거나 제거하려면 Microsoft 365 Defender **포털에서** **보안** 관리자 역할 그룹의 구성원이자 조직 관리  역할 그룹의 구성원인 **Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="247e5-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="247e5-138">고급 배달 정책에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="247e5-139">자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 및 [Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="247e5-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="247e5-140">해당 Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 Defender 포털에서 필요한 사용 권한과  해당 역할의 다른 기능에 대한 사용 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="247e5-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="247e5-141">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="247e5-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="247e5-142">고급 Microsoft 365 Defender 포털을 사용하여 고급 배달 정책에서 SecOps 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="247e5-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="247e5-143">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 \>  \>  \> **규칙** 섹션 \> **고급 배달으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="247e5-144">고급 배달 **페이지에서** **SecOps** 사서함 탭이 선택되어 있는지 확인한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="247e5-145">편집 ![ 아이콘 편집 ](../../media/m365-cc-sc-edit-icon.png) **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="247e5-146">구성된 피싱 시뮬레이션이 없는 경우 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="247e5-147">**SecOps** 사서함 편집 플라이아웃이 열리면 다음 단계 중 하나를 수행하여 SecOps 사서함으로 지정하려는 기존 Exchange Online 사서함을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="247e5-148">상자를 클릭하고 사서함 목록을 확인한 다음 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="247e5-149">상자에서 사서함의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 입력하기 시작하고 결과에서 사서함(표시 이름)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="247e5-150">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="247e5-151">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="247e5-152">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-152">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="247e5-154">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-154">next to the value.</span></span>

4. <span data-ttu-id="247e5-155">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="247e5-156">구성한 SecOps 사서함 항목이 **SecOps** 사서함 탭에 표시됩니다. 변경하려면 탭에서 ![ 편집 아이콘 ](../../media/m365-cc-sc-edit-icon.png) **편집을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="247e5-157">고급 Microsoft 365 Defender 포털을 사용하여 고급 배달 정책에서 타사 피싱 시뮬레이션 구성</span><span class="sxs-lookup"><span data-stu-id="247e5-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="247e5-158">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 \>  \>  \> **규칙** 섹션 \> **고급 배달으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="247e5-159">고급 배달 **페이지에서** 피싱  시뮬레이션 탭을 선택하고 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="247e5-160">편집 ![ 아이콘 편집 ](../../media/m365-cc-sc-edit-icon.png) **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="247e5-161">구성된 피싱 시뮬레이션이 없는 경우 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="247e5-162">열 **수 있는** 타사 피싱 시뮬레이션 플라이아웃 편집 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="247e5-163">**보내는 도메인:** 이 설정을 확장하고 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택하여 하나 이상의 전자 메일 주소 도메인(예: contoso.com)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="247e5-164">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="247e5-165">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="247e5-166">**IP** 보내기: 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택하려면 이 설정을 확장하고 유효한 IPv4 주소를 하나 이상 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="247e5-167">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="247e5-168">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-168">You can add up to 10 entries.</span></span> <span data-ttu-id="247e5-169">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-169">Valid values are:</span></span>
     - <span data-ttu-id="247e5-170">단일 IP: 예: 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="247e5-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="247e5-171">IP 범위: 예: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="247e5-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="247e5-172">CIDR IP: 예: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="247e5-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="247e5-173">허용할 시뮬레이션 **URL:** 이 설정을 확장하고 선택적으로 상자를 클릭하고 값을 입력한 다음 상자 아래에 표시되는 값을 선택하거나 입력하여 차단 또는 검색되지 않는 피싱 시뮬레이션 캠페인의 일부인 특정 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="247e5-174">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-174">You can add up to 10 entries.</span></span>

   <span data-ttu-id="247e5-175">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-175">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="247e5-177">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-177">next to the value.</span></span>

4. <span data-ttu-id="247e5-178">작업을 마치면 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-178">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="247e5-179">**처음:** **추가를** 클릭한 다음 **닫기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-179">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="247e5-180">**기존 편집:** **저장을 클릭한** 다음 닫기 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="247e5-180">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="247e5-181">구성한 타사 피싱 시뮬레이션 항목이 피싱 시뮬레이션 **탭에** 표시됩니다. 변경하려면 탭에서 ![ 편집 아이콘 ](../../media/m365-cc-sc-edit-icon.png) **편집을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-181">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="247e5-182">필터링 우회가 필요한 추가 시나리오</span><span class="sxs-lookup"><span data-stu-id="247e5-182">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="247e5-183">고급 배달 정책이 도움이 될 수 있는 두 가지 시나리오 외에도 필터링을 무시해야 하는 다른 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-183">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="247e5-184">**타사 필터:** 도메인의 MX 레코드가  메시지를 Office 365 경우(메시지가 먼저 다른 곳에 라우팅되는 [경우)](secure-by-default.md) 기본적으로 보안을 사용할 *수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="247e5-184">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="247e5-185">보호를 추가하려면 커넥터에 대해 향상된 필터링을 사용하도록 설정해야 합니다(목록 *건너뛰기라고도 합니다).*</span><span class="sxs-lookup"><span data-stu-id="247e5-185">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="247e5-186">자세한 내용은 [Manage mail flow using a third-party cloud service with Exchange Online.](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)</span><span class="sxs-lookup"><span data-stu-id="247e5-186">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="247e5-187">커넥터에 대해 향상된 필터링을 사용하지 않는 경우 메일 흐름 규칙(전송 규칙)을 사용하여 타사 필터링으로 이미 평가된 메시지에 대해 Microsoft 필터링을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-187">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="247e5-188">자세한 내용은 메일 흐름 규칙을 사용하여 [메시지에서 SCL 설정을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="247e5-188">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="247e5-189">**검토 중의** 가양성: 관리자 제출을 통해 Microsoft에서 여전히 분석하고 [](admin-submission.md) 있는 특정 메시지를 일시적으로 허용하여 Microsoft에 잘못 잘못된 것으로 잘못 표시된 알려진 좋은 메시지(가양성)를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-189">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="247e5-190">모든 재지정과 함께 \*\*\*\* 이러한 허용은 임시로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-190">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="247e5-191">Exchange Online 고급 배달 정책의 SecOps 사서함에 대한 PowerShell 절차</span><span class="sxs-lookup"><span data-stu-id="247e5-191">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="247e5-192">PowerShell에서 Exchange Online 고급 배달 정책의 SecOps 사서함의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-192">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="247e5-193">**SecOps override 정책**: **\* -SecOpsOverridePolicy** cmdlet에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-193">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="247e5-194">**SecOps는** **\* -SecOpsOverrideRule** cmdlet에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-194">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="247e5-195">이 동작의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-195">This behavior has the following results:</span></span>

- <span data-ttu-id="247e5-196">먼저 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-196">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="247e5-197">PowerShell에서 정책을 제거하면 해당 규칙도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-197">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="247e5-198">PowerShell에서 규칙을 제거하면 해당 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-198">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="247e5-199">해당 정책을 수동으로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-199">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="247e5-200">PowerShell을 사용하여 SecOps 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="247e5-200">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="247e5-201">PowerShell의 고급 배달 정책에서 SecOps 사서함을 구성하는 과정은 2단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-201">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="247e5-202">SecOps 재지정 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-202">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="247e5-203">규칙이 적용되는 정책을 지정하는 SecOps 다시 지정 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-203">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="247e5-204">1단계: PowerShell을 사용하여 SecOps 재지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="247e5-204">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="247e5-205">SecOps 재지정 정책을 만들 수 있는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-205">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="247e5-206">**참고:** 지정한 Name 값에 관계없이 정책 이름은 SecOpsOverridePolicy가 수록될 수 있으므로 해당 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-206">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="247e5-207">이 예에서는 SecOps 사서함 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-207">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="247e5-208">구문과 매개 변수에 대한 자세한 내용은 [New-SecOpsOverridePolicy를 참조하십시오.](/powershell/module/exchange/new-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-208">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="247e5-209">2단계: PowerShell을 사용하여 SecOps 재지정 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="247e5-209">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="247e5-210">이 예에서는 지정된 설정을 사용하여 SecOps 사서함 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-210">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="247e5-211">\*\*참고:\*\*\*\*지정한 이름 값에 관계없이 규칙 이름은 SecOpsOverrideRule이 됩니다. 여기서 은 고유한 GUID 값입니다(예: \<GUID\> \<GUID\> 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="247e5-211">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="247e5-212">구문과 매개 변수에 대한 자세한 내용은 [New-SecOpsOverrideRule을 참조하십시오.](/powershell/module/exchange/new-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-212">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="247e5-213">PowerShell을 사용하여 SecOps 재지정 정책 보기</span><span class="sxs-lookup"><span data-stu-id="247e5-213">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="247e5-214">이 예에서는 SecOps 사서함 정책 하나만에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-214">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="247e5-215">구문과 매개 변수에 대한 자세한 내용은 [Get-SecOpsOverridePolicy 를 참조하십시오.](/powershell/module/exchange/get-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-215">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="247e5-216">PowerShell을 사용하여 SecOps 재지정 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="247e5-216">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="247e5-217">이 예에서는 SecOps 재지정 규칙에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-217">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="247e5-218">이전 명령은 하나의 규칙만 반환해야 하지만, 보류 중인 모든 규칙이 결과에 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-218">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="247e5-219">이 예에서는 유효한 규칙(하나)과 잘못된 규칙을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-219">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="247e5-220">잘못된 규칙을 식별한 후 이 문서 의 의 2부에서 설명하는 **Remove-SecOpsOverrideRule** cmdlet을 사용하여 제거할 [수 있습니다.](#use-powershell-to-remove-secops-override-rules)</span><span class="sxs-lookup"><span data-stu-id="247e5-220">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="247e5-221">구문과 매개 변수에 대한 자세한 내용은 [Get-SecOpsOverrideRule을 참조하십시오.](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-221">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="247e5-222">PowerShell을 사용하여 SecOps 다시 설정 정책 수정</span><span class="sxs-lookup"><span data-stu-id="247e5-222">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="247e5-223">SecOps 다시 설정 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-223">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="247e5-224">이 예에서는 SecOps secops2@contoso.com 정책에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-224">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="247e5-225">**참고:** 연결된 유효한 SecOps 재지정 규칙이 있는 경우 규칙의 전자 메일 주소도 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-225">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="247e5-226">구문과 매개 변수에 대한 자세한 내용은 [Set-SecOpsOverridePolicy를 참조하십시오.](/powershell/module/exchange/set-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-226">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="247e5-227">PowerShell을 사용하여 SecOps 다시 설정 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="247e5-227">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="247e5-228">**Set-SecOpsOverrideRule** cmdlet은 SecOps override 규칙의 전자 메일 주소를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-228">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="247e5-229">SecOps 다시 설정 규칙에서 전자 메일 주소를 수정하려면 **Set-SecOpsOverridePolicy** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-229">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="247e5-230">구문과 매개 변수에 대한 자세한 내용은 [Set-SecOpsOverrideRule을 참조하십시오.](/powershell/module/exchange/set-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-230">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="247e5-231">PowerShell을 사용하여 SecOps 재지정 정책 제거</span><span class="sxs-lookup"><span data-stu-id="247e5-231">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="247e5-232">이 예에서는 SecOps 사서함 정책 및 해당 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-232">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="247e5-233">구문과 매개 변수에 대한 자세한 내용은 [Remove-SecOpsOverridePolicy를 참조하십시오.](/powershell/module/exchange/remove-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-233">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="247e5-234">PowerShell을 사용하여 SecOps 재지정 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="247e5-234">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="247e5-235">SecOps 재지정 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-235">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="247e5-236">이 예제에서는 지정한 SecOps 다시 지정 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-236">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="247e5-237">구문과 매개 변수에 대한 자세한 내용은 [Remove-SecOpsOverrideRule을 참조하십시오.](/powershell/module/exchange/remove-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-237">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="247e5-238">Exchange Online 고급 배달 정책의 타사 피싱 시뮬레이션에 대한 PowerShell 절차</span><span class="sxs-lookup"><span data-stu-id="247e5-238">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="247e5-239">PowerShell의 Exchange Online 고급 배달 정책에서 타사 피싱 시뮬레이션의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-239">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="247e5-240">**피싱 시뮬레이션은** **\* -PhishSimOverridePolicy** cmdlet에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-240">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="247e5-241">**피싱 시뮬레이션은** **\* -PhishSimOverrideRule** cmdlet에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-241">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="247e5-242">이 동작의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-242">This behavior has the following results:</span></span>

- <span data-ttu-id="247e5-243">먼저 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-243">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="247e5-244">정책과 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-244">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="247e5-245">PowerShell에서 정책을 제거하면 해당 규칙도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-245">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="247e5-246">PowerShell에서 규칙을 제거하면 해당 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-246">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="247e5-247">해당 정책을 수동으로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-247">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="247e5-248">PowerShell을 사용하여 타사 피싱 시뮬레이션 구성</span><span class="sxs-lookup"><span data-stu-id="247e5-248">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="247e5-249">PowerShell의 고급 배달 정책에서 타사 피싱 시뮬레이션을 구성하는 과정은 2단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-249">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="247e5-250">피싱 시뮬레이션 은(는) 정책에 대한 피싱 시뮬레이션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-250">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="247e5-251">규칙이 적용되는 정책을 지정하는 피싱 시뮬레이션 오버라이드 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-251">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="247e5-252">1단계: PowerShell을 사용하여 피싱 시뮬레이션 의회 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="247e5-252">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="247e5-253">이 예에서는 피싱 시뮬레이션 오버라이드 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-253">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="247e5-254">**참고:** 지정한 이름 값에 관계없이 정책 이름은 PhishSimOverridePolicy가 있으므로 해당 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-254">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="247e5-255">구문과 매개 변수에 대한 자세한 내용은 [New-PhishSimOverridePolicy 를 참조하십시오.](/powershell/module/exchange/new-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-255">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="247e5-256">2단계: PowerShell을 사용하여 피싱 시뮬레이션재해 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="247e5-256">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="247e5-257">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-257">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="247e5-258">지정한 이름 값에 관계없이 규칙 이름은 PhishSimOverrideRule이 됩니다. 여기서 은 고유한 GUID 값입니다(예: \<GUID\> \<GUID\> a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="247e5-258">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="247e5-259">유효한 IP 주소 항목은 다음 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-259">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="247e5-260">단일 IP: 예: 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="247e5-260">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="247e5-261">IP 범위: 예: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="247e5-261">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="247e5-262">CIDR IP: 예: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="247e5-262">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="247e5-263">이 예제에서는 지정된 설정을 사용하여 피싱 시뮬레이션 에지 적용 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-263">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="247e5-264">구문과 매개 변수에 대한 자세한 내용은 [New-PhishSimOverrideRule 을 참조하십시오.](/powershell/module/exchange/new-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-264">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="247e5-265">PowerShell을 사용하여 피싱 시뮬레이션에 대한 정책 보기</span><span class="sxs-lookup"><span data-stu-id="247e5-265">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="247e5-266">이 예에서는 피싱 시뮬레이션 재지정 정책 하나에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-266">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="247e5-267">구문과 매개 변수에 대한 자세한 내용은 [Get-PhishSimOverridePolicy를 참조하십시오.](/powershell/module/exchange/get-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-267">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="247e5-268">PowerShell을 사용하여 피싱 시뮬레이션에 대한 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="247e5-268">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="247e5-269">이 예제에서는 피싱 시뮬레이션 재지정 규칙에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-269">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="247e5-270">이전 명령은 하나의 규칙만 반환해야 하지만, 보류 중인 모든 규칙이 결과에 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-270">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="247e5-271">이 예에서는 유효한 규칙(하나)과 잘못된 규칙을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-271">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="247e5-272">잘못된 규칙을 식별한 후 이 문서 의 나중에 설명된 바와 같이 **Remove-PhisSimOverrideRule** cmdlet을 사용하여 제거할 [수 있습니다.](#use-powershell-to-remove-phishing-simulation-override-rules)</span><span class="sxs-lookup"><span data-stu-id="247e5-272">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="247e5-273">구문과 매개 변수에 대한 자세한 내용은 [Get-PhishSimOverrideRule 을 참조하십시오.](/powershell/module/exchange/get-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-273">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="247e5-274">PowerShell을 사용하여 피싱 시뮬레이션에 대한 정책 수정</span><span class="sxs-lookup"><span data-stu-id="247e5-274">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="247e5-275">피싱 시뮬레이션을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-275">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="247e5-276">이 예에서는 피싱 시뮬레이션 오버라이드 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-276">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="247e5-277">구문과 매개 변수에 대한 자세한 내용은 [Set-PhishSimOverridePolicy를 참조하십시오.](/powershell/module/exchange/set-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-277">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="247e5-278">PowerShell을 사용하여 피싱 시뮬레이션 수정 규칙</span><span class="sxs-lookup"><span data-stu-id="247e5-278">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="247e5-279">피싱 시뮬레이션 수정 규칙을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-279">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="247e5-280">이 예에서는 다음 설정을 사용하여 지정된 피싱 시뮬레이션 에지 적용 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-280">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="247e5-281">도메인 항목을 추가 blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="247e5-281">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="247e5-282">IP 주소 항목 192.168.1.55를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-282">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="247e5-283">이러한 변경 내용은 기존 항목에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-283">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="247e5-284">구문과 매개 변수에 대한 자세한 내용은 [Set-PhishSimOverrideRule을 참조하십시오.](/powershell/module/exchange/set-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-284">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="247e5-285">PowerShell을 사용하여 피싱 시뮬레이션에 대한 정책 제거</span><span class="sxs-lookup"><span data-stu-id="247e5-285">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="247e5-286">이 예에서는 피싱 시뮬레이션재해 정책 및 해당 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-286">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="247e5-287">구문과 매개 변수에 대한 자세한 내용은 [Remove-PhishSimOverridePolicy를 참조하십시오.](/powershell/module/exchange/remove-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="247e5-287">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="247e5-288">PowerShell을 사용하여 피싱 시뮬레이션에 대한 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="247e5-288">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="247e5-289">피싱 시뮬레이션 오버라이드 규칙을 제거하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-289">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="247e5-290">이 예제에서는 지정한 피싱 시뮬레이션 에보라이드 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="247e5-290">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="247e5-291">구문과 매개 변수에 대한 자세한 내용은 [Remove-PhishSimOverrideRule을 참조하십시오.](/powershell/module/exchange/remove-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="247e5-291">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
