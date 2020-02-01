---
title: Office 365 ATP의 캠페인보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection의 캠페인 보기에 대해 알아보세요.
ms.openlocfilehash: 65ae346fc4ffdcc502c7f479d7d92753cdb5b5bc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599765"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="c1f60-103">Office 365 ATP의 캠페인보기</span><span class="sxs-lookup"><span data-stu-id="c1f60-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="c1f60-104">이 주제에서 설명하는 기능은 현재 미리보기 상태이며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-104">The features described in this topic are currently in preview, and are subject to change.</span></span>

<span data-ttu-id="c1f60-105">캠페인 보기는 서비스의 피싱 공격을 식별하고 분류하는 Office 365 보안 및 준수 센터의 ATP (Advanced Threat Protection)의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="c1f60-106">캠페인 보기를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="c1f60-107">피싱 공격을 효과적으로 조사하고 이에 대처합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="c1f60-108">공격의 범위를 더 잘 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="c1f60-109">의사 결정자에게 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-109">Show value to decision makers.</span></span>

<span data-ttu-id="c1f60-110">캠페인 보기를 그 누구보다 빠르고 완벽하게 공격의 전체적인 상황을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="c1f60-111">캠페인이란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="c1f60-111">What is a campaign?</span></span>

<span data-ttu-id="c1f60-112">캠페인은 하나 이상의 조직에 대해 조율된 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="c1f60-113">오늘날 자격 증명과 회사 데이터를 도용하는 전자 메일 공격은 규모가 크고 수익성 있는 비즈니스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="c1f60-114">기술은 공격을 중지하는 데 도움이 되기 때문에 공격자는 정교한 노력을 통해 방법을 수정하며 지속적인 성공을 보장하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="c1f60-115">Microsoft는 전 세계의 Office 365 서비스 전체에서 방대한 양의 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터 및 경험을 활용하여 캠페인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="c1f60-116">공격 정보는 몇 가지 요인에 따라 분석되고 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="c1f60-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-117">For example:</span></span>

