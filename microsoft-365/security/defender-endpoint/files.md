---
title: 파일 리소스 유형
description: 파일과 관련된 끝점 경고에 대한 최근 Microsoft Defender를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c4d392c9c7777a5ab5435d70e36822e11aa39dae
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771192"
---
# <a name="file-resource-type"></a><span data-ttu-id="47516-104">파일 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="47516-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="47516-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="47516-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="47516-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="47516-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47516-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="47516-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="47516-108">Defender for Endpoint의 파일 엔터티를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47516-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="47516-109">메서드</span><span class="sxs-lookup"><span data-stu-id="47516-109">Methods</span></span>
<span data-ttu-id="47516-110">메서드</span><span class="sxs-lookup"><span data-stu-id="47516-110">Method</span></span>|<span data-ttu-id="47516-111">반환 형식</span><span class="sxs-lookup"><span data-stu-id="47516-111">Return Type</span></span> |<span data-ttu-id="47516-112">설명</span><span class="sxs-lookup"><span data-stu-id="47516-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="47516-113">파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="47516-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="47516-114">file</span><span class="sxs-lookup"><span data-stu-id="47516-114">file</span></span>](files.md) | <span data-ttu-id="47516-115">단일 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="47516-115">Get a single file</span></span> 
[<span data-ttu-id="47516-116">파일 관련 경고 목록</span><span class="sxs-lookup"><span data-stu-id="47516-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="47516-117">[경고](alerts.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="47516-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="47516-118">파일과 [](alerts.md) 연결된 경고 엔터티를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="47516-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="47516-119">파일 관련 컴퓨터 목록</span><span class="sxs-lookup"><span data-stu-id="47516-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="47516-120">[machine collection(컴퓨터](machine.md) 컬렉션)</span><span class="sxs-lookup"><span data-stu-id="47516-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="47516-121">경고와 [](machine.md) 연결된 컴퓨터 엔터티를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="47516-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="47516-122">파일 통계</span><span class="sxs-lookup"><span data-stu-id="47516-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="47516-123">통계 요약</span><span class="sxs-lookup"><span data-stu-id="47516-123">Statistics summary</span></span> | <span data-ttu-id="47516-124">지정한 파일의 보전을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="47516-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="47516-125">특성</span><span class="sxs-lookup"><span data-stu-id="47516-125">Properties</span></span>
|<span data-ttu-id="47516-126">속성</span><span class="sxs-lookup"><span data-stu-id="47516-126">Property</span></span> | <span data-ttu-id="47516-127">유형</span><span class="sxs-lookup"><span data-stu-id="47516-127">Type</span></span>    |   <span data-ttu-id="47516-128">설명</span><span class="sxs-lookup"><span data-stu-id="47516-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="47516-129">sha1</span><span class="sxs-lookup"><span data-stu-id="47516-129">sha1</span></span> | <span data-ttu-id="47516-130">String</span><span class="sxs-lookup"><span data-stu-id="47516-130">String</span></span> | <span data-ttu-id="47516-131">파일 콘텐츠의 Sha1 해시</span><span class="sxs-lookup"><span data-stu-id="47516-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="47516-132">sha256</span><span class="sxs-lookup"><span data-stu-id="47516-132">sha256</span></span> | <span data-ttu-id="47516-133">String</span><span class="sxs-lookup"><span data-stu-id="47516-133">String</span></span> | <span data-ttu-id="47516-134">파일 콘텐츠의 Sha256 해시</span><span class="sxs-lookup"><span data-stu-id="47516-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="47516-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="47516-135">globalPrevalence</span></span> | <span data-ttu-id="47516-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="47516-136">Nullable long</span></span> | <span data-ttu-id="47516-137">조직 전체의 파일 보전</span><span class="sxs-lookup"><span data-stu-id="47516-137">File prevalence across organization</span></span> |
|<span data-ttu-id="47516-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="47516-138">globalFirstObserved</span></span> | <span data-ttu-id="47516-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="47516-139">DateTimeOffset</span></span> | <span data-ttu-id="47516-140">파일이 처음으로 관찰된 시간</span><span class="sxs-lookup"><span data-stu-id="47516-140">First time the file was observed</span></span> |
|<span data-ttu-id="47516-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="47516-141">globalLastObserved</span></span> | <span data-ttu-id="47516-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="47516-142">DateTimeOffset</span></span> | <span data-ttu-id="47516-143">파일이 마지막으로 관찰된 시간</span><span class="sxs-lookup"><span data-stu-id="47516-143">Last time the file was observed</span></span> |
|<span data-ttu-id="47516-144">size</span><span class="sxs-lookup"><span data-stu-id="47516-144">size</span></span> | <span data-ttu-id="47516-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="47516-145">Nullable long</span></span> | <span data-ttu-id="47516-146">파일 크기</span><span class="sxs-lookup"><span data-stu-id="47516-146">Size of the file</span></span> |
|<span data-ttu-id="47516-147">fileType</span><span class="sxs-lookup"><span data-stu-id="47516-147">fileType</span></span> | <span data-ttu-id="47516-148">String</span><span class="sxs-lookup"><span data-stu-id="47516-148">String</span></span> | <span data-ttu-id="47516-149">파일 형식</span><span class="sxs-lookup"><span data-stu-id="47516-149">Type of the file</span></span> |
|<span data-ttu-id="47516-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="47516-150">isPeFile</span></span> | <span data-ttu-id="47516-151">부울</span><span class="sxs-lookup"><span data-stu-id="47516-151">Boolean</span></span> | <span data-ttu-id="47516-152">true이면 파일이 이식 가능한 실행 파일(예: "DLL", "EXE" 등)입니다.</span><span class="sxs-lookup"><span data-stu-id="47516-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="47516-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="47516-153">filePublisher</span></span> | <span data-ttu-id="47516-154">String</span><span class="sxs-lookup"><span data-stu-id="47516-154">String</span></span> | <span data-ttu-id="47516-155">파일 게시자</span><span class="sxs-lookup"><span data-stu-id="47516-155">File publisher</span></span> |
|<span data-ttu-id="47516-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="47516-156">fileProductName</span></span> | <span data-ttu-id="47516-157">String</span><span class="sxs-lookup"><span data-stu-id="47516-157">String</span></span> | <span data-ttu-id="47516-158">제품 이름</span><span class="sxs-lookup"><span data-stu-id="47516-158">Product name</span></span> |
|<span data-ttu-id="47516-159">signer</span><span class="sxs-lookup"><span data-stu-id="47516-159">signer</span></span> | <span data-ttu-id="47516-160">String</span><span class="sxs-lookup"><span data-stu-id="47516-160">String</span></span> | <span data-ttu-id="47516-161">파일 서명자</span><span class="sxs-lookup"><span data-stu-id="47516-161">File signer</span></span> |
|<span data-ttu-id="47516-162">발급자</span><span class="sxs-lookup"><span data-stu-id="47516-162">issuer</span></span> | <span data-ttu-id="47516-163">String</span><span class="sxs-lookup"><span data-stu-id="47516-163">String</span></span> | <span data-ttu-id="47516-164">파일 발급자</span><span class="sxs-lookup"><span data-stu-id="47516-164">File issuer</span></span> |
|<span data-ttu-id="47516-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="47516-165">signerHash</span></span> | <span data-ttu-id="47516-166">String</span><span class="sxs-lookup"><span data-stu-id="47516-166">String</span></span> | <span data-ttu-id="47516-167">서명 인증서의 해시</span><span class="sxs-lookup"><span data-stu-id="47516-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="47516-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="47516-168">isValidCertificate</span></span> | <span data-ttu-id="47516-169">부울</span><span class="sxs-lookup"><span data-stu-id="47516-169">Boolean</span></span> | <span data-ttu-id="47516-170">Microsoft Defender for Endpoint 에이전트에서 인증서 서명이 성공적으로 확인된 경우</span><span class="sxs-lookup"><span data-stu-id="47516-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="47516-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="47516-171">determinationType</span></span> | <span data-ttu-id="47516-172">String</span><span class="sxs-lookup"><span data-stu-id="47516-172">String</span></span> | <span data-ttu-id="47516-173">파일의 결정 유형</span><span class="sxs-lookup"><span data-stu-id="47516-173">The determination type of the file</span></span> |
|<span data-ttu-id="47516-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="47516-174">determinationValue</span></span> | <span data-ttu-id="47516-175">String</span><span class="sxs-lookup"><span data-stu-id="47516-175">String</span></span> | <span data-ttu-id="47516-176">결정 값</span><span class="sxs-lookup"><span data-stu-id="47516-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="47516-177">Json 표현</span><span class="sxs-lookup"><span data-stu-id="47516-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
