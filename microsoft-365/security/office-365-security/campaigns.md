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
ms.openlocfilehash: 350f4f9007bf6f09836080af65802a9757532dcc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083551"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="8b11f-103">Office 365 ATP의 캠페인보기</span><span class="sxs-lookup"><span data-stu-id="8b11f-103">Campaign Views in Office 365 ATP</span></span>

<span data-ttu-id="8b11f-104">캠페인 보기는 서비스의 피싱 공격을 식별하고 분류하는 Office 365 보안 및 준수 센터의 ATP (Advanced Threat Protection)의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="8b11f-105">캠페인 보기를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="8b11f-106">피싱 공격을 효과적으로 조사하고 이에 대처합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="8b11f-107">공격의 범위를 더 잘 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="8b11f-108">의사 결정자에게 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-108">Show value to decision makers.</span></span>

<span data-ttu-id="8b11f-109">캠페인 보기를 그 누구보다 빠르고 완벽하게 공격의 전체적인 상황을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="8b11f-110">캠페인이란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="8b11f-110">What is a campaign?</span></span>

<span data-ttu-id="8b11f-111">캠페인은 하나 이상의 조직에 대해 조율된 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="8b11f-112">자격 증명 및 회사 데이터를 도용 하는 전자 메일 공격은 대규모이 고 lucrative 업계입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="8b11f-113">공격을 중지 하기 위해 기술이 증가 함에 따라 공격자는 성공적인 성공을 위해 해당 메서드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="8b11f-114">Microsoft는 캠페인을 식별 하는 데 도움이 되도록 전체 Office 365 서비스에서 방대한 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire Office 365 service to help identify campaigns.</span></span> <span data-ttu-id="8b11f-115">다양 한 요인에 따라 공격 정보를 분석 하 고 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="8b11f-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-116">For example:</span></span>

