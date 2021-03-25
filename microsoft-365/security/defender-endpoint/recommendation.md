---
title: 권장 방법 및 속성
description: 최근 경고 중 가장 최근 알림을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198236"
---
# <a name="recommendation-resource-type"></a><span data-ttu-id="89f37-104">권장 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="89f37-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="89f37-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="89f37-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="89f37-106">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="89f37-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89f37-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="89f37-108">메서드</span><span class="sxs-lookup"><span data-stu-id="89f37-108">Methods</span></span>
<span data-ttu-id="89f37-109">메서드</span><span class="sxs-lookup"><span data-stu-id="89f37-109">Method</span></span> |<span data-ttu-id="89f37-110">반환 형식</span><span class="sxs-lookup"><span data-stu-id="89f37-110">Return Type</span></span> |<span data-ttu-id="89f37-111">설명</span><span class="sxs-lookup"><span data-stu-id="89f37-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="89f37-112">모든 권장 사항 나열</span><span class="sxs-lookup"><span data-stu-id="89f37-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="89f37-113">추천 컬렉션</span><span class="sxs-lookup"><span data-stu-id="89f37-113">Recommendation collection</span></span> | <span data-ttu-id="89f37-114">조직에 영향을 주는 모든 보안 권장 사항 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="89f37-115">ID로 권장 사용</span><span class="sxs-lookup"><span data-stu-id="89f37-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="89f37-116">권장 사항</span><span class="sxs-lookup"><span data-stu-id="89f37-116">Recommendation</span></span> | <span data-ttu-id="89f37-117">ID로 보안 권장을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="89f37-118">권장 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="89f37-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="89f37-119">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="89f37-119">Software</span></span>](software.md) | <span data-ttu-id="89f37-120">특정 소프트웨어와 관련된 보안 권장 검색</span><span class="sxs-lookup"><span data-stu-id="89f37-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="89f37-121">추천 장치 사용</span><span class="sxs-lookup"><span data-stu-id="89f37-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="89f37-122">MachineRef 컬렉션</span><span class="sxs-lookup"><span data-stu-id="89f37-122">MachineRef collection</span></span> | <span data-ttu-id="89f37-123">보안 권장과 연결된 장치 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="89f37-124">권장 취약성 확인</span><span class="sxs-lookup"><span data-stu-id="89f37-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="89f37-125">[취약성](vulnerability.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="89f37-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="89f37-126">보안 권장과 관련된 취약점 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="89f37-127">속성</span><span class="sxs-lookup"><span data-stu-id="89f37-127">Properties</span></span>
<span data-ttu-id="89f37-128">속성</span><span class="sxs-lookup"><span data-stu-id="89f37-128">Property</span></span> |   <span data-ttu-id="89f37-129">유형</span><span class="sxs-lookup"><span data-stu-id="89f37-129">Type</span></span>   |   <span data-ttu-id="89f37-130">설명</span><span class="sxs-lookup"><span data-stu-id="89f37-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="89f37-131">id</span><span class="sxs-lookup"><span data-stu-id="89f37-131">id</span></span> | <span data-ttu-id="89f37-132">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-132">String</span></span> | <span data-ttu-id="89f37-133">권장 ID</span><span class="sxs-lookup"><span data-stu-id="89f37-133">Recommendation ID</span></span>
<span data-ttu-id="89f37-134">productName</span><span class="sxs-lookup"><span data-stu-id="89f37-134">productName</span></span> | <span data-ttu-id="89f37-135">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-135">String</span></span> | <span data-ttu-id="89f37-136">관련 소프트웨어 이름</span><span class="sxs-lookup"><span data-stu-id="89f37-136">Related software name</span></span>  
<span data-ttu-id="89f37-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="89f37-137">recommendationName</span></span> | <span data-ttu-id="89f37-138">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-138">String</span></span> | <span data-ttu-id="89f37-139">권장 이름</span><span class="sxs-lookup"><span data-stu-id="89f37-139">Recommendation name</span></span>
<span data-ttu-id="89f37-140">약점</span><span class="sxs-lookup"><span data-stu-id="89f37-140">Weaknesses</span></span> | <span data-ttu-id="89f37-141">Long</span><span class="sxs-lookup"><span data-stu-id="89f37-141">Long</span></span> | <span data-ttu-id="89f37-142">검색된 취약성 수</span><span class="sxs-lookup"><span data-stu-id="89f37-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="89f37-143">공급업체</span><span class="sxs-lookup"><span data-stu-id="89f37-143">Vendor</span></span> | <span data-ttu-id="89f37-144">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-144">String</span></span> | <span data-ttu-id="89f37-145">관련 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="89f37-145">Related vendor name</span></span>
<span data-ttu-id="89f37-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="89f37-146">recommendedVersion</span></span> | <span data-ttu-id="89f37-147">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-147">String</span></span> | <span data-ttu-id="89f37-148">권장 버전</span><span class="sxs-lookup"><span data-stu-id="89f37-148">Recommended version</span></span>
<span data-ttu-id="89f37-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="89f37-149">recommendationCategory</span></span> | <span data-ttu-id="89f37-150">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-150">String</span></span> | <span data-ttu-id="89f37-151">권장 범주.</span><span class="sxs-lookup"><span data-stu-id="89f37-151">Recommendation category.</span></span> <span data-ttu-id="89f37-152">가능한 값은 "Accounts", "Application", "Network", "OS", "SecurityStack입니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="89f37-153">subCategory</span><span class="sxs-lookup"><span data-stu-id="89f37-153">subCategory</span></span> | <span data-ttu-id="89f37-154">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-154">String</span></span> | <span data-ttu-id="89f37-155">권장 하위 범주</span><span class="sxs-lookup"><span data-stu-id="89f37-155">Recommendation sub-category</span></span>
<span data-ttu-id="89f37-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="89f37-156">severityScore</span></span> | <span data-ttu-id="89f37-157">실수</span><span class="sxs-lookup"><span data-stu-id="89f37-157">Double</span></span> | <span data-ttu-id="89f37-158">구성이 조직의 장치에 대한 Microsoft 보안 점수에 미치는 잠재적인 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="89f37-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="89f37-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="89f37-159">publicExploit</span></span> | <span data-ttu-id="89f37-160">부울</span><span class="sxs-lookup"><span data-stu-id="89f37-160">Boolean</span></span> | <span data-ttu-id="89f37-161">공용 악용 사용 가능</span><span class="sxs-lookup"><span data-stu-id="89f37-161">Public exploit is available</span></span> 
<span data-ttu-id="89f37-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="89f37-162">activeAlert</span></span> | <span data-ttu-id="89f37-163">부울</span><span class="sxs-lookup"><span data-stu-id="89f37-163">Boolean</span></span> | <span data-ttu-id="89f37-164">활성 경고가 이 권장과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="89f37-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="89f37-165">associatedThreats</span></span> | <span data-ttu-id="89f37-166">문자열 컬렉션</span><span class="sxs-lookup"><span data-stu-id="89f37-166">String collection</span></span> | <span data-ttu-id="89f37-167">위협 분석 보고서가 이 권장과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="89f37-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="89f37-168">remediationType</span></span> | <span data-ttu-id="89f37-169">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-169">String</span></span> | <span data-ttu-id="89f37-170">수정 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-170">Remediation type.</span></span> <span data-ttu-id="89f37-171">가능한 값은 "ConfigurationChange","Update","Upgrade","Uninstall"입니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="89f37-172">상태</span><span class="sxs-lookup"><span data-stu-id="89f37-172">Status</span></span> | <span data-ttu-id="89f37-173">Enum</span><span class="sxs-lookup"><span data-stu-id="89f37-173">Enum</span></span> | <span data-ttu-id="89f37-174">권장 예외 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-174">Recommendation exception status.</span></span> <span data-ttu-id="89f37-175">가능한 값은 "Active" 및 "Exception"입니다.</span><span class="sxs-lookup"><span data-stu-id="89f37-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="89f37-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="89f37-176">configScoreImpact</span></span> | <span data-ttu-id="89f37-177">실수</span><span class="sxs-lookup"><span data-stu-id="89f37-177">Double</span></span> | <span data-ttu-id="89f37-178">장치에 대한 Microsoft 보안 점수 영향</span><span class="sxs-lookup"><span data-stu-id="89f37-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="89f37-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="89f37-179">exposureImpacte</span></span> | <span data-ttu-id="89f37-180">실수</span><span class="sxs-lookup"><span data-stu-id="89f37-180">Double</span></span> | <span data-ttu-id="89f37-181">노출 점수 영향</span><span class="sxs-lookup"><span data-stu-id="89f37-181">Exposure score impact</span></span>
<span data-ttu-id="89f37-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="89f37-182">totalMachineCount</span></span> | <span data-ttu-id="89f37-183">Long</span><span class="sxs-lookup"><span data-stu-id="89f37-183">Long</span></span> | <span data-ttu-id="89f37-184">설치된 장치 수</span><span class="sxs-lookup"><span data-stu-id="89f37-184">Number of installed devices</span></span>
<span data-ttu-id="89f37-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="89f37-185">exposedMachinesCount</span></span> | <span data-ttu-id="89f37-186">Long</span><span class="sxs-lookup"><span data-stu-id="89f37-186">Long</span></span> | <span data-ttu-id="89f37-187">취약성에 노출되는 설치된 장치 수</span><span class="sxs-lookup"><span data-stu-id="89f37-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="89f37-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="89f37-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="89f37-189">Long</span><span class="sxs-lookup"><span data-stu-id="89f37-189">Long</span></span> | <span data-ttu-id="89f37-190">영향을 받지 않는 장치 수</span><span class="sxs-lookup"><span data-stu-id="89f37-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="89f37-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="89f37-191">relatedComponent</span></span> | <span data-ttu-id="89f37-192">문자열</span><span class="sxs-lookup"><span data-stu-id="89f37-192">String</span></span> |  <span data-ttu-id="89f37-193">관련 소프트웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="89f37-193">Related software component</span></span>
