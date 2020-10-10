---
title: Office 365 ATP 계획의 캠페인 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
description: Office 365 Advanced Threat Protection의 캠페인 보기에 대해 알아보세요.
ms.openlocfilehash: 333e9c03cea9f16393169396ca016b09fd6a359d
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413977"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="7528a-103">Office 365 ATP의 캠페인보기</span><span class="sxs-lookup"><span data-stu-id="7528a-103">Campaign Views in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7528a-104">캠페인 보기는 ATP (Advanced Threat Protection) 계획 2의 기능입니다 (예: Microsoft 365 E5 또는 ATP 요금제 2 추가 기능이 있는 조직).</span><span class="sxs-lookup"><span data-stu-id="7528a-104">Campaign Views is a feature in Advanced Threat Protection (ATP) Plan 2 (for example Microsoft 365 E5 or organizations with an ATP Plan 2 add-on).</span></span> <span data-ttu-id="7528a-105">보안 & 준수 센터의 캠페인 보기는 서비스의 피싱 공격을 식별 하 고 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="7528a-106">캠페인 보기를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="7528a-107">피싱 공격을 효과적으로 조사하고 이에 대처합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="7528a-108">공격의 범위를 더 잘 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="7528a-109">의사 결정자에게 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-109">Show value to decision makers.</span></span>

<span data-ttu-id="7528a-110">캠페인 보기를 그 누구보다 빠르고 완벽하게 공격의 전체적인 상황을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="7528a-111">캠페인이란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="7528a-111">What is a campaign?</span></span>

<span data-ttu-id="7528a-112">캠페인은 하나 이상의 조직에 대해 조율된 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="7528a-113">자격 증명 및 회사 데이터를 도용 하는 전자 메일 공격은 대규모이 고 lucrative 업계입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="7528a-114">공격을 중지 하기 위해 기술이 증가 함에 따라 공격자는 성공적인 성공을 위해 해당 메서드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="7528a-115">Microsoft는 캠페인을 식별 하는 데 도움이 되도록 전체 서비스에서 방대한 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="7528a-116">다양 한 요인에 따라 공격 정보를 분석 하 고 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="7528a-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-117">For example:</span></span>

