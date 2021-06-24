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
ms.openlocfilehash: 819f78883aa75fbbdded2e47c1bb85945f080233
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108406"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="5dc44-103">사용자에 대한 타사 피싱 시뮬레이션 및 필터되지 않은 메시지의 SecOps 사서함 배달 구성</span><span class="sxs-lookup"><span data-stu-id="5dc44-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="5dc44-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="5dc44-104">**Applies to**</span></span>
- [<span data-ttu-id="5dc44-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5dc44-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5dc44-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="5dc44-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5dc44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5dc44-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="5dc44-108">이 문서에서 설명하는 기능은 미리 보기에 있으며, 모든 사람이 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="5dc44-109">기본적으로 조직의 [](secure-by-default.md)보안을 유지하기 위해 EOP(Exchange Online Protection)는 맬웨어 또는 높은 신뢰도 피싱으로 식별된 메시지에 대해 수신 허용 목록 또는 필터링 우회를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="5dc44-110">그러나 필터되지 않은 메시지를 배달해야 하는 특정 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="5dc44-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-111">For example:</span></span>

- <span data-ttu-id="5dc44-112">**타사 피싱 시뮬레이션:** 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 취약한 사용자를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="5dc44-113">**SecOps(보안 작업)** 사서함: 보안 팀에서 필터되지 않은 메시지를 수집 및 분석하는 데 사용하는 전용 사서함(좋음과 불량 모두)입니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="5dc44-114">이러한 특정 _시나리오에서_ 이러한 Microsoft 365 필터링하지 못하도록  하는 고급 배달 정책을 사용할 수 있습니다. <sup>\*</sup> 고급 배달 정책은 이러한 시나리오의 메시지가 다음 결과를 달성하도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="5dc44-115">EOP 및 Microsoft Defender for Office 365 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dc44-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="5dc44-116">스팸 및 피싱에 [대한 ZAP(제로](zero-hour-auto-purge.md) 아워 제거)는 이러한 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dc44-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="5dc44-117">[이러한 시나리오에서는](alerts.md) 기본 시스템 알림이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="5dc44-118">[Defender for Defender의](office-365-air.md) AIR Office 365 메시지는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="5dc44-119">타사 피싱 시뮬레이션을 위한 구체적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="5dc44-120">[관리자 제출은](admin-submission.md) 메시지가 피싱 시뮬레이션 캠페인의 일부이자 실제 위협이 아니라는 자동 응답을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="5dc44-121">경고와 AIR이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="5dc44-122">[금고 Defender for Office 365](safe-links.md) 링크는 이러한 메시지에서 구체적으로 식별된 URL을 차단하거나 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="5dc44-123">[금고 For Defender에서](safe-attachments.md) Office 365 메시지의 첨부 파일은 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="5dc44-124"><sup>\*</sup> 맬웨어 필터링 또는 맬웨어에 대한 ZAP를 무시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="5dc44-125">고급 배달 정책으로 식별된 메시지는 보안 위협이 아니기 때문에 메시지는 시스템 오버라이드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="5dc44-126">관리자는 다음 환경의 이러한 시스템 오버라이드를 필터링하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="5dc44-127">계획 2용 Defender의 위협 탐색기 Office 365 검색</span><span class="sxs-lookup"><span data-stu-id="5dc44-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="5dc44-128">위협 [탐색기/실시간](mdo-email-entity-page.md) 검색의 전자 메일 엔터티 페이지</span><span class="sxs-lookup"><span data-stu-id="5dc44-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="5dc44-129">[위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="5dc44-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="5dc44-130">끝점용 Microsoft Defender의 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="5dc44-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="5dc44-131">캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="5dc44-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5dc44-132">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="5dc44-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5dc44-133"><https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="5dc44-134">고급 배달 페이지로 직접 **이동하기 위해** 를 를 니다. <https://security.microsoft.com/advanceddelivery></span><span class="sxs-lookup"><span data-stu-id="5dc44-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="5dc44-135">이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-135">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5dc44-136">고급 배달 정책에서 구성된 설정을 만들거나 수정하거나 제거하려면 Microsoft 365 Defender **포털에서** **보안** 관리자 역할 그룹의 구성원이자 조직 관리  역할 그룹의 구성원인 **Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-136">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="5dc44-137">고급 배달 정책에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-137">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="5dc44-138">자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 및 [Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="5dc44-138">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="5dc44-139">해당 Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 Defender 포털에서 필요한 사용 권한과  해당 역할의 다른 기능에 대한 사용 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5dc44-139">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5dc44-140">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5dc44-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="5dc44-141">고급 Microsoft 365 Defender 포털을 사용하여 고급 배달 정책에서 SecOps 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="5dc44-141">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="5dc44-142">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 \>  \>  \> **규칙** 섹션 \> **고급 배달으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-142">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="5dc44-143">고급 배달 **페이지에서** **SecOps** 사서함 탭이 선택되어 있는지 확인한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-143">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="5dc44-144">편집 ![ 아이콘 편집 ](../../media/m365-cc-sc-edit-icon.png) **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-144">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="5dc44-145">구성된 피싱 시뮬레이션이 없는 경우 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-145">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="5dc44-146">**SecOps** 사서함 편집 플라이아웃이 열리면 다음 단계 중 하나를 수행하여 SecOps 사서함으로 지정하려는 기존 Exchange Online 사서함을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-146">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="5dc44-147">상자를 클릭하고 사서함 목록을 확인한 다음 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-147">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="5dc44-148">상자에서 사서함의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 입력하기 시작하고 결과에서 사서함(표시 이름)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-148">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="5dc44-149">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-149">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5dc44-150">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-150">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="5dc44-151">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-151">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="5dc44-153">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-153">next to the value.</span></span>

4. <span data-ttu-id="5dc44-154">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-154">When you're finished, click **Save**.</span></span>

<span data-ttu-id="5dc44-155">구성한 SecOps 사서함 항목이 **SecOps** 사서함 탭에 표시됩니다. 변경하려면 탭에서 ![ 편집 아이콘 ](../../media/m365-cc-sc-edit-icon.png) **편집을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-155">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="5dc44-156">고급 Microsoft 365 Defender 포털을 사용하여 고급 배달 정책에서 타사 피싱 시뮬레이션 구성</span><span class="sxs-lookup"><span data-stu-id="5dc44-156">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="5dc44-157">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 \>  \>  \> **규칙** 섹션 \> **고급 배달으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-157">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="5dc44-158">고급 배달 **페이지에서** 피싱  시뮬레이션 탭을 선택하고 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-158">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="5dc44-159">편집 ![ 아이콘 편집 ](../../media/m365-cc-sc-edit-icon.png) **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-159">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="5dc44-160">구성된 피싱 시뮬레이션이 없는 경우 추가 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-160">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="5dc44-161">열 **수 있는** 타사 피싱 시뮬레이션 플라이아웃 편집 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-161">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="5dc44-162">**보내는 도메인:** 이 설정을 확장하고 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택하여 하나 이상의 전자 메일 주소 도메인(예: contoso.com)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-162">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="5dc44-163">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-163">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5dc44-164">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-164">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="5dc44-165">**IP** 보내기: 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택하려면 이 설정을 확장하고 유효한 IPv4 주소를 하나 이상 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-165">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="5dc44-166">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-166">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5dc44-167">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-167">You can add up to 10 entries.</span></span> <span data-ttu-id="5dc44-168">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-168">Valid values are:</span></span>
     - <span data-ttu-id="5dc44-169">단일 IP: 예: 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="5dc44-169">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="5dc44-170">IP 범위: 예: 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="5dc44-170">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="5dc44-171">CIDR IP: 예: 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="5dc44-171">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="5dc44-172">허용할 시뮬레이션 **URL:** 이 설정을 확장하고 선택적으로 상자를 클릭하고 값을 입력한 다음 상자 아래에 표시되는 값을 선택하거나 입력하여 차단 또는 검색되지 않는 피싱 시뮬레이션 캠페인의 일부인 특정 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-172">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="5dc44-173">항목을 10개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-173">You can add up to 10 entries.</span></span>

   <span data-ttu-id="5dc44-174">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-174">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="5dc44-176">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-176">next to the value.</span></span>

4. <span data-ttu-id="5dc44-177">작업을 마치면 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-177">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="5dc44-178">**처음:** **추가를** 클릭한 다음 **닫기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-178">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="5dc44-179">**기존 편집:** **저장을 클릭한** 다음 닫기 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5dc44-179">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="5dc44-180">구성한 타사 피싱 시뮬레이션 항목이 피싱 시뮬레이션 **탭에** 표시됩니다. 변경하려면 탭에서 ![ 편집 아이콘 ](../../media/m365-cc-sc-edit-icon.png) **편집을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-180">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="5dc44-181">필터링 우회가 필요한 추가 시나리오</span><span class="sxs-lookup"><span data-stu-id="5dc44-181">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="5dc44-182">고급 배달 정책이 도움이 될 수 있는 두 가지 시나리오 외에도 필터링을 무시해야 하는 다른 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-182">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="5dc44-183">**타사 필터:** 도메인의 MX 레코드가  메시지를 Office 365 경우(메시지가 먼저 다른 곳에 라우팅되는 [경우)](secure-by-default.md) 기본적으로 보안을 사용할 *수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="5dc44-183">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="5dc44-184">타사 필터링을 통해 이미 평가된 메시지에 대해 Microsoft 필터링을 무시하기 위해 메일 흐름 규칙(전송 규칙)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-184">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="5dc44-185">자세한 내용은 메일 흐름 규칙을 사용하여 [메시지에서 SCL 설정을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="5dc44-185">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="5dc44-186">**검토 중의** 가양성: 관리자 제출을 통해 Microsoft에서 여전히 분석하고 [](admin-submission.md) 있는 특정 메시지를 일시적으로 허용하여 Microsoft에 잘못 잘못된 것으로 잘못 표시된 알려진 좋은 메시지(가양성)를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-186">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="5dc44-187">모든 재지정과 함께 \*\*\*\* 이러한 허용은 임시로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc44-187">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>
