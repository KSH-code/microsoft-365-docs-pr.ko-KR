---
title: ATP의 캠페인 보기
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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039480"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="fda81-103">ATP의 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="fda81-103">Campaign Views in ATP</span></span>

<span data-ttu-id="fda81-104">캠페인 보기는 보안 & 준수 센터의 ATP (Advanced Threat Protection)에서 서비스의 피싱 공격을 식별 하 고 분류 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="fda81-105">캠페인 보기를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="fda81-106">피싱 공격을 효과적으로 조사하고 이에 대처합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="fda81-107">공격의 범위를 더 잘 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="fda81-108">의사 결정자에게 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-108">Show value to decision makers.</span></span>

<span data-ttu-id="fda81-109">캠페인 보기를 그 누구보다 빠르고 완벽하게 공격의 전체적인 상황을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="fda81-110">캠페인이란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="fda81-110">What is a campaign?</span></span>

<span data-ttu-id="fda81-111">캠페인은 하나 이상의 조직에 대해 조율된 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="fda81-112">자격 증명 및 회사 데이터를 도용 하는 전자 메일 공격은 대규모이 고 lucrative 업계입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="fda81-113">공격을 중지 하기 위해 기술이 증가 함에 따라 공격자는 성공적인 성공을 위해 해당 메서드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="fda81-114">Microsoft는 캠페인을 식별 하는 데 도움이 되도록 전체 서비스에서 방대한 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="fda81-115">다양 한 요인에 따라 공격 정보를 분석 하 고 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="fda81-116">예시:</span><span class="sxs-lookup"><span data-stu-id="fda81-116">For example:</span></span>

- <span data-ttu-id="fda81-117">**공격 원본**: 원본 IP 주소 및 보낸 사람 전자 메일 도메인</span><span class="sxs-lookup"><span data-stu-id="fda81-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="fda81-118">**공격 메시지 속성**: 메시지의 콘텐츠, 스타일 및 톤입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="fda81-119">**받는 사람 공격**: 받는 사람 도메인, 받는 사람의 직무 기능(관리자, 임원 등), 회사 유형(대규모, 소규모, 공공 부문, 민간 부문 등) 및 산업.</span><span class="sxs-lookup"><span data-stu-id="fda81-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="fda81-120">**공격 페이로드**: 메시지에 있는 악의적인 링크, 첨부 파일 또는 기타 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="fda81-121">캠페인은 수명이 짧고 며칠, 주 또는 몇 개월 동안 활성 및 비활성 기간으로 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="fda81-122">특정 조직에 대해 캠페인을 시작할 수도 있고 조직이 여러 회사에 걸친 대규모 캠페인의 일부일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="fda81-123">캠페인 보기 보안 & 준수 센터</span><span class="sxs-lookup"><span data-stu-id="fda81-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="fda81-124">캠페인 보기는 **위협 관리** 캠페인의 [보안 & 준수 센터](https://protection.office.com) \> **Campaigns**또는에서 직접 제공 됩니다 <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="fda81-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![보안 및 규정 준수 센터의 캠페인 개요](../../media/campaigns-overview.png)

<span data-ttu-id="fda81-126">다음을 통해 캠페인을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="fda81-127">**위협 관리** \> **탐색기** \> **보기** \> **캠페인**</span><span class="sxs-lookup"><span data-stu-id="fda81-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="fda81-128">**위협 관리** \> **탐색기** \> **보기** \> **모든 전자 메일** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="fda81-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="fda81-129">**위협 관리** \> **탐색기** \> **보기** \> **피싱** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="fda81-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="fda81-130">**위협 관리** \> **탐색기** \> **보기** \> **맬웨어** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="fda81-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="fda81-131">캠페인 보기에 액세스 하려면 보안 & 준수 센터에서 **조직 관리**, **보안 관리자**또는 **보안 독자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="fda81-132">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fda81-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="fda81-133">캠페인 개요</span><span class="sxs-lookup"><span data-stu-id="fda81-133">Campaigns overview</span></span>

