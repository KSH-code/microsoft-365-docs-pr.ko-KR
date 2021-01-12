---
title: Microsoft Defender for Office 365 계획의 캠페인 보기
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
- m365initiative-defender-office365
description: Office 365용 Microsoft Defender의 캠페인 보기에 대해 자세히 알아보습니다.
ms.openlocfilehash: 20cb50a4b304e148df24e54fac3a05c484cfa4f0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794367"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0f868-103">Office 365용 Microsoft Defender의 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="0f868-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0f868-104">캠페인 보기는 Microsoft Defender for Office 365 계획 2의 기능입니다(예: Microsoft 365 E5 또는 Office 365 계획 2 추가 기능이 있는 조직).</span><span class="sxs-lookup"><span data-stu-id="0f868-104">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="0f868-105">보안 및 준수 & 보안 센터의 캠페인 보기는 서비스에서 피싱 공격을 식별하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="0f868-106">캠페인 보기를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="0f868-107">피싱 공격을 효과적으로 조사하고 이에 대처합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="0f868-108">공격의 범위를 더 잘 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="0f868-109">의사 결정자에게 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-109">Show value to decision makers.</span></span>

<span data-ttu-id="0f868-110">캠페인 보기를 그 누구보다 빠르고 완벽하게 공격의 전체적인 상황을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="0f868-111">캠페인이란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="0f868-111">What is a campaign?</span></span>

<span data-ttu-id="0f868-112">캠페인은 하나 이상의 조직에 대해 조율된 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="0f868-113">자격 증명 및 회사 데이터를 도용하는 전자 메일 공격은 규모가 크고 유력한 산업입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="0f868-114">공격자가 공격을 중지하기 위한 노력이 증가하면 공격자는 계속 성공하기 위해 방법을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="0f868-115">Microsoft는 전체 서비스에서 방대한 양의 피싱 방지, 스팸 방지 및 맬웨어 방지 데이터를 활용하여 캠페인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="0f868-116">여러 요인에 따라 공격 정보를 분석하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="0f868-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-117">For example:</span></span>

