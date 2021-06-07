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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771600"
---
# <a name="recommendation-resource-type"></a><span data-ttu-id="4e9c2-104">권장 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="4e9c2-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4e9c2-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4e9c2-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="4e9c2-106">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4e9c2-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4e9c2-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="4e9c2-108">메서드</span><span class="sxs-lookup"><span data-stu-id="4e9c2-108">Methods</span></span>
<span data-ttu-id="4e9c2-109">메서드</span><span class="sxs-lookup"><span data-stu-id="4e9c2-109">Method</span></span> |<span data-ttu-id="4e9c2-110">반환 형식</span><span class="sxs-lookup"><span data-stu-id="4e9c2-110">Return Type</span></span> |<span data-ttu-id="4e9c2-111">설명</span><span class="sxs-lookup"><span data-stu-id="4e9c2-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="4e9c2-112">모든 권장 사항 목록</span><span class="sxs-lookup"><span data-stu-id="4e9c2-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="4e9c2-113">추천 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4e9c2-113">Recommendation collection</span></span> | <span data-ttu-id="4e9c2-114">조직에 영향을 주는 모든 보안 권장 사항 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="4e9c2-115">ID별 권장 사항 가져오기</span><span class="sxs-lookup"><span data-stu-id="4e9c2-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="4e9c2-116">권장 사항</span><span class="sxs-lookup"><span data-stu-id="4e9c2-116">Recommendation</span></span> | <span data-ttu-id="4e9c2-117">ID로 보안 권장을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="4e9c2-118">권장 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="4e9c2-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="4e9c2-119">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="4e9c2-119">Software</span></span>](software.md) | <span data-ttu-id="4e9c2-120">특정 소프트웨어와 관련된 보안 권장 검색</span><span class="sxs-lookup"><span data-stu-id="4e9c2-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="4e9c2-121">추천 장치 사용</span><span class="sxs-lookup"><span data-stu-id="4e9c2-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="4e9c2-122">MachineRef 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4e9c2-122">MachineRef collection</span></span> | <span data-ttu-id="4e9c2-123">보안 권장과 연결된 장치 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="4e9c2-124">권장 취약성 확인</span><span class="sxs-lookup"><span data-stu-id="4e9c2-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="4e9c2-125">[취약성](vulnerability.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4e9c2-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="4e9c2-126">보안 권장과 관련된 취약점 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="4e9c2-127">특성</span><span class="sxs-lookup"><span data-stu-id="4e9c2-127">Properties</span></span>
<span data-ttu-id="4e9c2-128">속성</span><span class="sxs-lookup"><span data-stu-id="4e9c2-128">Property</span></span> |   <span data-ttu-id="4e9c2-129">유형</span><span class="sxs-lookup"><span data-stu-id="4e9c2-129">Type</span></span>   |   <span data-ttu-id="4e9c2-130">설명</span><span class="sxs-lookup"><span data-stu-id="4e9c2-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="4e9c2-131">id</span><span class="sxs-lookup"><span data-stu-id="4e9c2-131">id</span></span> | <span data-ttu-id="4e9c2-132">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-132">String</span></span> | <span data-ttu-id="4e9c2-133">권장 ID</span><span class="sxs-lookup"><span data-stu-id="4e9c2-133">Recommendation ID</span></span>
<span data-ttu-id="4e9c2-134">productName</span><span class="sxs-lookup"><span data-stu-id="4e9c2-134">productName</span></span> | <span data-ttu-id="4e9c2-135">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-135">String</span></span> | <span data-ttu-id="4e9c2-136">관련 소프트웨어 이름</span><span class="sxs-lookup"><span data-stu-id="4e9c2-136">Related software name</span></span>  
<span data-ttu-id="4e9c2-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="4e9c2-137">recommendationName</span></span> | <span data-ttu-id="4e9c2-138">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-138">String</span></span> | <span data-ttu-id="4e9c2-139">권장 이름</span><span class="sxs-lookup"><span data-stu-id="4e9c2-139">Recommendation name</span></span>
<span data-ttu-id="4e9c2-140">약점</span><span class="sxs-lookup"><span data-stu-id="4e9c2-140">Weaknesses</span></span> | <span data-ttu-id="4e9c2-141">Long</span><span class="sxs-lookup"><span data-stu-id="4e9c2-141">Long</span></span> | <span data-ttu-id="4e9c2-142">검색된 취약성 수</span><span class="sxs-lookup"><span data-stu-id="4e9c2-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="4e9c2-143">공급업체</span><span class="sxs-lookup"><span data-stu-id="4e9c2-143">Vendor</span></span> | <span data-ttu-id="4e9c2-144">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-144">String</span></span> | <span data-ttu-id="4e9c2-145">관련 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="4e9c2-145">Related vendor name</span></span>
<span data-ttu-id="4e9c2-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="4e9c2-146">recommendedVersion</span></span> | <span data-ttu-id="4e9c2-147">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-147">String</span></span> | <span data-ttu-id="4e9c2-148">권장 버전</span><span class="sxs-lookup"><span data-stu-id="4e9c2-148">Recommended version</span></span>
<span data-ttu-id="4e9c2-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="4e9c2-149">recommendationCategory</span></span> | <span data-ttu-id="4e9c2-150">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-150">String</span></span> | <span data-ttu-id="4e9c2-151">권장 범주.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-151">Recommendation category.</span></span> <span data-ttu-id="4e9c2-152">가능한 값은 "Accounts", "Application", "Network", "OS", "SecurityStack입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="4e9c2-153">subCategory</span><span class="sxs-lookup"><span data-stu-id="4e9c2-153">subCategory</span></span> | <span data-ttu-id="4e9c2-154">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-154">String</span></span> | <span data-ttu-id="4e9c2-155">권장 하위 범주</span><span class="sxs-lookup"><span data-stu-id="4e9c2-155">Recommendation sub-category</span></span>
<span data-ttu-id="4e9c2-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="4e9c2-156">severityScore</span></span> | <span data-ttu-id="4e9c2-157">실수</span><span class="sxs-lookup"><span data-stu-id="4e9c2-157">Double</span></span> | <span data-ttu-id="4e9c2-158">구성이 조직의 장치에 대한 Microsoft 보안 점수에 미치는 잠재적인 영향(1-10)</span><span class="sxs-lookup"><span data-stu-id="4e9c2-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="4e9c2-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="4e9c2-159">publicExploit</span></span> | <span data-ttu-id="4e9c2-160">부울</span><span class="sxs-lookup"><span data-stu-id="4e9c2-160">Boolean</span></span> | <span data-ttu-id="4e9c2-161">공용 악용 사용 가능</span><span class="sxs-lookup"><span data-stu-id="4e9c2-161">Public exploit is available</span></span> 
<span data-ttu-id="4e9c2-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="4e9c2-162">activeAlert</span></span> | <span data-ttu-id="4e9c2-163">부울</span><span class="sxs-lookup"><span data-stu-id="4e9c2-163">Boolean</span></span> | <span data-ttu-id="4e9c2-164">활성 경고가 이 권장과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="4e9c2-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="4e9c2-165">associatedThreats</span></span> | <span data-ttu-id="4e9c2-166">문자열 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4e9c2-166">String collection</span></span> | <span data-ttu-id="4e9c2-167">위협 분석 보고서가 이 권장과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="4e9c2-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="4e9c2-168">remediationType</span></span> | <span data-ttu-id="4e9c2-169">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-169">String</span></span> | <span data-ttu-id="4e9c2-170">수정 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-170">Remediation type.</span></span> <span data-ttu-id="4e9c2-171">가능한 값은 "ConfigurationChange","Update","Upgrade","Uninstall"입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="4e9c2-172">상태</span><span class="sxs-lookup"><span data-stu-id="4e9c2-172">Status</span></span> | <span data-ttu-id="4e9c2-173">Enum</span><span class="sxs-lookup"><span data-stu-id="4e9c2-173">Enum</span></span> | <span data-ttu-id="4e9c2-174">권장 예외 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-174">Recommendation exception status.</span></span> <span data-ttu-id="4e9c2-175">가능한 값은 "Active" 및 "Exception"입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9c2-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="4e9c2-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="4e9c2-176">configScoreImpact</span></span> | <span data-ttu-id="4e9c2-177">실수</span><span class="sxs-lookup"><span data-stu-id="4e9c2-177">Double</span></span> | <span data-ttu-id="4e9c2-178">장치에 대한 Microsoft 보안 점수 영향</span><span class="sxs-lookup"><span data-stu-id="4e9c2-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="4e9c2-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="4e9c2-179">exposureImpacte</span></span> | <span data-ttu-id="4e9c2-180">실수</span><span class="sxs-lookup"><span data-stu-id="4e9c2-180">Double</span></span> | <span data-ttu-id="4e9c2-181">노출 점수 영향</span><span class="sxs-lookup"><span data-stu-id="4e9c2-181">Exposure score impact</span></span>
<span data-ttu-id="4e9c2-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="4e9c2-182">totalMachineCount</span></span> | <span data-ttu-id="4e9c2-183">Long</span><span class="sxs-lookup"><span data-stu-id="4e9c2-183">Long</span></span> | <span data-ttu-id="4e9c2-184">설치된 장치 수</span><span class="sxs-lookup"><span data-stu-id="4e9c2-184">Number of installed devices</span></span>
<span data-ttu-id="4e9c2-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="4e9c2-185">exposedMachinesCount</span></span> | <span data-ttu-id="4e9c2-186">Long</span><span class="sxs-lookup"><span data-stu-id="4e9c2-186">Long</span></span> | <span data-ttu-id="4e9c2-187">취약성에 노출되는 설치된 장치 수</span><span class="sxs-lookup"><span data-stu-id="4e9c2-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="4e9c2-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="4e9c2-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="4e9c2-189">Long</span><span class="sxs-lookup"><span data-stu-id="4e9c2-189">Long</span></span> | <span data-ttu-id="4e9c2-190">영향을 받지 않는 장치 수</span><span class="sxs-lookup"><span data-stu-id="4e9c2-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="4e9c2-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="4e9c2-191">relatedComponent</span></span> | <span data-ttu-id="4e9c2-192">String</span><span class="sxs-lookup"><span data-stu-id="4e9c2-192">String</span></span> |  <span data-ttu-id="4e9c2-193">관련 소프트웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4e9c2-193">Related software component</span></span>