<span data-ttu-id="fda81-134">개요 페이지에는 모든 캠페인에 대 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="fda81-135">기본 **캠페인** 탭의 **캠페인 유형** 영역에는 하루 당 받는 사람 수를 보여 주는 막대 그래프가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="fda81-136">기본적으로 그래프에는 **피싱** 및 **맬웨어** 데이터가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="fda81-137">캠페인 데이터가 표시 되지 않으면 날짜 범위 또는 [필터](#filters-and-settings)를 변경해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="fda81-138">개요 페이지의 나머지 부분에는 **캠페인** 탭에 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="fda81-139">**이름**</span><span class="sxs-lookup"><span data-stu-id="fda81-139">**Name**</span></span>

- <span data-ttu-id="fda81-140">**샘플 제목**: 캠페인의 메시지 중 하나에 대한 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="fda81-141">캠페인의 모든 메시지에는 같은 주제가 포함 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="fda81-142">**대상**: 다음에 의해 계산 되는 백분율: (조직의 캠페인의 받는 사람 수)/(서비스의 모든 조직에서 캠페인에 있는 총 받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="fda81-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="fda81-143">이 값은 캠페인을 조직에서 구체적으로 지정 하는 수준 (값이 더 높음)과 서비스의 다른 조직에서 지시한 (낮은 값)에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="fda81-144">**Type**:이 값은 **피싱** 또는 **맬웨어**입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="fda81-145">**하위 유형**:이 값에는 캠페인에 대 한 자세한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="fda81-146">예시:</span><span class="sxs-lookup"><span data-stu-id="fda81-146">For example:</span></span>

  - <span data-ttu-id="fda81-147">**피싱**:이 캠페인에서 phished 되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="fda81-148">,,,, 등을 예로 들 `Microsoft` `365` `Unknown` `Outlook` `DocuSign` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="fda81-149">**맬웨어**: 또는 등이 `HTML/PHISH` `HTML/<MalwareFamilyName>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="fda81-150">사용 가능한 경우이 캠페인에 의해 phished 되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="fda81-151">검색이 ATP 기술에 따라 구동 되 면 접두사 **ATP-** 가 하위 형식 값에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="fda81-152">**받는 사람**: 이 캠페인을 대상으로 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="fda81-153">**Inboxed**:이 캠페인에서 메시지를 받은 사용자 수 (정크 메일 폴더로 배달 되지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="fda81-154">**클릭 한**경우: URL을 클릭 하거나 피싱 메시지의 첨부 파일을 연 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="fda81-155">**급여**: "**클릭 한**사람"으로 계산 되는 백분율을 클릭  /  **Inboxed**합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="fda81-156">이 값은 캠페인의 효율성 및 받는 사람이 메시지를 피싱 메일로 식별 하 고 페이로드 URL을 클릭 하지 못하도록 할지 여부를 나타내는 지표입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="fda81-157">이 값은 맬웨어 캠페인에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="fda81-158">**방문**함: 페이로드 웹 사이트에 실제로 적용 된 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="fda81-159">**클릭** 한 값이 있지만 안전한 링크가 웹 사이트에 대 한 액세스를 차단 하는 경우이 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="fda81-160">**캠페인 원본** 탭에는 세계 지도에 메시지 원본이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="fda81-161">필터 및 설정</span><span class="sxs-lookup"><span data-stu-id="fda81-161">Filters and settings</span></span>

<span data-ttu-id="fda81-162">캠페인 보기 페이지의 맨 위에는 특정 캠페인을 찾고 격리 하는 데 사용할 수 있는 몇 가지 필터 및 쿼리 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![캠페인 필터](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="fda81-164">시작할 수 있는 가장 기본적인 필터링은 시작 날짜/시간 및 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="fda81-165">보기를 추가로 필터링 하려면 **캠페인 유형** 단추를 클릭 하 고 원하는 항목을 선택한 다음 **새로 고침**을 클릭 하 여 여러 값 필터링을 통해 단일 속성을 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="fda81-166">사용 가능한 캠페인 속성은 다음 목록에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="fda81-167">기본</span><span class="sxs-lookup"><span data-stu-id="fda81-167">Basic</span></span>

  - <span data-ttu-id="fda81-168">**캠페인 유형**: **맬웨어** 또는 **피싱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="fda81-169">선택 항목을 지우면 둘 다를 선택 하는 것과 결과가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="fda81-170">**캠페인 이름**</span><span class="sxs-lookup"><span data-stu-id="fda81-170">**Campaign name**</span></span>
  - <span data-ttu-id="fda81-171">**캠페인 하위 유형**</span><span class="sxs-lookup"><span data-stu-id="fda81-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="fda81-172">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="fda81-172">**Sender**</span></span>
  - <span data-ttu-id="fda81-173">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="fda81-173">**Recipients**</span></span>
  - <span data-ttu-id="fda81-174">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="fda81-174">**Sender domain**</span></span>
  - <span data-ttu-id="fda81-175">**제목**</span><span class="sxs-lookup"><span data-stu-id="fda81-175">**Subject**</span></span>
  - <span data-ttu-id="fda81-176">**첨부 파일 이름**</span><span class="sxs-lookup"><span data-stu-id="fda81-176">**Attachment filename**</span></span>
  - <span data-ttu-id="fda81-177">**맬웨어 제품군**</span><span class="sxs-lookup"><span data-stu-id="fda81-177">**Malware family**</span></span>
  - <span data-ttu-id="fda81-178">**배달 작업**</span><span class="sxs-lookup"><span data-stu-id="fda81-178">**Delivery action**</span></span>
  - <span data-ttu-id="fda81-179">**검색 기술**</span><span class="sxs-lookup"><span data-stu-id="fda81-179">**Detection technology**</span></span>
  - <span data-ttu-id="fda81-180">**태그**</span><span class="sxs-lookup"><span data-stu-id="fda81-180">**Tags**</span></span>
  - <span data-ttu-id="fda81-181">**시스템 재정의**</span><span class="sxs-lookup"><span data-stu-id="fda81-181">**System overrides**</span></span>

- <span data-ttu-id="fda81-182">고급</span><span class="sxs-lookup"><span data-stu-id="fda81-182">Advanced</span></span>

  - <span data-ttu-id="fda81-183">**인터넷 메시지 id**: 메시지 헤더의 **메시지-id** 헤더 필드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="fda81-184">예를 들면 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 꺾쇠 괄호를 참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fda81-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="fda81-185">**네트워크 메시지 id**: 메시지 헤더의 **X-Exchange-네트워크-ID** 헤더 필드에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="fda81-186">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="fda81-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="fda81-187">**첨부 파일 sha256**: Windows에서 파일의 SHA256 해시 값을 찾으려면 명령 프롬프트에서 다음 명령을 실행 합니다 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="fda81-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="fda81-188">**클러스터 ID**</span><span class="sxs-lookup"><span data-stu-id="fda81-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="fda81-189">**경고 정책 ID**</span><span class="sxs-lookup"><span data-stu-id="fda81-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="fda81-190">URL</span><span class="sxs-lookup"><span data-stu-id="fda81-190">URLs</span></span>

  - <span data-ttu-id="fda81-191">**URL 도메인**</span><span class="sxs-lookup"><span data-stu-id="fda81-191">**URL domain**</span></span>
  - <span data-ttu-id="fda81-192">**URL 도메인 및 경로**</span><span class="sxs-lookup"><span data-stu-id="fda81-192">**URL domain and path**</span></span>
  - <span data-ttu-id="fda81-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="fda81-193">**URL**</span></span>
  - <span data-ttu-id="fda81-194">**URL 경로**</span><span class="sxs-lookup"><span data-stu-id="fda81-194">**URL path**</span></span>
  - <span data-ttu-id="fda81-195">**결과을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fda81-195">**Click verdict**</span></span>

<span data-ttu-id="fda81-196">여러 속성을 기준으로 필터링 하는 등 고급 필터링을 위해 **고급 필터** 단추를 클릭 하 여 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="fda81-197">동일한 캠페인 속성을 사용할 수 있지만 다음과 같은 기능이 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="fda81-198">**조건 추가** 를 클릭 하 여 여러 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="fda81-199">조건 사이에 **and** 또는 **or** 연산자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="fda81-200">조건 목록 아래쪽에 있는 **Condition 그룹** 항목을 선택 하 여 복잡 한 복합 조건을 형성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="fda81-201">작업이 끝나면 **쿼리** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="fda81-202">기본 필터나 고급 필터를 만든 후 **쿼리 저장** 또는 다른 **이름으로 저장**을 사용 하 여 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="fda81-203">나중에 캠페인 보기로 돌아가면 **저장 된 쿼리 설정을**클릭 하 여 저장 된 필터를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="fda81-204">그래프 또는 캠페인 목록을 내보내려면 **내보내기를** 클릭 하 고 **차트 데이터 내보내기** 또는 **캠페인 목록 내보내기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="fda81-205">Microsoft Defender ATP 구독을 사용 하는 경우에는 **Wdatp** 를 클릭 하 여 캠페인 정보를 MICROSOFT defender atp에 연결 하거나 연결을 끊을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="fda81-206">자세한 내용은 [Office 365 ATP를 Microsoft DEFENDER atp와 통합](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fda81-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="fda81-207">캠페인 세부 정보</span><span class="sxs-lookup"><span data-stu-id="fda81-207">Campaign details</span></span>

<span data-ttu-id="fda81-208">캠페인 이름을 클릭 하면 캠페인 세부 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="fda81-209">캠페인 정보</span><span class="sxs-lookup"><span data-stu-id="fda81-209">Campaign information</span></span>

<span data-ttu-id="fda81-210">캠페인 세부 정보 보기의 맨 위에서 다음과 같은 캠페인 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="fda81-211">**ID**: 고유한 캠페인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="fda81-212">**시작** 및 **종료**: 캠페인의 시작 날짜 및 종료 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="fda81-213">이러한 날짜는 개요 페이지에서 선택한 필터 날짜 보다 더 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="fda81-214">**영향**:이 섹션에는 선택한 날짜 범위 필터에 대 한 다음 데이터 또는 시간 표시 막대에서 선택한 날짜가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="fda81-215">총 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-215">The total number of recipients.</span></span>
  - <span data-ttu-id="fda81-216">"Inboxed" (즉, 정크 메일 폴더가 아니라 받은 편지 함으로 배달 됨)의 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="fda81-217">피싱 메시지의 URL 페이로드에서 클릭 한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="fda81-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="fda81-218">Howe 많은 사용자가 URL을 방문 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="fda81-219">**대상**: 다음에 의해 계산 되는 백분율: (조직의 캠페인의 받는 사람 수)/(서비스의 모든 조직에서 캠페인에 있는 총 받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="fda81-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="fda81-220">이 값은 캠페인의 전체 수명 보다 계산 되며 필터 날짜는 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="fda81-221">캠페인 활동의 대화형 시간 표시 막대: 타임 라인에는 캠페인의 전체 수명 동안의 활동이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="fda81-222">기본적으로 회색으로 표시 된 영역은 개요에서 선택한 날짜 범위 필터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="fda81-223">클릭 하 고 끌어 특정 시작점과 끝점을 선택 하 여 <u> **영향을 받는** 영역에 표시 되는 데이터와 다음 섹션에서 설명 하는 페이지의 나머지</u>부분을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="fda81-224">제목 표시줄의 캠페인 **기록** 다운로드 단추를 클릭 하 여 캠페인 ![ ](../../media/download-campaign-write-up-button.png) 세부 정보를 Word 문서 (기본적으로 CampaignReport.docx 명명 된)로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="fda81-225">이 문서에는 선택한 필터 날짜 뿐만 아니라 캠페인의 전체 수명에 대 한 세부 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![캠페인 정보](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="fda81-227">캠페인 흐름</span><span class="sxs-lookup"><span data-stu-id="fda81-227">Campaign flow</span></span>

<span data-ttu-id="fda81-228">캠페인 세부 정보 보기의 가운데에서 캠페인에 대 한 중요 한 세부 정보는 _Sankey_ 다이어그램 이라고 하는 가로 흐름도의 **흐름** 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="fda81-229">이러한 세부 정보는 캠페인의 요소와 조직에서 발생할 수 있는 영향을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="fda81-230">**흐름** 다이어그램에 표시 되는 정보는 이전 섹션에 설명 된 대로 시간 표시 막대에서 음영 처리 된 날짜 범위에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![사용자 URL 클릭을 포함하지 않는 캠페인 세부 정보](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="fda81-232">다이어그램에서 가로 밴드에 마우스를 올리면 관련 메시지 수(예: 특정 원본 IP의 메시지, 지정된 보낸 사람 도메인을 사용하는 원본 IP의 메시지)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="fda81-233">흐름도에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="fda81-234">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="fda81-234">**Sender IPs**</span></span>

- <span data-ttu-id="fda81-235">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="fda81-235">**Sender domains**</span></span>

- <span data-ttu-id="fda81-236">**Filter verdicts**: 이러한 값은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)에 설명 된 대로 사용 가능한 피싱 및 스팸 필터링 verdicts와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="fda81-237">사용 가능한 값은 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="fda81-238">**값**</span><span class="sxs-lookup"><span data-stu-id="fda81-238">**Value**</span></span>|<span data-ttu-id="fda81-239">**스팸 필터 결과**</span><span class="sxs-lookup"><span data-stu-id="fda81-239">**Spam filter verdict**</span></span>|<span data-ttu-id="fda81-240">**설명**</span><span class="sxs-lookup"><span data-stu-id="fda81-240">**Description**</span></span>|
  |<span data-ttu-id="fda81-241">**있도록**</span><span class="sxs-lookup"><span data-stu-id="fda81-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="fda81-242">스팸 필터링 (예: 전송 규칙이 라고도 하는 메일 흐름 규칙)에 의해 메시지가 스팸이 아닌 것으로 표시 되 고 필터링이 생략 되는 것으로 확인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="fda81-243">다른 이유로 인해 메시지는 스팸 필터링을 건너뛰었습니다 (예: 보낸 사람 및 받는 사람이 같은 조직에 있는 것 처럼 보이는 경우).</span><span class="sxs-lookup"><span data-stu-id="fda81-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="fda81-244">**수준**</span><span class="sxs-lookup"><span data-stu-id="fda81-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="fda81-245">메시지가 스팸 필터링 (예: 메일 흐름 규칙)을 통해 평가 되기 전에 스팸으로 표시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="fda81-246">**감지함**</span><span class="sxs-lookup"><span data-stu-id="fda81-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="fda81-247">메시지가 스팸 필터링에 의해 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="fda81-248">**검색 되지 않음**</span><span class="sxs-lookup"><span data-stu-id="fda81-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="fda81-249">메시지가 스팸 필터링에 의해 스팸으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="fda81-250">**해제할**</span><span class="sxs-lookup"><span data-stu-id="fda81-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="fda81-251">메시지가 격리에서 해제 되었기 때문에 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="fda81-252">**테 넌 트 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="fda81-253">스팸 방지 정책 설정 (예: 보낸 사람이 허용 된 보낸 사람 목록 또는 허용 도메인 목록에 있음) 때문에 메시지가 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="fda81-254">**테 넌 트 블록**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="fda81-255">스팸 방지 정책 설정으로 인해 메시지가 차단 되었습니다 (예: 보낸 사람이 허용 된 보낸 사람 목록이 나 허용 된 도메인 목록에 있음).</span><span class="sxs-lookup"><span data-stu-id="fda81-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="fda81-256">**사용자 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="fda81-257">보낸 사람이 Outlook의 사용자 수신 허용-보낸 사람 목록에 있기 때문에 메시지가 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="fda81-258">**사용자 차단**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="fda81-259">보낸 사람이 Outlook의 차단 된 보낸 사람 목록에 있기 때문에 스팸 필터링에 의해 메시지가 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="fda81-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="fda81-260">**ZAP**</span></span>|<span data-ttu-id="fda81-261">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fda81-261">n/a</span></span>|<span data-ttu-id="fda81-262">스팸 방지 정책 설정 (정크 메일 폴더로 이동 또는 격리 됨)에 따라 배달 된 메시지에 대해 [ZAP (자동 삭제)이](zero-hour-auto-purge.md) 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="fda81-263"><sup>\*</sup>허용 되는 메시지는 서비스에 의해 차단 되었을 가능성이 있으므로 스팸 방지 정책을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="fda81-264"><sup>\*\*</sup>스팸 방지 정책 메시지는 격리 되어야 하며 배달 되지는 않으므로 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="fda81-265">**전달 위치**: 사용자가 메시지에서 페이로드 URL을 클릭하지 않은 경우라도 (받은 편지함 또는 정크 메일 폴더로) 받는 사람에게 실제로 전달된 메시지를 조사하려 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="fda81-266">격리 됨에서 격리 된 메시지를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="fda81-267">자세한 내용은 [EOP에서 격리 된 전자 메일 메시지](quarantine-email-messages.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fda81-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="fda81-268">**폴더 삭제됨**</span><span class="sxs-lookup"><span data-stu-id="fda81-268">**Deleted folder**</span></span>
  - <span data-ttu-id="fda81-269">**끊김**</span><span class="sxs-lookup"><span data-stu-id="fda81-269">**Dropped**</span></span>
  - <span data-ttu-id="fda81-270">**외부**: 받는 사람이 하이브리드 환경의 온-프레미스 전자 메일 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="fda81-271">**실패**</span><span class="sxs-lookup"><span data-stu-id="fda81-271">**Failed**</span></span>
  - <span data-ttu-id="fda81-272">**받습니다**</span><span class="sxs-lookup"><span data-stu-id="fda81-272">**Forwarded**</span></span>
  - <span data-ttu-id="fda81-273">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="fda81-273">**Inbox**</span></span>
  - <span data-ttu-id="fda81-274">**정크 메일 폴더**</span><span class="sxs-lookup"><span data-stu-id="fda81-274">**Junk folder**</span></span>
  - <span data-ttu-id="fda81-275">**격리**</span><span class="sxs-lookup"><span data-stu-id="fda81-275">**Quarantine**</span></span>
  - <span data-ttu-id="fda81-276">**알 수 없음**</span><span class="sxs-lookup"><span data-stu-id="fda81-276">**Unknown**</span></span>

- <span data-ttu-id="fda81-277">**URL 클릭**: 다음 섹션에서이에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="fda81-278">10 개 보다 많은 항목이 포함 된 모든 계층에서 상위 10 개 항목이 표시 되 고 나머지는 **다른**항목에 함께 번들 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="fda81-279">URL 클릭</span><span class="sxs-lookup"><span data-stu-id="fda81-279">URL clicks</span></span>

<span data-ttu-id="fda81-280">피싱 메시지가 받는 사람 (받은 편지함 또는 정크 메일 폴더)에 배달 되 면 항상 사용자가 페이로드 URL을 클릭할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="fda81-281">전달 된 메시지에서 URL을 클릭 하는 것은 성공적인를 측정 하는 것은 아니지만, 처음에는 피싱 메시지가 사서함에 배달 된 이유를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="fda81-282">사용자가 피싱 메시지에서 페이로드 URL을 클릭 하면 해당 작업이 캠페인 세부 정보 보기에 있는 다이어그램의 **URL 클릭** 영역에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="fda81-283">**있도록**</span><span class="sxs-lookup"><span data-stu-id="fda81-283">**Allowed**</span></span>

- <span data-ttu-id="fda81-284">**Blockpage**: 받는 사람이 페이로드 URL을 클릭 했지만, 악의적인 웹 사이트에 대 한 액세스 권한이 조직의 [ATP 안전한 링크](atp-safe-links.md) 정책에 의해 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="fda81-285">**Blockpageoverride**: 받는 사람이 메시지의 페이로드 URL을 클릭 했을 때 ATP 안전한 링크가 중지 하려고 했지만 블록을 재정의할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="fda81-286">안전한 링크 [정책을](set-up-atp-safe-links-policies.md) 조사 하 여 사용자가 안전한 링크 결과를 재정의 하 고 악성 웹 사이트를 계속 사용할 수 있는 이유를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="fda81-287">**PendingDetonationPage**: ATP 안전한 첨부 파일은 가상 컴퓨터 환경에서 페이로드 URL을 열고 어떤 일이 진행 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="fda81-288">**PendingDetonationPageOverride**: 받는 사람이 페이로드 샌드 박싱 프로세스를 재정의 하 고 결과를 기다리지 않고 URL을 열 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="fda81-289">탭</span><span class="sxs-lookup"><span data-stu-id="fda81-289">Tabs</span></span>

<span data-ttu-id="fda81-290">캠페인 세부 정보 보기의 탭에서는 캠페인을 상세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="fda81-291">탭에 표시 되는 정보는 [캠페인 정보](#campaign-information) 섹션에 설명 된 대로 시간 표시 막대에서 음영 처리 된 날짜 범위에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="fda81-292">**URL 클릭**: 사용자가 피싱 메시지에서 페이로드 URL을 클릭 하지 않은 경우이 섹션은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="fda81-293">사용자가 URL을 클릭할 수 있는 경우 다음 값이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="fda81-294">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="fda81-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="fda81-296">**클릭 시간**</span><span class="sxs-lookup"><span data-stu-id="fda81-296">**Click time**</span></span>
  - <span data-ttu-id="fda81-297">**결과을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fda81-297">**Click verdict**</span></span>

- <span data-ttu-id="fda81-298">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="fda81-298">**Sender IPs**</span></span>

  - <span data-ttu-id="fda81-299">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="fda81-300">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="fda81-300">**Total count**</span></span>
  - <span data-ttu-id="fda81-301">**박스형**</span><span class="sxs-lookup"><span data-stu-id="fda81-301">**Inboxed**</span></span>
  - <span data-ttu-id="fda81-302">**박스형 아님**</span><span class="sxs-lookup"><span data-stu-id="fda81-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="fda81-303">**Spf 통과**: [Spf (sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)에 의해 보낸 사람이 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="fda81-304">SPF 유효성 검사를 통과 하지 못하는 보낸 사람은 보낸 사람이 인증 되지 않았거나 메시지가 합법적인 보낸 사람에 게 스푸핑 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="fda81-305">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="fda81-305">**Senders**</span></span>

  - <span data-ttu-id="fda81-306">**Sender**: 사용자가 전자 메일 클라이언트에 표시 하는 보낸 사람: 전자 메일 주소가 아닐 수도 있는,이 주소는 SMTP MAIL FROM 명령에 있는 실제 발신자 주소로,</span><span class="sxs-lookup"><span data-stu-id="fda81-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="fda81-307">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="fda81-307">**Total count**</span></span>
  - <span data-ttu-id="fda81-308">**박스형**</span><span class="sxs-lookup"><span data-stu-id="fda81-308">**Inboxed**</span></span>
  - <span data-ttu-id="fda81-309">**박스형 아님**</span><span class="sxs-lookup"><span data-stu-id="fda81-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="fda81-310">**Dkim 통과**: 보낸 사람이 [Dkim (도메인 키 확인 메일)](support-for-validation-of-dkim-signed-messages.md)에 의해 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="fda81-311">DKIM 유효성 검사를 통과 하지 않은 보낸 사람은 보낸 사람이 인증 되지 않았거나 메시지가 합법적인 보낸 사람에 게 스푸핑 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="fda81-312">**DMARC 통과**: 보낸 사람이 [도메인 기반 메시지 인증, 보고 및 적합성 (DMARC)](use-dmarc-to-validate-email.md)을 통해 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="fda81-313">DMARC 유효성 검사를 통과 하지 않은 보낸 사람은 보낸 사람이 인증 되지 않았거나 메시지가 합법적인 보낸 사람에 게 위장 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="fda81-314">**첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="fda81-314">**Attachments**</span></span>

  - <span data-ttu-id="fda81-315">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="fda81-315">**Filename**</span></span>
  - <span data-ttu-id="fda81-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="fda81-316">**SHA256**</span></span>
  - <span data-ttu-id="fda81-317">**맬웨어 제품군**</span><span class="sxs-lookup"><span data-stu-id="fda81-317">**Malware family**</span></span>
  - <span data-ttu-id="fda81-318">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="fda81-318">**Total count**</span></span>

- <span data-ttu-id="fda81-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="fda81-319">**URL**</span></span>

  - <span data-ttu-id="fda81-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda81-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="fda81-321">**합계**</span><span class="sxs-lookup"><span data-stu-id="fda81-321">**Total Count**</span></span>

<span data-ttu-id="fda81-322"><sup>\*</sup>이 값을 클릭하면 캠페인 세부 정보 보기 위쪽에 지정된 항목(사용자, URL 등)에 대한 자세한 정보가 포함된 플라이 아웃이 새로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="fda81-323">캠페인 세부 정보 보기로 돌아가려면 새 플라이 아웃에서 **완료**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="fda81-324">버튼</span><span class="sxs-lookup"><span data-stu-id="fda81-324">Buttons</span></span>

<span data-ttu-id="fda81-325">캠페인 세부 정보 보기의 버튼을 통해 위협 탐색기 기능을 사용하여 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="fda81-326">**캠페인 탐색**: **캠페인 ID** 값을 검색 필터로 사용하여 새로운 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="fda81-327">**Inboxed 메시지 살펴보기**: **캠페인 ID** 및 **배달 위치: 받은 편지함** 을 검색 필터로 사용 하 여 새 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fda81-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