- <span data-ttu-id="0f868-118">**공격 원본**: 원본 IP 주소 및 보낸 사람 전자 메일 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="0f868-119">**메시지 속성:** 메시지의 콘텐츠, 스타일 및 톤입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="0f868-120">**메시지 받는 사람:** 받는 사람 관련 방법</span><span class="sxs-lookup"><span data-stu-id="0f868-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="0f868-121">예를 들어 받는 사람 도메인, 받는 사람 작업 기능(관리자, 임원 등), 회사 유형(대규모, 소규모, 공용, 개인 등) 및 산업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="0f868-122">**공격 페이로드**: 메시지의 악성 링크, 첨부 파일 또는 기타 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="0f868-123">캠페인은 수명이 짧거나 활성 및 비활성 기간이 있는 며칠, 주 또는 몇 달에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="0f868-124">특정 조직에 대해 캠페인이 시작되거나 조직이 여러 회사에서 대규모 캠페인에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="0f868-125">보안 및 준수 & 캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="0f868-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="0f868-126">캠페인 보기는 위협 관리 [캠페인의](https://protection.office.com) 보안  & 준수 센터에서 또는 직접 사용할 \> 수 <https://protection.office.com/campaigns> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![보안 및 규정 준수 센터의 캠페인 개요](../../media/campaigns-overview.png)

<span data-ttu-id="0f868-128">다음에서 캠페인 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="0f868-129">**위협 관리** \> **탐색기** \> **보기** \> **캠페인**</span><span class="sxs-lookup"><span data-stu-id="0f868-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="0f868-130">**위협 관리** \> **탐색기** \> **보기** \> **모든 전자 메일** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="0f868-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="0f868-131">**위협 관리** \> **탐색기** \> **보기** \> **피싱** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="0f868-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="0f868-132">**위협 관리** \> **탐색기** \> **보기** \> **맬웨어** \> **캠페인** 탭</span><span class="sxs-lookup"><span data-stu-id="0f868-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="0f868-133">캠페인 보기에 액세스하려면 Security & 준수 센터에서 조직 관리, 보안 관리자 또는 보안 읽기 권한자 역할 그룹의 구성원 & 합니다. </span><span class="sxs-lookup"><span data-stu-id="0f868-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="0f868-134">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f868-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="0f868-135">캠페인 개요</span><span class="sxs-lookup"><span data-stu-id="0f868-135">Campaigns overview</span></span>

<span data-ttu-id="0f868-136">개요 페이지에는 모든 캠페인에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="0f868-137">기본 **캠페인** 탭에서  캠페인 유형 영역에는 하루 받는 사람 수를 보여 주며 막대 그래프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="0f868-138">기본적으로 그래프에는 **피싱** 데이터와 맬웨어 **데이터가 모두 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="0f868-139">캠페인 데이터가 없는 경우 날짜 범위 또는 필터를 [변경해 봐야 합니다.](#filters-and-settings)</span><span class="sxs-lookup"><span data-stu-id="0f868-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="0f868-140">개요 페이지의 나머지 섹션에는 캠페인 탭에 다음 **정보가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="0f868-141">**이름**</span><span class="sxs-lookup"><span data-stu-id="0f868-141">**Name**</span></span>

- <span data-ttu-id="0f868-142">**샘플 제목**: 캠페인의 메시지 중 하나에 대한 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="0f868-143">캠페인의 모든 메시지에 제목이 같을 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="0f868-144">**대상:** 계산된 비율: (조직의 캠페인 받는 사람 수) / (서비스의 모든 조직에서 캠페인의 총 받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="0f868-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="0f868-145">이 값은 캠페인이 조직을 위해 진행되는 수준(더 높은 값)과 서비스의 다른 조직(더 낮은 값)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="0f868-146">**형식**: 이 값은 **피싱** 또는 맬웨어입니다. </span><span class="sxs-lookup"><span data-stu-id="0f868-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="0f868-147">**하위 스타일**: 이 값에는 캠페인에 대한 자세한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="0f868-148">예제:</span><span class="sxs-lookup"><span data-stu-id="0f868-148">For example:</span></span>
  - <span data-ttu-id="0f868-149">**피싱**: 사용 가능한 경우 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="0f868-150">예를 들면 `Microsoft` 다음과 `365` `Unknown` `Outlook` `DocuSign` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="0f868-151">**맬웨어**: 예: `HTML/PHISH` `HTML/<MalwareFamilyName>` 또는 .</span><span class="sxs-lookup"><span data-stu-id="0f868-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="0f868-152">사용 가능한 경우 이 캠페인에 의해 피싱되는 브랜드입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="0f868-153">검색이 Office 365용 Defender 기술에 의해 구동되는 경우 **ATP-는** 하위타임 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-153">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="0f868-154">**받는 사람**: 이 캠페인을 대상으로 하는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="0f868-155">**받은 편지함:** 받은 편지함에서 이 캠페인에서 메시지를 받은 사용자 수입니다(정크 메일 폴더로 배달되지).</span><span class="sxs-lookup"><span data-stu-id="0f868-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="0f868-156">**클릭한** 사용자: URL을 클릭하거나 피싱 메시지에서 첨부 파일을 연 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="0f868-157">**클릭률**: " 클릭한 받은 **편지함"으로 계산된**  /  **백분율입니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="0f868-158">이 값은 캠페인의 효율성을 나타내는 지표입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="0f868-159">즉, 받는 사람이 메시지를 피싱으로 식별할 수 있으며 페이로드 URL을 클릭하지 않은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="0f868-160">**클릭률은** 맬웨어 캠페인에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="0f868-161">**방문:** 페이로드 웹 사이트를 통해 실제로 만든 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="0f868-162">클릭한  값이 있지만 안전한 링크로 웹 사이트에 대한 액세스가 차단된 경우 이 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="0f868-163">캠페인 **시작 탭에는** 세계 지도의 메시지 원본이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="0f868-164">필터 및 설정</span><span class="sxs-lookup"><span data-stu-id="0f868-164">Filters and settings</span></span>

<span data-ttu-id="0f868-165">캠페인 보기 페이지의 맨 위에는 특정 캠페인을 찾아 격리하는 데 도움이 되는 몇 가지 필터 및 쿼리 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![캠페인 필터](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="0f868-167">가장 기본적인 필터링은 시작 날짜/시간 및 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="0f868-168">보기를 추가로 필터링하려면 캠페인 유형 단추를 클릭하고 선택한  다음 새로 고침을 클릭하여 여러 값을 필터링하여 단일 속성을 필터링할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="0f868-169">캠페인 유형 단추에서 사용할 수  있는 필터링할 수 있는 캠페인 속성은 다음 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-169">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="0f868-170">**기본**:</span><span class="sxs-lookup"><span data-stu-id="0f868-170">**Basic**:</span></span>
  - <span data-ttu-id="0f868-171">**캠페인 유형:** **맬웨어 또는** **피싱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="0f868-172">선택을 지우면 두 가지를 선택하는 결과와 결과가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="0f868-173">**캠페인 이름**</span><span class="sxs-lookup"><span data-stu-id="0f868-173">**Campaign name**</span></span>
  - <span data-ttu-id="0f868-174">**캠페인 하위타이프**</span><span class="sxs-lookup"><span data-stu-id="0f868-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="0f868-175">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="0f868-175">**Sender**</span></span>
  - <span data-ttu-id="0f868-176">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="0f868-176">**Recipients**</span></span>
  - <span data-ttu-id="0f868-177">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="0f868-177">**Sender domain**</span></span>
  - <span data-ttu-id="0f868-178">**제목**</span><span class="sxs-lookup"><span data-stu-id="0f868-178">**Subject**</span></span>
  - <span data-ttu-id="0f868-179">**첨부 파일 이름**</span><span class="sxs-lookup"><span data-stu-id="0f868-179">**Attachment filename**</span></span>
  - <span data-ttu-id="0f868-180">**맬웨어 패밀리**</span><span class="sxs-lookup"><span data-stu-id="0f868-180">**Malware family**</span></span>
  - <span data-ttu-id="0f868-181">**태그:** 지정된 사용자 태그가 적용된 사용자 또는 그룹(우선 순위 계정 포함)</span><span class="sxs-lookup"><span data-stu-id="0f868-181">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0f868-182">사용자 태그에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0f868-182">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="0f868-183">**시스템 오버라이드**</span><span class="sxs-lookup"><span data-stu-id="0f868-183">**System overrides**</span></span>
  - <span data-ttu-id="0f868-184">**배달 작업**</span><span class="sxs-lookup"><span data-stu-id="0f868-184">**Delivery action**</span></span>
  - <span data-ttu-id="0f868-185">**추가 작업**</span><span class="sxs-lookup"><span data-stu-id="0f868-185">**Additional action**</span></span>
  - <span data-ttu-id="0f868-186">**방향**</span><span class="sxs-lookup"><span data-stu-id="0f868-186">**Directionality**</span></span>
  - <span data-ttu-id="0f868-187">**검색 기술**</span><span class="sxs-lookup"><span data-stu-id="0f868-187">**Detection technology**</span></span>
  - <span data-ttu-id="0f868-188">**원래 배달 위치**</span><span class="sxs-lookup"><span data-stu-id="0f868-188">**Original delivery location**</span></span>
  - <span data-ttu-id="0f868-189">**최신 배달 위치**</span><span class="sxs-lookup"><span data-stu-id="0f868-189">**Latest delivery location**</span></span>
  - <span data-ttu-id="0f868-190">**시스템 오버라이드**</span><span class="sxs-lookup"><span data-stu-id="0f868-190">**System overrides**</span></span>

- <span data-ttu-id="0f868-191">**고급**:</span><span class="sxs-lookup"><span data-stu-id="0f868-191">**Advanced**:</span></span>
  - <span data-ttu-id="0f868-192">**인터넷 메시지 ID:** 메시지 헤더의 **메시지-ID** 헤더 필드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-192">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="0f868-193">값의 예로는 괄호를 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-193">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="0f868-194">**네트워크 메시지 ID:** 메시지 헤더의 **X-MS-Exchange-Organization-Network-Message-Id** 헤더 필드에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-194">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="0f868-195">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="0f868-195">**Sender IP**</span></span>
  - <span data-ttu-id="0f868-196">**첨부 파일 SHA256:** Windows에서 파일의 SHA256 해시 값을 찾으면 명령 프롬프트에서 다음 명령을 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-196">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="0f868-197">**클러스터 ID**</span><span class="sxs-lookup"><span data-stu-id="0f868-197">**Cluster ID**</span></span>
  - <span data-ttu-id="0f868-198">**경고 정책 ID**</span><span class="sxs-lookup"><span data-stu-id="0f868-198">**Alert Policy ID**</span></span>
  - <span data-ttu-id="0f868-199">**ZAP URL 신호**</span><span class="sxs-lookup"><span data-stu-id="0f868-199">**ZAP URL signal**</span></span>

- <span data-ttu-id="0f868-200">**URL**:</span><span class="sxs-lookup"><span data-stu-id="0f868-200">**URLs**:</span></span>
  - <span data-ttu-id="0f868-201">**URL 도메인**</span><span class="sxs-lookup"><span data-stu-id="0f868-201">**URL domain**</span></span>
  - <span data-ttu-id="0f868-202">**URL 도메인 및 경로**</span><span class="sxs-lookup"><span data-stu-id="0f868-202">**URL domain and path**</span></span>
  - <span data-ttu-id="0f868-203">**URL**</span><span class="sxs-lookup"><span data-stu-id="0f868-203">**URL**</span></span>
  - <span data-ttu-id="0f868-204">**URL 경로**</span><span class="sxs-lookup"><span data-stu-id="0f868-204">**URL path**</span></span>
  - <span data-ttu-id="0f868-205">**Click verdict**</span><span class="sxs-lookup"><span data-stu-id="0f868-205">**Click verdict**</span></span>

<span data-ttu-id="0f868-206">여러 속성에 대한 필터링을 비롯한 고급 필터링의  경우 고급 필터 단추를 클릭하여 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-206">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="0f868-207">동일한 캠페인 속성을 사용할 수 있지만 다음과 같은 향상된 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-207">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="0f868-208">조건 추가를 **클릭하여 여러** 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-208">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="0f868-209">조건 간에 **And** 또는 **Or** 연산자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-209">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="0f868-210">조건 목록 **아래쪽에** 있는 조건 그룹 항목을 선택하여 복잡한 복합 조건을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-210">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="0f868-211">완료되면 쿼리 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-211">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="0f868-212">기본 필터나 고급 필터를 만든 후 쿼리  저장 또는 쿼리 저장을 사용하여 필터를 저장할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-212">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="0f868-213">나중에 캠페인 보기로 돌아오면 저장된 쿼리 설정을 클릭하여 저장된 필터를 **로드할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-213">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="0f868-214">그래프 또는 캠페인 목록을 내보내려면 내보내기 및  **차트** 데이터 내보내기 또는 캠페인 **목록 내보내기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-214">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="0f868-215">Endpoint용 Microsoft Defender 구독이 있는 경우 **MDE** 설정을 클릭하여 끝점용 Microsoft Defender를 사용하여 캠페인 정보를 연결하거나 연결을 끊을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-215">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0f868-216">자세한 내용은 [끝점용 Microsoft Defender와 Office 365용 Microsoft Defender 통합을 참조하세요.](integrate-office-365-ti-with-wdatp.md)</span><span class="sxs-lookup"><span data-stu-id="0f868-216">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="0f868-217">캠페인 세부 정보</span><span class="sxs-lookup"><span data-stu-id="0f868-217">Campaign details</span></span>

<span data-ttu-id="0f868-218">캠페인 이름을 클릭하면 캠페인 세부 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-218">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="0f868-219">캠페인 정보</span><span class="sxs-lookup"><span data-stu-id="0f868-219">Campaign information</span></span>

<span data-ttu-id="0f868-220">캠페인 세부 정보 보기 맨 위에 다음 캠페인 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-220">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="0f868-221">**ID**: 고유한 캠페인 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-221">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="0f868-222">**시작 및** **종료:** 캠페인의 시작 날짜 및 종료 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-222">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="0f868-223">이러한 날짜는 개요 페이지에서 선택한 필터 날짜보다 더 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-223">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="0f868-224">**영향:** 이 섹션에는 선택한 날짜 범위 필터(또는 시간 표시 막대에서 선택한 날짜 범위)에 대한 다음 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-224">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  - <span data-ttu-id="0f868-225">총 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-225">The total number of recipients.</span></span>
  - <span data-ttu-id="0f868-226">"받은 편지함"(즉, 정크 메일 폴더가 아닌 받은 편지함으로 배달) 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-226">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="0f868-227">피싱 메시지의 URL 페이로드를 클릭한 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-227">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="0f868-228">URL을 방문한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="0f868-228">Howe many users visited the URL.</span></span>

- <span data-ttu-id="0f868-229">**대상:** 계산된 비율: (조직의 캠페인 받는 사람 수) / (서비스의 모든 조직에서 캠페인의 총 받는 사람 수)</span><span class="sxs-lookup"><span data-stu-id="0f868-229">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="0f868-230">이 값은 캠페인의 전체 수명 동안 계산하며 날짜 필터에 따라 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-230">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="0f868-231">캠페인 활동의 대화형 타임라인: 타임라인에는 캠페인의 전체 수명 동안 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-231">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="0f868-232">기본적으로 음영 처리된 영역에는 개요에서 선택한 날짜 범위 필터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-232">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="0f868-233">클릭하고 끌어서 영향 영역에 표시되는 데이터를 변경하는 특정 시작점과 끝점을 선택할 수 있으며, 다음 섹션에 설명된 바와 같이 페이지의 나머지 부분에서 <u>변경됩니다.  </u></span><span class="sxs-lookup"><span data-stu-id="0f868-233">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="0f868-234">제목 표시줄에서 캠페인 쓰기  다운로드 단추 다운로드 캠페인 쓰기 아이콘을 클릭하여 캠페인 세부 정보를 Word 문서(기본적으로 CampaignReport.docx)로 다운로드할 수 ![ ](../../media/download-campaign-write-up-button.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-234">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="0f868-235">다운로드에는 선택한 필터 날짜 뿐만 아니라 캠페인의 전체 수명에 대한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-235">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![캠페인 정보](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="0f868-237">캠페인 흐름</span><span class="sxs-lookup"><span data-stu-id="0f868-237">Campaign flow</span></span>

<span data-ttu-id="0f868-238">캠페인 세부 정보 보기 중간에 가로 흐름 _다이어그램(Sankey_ 다이어그램)의 **흐름** 섹션에 캠페인에 대한 중요한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-238">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="0f868-239">이러한 세부 정보는 캠페인의 요소와 조직에서 발생할 수 있는 영향을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-239">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="0f868-240">흐름 다이어그램에 표시되는 정보는  이전 섹션에 설명된 바와 같이 시간 표시 막대의 음영 처리된 날짜 범위에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-240">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![사용자 URL 클릭을 포함하지 않는 캠페인 세부 정보](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="0f868-242">다이어그램에서 가로 밴드에 마우스를 올리면 관련 메시지 수(예: 특정 원본 IP의 메시지, 지정된 보낸 사람 도메인을 사용하는 원본 IP의 메시지)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-242">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="0f868-243">흐름도에는 다음과 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-243">The diagram contains the following information:</span></span>

- <span data-ttu-id="0f868-244">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="0f868-244">**Sender IPs**</span></span>
- <span data-ttu-id="0f868-245">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="0f868-245">**Sender domains**</span></span>
- <span data-ttu-id="0f868-246">**필터 판정:** 판정 값은 스팸 방지 메시지 헤더에 설명된 바와 같이 사용 가능한 피싱 및 스팸 필터링 판정과 [관련이 있습니다.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="0f868-246">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="0f868-247">사용 가능한 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-247">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="0f868-248">값</span><span class="sxs-lookup"><span data-stu-id="0f868-248">Value</span></span>|<span data-ttu-id="0f868-249">스팸 필터 판정</span><span class="sxs-lookup"><span data-stu-id="0f868-249">Spam filter verdict</span></span>|<span data-ttu-id="0f868-250">설명</span><span class="sxs-lookup"><span data-stu-id="0f868-250">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="0f868-251">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="0f868-251">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="0f868-252">메시지가 스팸 필터링에 의해 평가되기 전에 스팸이 아닌 것으로 표시되거나 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-252">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="0f868-253">예를 들어 메시지는 메일 흐름 규칙(전송 규칙)에 의해 스팸이 아닌 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-253">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="0f868-254">메시지는 다른 이유로 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-254">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="0f868-255">예를 들어 보낸 사람 및 받는 사람은 같은 조직에 있는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-255">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="0f868-256">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="0f868-256">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="0f868-257">메시지가 스팸 필터링에 의해 평가되기 전에 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-257">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="0f868-258">예를 들어 메일 흐름 규칙에 의해 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-258">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="0f868-259">**감지함**</span><span class="sxs-lookup"><span data-stu-id="0f868-259">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="0f868-260">메시지가 스팸 필터링에 의해 스팸으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-260">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="0f868-261">**검색되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-261">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="0f868-262">메시지가 스팸 필터링에 의해 스팸이 아닌 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-262">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="0f868-263">**릴리스**</span><span class="sxs-lookup"><span data-stu-id="0f868-263">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="0f868-264">메시지가 스팸 필터링에서 릴리스되어 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-264">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="0f868-265">**테넌트 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-265">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="0f868-266">스팸 방지 정책의 설정 때문에 메시지가 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-266">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="0f868-267">예를 들어 보낸 사람이 허용된 보낸 사람 목록 또는 허용된 도메인 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-267">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="0f868-268">**테넌트 블록**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-268">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="0f868-269">스팸 방지 정책의 설정 때문에 메시지가 스팸 필터링에 의해 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-269">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="0f868-270">예를 들어 보낸 사람이 허용된 보낸 사람 목록 또는 허용된 도메인 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-270">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="0f868-271">**사용자 허용**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-271">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="0f868-272">보낸 사람이 사용자의 수신 수신 -보낸 사람 목록에 있기 때문에 메시지가 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-272">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="0f868-273">**사용자 차단**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-273">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="0f868-274">보낸 사람이 사용자의 수신 차단된 보낸 사람 목록에 있기 때문에 메시지가 스팸 필터링에 의해 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-274">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="0f868-275">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="0f868-275">**ZAP**</span></span>|<span data-ttu-id="0f868-276">해당 없음</span><span class="sxs-lookup"><span data-stu-id="0f868-276">n/a</span></span>|<span data-ttu-id="0f868-277">[ZAP(제로](zero-hour-auto-purge.md) 아워 자동 비우기)는 배달된 메시지를 정크 메일 폴더 또는 정크 메일 폴더로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-277">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="0f868-278">스팸 방지 정책에서 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-278">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="0f868-279"><sup>\*</sup> 허용된 메시지가 서비스에 의해 차단될 가능성이 높기 때문에 스팸 방지 정책을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-279"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="0f868-280"><sup>\*\*</sup> 스팸 방지 정책을 검토합니다. 이러한 메시지는 배달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-280"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="0f868-281">**배달 위치:** 사용자가 메시지의 페이로드 URL을 클릭하지 않은 경우에도 받은 편지함 또는 정크 메일 폴더로 배달된 메시지를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-281">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="0f868-282">또한 분리된 메시지를 분리된 메시지에서 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-282">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="0f868-283">자세한 내용은 [EOP에서 Quarantined 전자 메일 메시지를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="0f868-283">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="0f868-284">**폴더 삭제됨**</span><span class="sxs-lookup"><span data-stu-id="0f868-284">**Deleted folder**</span></span>
  - <span data-ttu-id="0f868-285">**삭제**</span><span class="sxs-lookup"><span data-stu-id="0f868-285">**Dropped**</span></span>
  - <span data-ttu-id="0f868-286">**외부**: 받는 사람이 하이브리드 환경의 전자 메일 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-286">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="0f868-287">**실패**</span><span class="sxs-lookup"><span data-stu-id="0f868-287">**Failed**</span></span>
  - <span data-ttu-id="0f868-288">**전달된 경우**</span><span class="sxs-lookup"><span data-stu-id="0f868-288">**Forwarded**</span></span>
  - <span data-ttu-id="0f868-289">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="0f868-289">**Inbox**</span></span>
  - <span data-ttu-id="0f868-290">**정크 메일 폴더**</span><span class="sxs-lookup"><span data-stu-id="0f868-290">**Junk folder**</span></span>
  - <span data-ttu-id="0f868-291">**격리**</span><span class="sxs-lookup"><span data-stu-id="0f868-291">**Quarantine**</span></span>
  - <span data-ttu-id="0f868-292">**알 수 없음**</span><span class="sxs-lookup"><span data-stu-id="0f868-292">**Unknown**</span></span>

- <span data-ttu-id="0f868-293">**URL 클릭**: 다음 섹션에서 이러한 값에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-293">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="0f868-294">항목이 10개 이상 포함된 모든 계층에는 상위 10개 항목이 표시된 반면 나머지 항목은 다른 계층에서 번들로 **묶입니다.**</span><span class="sxs-lookup"><span data-stu-id="0f868-294">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="0f868-295">URL 클릭</span><span class="sxs-lookup"><span data-stu-id="0f868-295">URL clicks</span></span>

<span data-ttu-id="0f868-296">피싱 메시지가 받는 사람의 받은 편지함 또는 정크 메일 폴더로 배달되는 경우 사용자가 페이로드 URL을 클릭할 가능성이 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-296">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="0f868-297">URL을 클릭하지 않는 것은 성공의 측정값이지만 피싱 메시지가 사서함으로 배달된 이유를 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-297">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="0f868-298">사용자가 피싱 메시지의 페이로드 URL을 클릭하면 캠페인 세부 정보 보기에 **다이어그램의 URL** 클릭 영역에 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-298">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="0f868-299">**허용됨**</span><span class="sxs-lookup"><span data-stu-id="0f868-299">**Allowed**</span></span>
- <span data-ttu-id="0f868-300">**BlockPage:** 받는 사람이 페이로드 URL을 클릭했지만 악의적인 웹 사이트에 [](atp-safe-links.md) 대한 액세스가 조직의 안전 링크 정책에 의해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-300">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="0f868-301">**BlockPageOverride:** 받는 사람이 메시지의 페이로드 URL을 클릭했으나 안전한 링크에서 해당 URL을 중지하려고 했지만 차단을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-301">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="0f868-302">안전한 링크 [정책을](set-up-atp-safe-links-policies.md) 검사하여 사용자가 안전한 링크 판정을 의회하고 악의적인 웹 사이트로 계속 진행하도록 허용된 이유를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f868-302">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="0f868-303">**PendingDetonationPage:** Office 365용 Microsoft Defender의 안전한 첨부 파일은 가상 컴퓨터 환경에서 페이로드 URL을 열고 조사하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-303">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="0f868-304">**PendingDetonationPageOverride:** 받는 사람이 결과를 기다리지 않고 페이로드 검색 프로세스를 재지정하고 URL을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-304">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="0f868-305">탭</span><span class="sxs-lookup"><span data-stu-id="0f868-305">Tabs</span></span>

<span data-ttu-id="0f868-306">캠페인 세부 정보 보기의 탭을 사용하면 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-306">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="0f868-307">탭에 표시되는 정보는 캠페인 정보 섹션에 설명된 타임라인의 음영 처리된 날짜 범위에 [의해 제어됩니다.](#campaign-information)</span><span class="sxs-lookup"><span data-stu-id="0f868-307">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="0f868-308">**URL 클릭:** 사용자가 메시지에서 페이로드 URL을 클릭하지 않은 경우 이 섹션은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-308">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="0f868-309">사용자가 URL을 클릭할 수 있는 경우 다음 값이 채워됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-309">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="0f868-310">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-310">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="0f868-311">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-311">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="0f868-312">**클릭 시간**</span><span class="sxs-lookup"><span data-stu-id="0f868-312">**Click time**</span></span>
  - <span data-ttu-id="0f868-313">**Click verdict**</span><span class="sxs-lookup"><span data-stu-id="0f868-313">**Click verdict**</span></span>

- <span data-ttu-id="0f868-314">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="0f868-314">**Sender IPs**</span></span>
  - <span data-ttu-id="0f868-315">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-315">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="0f868-316">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="0f868-316">**Total count**</span></span>
  - <span data-ttu-id="0f868-317">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="0f868-317">**Inboxed**</span></span>
  - <span data-ttu-id="0f868-318">**받은 편지함 아함**</span><span class="sxs-lookup"><span data-stu-id="0f868-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="0f868-319">**SPF 통과:** 보낸 사람이 [SPF(Sender Policy Framework)에서 인증되었습니다.](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="0f868-319">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="0f868-320">SPF 유효성 검사를 통과하지 않은 보낸 사람이 확인되지 않은 보낸 사람 또는 메시지가 합법적인 보낸 사람에 대한 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-320">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="0f868-321">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="0f868-321">**Senders**</span></span>
  - <span data-ttu-id="0f868-322">**보낸 사람**: 사용자가 전자 메일 클라이언트에 표시하는 보낸 사람: 전자 메일 주소가 아닐 수도 있는 SMTP MAIL FROM 명령의 실제 보낸 사람 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-322">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="0f868-323">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="0f868-323">**Total count**</span></span>
  - <span data-ttu-id="0f868-324">**받은 편지함**</span><span class="sxs-lookup"><span data-stu-id="0f868-324">**Inboxed**</span></span>
  - <span data-ttu-id="0f868-325">**받은 편지함 아함**</span><span class="sxs-lookup"><span data-stu-id="0f868-325">**Not Inboxed**</span></span>
  - <span data-ttu-id="0f868-326">**DKIM 통과:** 보낸 사람이 [DKIM(Domain Keys Identified Mail)에 의해 인증되었습니다.](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="0f868-326">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="0f868-327">DKIM 유효성 검사를 통과하지 않은 보낸 사람이 확인되지 않은 보낸 사람 또는 메시지가 합법적인 보낸 사람에 대한 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-327">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="0f868-328">**DMARC 통과:** 보낸 사람이 도메인 기반 메시지 인증, 보고 및 [적합성(DMARC)에 의해 인증됩니다.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="0f868-328">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="0f868-329">DMARC 유효성 검사를 통과하지 않은 보낸 사람이 확인되지 않은 보낸 사람 또는 메시지가 합법적인 보낸 사람에 대한 스푸핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-329">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="0f868-330">**첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="0f868-330">**Attachments**</span></span>
  - <span data-ttu-id="0f868-331">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="0f868-331">**Filename**</span></span>
  - <span data-ttu-id="0f868-332">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="0f868-332">**SHA256**</span></span>
  - <span data-ttu-id="0f868-333">**맬웨어 패밀리**</span><span class="sxs-lookup"><span data-stu-id="0f868-333">**Malware family**</span></span>
  - <span data-ttu-id="0f868-334">**총 개수**</span><span class="sxs-lookup"><span data-stu-id="0f868-334">**Total count**</span></span>

- <span data-ttu-id="0f868-335">**URL**</span><span class="sxs-lookup"><span data-stu-id="0f868-335">**URL**</span></span>
  - <span data-ttu-id="0f868-336">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0f868-336">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="0f868-337">**합계**</span><span class="sxs-lookup"><span data-stu-id="0f868-337">**Total Count**</span></span>

<span data-ttu-id="0f868-338"><sup>\*</sup>이 값을 클릭하면 캠페인 세부 정보 보기 위쪽에 지정된 항목(사용자, URL 등)에 대한 자세한 정보가 포함된 플라이 아웃이 새로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-338"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="0f868-339">캠페인 세부 정보 보기로 돌아가려면 새 플라이 아웃에서 **완료** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-339">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="0f868-340">버튼</span><span class="sxs-lookup"><span data-stu-id="0f868-340">Buttons</span></span>

<span data-ttu-id="0f868-341">캠페인 세부 정보 보기의 버튼을 통해 위협 탐색기 기능을 사용하여 캠페인을 더 자세히 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-341">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="0f868-342">**캠페인 탐색**: **캠페인 ID** 값을 검색 필터로 사용하여 새로운 위협 탐색기 검색 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-342">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
- <span data-ttu-id="0f868-343">**받은 편지함 메시지** 탐색: 캠페인 **ID** 및 배달 위치를  사용하여 새 위협 탐색기 검색 탭( 받은 편지함을 검색 필터로)을 니다.</span><span class="sxs-lookup"><span data-stu-id="0f868-343">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