- <span data-ttu-id="c1f60-118">**원본 공격**: 원본 IP 주소와 보낸 사람의 전자 메일 도메인.</span><span class="sxs-lookup"><span data-stu-id="c1f60-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="c1f60-119">**Attack 메시지 속성**: 공격 메시지의 내용, 스타일 및 어조.</span><span class="sxs-lookup"><span data-stu-id="c1f60-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="c1f60-120">**받는 사람 공격**: 받는 사람 도메인, 받는 사람의 직무 기능(관리자, 임원 등), 회사 유형(대규모, 소규모, 공공 부문, 민간 부문 등) 및 산업.</span><span class="sxs-lookup"><span data-stu-id="c1f60-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="c1f60-121">**공격 페이로드**: 악성 링크, 첨부 파일 또는 기타 페이로드.</span><span class="sxs-lookup"><span data-stu-id="c1f60-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="c1f60-122">Office 365 보안 및 준수 센터 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="c1f60-122">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="c1f60-123">캠페인 보기는 [보안 및 준수](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) 센터의 다음 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="c1f60-124">**위협 관리** \> **탐색기** \> **보기** \> **피싱** \> **주요 캠페인(미리 보기)**</span><span class="sxs-lookup"><span data-stu-id="c1f60-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="c1f60-125">**위협 관리** \> **탐색기** \> **보기** \> **모든 전자 메일**\> **주요 캠페인(미리 보기)**</span><span class="sxs-lookup"><span data-stu-id="c1f60-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![보안 및 규정 준수 센터의 캠페인 개요](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="c1f60-127">현재 사용 가능한 유일한 필터링은 날짜 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="c1f60-128">캠페인 데이터가 나타나지 않으면 기간을 변경해보십시오.</span><span class="sxs-lookup"><span data-stu-id="c1f60-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="c1f60-129">개요 페이지에는 캠페인에 대한 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="c1f60-130">**이름**</span><span class="sxs-lookup"><span data-stu-id="c1f60-130">**Name**</span></span>

- <span data-ttu-id="c1f60-131">**샘플 제목**: 캠페인의 메시지 중 하나에 대한 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="c1f60-132">_모든_ 캠페인의 메시지에 이 동일한 주제 줄이 반드시 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="c1f60-133">**유형**: 현재 이 값은 항상 **Phish**입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="c1f60-134">**하위 유형**: 가능한 경우, 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="c1f60-135">검색이 ATP 기술에 의해 시작되면 **ATP** 접두사가 하위 형식 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="c1f60-136">**받는 사람**: 이 캠페인을 대상으로 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="c1f60-137">**전달됨**: 이 캠페인에서 받은 편지함으로 메시지를 받은 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="c1f60-138">**ID**: 이벤트의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="c1f60-139">캠페인 이름을 클릭하면 캠페인 세부 정보가 플라이 아웃에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="c1f60-140">캠페인 세부 정보</span><span class="sxs-lookup"><span data-stu-id="c1f60-140">Campaign details</span></span>

<span data-ttu-id="c1f60-141">캠페인 세부 정보 보기에서 다음과 같이 캠페인에 대한 많은 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="c1f60-142">캠페인 정보:</span><span class="sxs-lookup"><span data-stu-id="c1f60-142">Campaign information:</span></span>

  - <span data-ttu-id="c1f60-143">**ID**: 개요 화면에서 캠페인의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="c1f60-144">**시작** 및 **종료**: 선택한 날짜 범위 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="c1f60-145">**영향**: 선택한 날짜 범위에 보낸 메시지의 수, "받은 편지함"에 보관된 메시지의 수(즉, 받은 편지함으로 전달됨), 피싱 메시지의 URL 페이로드에서 클릭한 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="c1f60-146">캠페인 활동의 타임라인: 캠페인이 시작되고 종료 된 시간과 시간 경과 동안 발생한 메시지의 양입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="c1f60-147">캠페인 흐름</span><span class="sxs-lookup"><span data-stu-id="c1f60-147">Campaign flow</span></span>

<span data-ttu-id="c1f60-148">캠페인에 대한 중요 세부 정보는 **흐름** 섹션의 순서도(_Sankey_ 다이어그램이라고 함)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="c1f60-149">이러한 세부 정보는 캠페인의 요소와 조직에서 발생할 수 있는 영향을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![사용자 URL 클릭을 포함하지 않는 캠페인 세부 정보](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="c1f60-151">다이어그램에서 가로 밴드에 마우스를 올리면 관련 메시지 수(예: 특정 원본 IP의 메시지, 지정된 보낸 사람 도메인을 사용하는 원본 IP의 메시지)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="c1f60-152">흐름도에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-152">The diagram contains the following information:</span></span>

- <span data-ttu-id="c1f60-153">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="c1f60-153">**Sender IPs**</span></span>

- <span data-ttu-id="c1f60-154">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="c1f60-154">**Sender domains**</span></span>

- <span data-ttu-id="c1f60-155">**결과 필터**: 여기에 있는 값은 [스팸 방지 메시지 머리글](anti-spam-message-headers.md)에 설명된 대로 사용 가능한 피싱 방지 및 스팸 방지 필터 결과와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="c1f60-156">여기서 매우 중요한 값은 **테넌트에서 허용**하는 값이며, 이는 조직에서 허용된 설정에 따라 다른 경우에는 서비스(예: 허용된 보낸 사람 목록에 있는 도메인)에 의해 차단되었을 메시지가 허용됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="c1f60-157">**테넌트 차단**: 이 값은 조직의 설정(예: [차단된 보낸 사람 목록](create-block-sender-lists-in-office-365.md)에 있는 도메인 항목)에서 메시지를 감지하고 전달된 위치를 확인했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="c1f60-158">격리되지 않은 메시지의 경우 수신 거부 설정을 검토하여 메시지가 전달된 이유를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="c1f60-159">**감지함**</span><span class="sxs-lookup"><span data-stu-id="c1f60-159">**Detected**</span></span>

  - <span data-ttu-id="c1f60-160">**테넌트 허용**</span><span class="sxs-lookup"><span data-stu-id="c1f60-160">**Tenant Allow**</span></span>

- <span data-ttu-id="c1f60-161">**전달 위치**: 사용자가 메시지에서 페이로드 URL을 클릭하지 않은 경우라도 (받은 편지함 또는 정크 메일 폴더로) 받는 사람에게 실제로 전달된 메시지를 조사하려 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="c1f60-162">[Office 365의 전자 메일 메시지 격리](quarantine-email-messages.md)에서 격리된 메시지를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="c1f60-163">**정크 메일 폴더**</span><span class="sxs-lookup"><span data-stu-id="c1f60-163">**Junk folder**</span></span>

  - <span data-ttu-id="c1f60-164">**격리**</span><span class="sxs-lookup"><span data-stu-id="c1f60-164">**Quarantine**</span></span>

  - <span data-ttu-id="c1f60-165">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="c1f60-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="c1f60-166">URL 클릭</span><span class="sxs-lookup"><span data-stu-id="c1f60-166">URL clicks</span></span>

<span data-ttu-id="c1f60-167">받는 사람의 받은 편지함 또는 정크 메일 폴더로 전달되는 메시지가 사용자에 의해 실행될 가능성도 있습니다(즉, 사용자가 메시지에서 악의적인 URL을 클릭하는 경우).</span><span class="sxs-lookup"><span data-stu-id="c1f60-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="c1f60-168">그렇지 않은 경우에는 애초에 유해한 메시지가 메일함에 전달된 이유를 파악해야 하지만, 성공에 대한 작은 척도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="c1f60-169">사용자가 악의적인 URL을 클릭한 경우 다이어그램 영역의 **URL 클릭**에 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![사용자 URL 클릭을 포함 하는 캠페인 세부 정보](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="c1f60-171">**안전한 링크 차단**: 이 값은 받는 사람이 메시지에서 페이로드 URL을 클릭했지만 조직의 [ATP 안전한 링크](atp-safe-links.md) 정책에 의해 차단되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="c1f60-172">**안전한 링크 차단 재정의**: 이 값은 받는 사람이 메시지에서 페이로드 URL을 클릭하여 ATP가 이를 중지하려고 시도했지만 해당 차단을 재정의할 수 있었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="c1f60-173">[안전한 링크 정책](set-up-atp-safe-links-policies.md)을 검토하여 사용자가 안전한 링크 정책 결과를 재정의하고 악의적인 URL을 클릭할 수 있었던 이유를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="c1f60-174">탭</span><span class="sxs-lookup"><span data-stu-id="c1f60-174">Tabs</span></span>

<span data-ttu-id="c1f60-175">캠페인 세부 정보 보기에는 캠페인을 더 자세히 조사할 수 있는 몇 가지 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="c1f60-176">**URL 클릭**: 피싱 메시지의 페이로드 URL을 클릭하지 않은 경우에는 이 섹션이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="c1f60-177">사용자가 URL을 클릭할 수 있었던 경우</span><span class="sxs-lookup"><span data-stu-id="c1f60-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="c1f60-178">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1f60-178">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1f60-179">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1f60-179">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1f60-180">**시간 클릭**</span><span class="sxs-lookup"><span data-stu-id="c1f60-180">**Click Time**</span></span>

  - <span data-ttu-id="c1f60-181">**동작 클릭**</span><span class="sxs-lookup"><span data-stu-id="c1f60-181">**Click Action**</span></span>

- <span data-ttu-id="c1f60-182">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="c1f60-182">**Sender IPs**</span></span>

  - <span data-ttu-id="c1f60-183">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1f60-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1f60-184">**합계**</span><span class="sxs-lookup"><span data-stu-id="c1f60-184">**Total Count**</span></span>

  - <span data-ttu-id="c1f60-185">**받은 편지함 개수**</span><span class="sxs-lookup"><span data-stu-id="c1f60-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="c1f60-186">**차단된 개수**</span><span class="sxs-lookup"><span data-stu-id="c1f60-186">**Blocked Count**</span></span>

  - <span data-ttu-id="c1f60-187">**통과된 SPF**</span><span class="sxs-lookup"><span data-stu-id="c1f60-187">**SPF Passed**</span></span>

- <span data-ttu-id="c1f60-188">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="c1f60-188">**Senders**</span></span>

  - <span data-ttu-id="c1f60-189">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="c1f60-189">**Sender**</span></span>

  - <span data-ttu-id="c1f60-190">**합계**</span><span class="sxs-lookup"><span data-stu-id="c1f60-190">**Total Count**</span></span>

  - <span data-ttu-id="c1f60-191">**받은 편지함 개수**</span><span class="sxs-lookup"><span data-stu-id="c1f60-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="c1f60-192">**차단된 개수**</span><span class="sxs-lookup"><span data-stu-id="c1f60-192">**Blocked Count**</span></span>

  - <span data-ttu-id="c1f60-193">**통과된 DKIM**</span><span class="sxs-lookup"><span data-stu-id="c1f60-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="c1f60-194">**통과된 DMARC**</span><span class="sxs-lookup"><span data-stu-id="c1f60-194">**DMARC Passed**</span></span>

- <span data-ttu-id="c1f60-195">**페이로드**</span><span class="sxs-lookup"><span data-stu-id="c1f60-195">**Payloads**</span></span>

  - <span data-ttu-id="c1f60-196">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1f60-196">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1f60-197">**합계**</span><span class="sxs-lookup"><span data-stu-id="c1f60-197">**Total Count**</span></span>

<span data-ttu-id="c1f60-198"><sup>\*</sup>이 값을 클릭하면 캠페인 세부 정보 보기 위쪽에 지정된 항목(사용자, URL 등)에 대한 자세한 정보가 포함된 플라이 아웃이 새로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="c1f60-199">캠페인 세부 정보 보기로 돌아가려면 새 플라이 아웃에서 **완료**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="c1f60-200">버튼</span><span class="sxs-lookup"><span data-stu-id="c1f60-200">Buttons</span></span>

<span data-ttu-id="c1f60-201">캠페인 세부 정보 보기의 버튼을 통해 위협 탐색기 기능을 사용하여 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="c1f60-202">**캠페인 탐색**: **캠페인 ID** 값을 검색 필터로 사용하여 새로운 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="c1f60-203">**받은 편지함 메시지 탐색**: **캠페인 ID**과 **전달 위치: 받은 편지함**을 검색 필터로 사용하여 새로운 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1f60-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