- <span data-ttu-id="8b11f-117">**원본 공격**: 원본 IP 주소와 보낸 사람의 전자 메일 도메인.</span><span class="sxs-lookup"><span data-stu-id="8b11f-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="8b11f-118">**Attack 메시지 속성**: 공격 메시지의 내용, 스타일 및 어조.</span><span class="sxs-lookup"><span data-stu-id="8b11f-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="8b11f-119">**받는 사람 공격**: 받는 사람 도메인, 받는 사람의 직무 기능(관리자, 임원 등), 회사 유형(대규모, 소규모, 공공 부문, 민간 부문 등) 및 산업.</span><span class="sxs-lookup"><span data-stu-id="8b11f-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="8b11f-120">**공격 페이로드**: 악성 링크, 첨부 파일 또는 공격 메시지의 기타 페이로드</span><span class="sxs-lookup"><span data-stu-id="8b11f-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="8b11f-121">캠페인은 수명이 짧고 며칠, 주 또는 몇 개월 동안 활성 및 비활성 기간으로 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="8b11f-122">특정 조직에 대해 캠페인을 시작할 수도 있고 조직이 여러 회사에 걸친 대규모 캠페인의 일부일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="8b11f-123">Office 365 보안 및 준수 센터 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="8b11f-123">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="8b11f-124">캠페인 보기는 **위협 관리** \> **캠페인**의 [보안 & 준수 센터](https://protection.office.com) 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![보안 및 규정 준수 센터의 캠페인 개요](../../media/campaigns-overview.png)

<span data-ttu-id="8b11f-126">다음을 통해 캠페인을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="8b11f-127">**위협 관리** \> **탐색기** \> \*\*\*\* \> **캠페인** 보기</span><span class="sxs-lookup"><span data-stu-id="8b11f-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="8b11f-128">**위협 관리** \> **탐색기** \> \*\*\*\* \> **모든 전자** 메일 \> **캠페인** 보기</span><span class="sxs-lookup"><span data-stu-id="8b11f-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="8b11f-129">캠페인 데이터가 나타나지 않으면 기간을 변경해보십시오.</span><span class="sxs-lookup"><span data-stu-id="8b11f-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="8b11f-130">개요 페이지에는 캠페인에 대한 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="8b11f-131">**이름**</span><span class="sxs-lookup"><span data-stu-id="8b11f-131">**Name**</span></span>

- <span data-ttu-id="8b11f-132">**샘플 제목**: 캠페인의 메시지 중 하나에 대한 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="8b11f-133">캠페인의 모든 메시지에는 같은 주제가 포함 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="8b11f-134">**Type**: 현재이 값은 항상 **피싱**입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="8b11f-135">**하위 유형**: 가능한 경우, 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="8b11f-136">검색이 ATP 기술에 따라 구동 되 면 접두사 **ATP-** 가 하위 형식 값에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="8b11f-137">**받는 사람**: 이 캠페인을 대상으로 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="8b11f-138">**Inboxed**:이 캠페인에서 메시지를 받은 사용자 수 (정크로 배달 되지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="8b11f-139">**클릭 한**경우: 피싱 메시지에서 URL을 클릭 한 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="8b11f-140">**급여**: "**클릭 한** / **사람"으로**계산 되는 백분율을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="8b11f-141">이 값은 캠페인의 효율성 및 받는 사람이 메시지를 피싱 메일로 식별 하 고 페이로드 URL을 클릭 하지 못하도록 할지 여부를 나타내는 지표입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="8b11f-142">**방문**함: 페이로드 웹 사이트에 실제로 적용 된 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="8b11f-143">**클릭** 한 값이 있지만 안전한 링크가 웹 사이트에 대 한 액세스를 차단 하는 경우이 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="8b11f-144">캠페인 이름을 클릭하면 캠페인 세부 정보가 플라이 아웃에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="8b11f-145">캠페인 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8b11f-145">Campaign details</span></span>

<span data-ttu-id="8b11f-146">캠페인 세부 정보 보기에서 다음과 같이 캠페인에 대한 많은 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="8b11f-147">캠페인 정보:</span><span class="sxs-lookup"><span data-stu-id="8b11f-147">Campaign information:</span></span>

  - <span data-ttu-id="8b11f-148">**ID**: 고유한 캠페인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="8b11f-149">**시작** 및 **종료**: 선택한 날짜 범위 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="8b11f-150">**영향**: 선택한 날짜 범위 필터에 대 한 다음 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="8b11f-151">총 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-151">The total number of recipients.</span></span>

    - <span data-ttu-id="8b11f-152">"Inboxed" (즉, 받은 편지함에 배달 되는 정크 메일이 아닌 메시지)의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="8b11f-153">피싱 메시지의 URL 페이로드에서 클릭 한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="8b11f-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="8b11f-154">Howe 많은 사용자가 URL을 방문 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="8b11f-155">캠페인 활동의 타임라인: 캠페인이 시작되고 종료 된 시간과 시간 경과 동안 발생한 메시지의 양입니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="8b11f-156">캠페인 흐름</span><span class="sxs-lookup"><span data-stu-id="8b11f-156">Campaign flow</span></span>

<span data-ttu-id="8b11f-157">캠페인에 대한 중요 세부 정보는 **흐름** 섹션의 순서도(_Sankey_ 다이어그램이라고 함)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="8b11f-158">이러한 세부 정보는 캠페인의 요소와 조직에서 발생할 수 있는 영향을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![사용자 URL 클릭을 포함하지 않는 캠페인 세부 정보](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="8b11f-160">다이어그램에서 가로 밴드에 마우스를 올리면 관련 메시지 수(예: 특정 원본 IP의 메시지, 지정된 보낸 사람 도메인을 사용하는 원본 IP의 메시지)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="8b11f-161">흐름도에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="8b11f-162">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="8b11f-162">**Sender IPs**</span></span>

- <span data-ttu-id="8b11f-163">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="8b11f-163">**Sender domains**</span></span>

- <span data-ttu-id="8b11f-164">**결과 필터**: 여기에 있는 값은 [스팸 방지 메시지 머리글](anti-spam-message-headers.md)에 설명된 대로 사용 가능한 피싱 방지 및 스팸 방지 필터 결과와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-164">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="8b11f-165">사용 가능한 값은 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="8b11f-166">값</span><span class="sxs-lookup"><span data-stu-id="8b11f-166">Value</span></span>|<span data-ttu-id="8b11f-167">스팸 필터 결과</span><span class="sxs-lookup"><span data-stu-id="8b11f-167">Spam filter verdict</span></span>|<span data-ttu-id="8b11f-168">설명</span><span class="sxs-lookup"><span data-stu-id="8b11f-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="8b11f-169">**있도록**</span><span class="sxs-lookup"><span data-stu-id="8b11f-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="8b11f-170">메시지가 스팸으로 분류 된 것으로 표시 되 고 전송 규칙이 라고도 하는 메일 흐름 규칙을 통해 평가 되기 전에는 필터링을 건너 뜁니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-170">The message was marked as not spam and/or skipped filtering before being evaluated by the spam filter (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="8b11f-171">다른 이유로 인해 메시지는 스팸 필터링을 건너뛰었습니다 (예: 보낸 사람 및 받는 사람이 같은 조직에 있는 것 처럼 보이는 경우).</span><span class="sxs-lookup"><span data-stu-id="8b11f-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="8b11f-172">**수준**</span><span class="sxs-lookup"><span data-stu-id="8b11f-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="8b11f-173">메시지가 스팸 필터로 평가 되기 전에 스팸으로 표시 되었습니다 (예: 메일 흐름 규칙).</span><span class="sxs-lookup"><span data-stu-id="8b11f-173">The message was marked as spam before being evaluated by the spam filter (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="8b11f-174">**감지함**</span><span class="sxs-lookup"><span data-stu-id="8b11f-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="8b11f-175">스팸 필터에 의해 메시지가 스팸으로 표시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-175">The message was marked as spam by the spam filter.</span></span>|
  |<span data-ttu-id="8b11f-176">**검색 되지 않음**</span><span class="sxs-lookup"><span data-stu-id="8b11f-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="8b11f-177">스팸 필터에 의해 메시지가 스팸으로 표시 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-177">The message was marked as not spam by the spam filter.</span></span>|
  |<span data-ttu-id="8b11f-178">**해제할**</span><span class="sxs-lookup"><span data-stu-id="8b11f-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="8b11f-179">메시지가 격리에서 해제 되었기 때문에 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="8b11f-180">**테 넌 트 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="8b11f-181">스팸 필터 정책 구성 (예: 보낸 사람 또는 도메인이 **보낸 사람 허용** 목록에 있었던 경우)으로 인해 스팸 필터링이 무시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-181">The message skipped spam filtering due to the spam filter policy configuration (for example, the sender or domain was in hte **Sender allow** list).</span></span>|
  |<span data-ttu-id="8b11f-182">**테 넌 트 블록**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="8b11f-183">스팸 필터링 정책 구성으로 인해 메시지가 차단 되었습니다 (예: 보낸 사람 또는 도메인이 **보낸 사람 차단** 목록에 있었던 경우).</span><span class="sxs-lookup"><span data-stu-id="8b11f-183">The message was blocked by spam filtering due to the spam filter policy configuration (for example, the sender or domain was in the **Sender block** list).</span></span>|
  |<span data-ttu-id="8b11f-184">**사용자 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="8b11f-185">보낸 사람이 Outlook의 사용자 수신 허용-보낸 사람 목록에 있기 때문에 메시지가 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="8b11f-186">**사용자 차단**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="8b11f-187">보낸 사람이 Outlook의 차단 된 보낸 사람 목록에 있기 때문에 스팸 필터링에 의해 메시지가 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="8b11f-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="8b11f-188">**ZAP**</span></span>|<span data-ttu-id="8b11f-189">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8b11f-189">n/a</span></span>|<span data-ttu-id="8b11f-190">스팸 필터 정책 구성 (정크 메일 폴더로 이동 또는 격리 됨)에 따라 전송 된 메시지에 대해 [0 시간 자동 삭제 (ZAP)](zero-hour-auto-purge.md) 작업을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your spam filter policy configuration (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="8b11f-191"><sup>\*</sup>허용 된 메시지가 서비스에 의해 차단 되었을 수 있으므로 스팸 필터 정책 구성 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-191"><sup>\*</sup> Review your spam filter policy configuration settings, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="8b11f-192"><sup>\*\*</sup>스팸 필터 정책 구성 설정을 검토 하 여 배달 되지 않고 격리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-192"><sup>\*\*</sup> Review your spam filter policy configuration settings, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="8b11f-193">**전달 위치**: 사용자가 메시지에서 페이로드 URL을 클릭하지 않은 경우라도 (받은 편지함 또는 정크 메일 폴더로) 받는 사람에게 실제로 전달된 메시지를 조사하려 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="8b11f-194">격리 됨에서 격리 된 메시지를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="8b11f-195">자세한 내용은 [Office 365에서 전자 메일 메시지 격리](quarantine-email-messages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b11f-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="8b11f-196">**폴더 삭제됨**</span><span class="sxs-lookup"><span data-stu-id="8b11f-196">**Deleted folder**</span></span>

  - <span data-ttu-id="8b11f-197">**끊김**</span><span class="sxs-lookup"><span data-stu-id="8b11f-197">**Dropped**</span></span>

  - <span data-ttu-id="8b11f-198">**외부**: 받는 사람이 온-프레미스 전자 메일 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="8b11f-199">**실패**</span><span class="sxs-lookup"><span data-stu-id="8b11f-199">**Failed**</span></span>

  - <span data-ttu-id="8b11f-200">**받습니다**</span><span class="sxs-lookup"><span data-stu-id="8b11f-200">**Forwarded**</span></span>

  - <span data-ttu-id="8b11f-201">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="8b11f-201">**Inbox**</span></span>

  - <span data-ttu-id="8b11f-202">**정크 메일 폴더**</span><span class="sxs-lookup"><span data-stu-id="8b11f-202">**Junk folder**</span></span>

  - <span data-ttu-id="8b11f-203">**격리**</span><span class="sxs-lookup"><span data-stu-id="8b11f-203">**Quarantine**</span></span>

  - <span data-ttu-id="8b11f-204">**알 수 없음**</span><span class="sxs-lookup"><span data-stu-id="8b11f-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="8b11f-205">10 개 보다 많은 항목이 포함 된 모든 계층에서 상위 10 개 항목이 표시 되 고 나머지는 **다른**항목에 함께 번들 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="8b11f-206">URL 클릭</span><span class="sxs-lookup"><span data-stu-id="8b11f-206">URL clicks</span></span>

<span data-ttu-id="8b11f-207">피싱 메시지가 받는 사람 (받은 편지함 또는 정크 메일 폴더)에 배달 되 면 항상 사용자가 페이로드 URL을 클릭할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="8b11f-208">전달 된 메시지에서 URL을 클릭 하는 것은 성공적인를 측정 하는 것은 아니지만, 처음에는 피싱 메시지가 사서함에 배달 된 이유를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="8b11f-209">사용자가 피싱 메시지에서 페이로드 URL을 클릭 하면 해당 작업이 캠페인 세부 정보 보기에 있는 다이어그램의 **URL 클릭** 영역에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="8b11f-210">**있도록**</span><span class="sxs-lookup"><span data-stu-id="8b11f-210">**Allowed**</span></span>

- <span data-ttu-id="8b11f-211">**Blockpage**: 받는 사람이 페이로드 URL을 클릭 했지만, 악의적인 웹 사이트에 대 한 액세스 권한이 조직의 [ATP 안전한 링크](atp-safe-links.md) 정책에 의해 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="8b11f-212">**Blockpageoverride**: 받는 사람이 메시지의 페이로드 URL을 클릭 했을 때 ATP 안전한 링크가 중지 하려고 했지만 블록을 재정의할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="8b11f-213">안전한 링크 [정책을](set-up-atp-safe-links-policies.md) 조사 하 여 사용자가 안전한 링크 결과를 재정의 하 고 악성 웹 사이트를 계속 사용할 수 있는 이유를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="8b11f-214">**PendingDetonationPage**: ATP 안전한 첨부 파일은 가상 컴퓨터 환경에서 페이로드 URL을 열고 어떤 일이 진행 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="8b11f-215">**PendingDetonationPageOverride**: 받는 사람이 페이로드 샌드 박싱 프로세스를 재정의 하 고 결과를 기다리지 않고 URL을 열 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="8b11f-216">탭</span><span class="sxs-lookup"><span data-stu-id="8b11f-216">Tabs</span></span>

<span data-ttu-id="8b11f-217">캠페인 세부 정보 보기에는 캠페인을 더 자세히 조사할 수 있는 몇 가지 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="8b11f-218">**URL 클릭**: 사용자가 피싱 메시지에서 페이로드 URL을 클릭 하지 않은 경우이 섹션은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="8b11f-219">사용자가 URL을 클릭할 수 있는 경우 다음 값이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="8b11f-220">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="8b11f-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="8b11f-222">**시간 클릭**</span><span class="sxs-lookup"><span data-stu-id="8b11f-222">**Click Time**</span></span>

  - <span data-ttu-id="8b11f-223">**동작 클릭**</span><span class="sxs-lookup"><span data-stu-id="8b11f-223">**Click Action**</span></span>

- <span data-ttu-id="8b11f-224">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="8b11f-224">**Sender IPs**</span></span>

  - <span data-ttu-id="8b11f-225">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="8b11f-226">**합계**</span><span class="sxs-lookup"><span data-stu-id="8b11f-226">**Total Count**</span></span>

  - <span data-ttu-id="8b11f-227">**받은 편지함 개수**</span><span class="sxs-lookup"><span data-stu-id="8b11f-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="8b11f-228">**차단된 개수**</span><span class="sxs-lookup"><span data-stu-id="8b11f-228">**Blocked Count**</span></span>

  - <span data-ttu-id="8b11f-229">**Spf 통과**: [Spf (sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)에 의해 보낸 사람이 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="8b11f-230">SPF 유효성 검사를 통과 하지 못하는 보낸 사람은 보낸 사람이 인증 되지 않았거나 메시지가 합법적인 보낸 사람에 게 스푸핑 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="8b11f-231">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="8b11f-231">**Senders**</span></span>

  - <span data-ttu-id="8b11f-232">**Sender**: 사용자가 전자 메일 클라이언트에 표시 하는 보낸 사람: 전자 메일 주소가 아닐 수도 있는,이 주소는 SMTP MAIL FROM 명령에 있는 실제 발신자 주소로,</span><span class="sxs-lookup"><span data-stu-id="8b11f-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="8b11f-233">**합계**</span><span class="sxs-lookup"><span data-stu-id="8b11f-233">**Total Count**</span></span>

  - <span data-ttu-id="8b11f-234">**박스형**</span><span class="sxs-lookup"><span data-stu-id="8b11f-234">**Inboxed**</span></span>

  - <span data-ttu-id="8b11f-235">**박스형 아님**</span><span class="sxs-lookup"><span data-stu-id="8b11f-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="8b11f-236">**Dkim 통과**: 보낸 사람이 [Dkim (도메인 키 확인 메일)](support-for-validation-of-dkim-signed-messages.md)에 의해 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="8b11f-237">DKIM 유효성 검사를 통과 하지 않은 보낸 사람은 보낸 사람이 인증 되지 않았거나 메시지가 합법적인 보낸 사람에 게 스푸핑 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="8b11f-238">**DMARC 통과**: 보낸 사람이 [도메인 기반 메시지 인증, 보고 및 적합성 (DMARC)](use-dmarc-to-validate-email.md)을 통해 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="8b11f-239">DMARC 유효성 검사를 통과 하지 않은 보낸 사람은 보낸 사람이 인증 되지 않았거나 메시지가 합법적인 보낸 사람에 게 위장 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="8b11f-240">**페이로드**</span><span class="sxs-lookup"><span data-stu-id="8b11f-240">**Payloads**</span></span>

  - <span data-ttu-id="8b11f-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b11f-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="8b11f-242">**합계**</span><span class="sxs-lookup"><span data-stu-id="8b11f-242">**Total Count**</span></span>

<span data-ttu-id="8b11f-243"><sup>\*</sup>이 값을 클릭하면 캠페인 세부 정보 보기 위쪽에 지정된 항목(사용자, URL 등)에 대한 자세한 정보가 포함된 플라이 아웃이 새로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="8b11f-244">캠페인 세부 정보 보기로 돌아가려면 새 플라이 아웃에서 **완료**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="8b11f-245">버튼</span><span class="sxs-lookup"><span data-stu-id="8b11f-245">Buttons</span></span>

<span data-ttu-id="8b11f-246">캠페인 세부 정보 보기의 버튼을 통해 위협 탐색기 기능을 사용하여 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="8b11f-247">**캠페인 탐색**: **캠페인 ID** 값을 검색 필터로 사용하여 새로운 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="8b11f-248">**Inboxed 메시지 살펴보기**: **캠페인 ID** 및 **배달 위치: 받은 편지함** 을 검색 필터로 사용 하 여 새 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8b11f-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
