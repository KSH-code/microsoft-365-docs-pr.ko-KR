---
title: 소프트웨어 방법 및 속성
description: 최근 경고를 검색합니다.
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
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771414"
---
# <a name="software-resource-type"></a><span data-ttu-id="5f8ef-104">소프트웨어 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="5f8ef-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f8ef-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f8ef-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f8ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5f8ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f8ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5f8ef-108">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5f8ef-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5f8ef-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5f8ef-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5f8ef-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="5f8ef-111">메서드</span><span class="sxs-lookup"><span data-stu-id="5f8ef-111">Methods</span></span>

<span data-ttu-id="5f8ef-112">메서드</span><span class="sxs-lookup"><span data-stu-id="5f8ef-112">Method</span></span> |<span data-ttu-id="5f8ef-113">반환 형식</span><span class="sxs-lookup"><span data-stu-id="5f8ef-113">Return Type</span></span> |<span data-ttu-id="5f8ef-114">설명</span><span class="sxs-lookup"><span data-stu-id="5f8ef-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="5f8ef-115">소프트웨어 목록</span><span class="sxs-lookup"><span data-stu-id="5f8ef-115">List software</span></span>](get-software.md) | <span data-ttu-id="5f8ef-116">소프트웨어 컬렉션</span><span class="sxs-lookup"><span data-stu-id="5f8ef-116">Software collection</span></span> | <span data-ttu-id="5f8ef-117">조직 소프트웨어 인벤토리를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="5f8ef-118">ID별 소프트웨어 가져오기</span><span class="sxs-lookup"><span data-stu-id="5f8ef-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="5f8ef-119">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="5f8ef-119">Software</span></span> | <span data-ttu-id="5f8ef-120">소프트웨어 ID로 특정 소프트웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="5f8ef-121">소프트웨어 버전 배포 목록</span><span class="sxs-lookup"><span data-stu-id="5f8ef-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="5f8ef-122">배포 모음</span><span class="sxs-lookup"><span data-stu-id="5f8ef-122">Distribution collection</span></span> | <span data-ttu-id="5f8ef-123">소프트웨어 ID로 소프트웨어 버전 배포를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="5f8ef-124">소프트웨어별 컴퓨터 목록</span><span class="sxs-lookup"><span data-stu-id="5f8ef-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="5f8ef-125">MachineRef 컬렉션</span><span class="sxs-lookup"><span data-stu-id="5f8ef-125">MachineRef collection</span></span> | <span data-ttu-id="5f8ef-126">소프트웨어 ID와 연결된 장치 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="5f8ef-127">소프트웨어별 취약성 목록</span><span class="sxs-lookup"><span data-stu-id="5f8ef-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="5f8ef-128">[취약성](vulnerability.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="5f8ef-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="5f8ef-129">소프트웨어 ID와 관련된 취약점 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="5f8ef-130">누락된 KB 가져오기</span><span class="sxs-lookup"><span data-stu-id="5f8ef-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="5f8ef-131">KB 컬렉션</span><span class="sxs-lookup"><span data-stu-id="5f8ef-131">KB collection</span></span> | <span data-ttu-id="5f8ef-132">소프트웨어 ID와 연결된 누락된 KB 목록 다운로드</span><span class="sxs-lookup"><span data-stu-id="5f8ef-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="5f8ef-133">특성</span><span class="sxs-lookup"><span data-stu-id="5f8ef-133">Properties</span></span>

<span data-ttu-id="5f8ef-134">속성</span><span class="sxs-lookup"><span data-stu-id="5f8ef-134">Property</span></span> |   <span data-ttu-id="5f8ef-135">유형</span><span class="sxs-lookup"><span data-stu-id="5f8ef-135">Type</span></span>   |   <span data-ttu-id="5f8ef-136">설명</span><span class="sxs-lookup"><span data-stu-id="5f8ef-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="5f8ef-137">id</span><span class="sxs-lookup"><span data-stu-id="5f8ef-137">id</span></span> | <span data-ttu-id="5f8ef-138">String</span><span class="sxs-lookup"><span data-stu-id="5f8ef-138">String</span></span> | <span data-ttu-id="5f8ef-139">소프트웨어 ID</span><span class="sxs-lookup"><span data-stu-id="5f8ef-139">Software ID</span></span>
<span data-ttu-id="5f8ef-140">이름</span><span class="sxs-lookup"><span data-stu-id="5f8ef-140">Name</span></span> | <span data-ttu-id="5f8ef-141">String</span><span class="sxs-lookup"><span data-stu-id="5f8ef-141">String</span></span> | <span data-ttu-id="5f8ef-142">소프트웨어 이름</span><span class="sxs-lookup"><span data-stu-id="5f8ef-142">Software name</span></span>
<span data-ttu-id="5f8ef-143">공급업체</span><span class="sxs-lookup"><span data-stu-id="5f8ef-143">Vendor</span></span> | <span data-ttu-id="5f8ef-144">String</span><span class="sxs-lookup"><span data-stu-id="5f8ef-144">String</span></span> | <span data-ttu-id="5f8ef-145">소프트웨어 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="5f8ef-145">Software vendor name</span></span>
<span data-ttu-id="5f8ef-146">약점</span><span class="sxs-lookup"><span data-stu-id="5f8ef-146">Weaknesses</span></span> | <span data-ttu-id="5f8ef-147">Long</span><span class="sxs-lookup"><span data-stu-id="5f8ef-147">Long</span></span> | <span data-ttu-id="5f8ef-148">검색된 취약성 수</span><span class="sxs-lookup"><span data-stu-id="5f8ef-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="5f8ef-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="5f8ef-149">publicExploit</span></span> | <span data-ttu-id="5f8ef-150">부울</span><span class="sxs-lookup"><span data-stu-id="5f8ef-150">Boolean</span></span> | <span data-ttu-id="5f8ef-151">일부 취약성에 대한 공개 악용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="5f8ef-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="5f8ef-152">activeAlert</span></span> | <span data-ttu-id="5f8ef-153">부울</span><span class="sxs-lookup"><span data-stu-id="5f8ef-153">Boolean</span></span> | <span data-ttu-id="5f8ef-154">활성 경고가 이 소프트웨어와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-154">Active alert is associated with this software</span></span>
<span data-ttu-id="5f8ef-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="5f8ef-155">exposedMachines</span></span> | <span data-ttu-id="5f8ef-156">Long</span><span class="sxs-lookup"><span data-stu-id="5f8ef-156">Long</span></span> | <span data-ttu-id="5f8ef-157">노출된 장치 수</span><span class="sxs-lookup"><span data-stu-id="5f8ef-157">Number of exposed devices</span></span>
<span data-ttu-id="5f8ef-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="5f8ef-158">impactScore</span></span> | <span data-ttu-id="5f8ef-159">실수</span><span class="sxs-lookup"><span data-stu-id="5f8ef-159">Double</span></span> | <span data-ttu-id="5f8ef-160">이 소프트웨어의 노출 점수 영향</span><span class="sxs-lookup"><span data-stu-id="5f8ef-160">Exposure score impact of this software</span></span>
