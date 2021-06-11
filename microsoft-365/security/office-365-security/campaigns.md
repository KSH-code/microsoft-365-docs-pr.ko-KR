---
title: Microsoft Defender for Office 365 캠페인 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba619c5341913190bfb84dbc34b938deee8f42ca
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879135"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1c2a2-103">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1c2a2-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1c2a2-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-104">**Applies to**</span></span>
- [<span data-ttu-id="1c2a2-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="1c2a2-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="1c2a2-106">캠페인 보기는 Microsoft Defender for Office 365 계획 2의 기능입니다(예: Microsoft 365 E5 요금제 2 추가 기능에 대한 Defender가 Office 365 조직).</span><span class="sxs-lookup"><span data-stu-id="1c2a2-106">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example, Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="1c2a2-107">Microsoft 365 Defender 포털의 캠페인 보기는 서비스에서 피싱 공격을 식별하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-107">Campaign Views in the Microsoft 365 Defender portal identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="1c2a2-108">캠페인 보기를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-108">Campaign Views can help you to:</span></span>

- <span data-ttu-id="1c2a2-109">피싱 공격을 효과적으로 조사하고 이에 대처합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-109">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="1c2a2-110">공격의 범위를 더 잘 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-110">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="1c2a2-111">의사 결정자에게 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-111">Show value to decision makers.</span></span>

<span data-ttu-id="1c2a2-112">캠페인 보기를 그 누구보다 빠르고 완벽하게 공격의 전체적인 상황을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-112">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="1c2a2-113">캠페인이란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="1c2a2-113">What is a campaign?</span></span>

<span data-ttu-id="1c2a2-114">캠페인은 하나 이상의 조직에 대해 조율된 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-114">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="1c2a2-115">자격 증명 및 회사 데이터를 도용하는 전자 메일 공격은 대규모의 기업입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-115">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="1c2a2-116">기술이 공격을 중지하기 위한 노력이 증가하면 공격자는 계속 성공하기 위해 방법을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-116">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="1c2a2-117">Microsoft는 전체 서비스에서 방대한 양의 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터를 활용하여 캠페인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-117">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="1c2a2-118">여러 요인에 따라 공격 정보를 분석하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-118">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="1c2a2-119">예:</span><span class="sxs-lookup"><span data-stu-id="1c2a2-119">For example:</span></span>

- <span data-ttu-id="1c2a2-120">**공격 원본**: 원본 IP 주소 및 보낸 사람 전자 메일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-120">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="1c2a2-121">**메시지 속성:** 메시지의 콘텐츠, 스타일 및 톤입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-121">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="1c2a2-122">**메시지 받는 사람:** 받는 사람 관련 방법</span><span class="sxs-lookup"><span data-stu-id="1c2a2-122">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="1c2a2-123">예를 들어 받는 사람 도메인, 받는 사람 작업 기능(관리자, 임원 등), 회사 유형(대규모, 소규모, 공용, 개인 등) 및 산업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-123">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="1c2a2-124">**공격 페이로드:** 메시지의 악성 링크, 첨부 파일 또는 기타 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-124">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="1c2a2-125">캠페인은 수명이 짧거나 활성 및 비활성 기간이 있는 며칠, 몇 주 또는 몇 달에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-125">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="1c2a2-126">특정 조직에 대해 캠페인이 시작되거나 조직이 여러 회사에서 대규모 캠페인에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-126">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="1c2a2-127">Microsoft 365 Defender 포털의 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="1c2a2-127">Campaign Views in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="1c2a2-128">캠페인 보기는 에서 Microsoft 365 Defender 포털( ) 또는 전자 메일 & 캠페인에서 사용할 수 있습니다. 또는 에서 직접 사용할 수 <https://security.microsoft.com>  \>  <https://security.microsoft.com/campaigns> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-128">Campaign Views is available in the Microsoft 365 Defender portal (<https://security.microsoft.com>) at **Email & collaboration** \> **Campaigns**, or directly at <https://security.microsoft.com/campaigns>.</span></span>

![Microsoft 365 Defender 포털의 캠페인 개요](../../media/campaigns-overview.png)

<span data-ttu-id="1c2a2-130">다음에서 캠페인 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-130">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="1c2a2-131">**전자 메일 & 공동 작업** \> **탐색기** \> **보기** \> **캠페인**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-131">**Email & collaboration** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="1c2a2-132">**전자 메일 & 공동 작업** \> **탐색기** \> **보기** \> **모든 전자 메일** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="1c2a2-132">**Email & collaboration** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="1c2a2-133">**전자 메일 & 공동 작업** \> **탐색기** \> **보기** \> **피싱** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="1c2a2-133">**Email & collaboration** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="1c2a2-134">**전자 메일 & 공동 작업** \> **탐색기** \> **보기** \> **맬웨어** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="1c2a2-134">**Email & collaboration** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="1c2a2-135">캠페인 보기에 액세스하려면 Microsoft 365 Defender 포털에서 조직 관리,  보안 관리자 또는 보안 읽기 권한자 역할 그룹의 구성원 Microsoft 365 합니다. </span><span class="sxs-lookup"><span data-stu-id="1c2a2-135">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="1c2a2-136">자세한 내용은 [Defender 포털의 Microsoft 365 참조하세요.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-136">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="1c2a2-137">캠페인 개요</span><span class="sxs-lookup"><span data-stu-id="1c2a2-137">Campaigns overview</span></span>

<span data-ttu-id="1c2a2-138">개요 페이지에는 모든 캠페인에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-138">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="1c2a2-139">기본 **캠페인** 탭에서 캠페인 유형 **영역에는** 하루 받는 사람 수를 표시하는 막대 그래프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-139">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="1c2a2-140">기본적으로 그래프에는 **피싱 및** 맬웨어 데이터가 **모두** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-140">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="1c2a2-141">캠페인 데이터가 없는 경우 날짜 범위 또는 필터를 [변경해 봐야 합니다.](#filters-and-settings)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-141">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="1c2a2-142">개요 페이지의 그래프 아래 표에는 캠페인 탭에 다음 정보가 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-142">The table below the graph on the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="1c2a2-143">**이름**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-143">**Name**</span></span>

- <span data-ttu-id="1c2a2-144">**샘플 제목**: 캠페인의 메시지 중 하나에 대한 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-144">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="1c2a2-145">캠페인의 모든 메시지의 제목이 같을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-145">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="1c2a2-146">**대상:** 계산된 비율: (조직의 캠페인 받는 사람 수) / (서비스의 모든 조직에서 캠페인의 총 받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-146">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="1c2a2-147">이 값은 캠페인이 조직에서만 진행되는 정도(더 높은 값)와 서비스의 다른 조직(더 낮은 값)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-147">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="1c2a2-148">**유형:** 이 값은 **피싱 또는** 맬웨어입니다. </span><span class="sxs-lookup"><span data-stu-id="1c2a2-148">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="1c2a2-149">**하위 스타일:** 이 값에는 캠페인에 대한 자세한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-149">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="1c2a2-150">예:</span><span class="sxs-lookup"><span data-stu-id="1c2a2-150">For example:</span></span>
  - <span data-ttu-id="1c2a2-151">**피싱:** 사용 가능한 경우 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-151">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="1c2a2-152">예를 들면 `Microsoft` , , , 또는 `365` `Unknown` `Outlook` `DocuSign` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-152">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="1c2a2-153">**맬웨어**: 예: `HTML/PHISH` `HTML/<MalwareFamilyName>` 또는 .</span><span class="sxs-lookup"><span data-stu-id="1c2a2-153">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="1c2a2-154">사용 가능한 경우 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-154">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="1c2a2-155">검색이 기본 기술에 대한 Defender에 Office 365 경우 **ATP-는** 하위 스타일 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-155">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="1c2a2-156">**받는 사람**: 이 캠페인을 대상으로 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-156">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="1c2a2-157">**받은 편지함:** 받은 편지함에서 이 캠페인에서 메시지를 받은 사용자 수(정크 메일 폴더로 배달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-157">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="1c2a2-158">**클릭한** 사용자: URL을 클릭하거나 피싱 메시지에서 첨부 파일을 연 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-158">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="1c2a2-159">**클릭률**: "**받은** 편지함 " 클릭으로  /  **계산된 백분율입니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-159">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="1c2a2-160">이 값은 캠페인의 효율성을 나타내는 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-160">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="1c2a2-161">즉, 받는 사람이 메시지를 피싱으로 식별할 수 있으며 페이로드 URL을 클릭하지 않은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-161">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="1c2a2-162">**클릭률은** 맬웨어 캠페인에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-162">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="1c2a2-163">**방문한** 사용자: 페이로드 웹 사이트를 통해 실제로 만든 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-163">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="1c2a2-164">클릭한  값이 있지만 안전한 링크로 웹 사이트에 대한 액세스가 차단된 경우 이 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-164">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="1c2a2-165">캠페인 **시작 탭에는** 세계 지도의 메시지 원본이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-165">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="1c2a2-166">필터 및 설정</span><span class="sxs-lookup"><span data-stu-id="1c2a2-166">Filters and settings</span></span>

<span data-ttu-id="1c2a2-167">캠페인 페이지 맨  위에는 특정 캠페인을 찾아 격리하는 데 도움이 되는 몇 가지 필터 및 쿼리 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-167">At the top of the **Campaign** page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![캠페인 필터](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="1c2a2-169">가장 기본적인 필터링은 시작 날짜/시간 및 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-169">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="1c2a2-170">보기를 추가로 필터링하려면 캠페인 유형 단추를 클릭하고 선택한  다음 새로 고침을 클릭하여 여러 값을 필터링하여 단일 속성을 만들 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-170">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="1c2a2-171">캠페인 유형 단추에서 사용할 수  있는 필터링할 수 있는 캠페인 속성은 다음 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-171">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="1c2a2-172">**기본**:</span><span class="sxs-lookup"><span data-stu-id="1c2a2-172">**Basic**:</span></span>
  - <span data-ttu-id="1c2a2-173">**캠페인 유형**: **맬웨어 또는** **피싱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-173">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="1c2a2-174">선택을 지우면 두 가지를 모두 선택하는 결과와 결과가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-174">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="1c2a2-175">**캠페인 이름**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-175">**Campaign name**</span></span>
  - <span data-ttu-id="1c2a2-176">**캠페인 하위 스타일**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-176">**Campaign subtype**</span></span>
  - <span data-ttu-id="1c2a2-177">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-177">**Sender**</span></span>
  - <span data-ttu-id="1c2a2-178">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-178">**Recipients**</span></span>
  - <span data-ttu-id="1c2a2-179">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-179">**Sender domain**</span></span>
  - <span data-ttu-id="1c2a2-180">**제목**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-180">**Subject**</span></span>
  - <span data-ttu-id="1c2a2-181">**첨부 파일 이름**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-181">**Attachment filename**</span></span>
  - <span data-ttu-id="1c2a2-182">**맬웨어 패밀리**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-182">**Malware family**</span></span>
  - <span data-ttu-id="1c2a2-183">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-183">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1c2a2-184">사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-184">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1c2a2-185">**배달 작업**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-185">**Delivery action**</span></span>
  - <span data-ttu-id="1c2a2-186">**추가 작업**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-186">**Additional action**</span></span>
  - <span data-ttu-id="1c2a2-187">**방향**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-187">**Directionality**</span></span>
  - <span data-ttu-id="1c2a2-188">**검색 기술**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-188">**Detection technology**</span></span>
  - <span data-ttu-id="1c2a2-189">**원본 배달 위치**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-189">**Original delivery location**</span></span>
  - <span data-ttu-id="1c2a2-190">**최신 배달 위치**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-190">**Latest delivery location**</span></span>
  - <span data-ttu-id="1c2a2-191">**시스템 오버라이드**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-191">**System overrides**</span></span>

- <span data-ttu-id="1c2a2-192">**고급**:</span><span class="sxs-lookup"><span data-stu-id="1c2a2-192">**Advanced**:</span></span>
  - <span data-ttu-id="1c2a2-193">**인터넷 메시지 ID:** 메시지 헤더의 **Message-ID** 헤더 필드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-193">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="1c2a2-194">값을 예로 들 수 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 있습니다(괄호 참고).</span><span class="sxs-lookup"><span data-stu-id="1c2a2-194">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="1c2a2-195">**네트워크 메시지 ID:** 메시지 헤더의 **X-MS-Exchange-Organization-Network-Message-Id** 헤더 필드에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-195">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="1c2a2-196">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-196">**Sender IP**</span></span>
  - <span data-ttu-id="1c2a2-197">**첨부 파일 SHA256:** 파일에서 파일의 SHA256 해시 값을 Windows 명령 프롬프트에서 다음 명령을 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 실행합니다. .</span><span class="sxs-lookup"><span data-stu-id="1c2a2-197">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="1c2a2-198">**클러스터 ID**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-198">**Cluster ID**</span></span>
  - <span data-ttu-id="1c2a2-199">**경고 ID**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-199">**Alert ID**</span></span>
  - <span data-ttu-id="1c2a2-200">**경고 정책 ID**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-200">**Alert Policy ID**</span></span>
  - <span data-ttu-id="1c2a2-201">**캠페인 ID**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-201">**Campaign ID**</span></span>
  - <span data-ttu-id="1c2a2-202">**ZAP URL 신호**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-202">**ZAP URL signal**</span></span>

- <span data-ttu-id="1c2a2-203">**URL**:</span><span class="sxs-lookup"><span data-stu-id="1c2a2-203">**URLs**:</span></span>
  - <span data-ttu-id="1c2a2-204">**URL 도메인**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-204">**URL domain**</span></span>
  - <span data-ttu-id="1c2a2-205">**URL 도메인 및 경로**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-205">**URL domain and path**</span></span>
  - <span data-ttu-id="1c2a2-206">**URL**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-206">**URL**</span></span>
  - <span data-ttu-id="1c2a2-207">**URL 경로**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-207">**URL path**</span></span>
  - <span data-ttu-id="1c2a2-208">**Click verdict**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-208">**Click verdict**</span></span>

<span data-ttu-id="1c2a2-209">여러 속성에 대한 필터링을 비롯한 고급 필터링의  경우 고급 필터 단추를 클릭하여 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-209">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="1c2a2-210">동일한 캠페인 속성을 사용할 수 있지만 다음과 같은 기능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-210">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="1c2a2-211">조건 **추가를 클릭하여** 여러 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-211">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="1c2a2-212">조건 간에 **And** 또는 **Or 연산자를** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-212">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="1c2a2-213">조건 목록 아래쪽에서 **조건** 그룹 항목을 선택하여 복합 조건을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-213">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="1c2a2-214">완료되면 쿼리 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-214">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="1c2a2-215">기본 필터나 고급 필터를 만든 후 쿼리  저장 또는 쿼리를 로 저장을 사용하여 **저장할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-215">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="1c2a2-216">나중에 캠페인 페이지로  돌아오면 저장된 쿼리 설정 을 클릭하여 저장된 **필터를 로드할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-216">Later, when you return to the **Campaigns** page, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="1c2a2-217">그래프 또는 캠페인 목록을 내보내려면 내보내기 를 클릭하고 차트 데이터 내보내기 **또는** 캠페인 목록  **내보내기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-217">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="1c2a2-218">Endpoint용 Microsoft Defender 구독이 있는 경우 **MDE** 구독을 설정 끝점용 Microsoft Defender를 사용하여 캠페인 정보를 연결하거나 연결을 끊을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-218">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1c2a2-219">자세한 내용은 [Endpoint용 Microsoft Defender와 Office 365 Microsoft Defender 통합을 참조하세요.](integrate-office-365-ti-with-mde.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-219">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="1c2a2-220">캠페인 세부 정보</span><span class="sxs-lookup"><span data-stu-id="1c2a2-220">Campaign details</span></span>

<span data-ttu-id="1c2a2-221">캠페인 이름을 클릭하면 캠페인 세부 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-221">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="1c2a2-222">캠페인 정보</span><span class="sxs-lookup"><span data-stu-id="1c2a2-222">Campaign information</span></span>

<span data-ttu-id="1c2a2-223">캠페인 세부 정보 보기 맨 위에 다음 캠페인 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-223">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="1c2a2-224">**캠페인 ID:** 고유한 캠페인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-224">**Campaign ID**: The unique campaign identifier.</span></span>
- <span data-ttu-id="1c2a2-225">**활동**: 캠페인의 기간 및 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-225">**Activity**: The duration and activity of the campaign.</span></span>
- <span data-ttu-id="1c2a2-226">선택한 날짜 범위 필터 또는 시간 표시 막대에서 선택한 날짜 범위에 대한 다음 데이터</span><span class="sxs-lookup"><span data-stu-id="1c2a2-226">The following data for the date range filter you selected (or that you select in the timeline):</span></span>
- <span data-ttu-id="1c2a2-227">**영향**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-227">**Impact**</span></span>
- <span data-ttu-id="1c2a2-228">**메시지:** 총 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-228">**Messages**: The total number of recipients.</span></span>
- <span data-ttu-id="1c2a2-229">**받은 편지함:** 정크 메일 폴더가 아니라 받은 편지함으로 배달된 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-229">**Inboxed**: The number of messages that were delivered to the Inbox, not to the Junk Email folder.</span></span>
- <span data-ttu-id="1c2a2-230">**클릭한 링크:** 피싱 메시지의 URL 페이로드를 클릭한 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-230">**Clicked link**: How many users clicked on the URL payload in the phishing message.</span></span>
- <span data-ttu-id="1c2a2-231">**방문한 링크:** URL을 방문한 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-231">**Visited link**: How many users visited the URL.</span></span>
- <span data-ttu-id="1c2a2-232">**Targeted(%)**: 계산된 비율: (조직의 캠페인 받는 사람 수) / (서비스의 모든 조직에서 캠페인의 총 받는 사람 수).</span><span class="sxs-lookup"><span data-stu-id="1c2a2-232">**Targeted(%)**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="1c2a2-233">이 값은 캠페인의 전체 수명 동안 계산하며 날짜 필터에 따라 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-233">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>
- <span data-ttu-id="1c2a2-234">다음 섹션에 설명된 캠페인 흐름에 대한 시작 날짜/시간 및 종료 데이터/시간 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-234">Start date/time and end data/time filters for the campaign flow as described in the next section.</span></span>
- <span data-ttu-id="1c2a2-235">캠페인 활동의 대화형 타임라인: 타임라인에는 캠페인의 전체 수명 동안 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-235">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="1c2a2-236">검색된 메시지의 양을 확인하기 위해 그래프의 데이터 포인트 위에 마우스를 대면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-236">You can hover over the data points in the graph to see the amount of detected messages.</span></span>

![캠페인 정보](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="1c2a2-238">캠페인 흐름</span><span class="sxs-lookup"><span data-stu-id="1c2a2-238">Campaign flow</span></span>

<span data-ttu-id="1c2a2-239">캠페인 세부 정보 보기 중간에 캠페인에 대한 중요한 세부 정보가 가로 흐름 _다이어그램(Sankey_ 다이어그램)에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-239">In the middle of the campaign details view, important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="1c2a2-240">이러한 세부 정보는 캠페인의 요소와 조직에서 발생할 수 있는 영향을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-240">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="1c2a2-241">흐름 다이어그램에 표시되는 정보는 이전 섹션에 설명된 바와 같이 시간 표시 막대의 날짜 범위 필터에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-241">The information that's displayed in the flow diagram is controlled by the date range filter in the timeline as described in the previous section.</span></span>

![사용자 URL 클릭을 포함하지 않는 캠페인 세부 정보](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="1c2a2-243">다이어그램에서 가로 밴드에 마우스를 올리면 관련 메시지 수(예: 특정 원본 IP의 메시지, 지정된 보낸 사람 도메인을 사용하는 원본 IP의 메시지)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-243">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="1c2a2-244">흐름도에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-244">The diagram contains the following information:</span></span>

- <span data-ttu-id="1c2a2-245">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-245">**Sender IPs**</span></span>
- <span data-ttu-id="1c2a2-246">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-246">**Sender domains**</span></span>
- <span data-ttu-id="1c2a2-247">**필터 판정:** 판정 값은 스팸 방지 메시지 헤더에 설명된 바와 같이 사용 가능한 피싱 및 스팸 필터링 [판정과 관련이 있습니다.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-247">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="1c2a2-248">사용 가능한 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-248">The available values are described in the following table:</span></span>

  <br>

  ****

  |<span data-ttu-id="1c2a2-249">값</span><span class="sxs-lookup"><span data-stu-id="1c2a2-249">Value</span></span>|<span data-ttu-id="1c2a2-250">스팸 필터 판정</span><span class="sxs-lookup"><span data-stu-id="1c2a2-250">Spam filter verdict</span></span>|<span data-ttu-id="1c2a2-251">설명</span><span class="sxs-lookup"><span data-stu-id="1c2a2-251">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="1c2a2-252">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-252">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="1c2a2-253">메시지가 스팸 필터링에 의해 평가되기 전에 스팸 및/또는 건너뛴 필터링으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-253">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="1c2a2-254">예를 들어 메시지는 메일 흐름 규칙(전송 규칙)에 의해 스팸이 아닌 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-254">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="1c2a2-255">다른 이유로 메시지에서 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-255">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="1c2a2-256">예를 들어 보낸 사람 및 받는 사람이 같은 조직에 있는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-256">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="1c2a2-257">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-257">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="1c2a2-258">메시지가 스팸 필터링에 의해 평가되기 전에 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-258">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="1c2a2-259">예를 들어 메일 흐름 규칙에 의해</span><span class="sxs-lookup"><span data-stu-id="1c2a2-259">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="1c2a2-260">**감지함**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-260">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="1c2a2-261">메시지가 스팸 필터링에 의해 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-261">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="1c2a2-262">**검색되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-262">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="1c2a2-263">메시지가 스팸 필터링에 의해 스팸이 아닌 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-263">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="1c2a2-264">**릴리스**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-264">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="1c2a2-265">메시지가 스팸 필터링에서 릴리스되어 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-265">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="1c2a2-266">**테넌트 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-266">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="1c2a2-267">스팸 방지 정책의 설정 때문에 메시지가 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-267">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="1c2a2-268">예를 들어 보낸 사람이 허용된 보낸 사람 목록 또는 허용된 도메인 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-268">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="1c2a2-269">**테넌트 차단**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-269">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="1c2a2-270">스팸 방지 정책의 설정 때문에 메시지가 스팸 필터링에 의해 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-270">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="1c2a2-271">예를 들어 보낸 사람이 허용된 보낸 사람 목록 또는 허용된 도메인 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-271">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="1c2a2-272">**사용자 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-272">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="1c2a2-273">보낸 사람이 사용자의 수신- 보낸 사람 목록에 있기 때문에 메시지에서 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-273">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="1c2a2-274">**사용자 차단**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-274">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="1c2a2-275">보낸 사람이 사용자의 수신 차단된 보낸 사람 목록에 있기 때문에 메시지가 스팸 필터링에 의해 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-275">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="1c2a2-276">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-276">**ZAP**</span></span>|<span data-ttu-id="1c2a2-277">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1c2a2-277">n/a</span></span>|<span data-ttu-id="1c2a2-278">[ZAP(제로](zero-hour-auto-purge.md) 아워 자동 제거)는 배달된 메시지를 정크 메일 폴더 또는 검역소로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-278">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="1c2a2-279">스팸 방지 정책에서 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-279">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="1c2a2-280"><sup>\*</sup> 허용된 메시지가 서비스에 의해 차단될 가능성이 높기 때문에 스팸 방지 정책을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-280"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="1c2a2-281"><sup>\*\*</sup> 스팸 방지 정책을 검토합니다. 이러한 메시지는 배달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-281"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="1c2a2-282">**메시지 대상:** 사용자가 메시지의 페이로드 URL을 클릭하지 않았어도 받은 편지함 또는 정크 메일 폴더로 배달된 메시지를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-282">**Message destinations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="1c2a2-283">또한 검지에서 분리된 메시지를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-283">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="1c2a2-284">자세한 내용은 [EOP에서 Quarantined email messages를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-284">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="1c2a2-285">**폴더 삭제됨**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-285">**Deleted folder**</span></span>
  - <span data-ttu-id="1c2a2-286">**삭제**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-286">**Dropped**</span></span>
  - <span data-ttu-id="1c2a2-287">**외부:** 받는 사람이 하이브리드 환경의 사내 전자 메일 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-287">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="1c2a2-288">**실패**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-288">**Failed**</span></span>
  - <span data-ttu-id="1c2a2-289">**전달**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-289">**Forwarded**</span></span>
  - <span data-ttu-id="1c2a2-290">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-290">**Inbox**</span></span>
  - <span data-ttu-id="1c2a2-291">**정크 메일 폴더**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-291">**Junk folder**</span></span>
  - <span data-ttu-id="1c2a2-292">**격리**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-292">**Quarantine**</span></span>
  - <span data-ttu-id="1c2a2-293">**알 수 없음**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-293">**Unknown**</span></span>

- <span data-ttu-id="1c2a2-294">**URL 클릭:** 이러한 값은 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-294">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="1c2a2-295">10개가 넘는 항목이 포함된 모든 계층에는 상위 10개 항목이 표시된 반면 나머지 항목은 기타 에 **번들로 묶입니다.**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-295">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="1c2a2-296">URL 클릭</span><span class="sxs-lookup"><span data-stu-id="1c2a2-296">URL clicks</span></span>

<span data-ttu-id="1c2a2-297">피싱 메시지가 받는 사람의 받은 편지함 또는 정크 메일 폴더로 배달되는 경우 항상 사용자가 페이로드 URL을 클릭할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-297">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="1c2a2-298">URL을 클릭하지 않는 것은 성공의 작은 측정값이지만 피싱 메시지가 사서함으로 배달된 이유를 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-298">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="1c2a2-299">사용자가 피싱 메시지의 페이로드 URL을 클릭하면 캠페인 세부 정보 보기에 있는 **다이어그램의 URL** 클릭 영역에 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-299">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="1c2a2-300">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-300">**Allowed**</span></span>
- <span data-ttu-id="1c2a2-301">**BlockPage:** 받는 사람이 페이로드 URL을 클릭했지만 조직의 안전한 링크 정책에 [](safe-links.md) 의해 악의적인 웹 사이트에 대한 액세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-301">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="1c2a2-302">**BlockPageOverride:** 받는 사람이 메시지의 페이로드 URL을 클릭했으나 안전한 링크에서 해당 URL을 중지하려고 했지만 차단을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-302">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="1c2a2-303">안전한 링크 [정책을 검사하여](set-up-safe-links-policies.md) 사용자가 안전한 링크 판정을 어버렸다가 악의적인 웹 사이트로 계속 진행할 수 있는 이유를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-303">Inspect your [Safe Links policies](set-up-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="1c2a2-304">**PendingDetonationPage:** Microsoft Defender의 안전한 첨부 Office 365 가상 컴퓨터 환경에서 페이로드 URL을 열고 조사하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-304">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="1c2a2-305">**PendingDetonationPageOverride:** 받는 사람이 페이로드 검색 프로세스를 다시 정하고 결과를 기다리지 않고 URL을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-305">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="1c2a2-306">탭</span><span class="sxs-lookup"><span data-stu-id="1c2a2-306">Tabs</span></span>

<span data-ttu-id="1c2a2-307">캠페인 세부 정보 보기의 탭을 사용하면 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-307">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="1c2a2-308">탭에 표시되는 정보는 캠페인 정보 섹션에 설명된 바와 같이 타임라인의 날짜 범위 필터에 [의해 제어됩니다.](#campaign-information)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-308">The information that's displayed on the tabs is controlled by the date range filter in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="1c2a2-309">**URL 클릭:** 사용자가 메시지의 페이로드 URL을 클릭하지 않은 경우 이 섹션은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-309">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="1c2a2-310">사용자가 URL을 클릭할 수 있는 경우 다음 값이 채워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-310">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="1c2a2-311">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-311">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="1c2a2-312">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-312">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="1c2a2-313">**클릭 시간**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-313">**Click time**</span></span>
  - <span data-ttu-id="1c2a2-314">**Click verdict**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-314">**Click verdict**</span></span>

- <span data-ttu-id="1c2a2-315">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-315">**Sender IPs**</span></span>
  - <span data-ttu-id="1c2a2-316">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-316">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="1c2a2-317">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-317">**Total count**</span></span>
  - <span data-ttu-id="1c2a2-318">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-318">**Inboxed**</span></span>
  - <span data-ttu-id="1c2a2-319">**받은 편지함 아미기**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-319">**Not Inboxed**</span></span>
  - <span data-ttu-id="1c2a2-320">**SPF 전달:** 보낸 사람이 [SPF(Sender Policy](how-office-365-uses-spf-to-prevent-spoofing.md)Framework)에 의해 인증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-320">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="1c2a2-321">SPF 유효성 검사를 통과하지 않은 보낸 사람이 확인되지 않은 보낸 사람 또는 메시지가 합법적인 보낸 사람 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-321">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="1c2a2-322">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-322">**Senders**</span></span>
  - <span data-ttu-id="1c2a2-323">**보낸 사람:** SMTP MAIL FROM 명령의 실제 보낸 사람 주소로, 사용자가 전자 메일 클라이언트에 표시하는 보낸 사람: 전자 메일 주소가 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-323">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="1c2a2-324">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-324">**Total count**</span></span>
  - <span data-ttu-id="1c2a2-325">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-325">**Inboxed**</span></span>
  - <span data-ttu-id="1c2a2-326">**받은 편지함 아미기**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-326">**Not Inboxed**</span></span>
  - <span data-ttu-id="1c2a2-327">**DKIM 통과:** 보낸 사람이 [DKIM(Domain Keys Identified Mail)에 의해 인증되었습니다.](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-327">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="1c2a2-328">DKIM 유효성 검사를 통과하지 않은 보낸 사람이 확인되지 않은 보낸 사람 또는 메시지가 합법적인 보낸 사람 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-328">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="1c2a2-329">**DMARC 전달:** 보낸 사람이 도메인 기반 메시지 인증, 보고 및 [적합성(DMARC)에 의해 인증됩니다.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a2-329">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="1c2a2-330">DMARC 유효성 검사를 통과하지 않은 보낸 사람이 확인되지 않은 보낸 사람 또는 메시지가 합법적인 보낸 사람 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-330">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="1c2a2-331">**첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-331">**Attachments**</span></span>
  - <span data-ttu-id="1c2a2-332">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-332">**Filename**</span></span>
  - <span data-ttu-id="1c2a2-333">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-333">**SHA256**</span></span>
  - <span data-ttu-id="1c2a2-334">**맬웨어 패밀리**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-334">**Malware family**</span></span>
  - <span data-ttu-id="1c2a2-335">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-335">**Total count**</span></span>

- <span data-ttu-id="1c2a2-336">**URL**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-336">**URL**</span></span>
  - <span data-ttu-id="1c2a2-337">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1c2a2-337">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="1c2a2-338">**합계**</span><span class="sxs-lookup"><span data-stu-id="1c2a2-338">**Total Count**</span></span>

<span data-ttu-id="1c2a2-339"><sup>\*</sup>이 값을 클릭하면 캠페인 세부 정보 보기 위쪽에 지정된 항목(사용자, URL 등)에 대한 자세한 정보가 포함된 플라이 아웃이 새로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-339"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="1c2a2-340">캠페인 세부 정보 보기로 돌아가려면 새 플라이 아웃에서 **완료** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-340">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="1c2a2-341">버튼</span><span class="sxs-lookup"><span data-stu-id="1c2a2-341">Buttons</span></span>

<span data-ttu-id="1c2a2-342">캠페인 세부 정보 보기 아래쪽에 있는 단추를 사용하면 캠페인에 대한 세부 정보를 조사하고 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-342">The buttons at the bottom the campaign details view allow you to investigate and record details about the campaign:</span></span>

- <span data-ttu-id="1c2a2-343">**메시지 탐색:** 위협 탐색기 기능을 사용하여 캠페인을 더 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-343">**Explore messages**: Use the power of Threat Explorer to further investigate the campaign:</span></span>
  - <span data-ttu-id="1c2a2-344">**모든 메시지:** 캠페인 **ID** 값을 검색 필터로 사용하여 새 위협 탐색기 검색 탭을 니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-344">**All messages**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
  - <span data-ttu-id="1c2a2-345">**받은 편지함 메시지:** 캠페인 **ID** 및 배달 **위치:** 받은 편지함을 검색 필터로 사용하여 새 위협 탐색기 검색 탭을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="1c2a2-345">**Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
  - <span data-ttu-id="1c2a2-346">**내부 메시지:** 캠페인 **ID** 및 방향: 검색 필터로 **반(Intra-org)를** 사용하여 새 위협 탐색기 검색 탭을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-346">**Internal messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Directionality: Intra-org** as the search filter.</span></span>

- <span data-ttu-id="1c2a2-347">**위협 보고서 다운로드:** 캠페인 세부 정보를 Word 문서에 다운로드합니다(기본적으로 CampaignReport.docx.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-347">**Download threat report**: Download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="1c2a2-348">다운로드에는 선택한 필터 날짜만이 아니라 캠페인의 전체 수명에 대한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c2a2-348">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>
