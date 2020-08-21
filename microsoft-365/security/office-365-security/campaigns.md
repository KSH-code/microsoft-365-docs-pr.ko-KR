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
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection의 캠페인 보기에 대해 알아보세요.
ms.openlocfilehash: f0f5d2305b4f17c7018d32eebd155b4ad2d459e7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825800"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="612c4-103">ATP의 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="612c4-103">Campaign Views in ATP</span></span>

<span data-ttu-id="612c4-104">캠페인 보기는 보안 & 준수 센터의 ATP(Advanced Threat Protection)의 기능으로 서비스의 피싱 공격을 식별하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="612c4-105">캠페인 보기를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="612c4-106">피싱 공격을 효과적으로 조사하고 이에 대처합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="612c4-107">공격의 범위를 더 잘 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="612c4-108">의사 결정자에게 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-108">Show value to decision makers.</span></span>

<span data-ttu-id="612c4-109">캠페인 보기를 그 누구보다 빠르고 완벽하게 공격의 전체적인 상황을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="612c4-110">캠페인이란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="612c4-110">What is a campaign?</span></span>

<span data-ttu-id="612c4-111">캠페인은 하나 이상의 조직에 대해 조율된 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="612c4-112">자격 증명과 회사 데이터를 도용하는 전자 메일 공격은 규모가 크고 예산적인 업계입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="612c4-113">기술은 공격을 중지하는 데 노트가 늘어나면서 공격자는 계속 성공을 보이기 위해 노의식을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="612c4-114">Microsoft는 캠페인을 식별하는 데 도움이 되이된 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터를 많은 양으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="612c4-115">당사는 여러 요소에 따라 공격 정보를 분석하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="612c4-116">예제:</span><span class="sxs-lookup"><span data-stu-id="612c4-116">For example:</span></span>

- <span data-ttu-id="612c4-117">**공격 소스:** 원본 IP 주소 및 보낸 사람의 전자 메일 도메인.</span><span class="sxs-lookup"><span data-stu-id="612c4-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="612c4-118">**공격 메시지 속성:** 메시지의 내용, 스타일 및 어신</span><span class="sxs-lookup"><span data-stu-id="612c4-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="612c4-119">**받는 사람 공격**: 받는 사람 도메인, 받는 사람의 직무 기능(관리자, 임원 등), 회사 유형(대규모, 소규모, 공공 부문, 민간 부문 등) 및 산업.</span><span class="sxs-lookup"><span data-stu-id="612c4-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="612c4-120">**공격 페이로드:** 메시지의 악성 링크, 첨부 파일 또는 기타 페이로드</span><span class="sxs-lookup"><span data-stu-id="612c4-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="612c4-121">캠페인이 길거나 수명주일 수도 있고 활성 기간과 비활성 기간을 포함하여 며칠, 주 또는 월에 걸려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="612c4-122">캠페인은 특정 조직에 대해 실행된 경우도 있고 조직이 여러 회사의 보다 큰 캠페인의 일부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="612c4-123">보안 컨트롤의 보안 & 보기</span><span class="sxs-lookup"><span data-stu-id="612c4-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="612c4-124">캠페인 보기는 위협 관리 [캠페인의 보안 &](https://protection.office.com) 보안 **Threat management** \> **센터에서**제공되거나 직접 제공될 수 <https://protection.office.com/campaigns> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![보안 및 규정 준수 센터의 캠페인 개요](../../media/campaigns-overview.png)

<span data-ttu-id="612c4-126">또한 다음에서 캠페인 보기로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="612c4-127">**위협 관리** \> **탐색기** \> **보기** \> **캠페인**</span><span class="sxs-lookup"><span data-stu-id="612c4-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="612c4-128">**위협 관리** \> **탐색기** \> **보기** \> **모든 전자 메일** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="612c4-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="612c4-129">**위협 관리** \> **탐색기** \> **보기** \> **피싱** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="612c4-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="612c4-130">**위협 관리** \> **탐색기** \> **보기** \> **맬웨어** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="612c4-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="612c4-131">캠페인 보기에 액세스하려면 준수 센터에서 보안 관리 센터에서 **조직**관리, **보안**관리자 또는 **보안** 독자 역할 그룹의 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="612c4-132">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="612c4-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="612c4-133">캠페인 개요</span><span class="sxs-lookup"><span data-stu-id="612c4-133">Campaigns overview</span></span>

