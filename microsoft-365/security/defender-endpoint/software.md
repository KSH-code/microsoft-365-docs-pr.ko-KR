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
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187305"
---
# <a name="software-resource-type"></a><span data-ttu-id="220e7-104">소프트웨어 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="220e7-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="220e7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="220e7-105">**Applies to:**</span></span>
- [<span data-ttu-id="220e7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="220e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="220e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="220e7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="220e7-108">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="220e7-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="220e7-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="220e7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="220e7-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="220e7-111">메서드</span><span class="sxs-lookup"><span data-stu-id="220e7-111">Methods</span></span>

<span data-ttu-id="220e7-112">메서드</span><span class="sxs-lookup"><span data-stu-id="220e7-112">Method</span></span> |<span data-ttu-id="220e7-113">반환 형식</span><span class="sxs-lookup"><span data-stu-id="220e7-113">Return Type</span></span> |<span data-ttu-id="220e7-114">설명</span><span class="sxs-lookup"><span data-stu-id="220e7-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="220e7-115">목록 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="220e7-115">List software</span></span>](get-software.md) | <span data-ttu-id="220e7-116">소프트웨어 컬렉션</span><span class="sxs-lookup"><span data-stu-id="220e7-116">Software collection</span></span> | <span data-ttu-id="220e7-117">조직 소프트웨어 인벤토리를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="220e7-118">ID로 소프트웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="220e7-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="220e7-119">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="220e7-119">Software</span></span> | <span data-ttu-id="220e7-120">소프트웨어 ID로 특정 소프트웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="220e7-121">소프트웨어 버전 배포 목록</span><span class="sxs-lookup"><span data-stu-id="220e7-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="220e7-122">배포 모음</span><span class="sxs-lookup"><span data-stu-id="220e7-122">Distribution collection</span></span> | <span data-ttu-id="220e7-123">소프트웨어 ID로 소프트웨어 버전 배포를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="220e7-124">소프트웨어로 컴퓨터 나열</span><span class="sxs-lookup"><span data-stu-id="220e7-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="220e7-125">MachineRef 컬렉션</span><span class="sxs-lookup"><span data-stu-id="220e7-125">MachineRef collection</span></span> | <span data-ttu-id="220e7-126">소프트웨어 ID와 연결된 장치 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="220e7-127">소프트웨어의 취약성 목록</span><span class="sxs-lookup"><span data-stu-id="220e7-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="220e7-128">[취약성](vulnerability.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="220e7-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="220e7-129">소프트웨어 ID와 관련된 취약점 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="220e7-130">누락된 KB</span><span class="sxs-lookup"><span data-stu-id="220e7-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="220e7-131">KB 컬렉션</span><span class="sxs-lookup"><span data-stu-id="220e7-131">KB collection</span></span> | <span data-ttu-id="220e7-132">소프트웨어 ID와 연결된 누락된 KB 목록 다운로드</span><span class="sxs-lookup"><span data-stu-id="220e7-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="220e7-133">속성</span><span class="sxs-lookup"><span data-stu-id="220e7-133">Properties</span></span>

<span data-ttu-id="220e7-134">속성</span><span class="sxs-lookup"><span data-stu-id="220e7-134">Property</span></span> |   <span data-ttu-id="220e7-135">유형</span><span class="sxs-lookup"><span data-stu-id="220e7-135">Type</span></span>   |   <span data-ttu-id="220e7-136">설명</span><span class="sxs-lookup"><span data-stu-id="220e7-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="220e7-137">id</span><span class="sxs-lookup"><span data-stu-id="220e7-137">id</span></span> | <span data-ttu-id="220e7-138">문자열</span><span class="sxs-lookup"><span data-stu-id="220e7-138">String</span></span> | <span data-ttu-id="220e7-139">소프트웨어 ID</span><span class="sxs-lookup"><span data-stu-id="220e7-139">Software ID</span></span>
<span data-ttu-id="220e7-140">이름</span><span class="sxs-lookup"><span data-stu-id="220e7-140">Name</span></span> | <span data-ttu-id="220e7-141">문자열</span><span class="sxs-lookup"><span data-stu-id="220e7-141">String</span></span> | <span data-ttu-id="220e7-142">소프트웨어 이름</span><span class="sxs-lookup"><span data-stu-id="220e7-142">Software name</span></span>
<span data-ttu-id="220e7-143">공급업체</span><span class="sxs-lookup"><span data-stu-id="220e7-143">Vendor</span></span> | <span data-ttu-id="220e7-144">문자열</span><span class="sxs-lookup"><span data-stu-id="220e7-144">String</span></span> | <span data-ttu-id="220e7-145">소프트웨어 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="220e7-145">Software vendor name</span></span>
<span data-ttu-id="220e7-146">약점</span><span class="sxs-lookup"><span data-stu-id="220e7-146">Weaknesses</span></span> | <span data-ttu-id="220e7-147">Long</span><span class="sxs-lookup"><span data-stu-id="220e7-147">Long</span></span> | <span data-ttu-id="220e7-148">검색된 취약성 수</span><span class="sxs-lookup"><span data-stu-id="220e7-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="220e7-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="220e7-149">publicExploit</span></span> | <span data-ttu-id="220e7-150">부울</span><span class="sxs-lookup"><span data-stu-id="220e7-150">Boolean</span></span> | <span data-ttu-id="220e7-151">일부 취약성에 대한 공개 악용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="220e7-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="220e7-152">activeAlert</span></span> | <span data-ttu-id="220e7-153">부울</span><span class="sxs-lookup"><span data-stu-id="220e7-153">Boolean</span></span> | <span data-ttu-id="220e7-154">활성 경고가 이 소프트웨어와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="220e7-154">Active alert is associated with this software</span></span>
<span data-ttu-id="220e7-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="220e7-155">exposedMachines</span></span> | <span data-ttu-id="220e7-156">Long</span><span class="sxs-lookup"><span data-stu-id="220e7-156">Long</span></span> | <span data-ttu-id="220e7-157">노출된 장치 수</span><span class="sxs-lookup"><span data-stu-id="220e7-157">Number of exposed devices</span></span>
<span data-ttu-id="220e7-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="220e7-158">impactScore</span></span> | <span data-ttu-id="220e7-159">실수</span><span class="sxs-lookup"><span data-stu-id="220e7-159">Double</span></span> | <span data-ttu-id="220e7-160">이 소프트웨어의 노출 점수 영향</span><span class="sxs-lookup"><span data-stu-id="220e7-160">Exposure score impact of this software</span></span>
