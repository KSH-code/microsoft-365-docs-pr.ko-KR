---
title: 표시기 관리
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시, IP 주소, URL 또는 도메인에 대한 표시기를 관리합니다.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185948"
---
# <a name="manage-indicators"></a><span data-ttu-id="09dea-104">표시기 관리</span><span class="sxs-lookup"><span data-stu-id="09dea-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="09dea-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="09dea-105">**Applies to:**</span></span>
- [<span data-ttu-id="09dea-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="09dea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="09dea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09dea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="09dea-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="09dea-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="09dea-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="09dea-110">탐색 창에서 설정   >  **표시기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09dea-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="09dea-111">관리할 엔터티 유형의 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="09dea-112">표시기 세부 정보를 업데이트하고  목록에서  엔터티를 제거하려면 저장 또는 삭제 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="09dea-113">IoC 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="09dea-113">Import a list of IoCs</span></span>

<span data-ttu-id="09dea-114">표시기 특성, 수행되는 작업 및 기타 세부 정보를 정의하는 CSV 파일을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="09dea-115">지원되는 열 특성을 알고자 샘플 CSV를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="09dea-116">탐색 창에서 설정   >  **표시기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09dea-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="09dea-117">표시기를 가져올 엔터티 유형의 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="09dea-118">파일 **선택**  >  **가져오기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09dea-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="09dea-119">가져오기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09dea-119">Select **Import**.</span></span> <span data-ttu-id="09dea-120">가져오고자 하는 모든 파일에 대해 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="09dea-121">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-121">Select **Done**.</span></span>

<span data-ttu-id="09dea-122">다음 표에는 지원되는 매개 변수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="09dea-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09dea-123">Parameter</span></span> | <span data-ttu-id="09dea-124">유형</span><span class="sxs-lookup"><span data-stu-id="09dea-124">Type</span></span>    |   <span data-ttu-id="09dea-125">설명</span><span class="sxs-lookup"><span data-stu-id="09dea-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="09dea-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="09dea-126">indicatorType</span></span> | <span data-ttu-id="09dea-127">Enum</span><span class="sxs-lookup"><span data-stu-id="09dea-127">Enum</span></span> | <span data-ttu-id="09dea-128">표시기 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-128">Type of the indicator.</span></span> <span data-ttu-id="09dea-129">가능한 값은 "FileSha1", "FileSha256", "IpAddress", "DomainName" 및 "Url"입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="09dea-130">**필수**</span><span class="sxs-lookup"><span data-stu-id="09dea-130">**Required**</span></span>
<span data-ttu-id="09dea-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="09dea-131">indicatorValue</span></span> | <span data-ttu-id="09dea-132">문자열</span><span class="sxs-lookup"><span data-stu-id="09dea-132">String</span></span> | <span data-ttu-id="09dea-133">Indicator [엔터티의 ID입니다.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="09dea-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="09dea-134">**필수**</span><span class="sxs-lookup"><span data-stu-id="09dea-134">**Required**</span></span>
<span data-ttu-id="09dea-135">조치</span><span class="sxs-lookup"><span data-stu-id="09dea-135">action</span></span> | <span data-ttu-id="09dea-136">Enum</span><span class="sxs-lookup"><span data-stu-id="09dea-136">Enum</span></span> | <span data-ttu-id="09dea-137">표시기가 조직에서 검색되는 경우 수행되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="09dea-138">가능한 값은 "Alert", "AlertAndBlock" 및 "Allowed"입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="09dea-139">**필수**</span><span class="sxs-lookup"><span data-stu-id="09dea-139">**Required**</span></span>
<span data-ttu-id="09dea-140">title</span><span class="sxs-lookup"><span data-stu-id="09dea-140">title</span></span> | <span data-ttu-id="09dea-141">문자열</span><span class="sxs-lookup"><span data-stu-id="09dea-141">String</span></span> | <span data-ttu-id="09dea-142">표시기 경고 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-142">Indicator alert title.</span></span> <span data-ttu-id="09dea-143">**필수**</span><span class="sxs-lookup"><span data-stu-id="09dea-143">**Required**</span></span>
<span data-ttu-id="09dea-144">설명</span><span class="sxs-lookup"><span data-stu-id="09dea-144">description</span></span> | <span data-ttu-id="09dea-145">문자열</span><span class="sxs-lookup"><span data-stu-id="09dea-145">String</span></span> |  <span data-ttu-id="09dea-146">표시기 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-146">Description of the indicator.</span></span> <span data-ttu-id="09dea-147">**필수**</span><span class="sxs-lookup"><span data-stu-id="09dea-147">**Required**</span></span>
<span data-ttu-id="09dea-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="09dea-148">expirationTime</span></span> | <span data-ttu-id="09dea-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="09dea-149">DateTimeOffset</span></span> | <span data-ttu-id="09dea-150">YYYY-MM-DDTHH:MM:SS.0Z 형식의 표시기 만료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="09dea-151">**선택**</span><span class="sxs-lookup"><span data-stu-id="09dea-151">**Optional**</span></span>
<span data-ttu-id="09dea-152">심각도</span><span class="sxs-lookup"><span data-stu-id="09dea-152">severity</span></span> | <span data-ttu-id="09dea-153">Enum</span><span class="sxs-lookup"><span data-stu-id="09dea-153">Enum</span></span> | <span data-ttu-id="09dea-154">표시기 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-154">The severity of the indicator.</span></span> <span data-ttu-id="09dea-155">가능한 값은 "정보", "낮음", "중간" 및 "높음"입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="09dea-156">**선택**</span><span class="sxs-lookup"><span data-stu-id="09dea-156">**Optional**</span></span>
<span data-ttu-id="09dea-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="09dea-157">recommendedActions</span></span> | <span data-ttu-id="09dea-158">문자열</span><span class="sxs-lookup"><span data-stu-id="09dea-158">String</span></span> | <span data-ttu-id="09dea-159">TI 표시기 경고 권장 작업.</span><span class="sxs-lookup"><span data-stu-id="09dea-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="09dea-160">**선택**</span><span class="sxs-lookup"><span data-stu-id="09dea-160">**Optional**</span></span>
<span data-ttu-id="09dea-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="09dea-161">rbacGroupNames</span></span> | <span data-ttu-id="09dea-162">문자열</span><span class="sxs-lookup"><span data-stu-id="09dea-162">String</span></span> | <span data-ttu-id="09dea-163">콤보로 구분된 RBAC 그룹 이름 목록 표시기가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="09dea-164">**선택**</span><span class="sxs-lookup"><span data-stu-id="09dea-164">**Optional**</span></span>
<span data-ttu-id="09dea-165">category</span><span class="sxs-lookup"><span data-stu-id="09dea-165">category</span></span> | <span data-ttu-id="09dea-166">문자열</span><span class="sxs-lookup"><span data-stu-id="09dea-166">String</span></span> | <span data-ttu-id="09dea-167">경고 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-167">Category of the alert.</span></span> <span data-ttu-id="09dea-168">예로는 실행 및 자격 증명 액세스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="09dea-169">**선택**</span><span class="sxs-lookup"><span data-stu-id="09dea-169">**Optional**</span></span>
<span data-ttu-id="09dea-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="09dea-170">mitretechniques</span></span>| <span data-ttu-id="09dea-171">문자열</span><span class="sxs-lookup"><span data-stu-id="09dea-171">String</span></span> | <span data-ttu-id="09dea-172">MITRE 기술 코드/id(콤보로 구분)</span><span class="sxs-lookup"><span data-stu-id="09dea-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="09dea-173">자세한 내용은 [Enterprise 전술을 참조하세요.](https://attack.mitre.org/tactics/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="09dea-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="09dea-174">**선택 사항** MITRE 기술을 사용할 때 범주에 값을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09dea-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="09dea-175">자세한 내용은 끝점용 Microsoft Defender 경고 범주가 [이제 MITRE ATT 및 CK에&참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)</span><span class="sxs-lookup"><span data-stu-id="09dea-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="09dea-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09dea-176">See also</span></span>
- [<span data-ttu-id="09dea-177">표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="09dea-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="09dea-178">파일에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="09dea-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="09dea-179">IPS 및 URL/도메인에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="09dea-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="09dea-180">인증서를 기반으로 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="09dea-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