<span data-ttu-id="612c4-134">개요 페이지에는 모든 캠페인에 대한 정보가 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="612c4-135">기본 **캠페인 탭에서** 캠페인 **유형** 영역에는 일별 받는 사람 수를 보여 주는 막대 그래프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="612c4-136">기본적으로 그래프에는 피싱 및 **맬웨어 데이터가** 모두 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="612c4-137">캠페인 데이터가 나타나지 않으면 날짜 범위를 변경하거나 필터를 [변경해 보세요.](#filters-and-settings)</span><span class="sxs-lookup"><span data-stu-id="612c4-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="612c4-138">나머지 개요 페이지에서는 캠페인 탭에 **대한 다음 정보를 보여줍니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="612c4-139">**이름**</span><span class="sxs-lookup"><span data-stu-id="612c4-139">**Name**</span></span>

- <span data-ttu-id="612c4-140">**샘플 제목**: 캠페인의 메시지 중 하나에 대한 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="612c4-141">캠페인의 모든 메시지는 반드시 같은 제목을 가지지 제한이 관련는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="612c4-142">**Targeted**: 계산되는 비율입니다. (조직의 캠페인 받는 사람 수) / (서비스의 모든 조직 내 캠페인에 있는 받는 사람의 총 수)</span><span class="sxs-lookup"><span data-stu-id="612c4-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="612c4-143">이 값은 캠페인이 조직에 특별히 특별히 감지되는 수준과 서비스의 다른 조직에서 대상으로 지정된 수준(낮은 가치)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="612c4-144">**형식**: 이 값은 피싱 **또는** **맬웨어입니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="612c4-145">**하위 유형**: 이 값에는 캠페인에 대한 자세한 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="612c4-146">예제:</span><span class="sxs-lookup"><span data-stu-id="612c4-146">For example:</span></span>

  - <span data-ttu-id="612c4-147">**피싱:** 가능한 경우, 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="612c4-148">같은 의미로 오가, `Microsoft` `365` `Unknown` `Outlook` 또는 `DocuSign`</span><span class="sxs-lookup"><span data-stu-id="612c4-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="612c4-149">**맬웨어**: 예 또는 `HTML/PHISH` `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="612c4-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="612c4-150">가능한 경우 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="612c4-151">검색이 ATP 기술에 의해 시작되면 **ATP** 접두사는 하위 형식 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="612c4-152">**받는 사람**: 이 캠페인을 대상으로 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="612c4-153">**받은**편지함: 이 캠페인(정크 메일 폴더로 전달되지 않음)에서 이 캠페인으로부터 메시지를 받은 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="612c4-154">**클릭됨**: URL을 클릭하거나 피싱 메시지에서 첨부 파일을 여는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="612c4-155">**Rate:\*\*\*\*"클릭된**받은 편지함"으로 계산된  /  **비율입니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="612c4-156">이 값은 캠페인의 유효성과 받는 사람이 메시지를 피싱으로 식별하고 페이로드 URL클릭을 피할 수 있었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="612c4-157">이 값은 맬웨어 캠페인에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="612c4-158">**방문:** 실제로 페이로드 웹 사이트를 통해 추가한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="612c4-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="612c4-159">클릭한 **값만 있지만** 웹 사이트에 대한 액세스가 차단된 안전한 링크가 있는 경우 이 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="612c4-160">**캠페인 시작 페이지 Tab은** 세계 지도의 메시지 원본을 보여 보여 입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="612c4-161">필터 및 설정</span><span class="sxs-lookup"><span data-stu-id="612c4-161">Filters and settings</span></span>

<span data-ttu-id="612c4-162">캠페인 보기 페이지의 맨 위에는 특정 캠페인을 찾고 분리하는 데 도움이 되는 여러 필터 및 쿼리 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![캠페인 필터](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="612c4-164">수행할 수 있는 가장 기본적인 필터링은 시작 날짜/시간 및 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="612c4-165">보기를 더 세부적으로 필터링하려면 캠페인 유형 단추를 클릭하고 **선택을** 한 다음 새로 고침을 클릭하여 여러 값 필터링으로 단일 속성을 수행할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="612c4-166">사용 가능한 캠페인 속성은 다음 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="612c4-167">기본</span><span class="sxs-lookup"><span data-stu-id="612c4-167">Basic</span></span>

  - <span data-ttu-id="612c4-168">**캠페인 유형:** 맬웨어 **또는** **피싱 선택.**</span><span class="sxs-lookup"><span data-stu-id="612c4-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="612c4-169">선택 항목을 지우는 결과는 두 가지 모두 선택하는 결과와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="612c4-170">**캠페인 이름**</span><span class="sxs-lookup"><span data-stu-id="612c4-170">**Campaign name**</span></span>
  - <span data-ttu-id="612c4-171">**캠페인 하위 유형**</span><span class="sxs-lookup"><span data-stu-id="612c4-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="612c4-172">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="612c4-172">**Sender**</span></span>
  - <span data-ttu-id="612c4-173">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="612c4-173">**Recipients**</span></span>
  - <span data-ttu-id="612c4-174">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="612c4-174">**Sender domain**</span></span>
  - <span data-ttu-id="612c4-175">**제목**</span><span class="sxs-lookup"><span data-stu-id="612c4-175">**Subject**</span></span>
  - <span data-ttu-id="612c4-176">**첨부 파일 이름**</span><span class="sxs-lookup"><span data-stu-id="612c4-176">**Attachment filename**</span></span>
  - <span data-ttu-id="612c4-177">**맬웨어 제품군**</span><span class="sxs-lookup"><span data-stu-id="612c4-177">**Malware family**</span></span>
  - <span data-ttu-id="612c4-178">**배달 작업**</span><span class="sxs-lookup"><span data-stu-id="612c4-178">**Delivery action**</span></span>
  - <span data-ttu-id="612c4-179">**검색 기술**</span><span class="sxs-lookup"><span data-stu-id="612c4-179">**Detection technology**</span></span>
  - <span data-ttu-id="612c4-180">**태그**</span><span class="sxs-lookup"><span data-stu-id="612c4-180">**Tags**</span></span>
  - <span data-ttu-id="612c4-181">**시스템 재정의**</span><span class="sxs-lookup"><span data-stu-id="612c4-181">**System overrides**</span></span>

- <span data-ttu-id="612c4-182">고급</span><span class="sxs-lookup"><span data-stu-id="612c4-182">Advanced</span></span>

  - <span data-ttu-id="612c4-183">**인터넷 메시지 ID:** 메시지 **헤더의 메시지 ID 헤더** 필드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="612c4-184">괄성에 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 주의해야 합니다(</span><span class="sxs-lookup"><span data-stu-id="612c4-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="612c4-185">**네트워크 메시지 ID:** 메시지 헤더의 **X-MS-Exchange-Organization-Network-Message-Id 헤더** 필드에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="612c4-186">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="612c4-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="612c4-187">**첨부 파일 SHA256**: Windows에서 파일의 SHA256 해시 값을 찾으려면 명령 프롬프트에서 다음 명령을 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="612c4-188">**클러스터 ID**</span><span class="sxs-lookup"><span data-stu-id="612c4-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="612c4-189">**경고 정책 ID**</span><span class="sxs-lookup"><span data-stu-id="612c4-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="612c4-190">URL</span><span class="sxs-lookup"><span data-stu-id="612c4-190">URLs</span></span>

  - <span data-ttu-id="612c4-191">**URL 도메인**</span><span class="sxs-lookup"><span data-stu-id="612c4-191">**URL domain**</span></span>
  - <span data-ttu-id="612c4-192">**URL 도메인 및 경로**</span><span class="sxs-lookup"><span data-stu-id="612c4-192">**URL domain and path**</span></span>
  - <span data-ttu-id="612c4-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="612c4-193">**URL**</span></span>
  - <span data-ttu-id="612c4-194">**URL 경로**</span><span class="sxs-lookup"><span data-stu-id="612c4-194">**URL path**</span></span>
  - <span data-ttu-id="612c4-195">**결과 클릭**</span><span class="sxs-lookup"><span data-stu-id="612c4-195">**Click verdict**</span></span>

<span data-ttu-id="612c4-196">여러 속성에 대한 필터링을 비롯한 고급 필터링을 위해 고급 필터 단추를 **클릭하면 쿼리를** 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="612c4-197">동일한 캠페인 속성을 사용할 수 있지만 다음과 같은 기능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="612c4-198">조건 추가를 **클릭하여 여러** 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="612c4-199">조건 간에 And **또는** **Or 연산자를** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="612c4-200">조건 목록의 맨 **아래에** 있는 조건 그룹 항목을 선택하여 복합 조건을 양식화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="612c4-201">작업을 마치면 쿼리 단추를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="612c4-202">기본 필터나 고급 필터를 작성한 후 저장 쿼리 또는 다른 이름으로 **저장 쿼리를 사용하여** **저장할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="612c4-203">나중에 캠페인 보기로 돌아가면 저장된 쿼리 설정을 클릭하여 저장된 필터를 **로드할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="612c4-204">그래프나 캠페인 목록을 내보내려면 **차트 데이터** 내보내기를 클릭하고 차트 **데이터 내보내기 또는** **캠페인 내보내기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="612c4-205">Microsoft Defender ATP 구독이 있는 경우 **WDATP를** 클릭하여 캠페인 정보를 Microsoft Defender ATP로 연결하거나 연결을 끊을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="612c4-206">자세한 내용은 [Office 365 ATP와 Microsoft Defender ATP 통합을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)</span><span class="sxs-lookup"><span data-stu-id="612c4-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="612c4-207">캠페인 세부 정보</span><span class="sxs-lookup"><span data-stu-id="612c4-207">Campaign details</span></span>

<span data-ttu-id="612c4-208">캠페인 이름을 클릭하면 캠페인 세부 정보가 플라이 아웃에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="612c4-209">캠페인 정보</span><span class="sxs-lookup"><span data-stu-id="612c4-209">Campaign information</span></span>

<span data-ttu-id="612c4-210">캠페인 세부 정보 보기의 위쪽에서 다음 캠페인 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="612c4-211">**ID**: 고유한 캠페인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="612c4-212">**시작** 및 **종료됨:** 캠페인 시작 및 종료 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="612c4-213">이러한 날짜는 개요 페이지에서 선택한 필터 날짜보다 더 많은 시간을 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="612c4-214">**영향:** 이 섹션에는 선택한 날짜 범위 필터나 시간 표시 막대에서 선택한 필터에 대한 다음과 같은 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="612c4-215">총 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-215">The total number of recipients.</span></span>
  - <span data-ttu-id="612c4-216">"받은 편지함"(즉, 정크 메일 폴더가 아님으로 전달됨) 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="612c4-217">피싱 메시지의 URL 페이로드를 클릭하는 사용자 수</span><span class="sxs-lookup"><span data-stu-id="612c4-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="612c4-218">하지만 많은 사용자가 해당 URL을 방문하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="612c4-219">**Targeted**: 계산되는 비율입니다. (조직의 캠페인 받는 사람 수) / (서비스의 모든 조직 내 캠페인에 있는 받는 사람의 총 수)</span><span class="sxs-lookup"><span data-stu-id="612c4-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="612c4-220">이 값은 캠페인의 전체 수명 동안 계산되며 필터 날짜를 변경하지 는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="612c4-221">캠페인 활동의 대화형 타임라인: 타임라인에는 캠페인의 전체 수명 동안 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="612c4-222">기본적으로 음시된 영역에는 개요에서 선택한 날짜 범위 필터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="612c4-223">클릭하고 끌어서 특정 시작점과 끝점을 선택할 수 있습니다. <u>이렇게 하면 **영향** 영역및 나머지 페이지에서 설명하는</u>정보에 나와 있는 나머지 부분에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="612c4-224">제목 표시줄에서 캠페인 **Download campaign write-up** 쓰기,캠페인 쓰기 아이콘을 클릭하여 캠페인 세부 정보를 Word 문서(기본적으로 ![ 명명된 ](../../media/download-campaign-write-up-button.png) CampaignReport.docx)에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="612c4-225">이 문서에는 선택한 필터 날짜뿐만 이래 캠페인의 전체 수명에 대한 세부 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![캠페인 정보](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="612c4-227">캠페인 흐름</span><span class="sxs-lookup"><span data-stu-id="612c4-227">Campaign flow</span></span>

<span data-ttu-id="612c4-228">캠페인 세부 정보 보기의 중간에서 캠페인에 대한 중요 세부 정보는 **수평 흐름** 다이어그램(Sankey 다이어그램이라고도 _함)의_ 흐름 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="612c4-229">이러한 세부 정보는 캠페인의 요소와 조직에서 발생할 수 있는 영향을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="612c4-230">흐름 다이어그램에 표시되는 정보는 **이전** 섹션에서 설명한 것과 같이 시간 표시 막대의 음영 날짜 범위에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![사용자 URL 클릭을 포함하지 않는 캠페인 세부 정보](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="612c4-232">다이어그램에서 가로 밴드에 마우스를 올리면 관련 메시지 수(예: 특정 원본 IP의 메시지, 지정된 보낸 사람 도메인을 사용하는 원본 IP의 메시지)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="612c4-233">흐름도에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="612c4-234">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="612c4-234">**Sender IPs**</span></span>

- <span data-ttu-id="612c4-235">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="612c4-235">**Sender domains**</span></span>

- <span data-ttu-id="612c4-236">**필터 결과:** 이 값은 스팸 방지 메시지 헤더에 설명된 바와 같이 사용 가능한 피싱 및 [스팸 필터링 결과와 관련이 있습니다.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="612c4-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="612c4-237">사용 가능한 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="612c4-238">값</span><span class="sxs-lookup"><span data-stu-id="612c4-238">Value</span></span>|<span data-ttu-id="612c4-239">스팸 필터 검색</span><span class="sxs-lookup"><span data-stu-id="612c4-239">Spam filter verdict</span></span>|<span data-ttu-id="612c4-240">설명</span><span class="sxs-lookup"><span data-stu-id="612c4-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="612c4-241">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="612c4-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="612c4-242">스팸 필터링(예: 전송 규칙이라고도 함)으로 평가되기 전에 메시지가 스팸이 아니며, 필터링을 건너뛰는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="612c4-243">다른 이유로 인해 메시지가 스팸 필터링을 건너뛰는 경우(예: 보낸 사람과 받는 사람이 같은 조직에 있는 것 같습니다).</span><span class="sxs-lookup"><span data-stu-id="612c4-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="612c4-244">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="612c4-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="612c4-245">스팸 필터링에 의해 메시지가 스팸으로 표시되었다고 추정합니다(예: 메일 흐름 규칙에 의해).</span><span class="sxs-lookup"><span data-stu-id="612c4-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="612c4-246">**감지함**</span><span class="sxs-lookup"><span data-stu-id="612c4-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="612c4-247">메시지가 스팸 필터링에 의해 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="612c4-248">**검색되지 않음**</span><span class="sxs-lookup"><span data-stu-id="612c4-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="612c4-249">메시지가 스팸 필터링에 의해 스팸이 아음으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="612c4-250">**릴리스된**</span><span class="sxs-lookup"><span data-stu-id="612c4-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="612c4-251">메시지가 격리에서 릴리스되었기 때문에 해당 메시지가 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="612c4-252">**테넌트 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="612c4-253">스팸 방지 정책 설정으로 인해 메시지가 스팸 필터링을 건너뛰었습니다(예: 보낸 사람이 허용된 보낸 사람 목록이나 허용된 도메인 목록에 있습니다).</span><span class="sxs-lookup"><span data-stu-id="612c4-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="612c4-254">**테넌트 블록**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="612c4-255">스팸 방지 정책 설정으로 인해(예: 보낸 사람이 허용된 보낸 사람 목록이나 허용된 도메인 목록에 있습니다)로 인해 메시지가 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="612c4-256">**사용자 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="612c4-257">보낸 사람이 Outlook에서 사용자의 수신 허용 - 보낸 사람 목록에 있어 메시지를 스팸 필터링을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="612c4-258">**사용자 차단**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="612c4-259">보낸 사람이 Outlook에서 사용자의 수신 거부 목록에 있어 메시지가 스팸 필터링에 의해 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="612c4-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="612c4-260">**ZAP**</span></span>|<span data-ttu-id="612c4-261">해당 없음</span><span class="sxs-lookup"><span data-stu-id="612c4-261">n/a</span></span>|<span data-ttu-id="612c4-262">[스팸 방지 정책 설정(정크 메일 폴더 또는 격리)에](zero-hour-auto-purge.md) 따라 배달된 메시지에 대한 ZAP(제로 아사이트 자동 제거)에 대한 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="612c4-263"><sup>\*</sup> 스팸 방지 정책을 검토합니다. 스팸 방지 정책은 서비스에 의해 차단되었을 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="612c4-264"><sup>\*\*</sup> 이러한 메시지가 격리되어야 하므로 스팸 방지 정책을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="612c4-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="612c4-265">**전달 위치**: 사용자가 메시지에서 페이로드 URL을 클릭하지 않은 경우라도 (받은 편지함 또는 정크 메일 폴더로) 받는 사람에게 실제로 전달된 메시지를 조사하려 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="612c4-266">또한 격리에서 격리된 메시지를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="612c4-267">자세한 내용은 [EOP에서 격리된 전자 메일 메시지를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="612c4-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="612c4-268">**폴더 삭제됨**</span><span class="sxs-lookup"><span data-stu-id="612c4-268">**Deleted folder**</span></span>
  - <span data-ttu-id="612c4-269">**놓기**</span><span class="sxs-lookup"><span data-stu-id="612c4-269">**Dropped**</span></span>
  - <span data-ttu-id="612c4-270">**외부**: 받는 사람이 하이브리드 환경의 온-프레미스 전자 메일 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="612c4-271">**실패**</span><span class="sxs-lookup"><span data-stu-id="612c4-271">**Failed**</span></span>
  - <span data-ttu-id="612c4-272">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="612c4-272">**Forwarded**</span></span>
  - <span data-ttu-id="612c4-273">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="612c4-273">**Inbox**</span></span>
  - <span data-ttu-id="612c4-274">**정크 메일 폴더**</span><span class="sxs-lookup"><span data-stu-id="612c4-274">**Junk folder**</span></span>
  - <span data-ttu-id="612c4-275">**격리**</span><span class="sxs-lookup"><span data-stu-id="612c4-275">**Quarantine**</span></span>
  - <span data-ttu-id="612c4-276">**알 수 없음**</span><span class="sxs-lookup"><span data-stu-id="612c4-276">**Unknown**</span></span>

- <span data-ttu-id="612c4-277">**URL 클릭:** 다음 섹션에서이 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="612c4-278">10개 이상의 항목이 포함된 모든 계층에는 상위 10개 항목이 표시되면서 나머지는 다른 항목들에서 함께 번들로 **제공됩니다.**</span><span class="sxs-lookup"><span data-stu-id="612c4-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="612c4-279">URL 클릭</span><span class="sxs-lookup"><span data-stu-id="612c4-279">URL clicks</span></span>

<span data-ttu-id="612c4-280">피싱 메시지가 받는 사람에게 배달(받은 편지함 또는 정크 메일 폴더)되면 언제든지 페이로드 URL을 클릭할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="612c4-281">배달된 메시지에서 URL을 클릭하지 않을 경우 작은 성공 측정값을 나타내지만, 피싱 메시지가 처음에는 사서함에 배달된 이유를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="612c4-282">사용자가 피싱 메시지에서 페이로드 URL을 클릭하면 **캠페인** 세부 정보 보기에서 다이어그램의 다이어그램 영역을 클릭하는 작업이 URL 클릭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="612c4-283">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="612c4-283">**Allowed**</span></span>

- <span data-ttu-id="612c4-284">**BlockPage**: 받는 사람이 페이로드 URL을 클릭하지만 악성 웹 사이트에 대한 [액세스는 조직내 ATP 안전한 링크 정책에](atp-safe-links.md) 의해 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="612c4-285">**BlockPageOverride**: 받는 사람이 메시지에서 페이로드 URL을 클릭하면 ATP가 이를 중지하려고 시도했습니다. 하지만 이 차단을 재정의할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="612c4-286">사용자가 안전한 링크 정책 결과를 재정의하고 악의적인 웹 사이트로 이동할 수 있도록 허용된 이유를 확인하려면 안전한 링크 정책을 조사해야 합니다. [Safe Links policies](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="612c4-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="612c4-287">**PendingDetonationPage**: ATP 안전한 첨부 파일은 가상 컴퓨터 환경에서 페이로드 URL을 열어 수행되는 프로세스를 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="612c4-288">**PendingDetonationPageOverride**: 받는 사람이 페이로드 데트를 재정의하고 결과를 기다리지 않고 URL을 열 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="612c4-289">탭</span><span class="sxs-lookup"><span data-stu-id="612c4-289">Tabs</span></span>

<span data-ttu-id="612c4-290">캠페인 세부 정보 보기의 탭을 통해 캠페인을 더 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="612c4-291">탭에 표시되는 정보는 캠페인 정보 섹션에 설명된 것과 같이 시간 표시 막대의 음영 [날짜 범위에 의해 제어됩니다.](#campaign-information)</span><span class="sxs-lookup"><span data-stu-id="612c4-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="612c4-292">**URL 클릭:** 사용자가 피싱 메시지에서 페이로드 URL을 클릭하지 않은 경우 이 섹션은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="612c4-293">사용자가 URL을 클릭할 수 있는 경우 다음 값이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="612c4-294">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="612c4-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="612c4-296">**시간 클릭**</span><span class="sxs-lookup"><span data-stu-id="612c4-296">**Click time**</span></span>
  - <span data-ttu-id="612c4-297">**결과 클릭**</span><span class="sxs-lookup"><span data-stu-id="612c4-297">**Click verdict**</span></span>

- <span data-ttu-id="612c4-298">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="612c4-298">**Sender IPs**</span></span>

  - <span data-ttu-id="612c4-299">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="612c4-300">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="612c4-300">**Total count**</span></span>
  - <span data-ttu-id="612c4-301">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="612c4-301">**Inboxed**</span></span>
  - <span data-ttu-id="612c4-302">**받은 편지함이 아지함**</span><span class="sxs-lookup"><span data-stu-id="612c4-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="612c4-303">**SPF 통과:** 보낸 사람이 [SPF(Sender Policy Framework)를 사용하여 인증되었습니다.](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="612c4-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="612c4-304">SPF 유효성 검사를 통과하지 못한 보낸 사람은 보낸 사람이 인증되지 않았거나 메시지가 합법적 보낸 사람을 스푸핑하고 있는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="612c4-305">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="612c4-305">**Senders**</span></span>

  - <span data-ttu-id="612c4-306">**보낸**사람 : SMTP MAIL FROM 명령의 실제 보낸 사람 주소이며, 이는 전자 메일 클라이언트에서 사용자에게 표시되는 보낸 사람: 전자 메일 주소가 아무것도 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="612c4-307">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="612c4-307">**Total count**</span></span>
  - <span data-ttu-id="612c4-308">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="612c4-308">**Inboxed**</span></span>
  - <span data-ttu-id="612c4-309">**받은 편지함이 아지함**</span><span class="sxs-lookup"><span data-stu-id="612c4-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="612c4-310">**DKIM이 전달됨**: 보낸 사람이 [DKIM(Domain Keys Identified Mail)에 의해 인증되었습니다.](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="612c4-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="612c4-311">DKIM 유효성 검사를 통과하지 않는 보낸 사람은 보낸 사람이 인증되지 않았거나 합법적 보낸 사람을 스푸핑하고 있는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="612c4-312">**DMARC 통과:** 보낸 사람이 [DMARC(도메인 기반 메시지 인증, 보고 및 적정)에 의해 인증되었습니다.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="612c4-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="612c4-313">DMARC 유효성 검사를 통과하지 못한 보낸 사람은 보낸 사람이 인증되지 않았거나 합법적인 보낸 사람을 스푸핑하고 있는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="612c4-314">**첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="612c4-314">**Attachments**</span></span>

  - <span data-ttu-id="612c4-315">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="612c4-315">**Filename**</span></span>
  - <span data-ttu-id="612c4-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="612c4-316">**SHA256**</span></span>
  - <span data-ttu-id="612c4-317">**맬웨어 제품군**</span><span class="sxs-lookup"><span data-stu-id="612c4-317">**Malware family**</span></span>
  - <span data-ttu-id="612c4-318">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="612c4-318">**Total count**</span></span>

- <span data-ttu-id="612c4-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="612c4-319">**URL**</span></span>

  - <span data-ttu-id="612c4-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="612c4-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="612c4-321">**합계**</span><span class="sxs-lookup"><span data-stu-id="612c4-321">**Total Count**</span></span>

<span data-ttu-id="612c4-322"><sup>\*</sup>이 값을 클릭하면 캠페인 세부 정보 보기 위쪽에 지정된 항목(사용자, URL 등)에 대한 자세한 정보가 포함된 플라이 아웃이 새로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="612c4-323">캠페인 세부 정보 보기로 돌아가려면 새 플라이 아웃에서 **완료**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="612c4-324">버튼</span><span class="sxs-lookup"><span data-stu-id="612c4-324">Buttons</span></span>

<span data-ttu-id="612c4-325">캠페인 세부 정보 보기의 버튼을 통해 위협 탐색기 기능을 사용하여 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="612c4-326">**캠페인 탐색**: **캠페인 ID** 값을 검색 필터로 사용하여 새로운 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="612c4-327">**받은 편지함 메시지 탐색:** 캠페인 ID 및 배달 위치를 **사용하는 새로운** 위협 탐색기 검색 **탭을 엽니다. 받은 편지함을** 검색 필터로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="612c4-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