- <span data-ttu-id="7528a-118">**공격 원본**: 원본 IP 주소 및 보낸 사람 전자 메일 도메인</span><span class="sxs-lookup"><span data-stu-id="7528a-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="7528a-119">**메시지 속성**: 메시지의 콘텐츠, 스타일 및 톤입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="7528a-120">**메시지 받는 사람**: 받는 사람이 연결 되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="7528a-121">예를 들어 받는 사람 도메인, 받는 사람 작업 기능 (관리자 및 임원 등), 회사 유형 (대규모, 소형, 공용, 개인 등), 산업 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="7528a-122">**공격 페이로드**: 메시지에 있는 악의적인 링크, 첨부 파일 또는 기타 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="7528a-123">캠페인은 수명이 짧고 며칠, 주 또는 몇 개월 동안 활성 및 비활성 기간으로 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="7528a-124">특정 조직에 대해 캠페인을 시작할 수도 있고 조직이 여러 회사에 걸친 대규모 캠페인의 일부일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="7528a-125">보안 & 준수 센터의 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="7528a-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="7528a-126">캠페인 보기는 **위협 관리** 캠페인의 [보안 & 준수 센터](https://protection.office.com) \> **Campaigns**또는에서 직접 제공 됩니다 <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="7528a-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![보안 및 규정 준수 센터의 캠페인 개요](../../media/campaigns-overview.png)

<span data-ttu-id="7528a-128">다음을 통해 캠페인을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="7528a-129">**위협 관리** \> **탐색기** \> **보기** \> **캠페인**</span><span class="sxs-lookup"><span data-stu-id="7528a-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="7528a-130">**위협 관리** \> **탐색기** \> **보기** \> **모든 전자 메일** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="7528a-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="7528a-131">**위협 관리** \> **탐색기** \> **보기** \> **피싱** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="7528a-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="7528a-132">**위협 관리** \> **탐색기** \> **보기** \> **맬웨어** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="7528a-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="7528a-133">캠페인 보기에 액세스 하려면 보안 & 준수 센터에서 **조직 관리**, **보안 관리자**또는 **보안 독자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="7528a-134">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7528a-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="7528a-135">캠페인 개요</span><span class="sxs-lookup"><span data-stu-id="7528a-135">Campaigns overview</span></span>

<span data-ttu-id="7528a-136">개요 페이지에는 모든 캠페인에 대 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="7528a-137">기본 **캠페인** 탭의 **캠페인 유형** 영역에는 하루 당 받는 사람 수를 보여 주는 막대 그래프가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="7528a-138">기본적으로 그래프에는 **피싱** 및 **맬웨어** 데이터가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="7528a-139">캠페인 데이터가 표시 되지 않으면 날짜 범위 또는 [필터](#filters-and-settings)를 변경해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="7528a-140">개요 페이지의 나머지 부분에는 **캠페인** 탭에 다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="7528a-141">**이름**</span><span class="sxs-lookup"><span data-stu-id="7528a-141">**Name**</span></span>

- <span data-ttu-id="7528a-142">**샘플 제목**: 캠페인의 메시지 중 하나에 대한 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="7528a-143">캠페인의 모든 메시지에는 같은 주제가 포함 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="7528a-144">**대상**: 다음에 의해 계산 되는 백분율: (조직의 캠페인의 받는 사람 수)/(서비스의 모든 조직에서 캠페인에 있는 총 받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="7528a-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="7528a-145">이 값은 캠페인을 조직 (더 높은 값)과 서비스의 다른 조직에서 지정 된 수준 (낮은 값)과 비교 하 여 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="7528a-146">**Type**:이 값은 **피싱** 또는 **맬웨어**입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="7528a-147">**하위 유형**:이 값에는 캠페인에 대 한 자세한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="7528a-148">예제:</span><span class="sxs-lookup"><span data-stu-id="7528a-148">For example:</span></span>

  - <span data-ttu-id="7528a-149">**피싱**:이 캠페인에서 phished 되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="7528a-150">,,,, 등을 예로 들 `Microsoft` `365` `Unknown` `Outlook` `DocuSign` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="7528a-151">**맬웨어**: 또는 등이 `HTML/PHISH` `HTML/<MalwareFamilyName>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="7528a-152">사용 가능한 경우이 캠페인에 의해 phished 되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="7528a-153">검색이 ATP 기술에 따라 구동 되 면 접두사 **ATP-** 가 하위 형식 값에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-153">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="7528a-154">**받는 사람**: 이 캠페인을 대상으로 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="7528a-155">**Inboxed**:이 캠페인에서 메시지를 받은 사용자 수 (정크 메일 폴더로 배달 되지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="7528a-156">**클릭 한**경우: URL을 클릭 하거나 피싱 메시지의 첨부 파일을 연 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="7528a-157">**급여**: "**클릭 한**사람"으로 계산 되는 백분율을 클릭  /  **Inboxed**합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="7528a-158">이 값은 캠페인의 효과에 대 한 지표입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="7528a-159">즉, 받는 사람이 메시지를 피싱 메일로 식별 하 고 페이로드 URL을 클릭 하지 않은 경우에도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="7528a-160">맬웨어 캠페인에서는 **클릭 속도가** 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="7528a-161">**방문**함: 페이로드 웹 사이트에 실제로 적용 된 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="7528a-162">**클릭** 한 값이 있지만 안전한 링크가 웹 사이트에 대 한 액세스를 차단 하는 경우이 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="7528a-163">**캠페인 원본** 탭에는 세계 지도에 메시지 원본이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="7528a-164">필터 및 설정</span><span class="sxs-lookup"><span data-stu-id="7528a-164">Filters and settings</span></span>

<span data-ttu-id="7528a-165">캠페인 보기 페이지의 맨 위에는 특정 캠페인을 찾고 격리 하는 데 사용할 수 있는 몇 가지 필터 및 쿼리 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![캠페인 필터](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="7528a-167">시작할 수 있는 가장 기본적인 필터링은 시작 날짜/시간 및 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="7528a-168">보기를 추가로 필터링 하려면 **캠페인 유형** 단추를 클릭 하 고 원하는 항목을 선택한 다음 **새로 고침**을 클릭 하 여 여러 값 필터링을 통해 단일 속성을 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="7528a-169">사용 가능한 캠페인 속성은 다음 목록에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-169">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="7528a-170">Basic</span><span class="sxs-lookup"><span data-stu-id="7528a-170">Basic</span></span>

  - <span data-ttu-id="7528a-171">**캠페인 유형**: **맬웨어** 또는 **피싱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="7528a-172">선택 항목을 지우면 둘 다를 선택 하는 것과 결과가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="7528a-173">**캠페인 이름**</span><span class="sxs-lookup"><span data-stu-id="7528a-173">**Campaign name**</span></span>
  - <span data-ttu-id="7528a-174">**캠페인 하위 유형**</span><span class="sxs-lookup"><span data-stu-id="7528a-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="7528a-175">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="7528a-175">**Sender**</span></span>
  - <span data-ttu-id="7528a-176">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="7528a-176">**Recipients**</span></span>
  - <span data-ttu-id="7528a-177">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="7528a-177">**Sender domain**</span></span>
  - <span data-ttu-id="7528a-178">**제목**</span><span class="sxs-lookup"><span data-stu-id="7528a-178">**Subject**</span></span>
  - <span data-ttu-id="7528a-179">**첨부 파일 이름**</span><span class="sxs-lookup"><span data-stu-id="7528a-179">**Attachment filename**</span></span>
  - <span data-ttu-id="7528a-180">**맬웨어 제품군**</span><span class="sxs-lookup"><span data-stu-id="7528a-180">**Malware family**</span></span>
  - <span data-ttu-id="7528a-181">**배달 작업**</span><span class="sxs-lookup"><span data-stu-id="7528a-181">**Delivery action**</span></span>
  - <span data-ttu-id="7528a-182">**검색 기술**</span><span class="sxs-lookup"><span data-stu-id="7528a-182">**Detection technology**</span></span>
  - <span data-ttu-id="7528a-183">**태그**</span><span class="sxs-lookup"><span data-stu-id="7528a-183">**Tags**</span></span>
  - <span data-ttu-id="7528a-184">**시스템 재정의**</span><span class="sxs-lookup"><span data-stu-id="7528a-184">**System overrides**</span></span>

- <span data-ttu-id="7528a-185">고급</span><span class="sxs-lookup"><span data-stu-id="7528a-185">Advanced</span></span>

  - <span data-ttu-id="7528a-186">**인터넷 메시지 id**: 메시지 헤더의 **메시지-id** 헤더 필드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-186">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="7528a-187">예를 들면 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 꺾쇠 괄호를 참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7528a-187">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="7528a-188">**네트워크 메시지 id**: 메시지 헤더의 **X-Exchange-네트워크-ID** 헤더 필드에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-188">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="7528a-189">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="7528a-189">**Sender IP**</span></span>
  
  - <span data-ttu-id="7528a-190">**첨부 파일 sha256**: Windows에서 파일의 SHA256 해시 값을 찾으려면 명령 프롬프트에서 다음 명령을 실행 합니다 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="7528a-190">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="7528a-191">**클러스터 ID**</span><span class="sxs-lookup"><span data-stu-id="7528a-191">**Cluster ID**</span></span>
  
  - <span data-ttu-id="7528a-192">**경고 정책 ID**</span><span class="sxs-lookup"><span data-stu-id="7528a-192">**Alert Policy ID**</span></span>

- <span data-ttu-id="7528a-193">URL</span><span class="sxs-lookup"><span data-stu-id="7528a-193">URLs</span></span>

  - <span data-ttu-id="7528a-194">**URL 도메인**</span><span class="sxs-lookup"><span data-stu-id="7528a-194">**URL domain**</span></span>
  - <span data-ttu-id="7528a-195">**URL 도메인 및 경로**</span><span class="sxs-lookup"><span data-stu-id="7528a-195">**URL domain and path**</span></span>
  - <span data-ttu-id="7528a-196">**URL**</span><span class="sxs-lookup"><span data-stu-id="7528a-196">**URL**</span></span>
  - <span data-ttu-id="7528a-197">**URL 경로**</span><span class="sxs-lookup"><span data-stu-id="7528a-197">**URL path**</span></span>
  - <span data-ttu-id="7528a-198">**결과을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7528a-198">**Click verdict**</span></span>

<span data-ttu-id="7528a-199">여러 속성을 기준으로 필터링 하는 등 고급 필터링을 위해 **고급 필터** 단추를 클릭 하 여 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-199">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="7528a-200">동일한 캠페인 속성을 사용할 수 있지만 다음과 같은 기능이 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-200">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="7528a-201">**조건 추가** 를 클릭 하 여 여러 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-201">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="7528a-202">조건 사이에 **and** 또는 **or** 연산자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-202">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="7528a-203">조건 목록 아래쪽에 있는 **Condition 그룹** 항목을 선택 하 여 복잡 한 복합 조건을 형성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-203">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="7528a-204">작업이 끝나면 **쿼리** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-204">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="7528a-205">기본 필터나 고급 필터를 만든 후 **쿼리 저장** 또는 다른 **이름으로 저장**을 사용 하 여 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-205">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="7528a-206">나중에 캠페인 보기로 돌아가면 **저장 된 쿼리 설정을**클릭 하 여 저장 된 필터를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-206">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="7528a-207">그래프 또는 캠페인 목록을 내보내려면 **내보내기를** 클릭 하 고 **차트 데이터 내보내기** 또는 **캠페인 목록 내보내기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-207">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="7528a-208">Microsoft Defender ATP 구독을 사용 하는 경우에는 **Wdatp** 를 클릭 하 여 캠페인 정보를 MICROSOFT defender atp에 연결 하거나 연결을 끊을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-208">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="7528a-209">자세한 내용은 [Office 365 ATP를 Microsoft DEFENDER atp와 통합](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7528a-209">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="7528a-210">캠페인 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7528a-210">Campaign details</span></span>

<span data-ttu-id="7528a-211">캠페인 이름을 클릭 하면 캠페인 세부 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-211">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="7528a-212">캠페인 정보</span><span class="sxs-lookup"><span data-stu-id="7528a-212">Campaign information</span></span>

<span data-ttu-id="7528a-213">캠페인 세부 정보 보기의 맨 위에서 다음과 같은 캠페인 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-213">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="7528a-214">**ID**: 고유한 캠페인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-214">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="7528a-215">**시작** 및 **종료**: 캠페인의 시작 날짜 및 종료 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-215">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="7528a-216">이러한 날짜는 개요 페이지에서 선택한 필터 날짜 보다 더 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-216">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="7528a-217">**영향**:이 섹션에는 선택한 날짜 범위 필터에 대 한 다음 데이터 또는 시간 표시 막대에서 선택한 날짜가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-217">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="7528a-218">총 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-218">The total number of recipients.</span></span>
  - <span data-ttu-id="7528a-219">"Inboxed" (즉, 정크 메일 폴더가 아니라 받은 편지 함으로 배달 됨)의 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-219">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="7528a-220">피싱 메시지의 URL 페이로드에서 클릭 한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="7528a-220">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="7528a-221">Howe 많은 사용자가 URL을 방문 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-221">Howe many users visited the URL.</span></span>

- <span data-ttu-id="7528a-222">**대상**: 다음에 의해 계산 되는 백분율: (조직의 캠페인의 받는 사람 수)/(서비스의 모든 조직에서 캠페인에 있는 총 받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="7528a-222">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="7528a-223">이 값은 캠페인의 전체 수명에 따라 계산 되며 날짜 필터에 따라 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-223">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="7528a-224">캠페인 활동의 대화형 시간 표시 막대: 타임 라인에는 캠페인의 전체 수명 동안의 활동이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-224">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="7528a-225">기본적으로 회색으로 표시 된 영역은 개요에서 선택한 날짜 범위 필터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-225">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="7528a-226">클릭 하 고 끌어 특정 시작점과 끝점을 선택 하 여 <u> **영향을 받는** 영역에 표시 되는 데이터와 다음 섹션에서 설명 하는 페이지의 나머지</u>부분을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-226">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="7528a-227">제목 표시줄의 캠페인 **기록** 다운로드 단추를 클릭 하 여 캠페인 ![ ](../../media/download-campaign-write-up-button.png) 세부 정보를 Word 문서 (기본적으로 CampaignReport.docx 명명 된)로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-227">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="7528a-228">이 다운로드에는 선택한 필터 날짜 뿐만 아니라 캠페인의 전체 수명에 대 한 세부 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-228">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![캠페인 정보](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="7528a-230">캠페인 흐름</span><span class="sxs-lookup"><span data-stu-id="7528a-230">Campaign flow</span></span>

<span data-ttu-id="7528a-231">캠페인 세부 정보 보기의 가운데에서 캠페인에 대 한 중요 한 세부 정보는 _Sankey_ 다이어그램 이라고 하는 가로 흐름도의 **흐름** 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-231">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="7528a-232">이러한 세부 정보는 캠페인의 요소와 조직에서 발생할 수 있는 영향을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-232">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="7528a-233">**흐름** 다이어그램에 표시 되는 정보는 이전 섹션에 설명 된 대로 시간 표시 막대에서 음영 처리 된 날짜 범위에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-233">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![사용자 URL 클릭을 포함하지 않는 캠페인 세부 정보](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="7528a-235">다이어그램에서 가로 밴드에 마우스를 올리면 관련 메시지 수(예: 특정 원본 IP의 메시지, 지정된 보낸 사람 도메인을 사용하는 원본 IP의 메시지)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-235">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="7528a-236">흐름도에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-236">The diagram contains the following information:</span></span>

- <span data-ttu-id="7528a-237">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="7528a-237">**Sender IPs**</span></span>

- <span data-ttu-id="7528a-238">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="7528a-238">**Sender domains**</span></span>

- <span data-ttu-id="7528a-239">**Filter verdicts**: 결과 값은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)에 설명 된 대로 사용 가능한 피싱 및 스팸 필터링 verdicts와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-239">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="7528a-240">사용 가능한 값은 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-240">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="7528a-241">값</span><span class="sxs-lookup"><span data-stu-id="7528a-241">Value</span></span>|<span data-ttu-id="7528a-242">스팸 필터 결과</span><span class="sxs-lookup"><span data-stu-id="7528a-242">Spam filter verdict</span></span>|<span data-ttu-id="7528a-243">설명</span><span class="sxs-lookup"><span data-stu-id="7528a-243">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="7528a-244">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="7528a-244">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="7528a-245">메시지가 스팸으로 표시 되지 않거나 스팸 필터링을 통해 평가 되기 전에 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-245">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="7528a-246">예를 들어 메시지는 메일 흐름 규칙 (전송 규칙이 라고도 함)에 의해 스팸으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-246">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span><br/><br/><span data-ttu-id="7528a-247">다른 이유로 인해 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-247">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="7528a-248">예를 들어 보낸 사람 및 받는 사람은 같은 조직에 있는 것 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-248">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="7528a-249">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="7528a-249">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="7528a-250">스팸 필터링을 통해 메시지가 평가 되기 전에 스팸으로 표시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-250">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="7528a-251">예를 들어 메일 흐름 규칙을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-251">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="7528a-252">**감지함**</span><span class="sxs-lookup"><span data-stu-id="7528a-252">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="7528a-253">메시지가 스팸 필터링에 의해 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-253">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="7528a-254">**검색 되지 않음**</span><span class="sxs-lookup"><span data-stu-id="7528a-254">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="7528a-255">메시지가 스팸 필터링에 의해 스팸으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-255">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="7528a-256">**해제할**</span><span class="sxs-lookup"><span data-stu-id="7528a-256">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="7528a-257">메시지가 격리에서 해제 되었기 때문에 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-257">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="7528a-258">**테 넌 트 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-258">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="7528a-259">스팸 방지 정책 설정으로 인해 메시지에서 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-259">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="7528a-260">예를 들어 보낸 사람이 허용 된 보낸 사람 목록 또는 허용 도메인 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-260">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="7528a-261">**테 넌 트 블록**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-261">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="7528a-262">스팸 방지 정책의 설정 때문에 스팸 필터링에 의해 메시지가 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-262">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="7528a-263">예를 들어 보낸 사람이 허용 된 보낸 사람 목록 또는 허용 도메인 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-263">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="7528a-264">**사용자 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-264">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="7528a-265">보낸 사람이 사용자의 수신 허용-보낸 사람 목록에 있기 때문에 메시지가 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-265">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="7528a-266">**사용자 차단**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-266">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="7528a-267">보낸 사람이 사용자의 차단 된 보낸 사람 목록에 있기 때문에 스팸 필터링에 의해 메시지가 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-267">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="7528a-268">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="7528a-268">**ZAP**</span></span>|<span data-ttu-id="7528a-269">해당 없음</span><span class="sxs-lookup"><span data-stu-id="7528a-269">n/a</span></span>|<span data-ttu-id="7528a-270">[자동 삭제 (ZAP)](zero-hour-auto-purge.md) 는 배달 된 메시지를 정크 메일 폴더 또는 격리로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-270">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="7528a-271">스팸 방지 정책에서 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-271">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="7528a-272"><sup>\*</sup> 허용 되는 메시지는 서비스에 의해 차단 되었을 가능성이 있으므로 스팸 방지 정책을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-272"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="7528a-273"><sup>\*\*</sup> 스팸 방지 정책 메시지는 격리 되어야 하며 배달 되지는 않으므로 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-273"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="7528a-274">**배달 위치**: 사용자가 메시지에서 페이로드 URL을 클릭 하지 않은 경우에도 받는 사람에 게 배달 된 메시지 (받은 편지함 또는 정크 메일 폴더)를 조사 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-274">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="7528a-275">격리 됨에서 격리 된 메시지를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-275">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="7528a-276">자세한 내용은 [EOP에서 격리 된 전자 메일 메시지](quarantine-email-messages.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7528a-276">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="7528a-277">**폴더 삭제됨**</span><span class="sxs-lookup"><span data-stu-id="7528a-277">**Deleted folder**</span></span>
  - <span data-ttu-id="7528a-278">**끊김**</span><span class="sxs-lookup"><span data-stu-id="7528a-278">**Dropped**</span></span>
  - <span data-ttu-id="7528a-279">**외부**: 받는 사람이 하이브리드 환경의 온-프레미스 전자 메일 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-279">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="7528a-280">**실패**</span><span class="sxs-lookup"><span data-stu-id="7528a-280">**Failed**</span></span>
  - <span data-ttu-id="7528a-281">**받습니다**</span><span class="sxs-lookup"><span data-stu-id="7528a-281">**Forwarded**</span></span>
  - <span data-ttu-id="7528a-282">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="7528a-282">**Inbox**</span></span>
  - <span data-ttu-id="7528a-283">**정크 메일 폴더**</span><span class="sxs-lookup"><span data-stu-id="7528a-283">**Junk folder**</span></span>
  - <span data-ttu-id="7528a-284">**격리**</span><span class="sxs-lookup"><span data-stu-id="7528a-284">**Quarantine**</span></span>
  - <span data-ttu-id="7528a-285">**알 수 없음**</span><span class="sxs-lookup"><span data-stu-id="7528a-285">**Unknown**</span></span>

- <span data-ttu-id="7528a-286">**URL 클릭**: 다음 섹션에서는 이러한 값에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-286">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="7528a-287">10 개 보다 많은 항목이 포함 된 모든 계층에서 상위 10 개 항목이 표시 되 고 나머지는 **다른**항목에 함께 번들 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-287">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="7528a-288">URL 클릭</span><span class="sxs-lookup"><span data-stu-id="7528a-288">URL clicks</span></span>

<span data-ttu-id="7528a-289">피싱 메시지가 받는 사람의 받은 편지함 또는 정크 메일 폴더로 배달 되 면 항상 사용자가 페이로드 URL을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-289">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="7528a-290">URL을 클릭 하는 것은 성공적인를 측정 하는 것이 아니지만 피싱 메시지가 사서함에 배달 되는 이유를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-290">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="7528a-291">사용자가 피싱 메시지에서 페이로드 URL을 클릭 하면 해당 작업이 캠페인 세부 정보 보기에 있는 다이어그램의 **URL 클릭** 영역에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-291">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="7528a-292">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="7528a-292">**Allowed**</span></span>

- <span data-ttu-id="7528a-293">**Blockpage**: 받는 사람이 페이로드 URL을 클릭 했지만 해당 사용자의 악의적인 웹 사이트에 대 한 액세스 권한이 조직의 [안전한 링크](atp-safe-links.md) 정책에 의해 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-293">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>

- <span data-ttu-id="7528a-294">**Blockpageoverride**: 받는 사람이 메시지의 페이로드 URL을 클릭 했지만 안전한 링크가 중지 하려고 했지만 차단 된 링크를 무시할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-294">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="7528a-295">[안전한 링크 정책을](set-up-atp-safe-links-policies.md) 조사 하 여 사용자가 안전한 링크 결과를 재정의 하 고 악성 웹 사이트로 계속 이동할 수 있는 이유를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-295">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="7528a-296">**PendingDetonationPage**: OFFICE 365 ATP의 안전한 첨부 파일은 가상 컴퓨터 환경에서 페이로드 URL을 열고 조사 하는 과정을 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-296">**PendingDetonationPage**: Safe Attachments in Office 365 ATP is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>

- <span data-ttu-id="7528a-297">**PendingDetonationPageOverride**: 받는 사람이 페이로드 샌드 박싱 프로세스를 재정의 하 고 결과를 기다리지 않고 URL을 열 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-297">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="7528a-298">탭</span><span class="sxs-lookup"><span data-stu-id="7528a-298">Tabs</span></span>

<span data-ttu-id="7528a-299">캠페인 세부 정보 보기의 탭에서는 캠페인을 상세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-299">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="7528a-300">탭에 표시 되는 정보는 [캠페인 정보](#campaign-information) 섹션에 설명 된 대로 시간 표시 막대에서 음영 처리 된 날짜 범위에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-300">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="7528a-301">**URL 클릭**: 사용자가 메시지에서 페이로드 URL을 클릭 하지 않은 경우이 섹션은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-301">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="7528a-302">사용자가 URL을 클릭할 수 있는 경우 다음 값이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-302">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="7528a-303">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-303">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="7528a-304">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-304">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="7528a-305">**클릭 시간**</span><span class="sxs-lookup"><span data-stu-id="7528a-305">**Click time**</span></span>
  - <span data-ttu-id="7528a-306">**결과을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7528a-306">**Click verdict**</span></span>

- <span data-ttu-id="7528a-307">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="7528a-307">**Sender IPs**</span></span>

  - <span data-ttu-id="7528a-308">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-308">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="7528a-309">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="7528a-309">**Total count**</span></span>
  - <span data-ttu-id="7528a-310">**박스형**</span><span class="sxs-lookup"><span data-stu-id="7528a-310">**Inboxed**</span></span>
  - <span data-ttu-id="7528a-311">**박스형 아님**</span><span class="sxs-lookup"><span data-stu-id="7528a-311">**Not Inboxed**</span></span>
  - <span data-ttu-id="7528a-312">**Spf 통과**: [Spf (sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)에 의해 보낸 사람이 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-312">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="7528a-313">SPF 유효성 검사를 통과 하지 못하는 보낸 사람이 인증 되지 않은 보낸 사람을 표시 하거나, 메시지가 합법적인 보낸 사람에 게 스푸핑 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-313">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="7528a-314">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="7528a-314">**Senders**</span></span>

  - <span data-ttu-id="7528a-315">**Sender**: 사용자가 전자 메일 클라이언트에 표시 하는 보낸 사람: 전자 메일 주소가 아닐 수도 있는,이 주소는 SMTP MAIL FROM 명령에 있는 실제 발신자 주소로,</span><span class="sxs-lookup"><span data-stu-id="7528a-315">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="7528a-316">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="7528a-316">**Total count**</span></span>
  - <span data-ttu-id="7528a-317">**박스형**</span><span class="sxs-lookup"><span data-stu-id="7528a-317">**Inboxed**</span></span>
  - <span data-ttu-id="7528a-318">**박스형 아님**</span><span class="sxs-lookup"><span data-stu-id="7528a-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="7528a-319">**Dkim 통과**: 보낸 사람이 [Dkim (도메인 키 확인 메일)](support-for-validation-of-dkim-signed-messages.md)에 의해 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-319">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="7528a-320">DKIM 유효성 검사를 통과 하지 못하는 보낸 사람이 인증 되지 않은 보낸 사람을 표시 하거나, 메시지가 합법적인 보낸 사람에 게 스푸핑 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-320">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="7528a-321">**DMARC 통과**: 보낸 사람이 [도메인 기반 메시지 인증, 보고 및 적합성 (DMARC)](use-dmarc-to-validate-email.md)을 통해 인증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-321">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="7528a-322">DMARC 유효성 검사를 통과 하지 못한 보낸 사람이 인증 되지 않은 보낸 사람을 표시 하거나, 메시지가 합법적인 보낸 사람에 게 스푸핑 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-322">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="7528a-323">**첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="7528a-323">**Attachments**</span></span>

  - <span data-ttu-id="7528a-324">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="7528a-324">**Filename**</span></span>
  - <span data-ttu-id="7528a-325">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="7528a-325">**SHA256**</span></span>
  - <span data-ttu-id="7528a-326">**맬웨어 제품군**</span><span class="sxs-lookup"><span data-stu-id="7528a-326">**Malware family**</span></span>
  - <span data-ttu-id="7528a-327">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="7528a-327">**Total count**</span></span>

- <span data-ttu-id="7528a-328">**URL**</span><span class="sxs-lookup"><span data-stu-id="7528a-328">**URL**</span></span>

  - <span data-ttu-id="7528a-329">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7528a-329">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="7528a-330">**합계**</span><span class="sxs-lookup"><span data-stu-id="7528a-330">**Total Count**</span></span>

<span data-ttu-id="7528a-331"><sup>\*</sup>이 값을 클릭하면 캠페인 세부 정보 보기 위쪽에 지정된 항목(사용자, URL 등)에 대한 자세한 정보가 포함된 플라이 아웃이 새로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-331"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="7528a-332">캠페인 세부 정보 보기로 돌아가려면 새 플라이 아웃에서 **완료**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-332">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="7528a-333">버튼</span><span class="sxs-lookup"><span data-stu-id="7528a-333">Buttons</span></span>

<span data-ttu-id="7528a-334">캠페인 세부 정보 보기의 버튼을 통해 위협 탐색기 기능을 사용하여 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-334">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="7528a-335">**캠페인 탐색**: **캠페인 ID** 값을 검색 필터로 사용하여 새로운 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-335">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="7528a-336">**Inboxed 메시지 살펴보기**: **캠페인 ID** 및 **배달 위치: 받은 편지함** 을 검색 필터로 사용 하 여 새 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7528a-336">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
