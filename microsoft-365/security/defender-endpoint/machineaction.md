---
title: machineAction 리소스 유형
description: 끝점용 Microsoft Defender의 MachineAction 리소스 유형의 메서드 및 속성에 대해 자세히 알아보습니다.
keywords: api, 지원되는 api, get, machineaction, recent
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
ms.technology: mde
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187388"
---
# <a name="machineaction-resource-type"></a><span data-ttu-id="974e1-104">MachineAction 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="974e1-104">MachineAction resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="974e1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="974e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="974e1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="974e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="974e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="974e1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="974e1-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="974e1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="974e1-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="974e1-110">자세한 내용은 응답 [작업을 참조하세요.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="974e1-110">For more information, see [Response Actions](respond-machine-alerts.md).</span></span> 

| <span data-ttu-id="974e1-111">메서드</span><span class="sxs-lookup"><span data-stu-id="974e1-111">Method</span></span>                                                            | <span data-ttu-id="974e1-112">반환 형식</span><span class="sxs-lookup"><span data-stu-id="974e1-112">Return Type</span></span>                        | <span data-ttu-id="974e1-113">설명</span><span class="sxs-lookup"><span data-stu-id="974e1-113">Description</span></span>                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [<span data-ttu-id="974e1-114">MachineActions 목록</span><span class="sxs-lookup"><span data-stu-id="974e1-114">List MachineActions</span></span>](get-machineactions-collection.md)           | [<span data-ttu-id="974e1-115">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-115">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-116">컴퓨터 [작업 엔터티를](machineaction.md) 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-116">List [Machine Action](machineaction.md) entities.</span></span>           |
| [<span data-ttu-id="974e1-117">MachineAction 사용</span><span class="sxs-lookup"><span data-stu-id="974e1-117">Get MachineAction</span></span>](get-machineaction-object.md)                  | [<span data-ttu-id="974e1-118">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-118">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-119">단일 컴퓨터 작업 [엔터티를](machineaction.md) 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-119">Get a single [Machine Action](machineaction.md) entity.</span></span>     |
| [<span data-ttu-id="974e1-120">조사 패키지 수집</span><span class="sxs-lookup"><span data-stu-id="974e1-120">Collect investigation package</span></span>](collect-investigation-package.md) | [<span data-ttu-id="974e1-121">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-121">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-122">컴퓨터 에서 조사 패키지를 [수집합니다.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="974e1-122">Collect investigation package from a [machine](machine.md).</span></span> |
| [<span data-ttu-id="974e1-123">조사 패키지 SAS URI 가져오기</span><span class="sxs-lookup"><span data-stu-id="974e1-123">Get investigation package SAS URI</span></span>](get-package-sas-uri.md)       | [<span data-ttu-id="974e1-124">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-124">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-125">조사 패키지 다운로드를 위한 URI를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-125">Get URI for downloading the investigation package.</span></span>          |
| [<span data-ttu-id="974e1-126">컴퓨터 격리</span><span class="sxs-lookup"><span data-stu-id="974e1-126">Isolate machine</span></span>](isolate-machine.md)                             | [<span data-ttu-id="974e1-127">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-127">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-128">네트워크에서 [컴퓨터](machine.md) 격리.</span><span class="sxs-lookup"><span data-stu-id="974e1-128">Isolate [machine](machine.md) from network.</span></span>                 |
| [<span data-ttu-id="974e1-129">컴퓨터 격리 해제</span><span class="sxs-lookup"><span data-stu-id="974e1-129">Release machine from isolation</span></span>](unisolate-machine.md)            | [<span data-ttu-id="974e1-130">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-130">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-131">[컴퓨터의](machine.md) 고리에서 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-131">Release [machine](machine.md) from Isolation.</span></span>               |
| [<span data-ttu-id="974e1-132">앱 실행 제한</span><span class="sxs-lookup"><span data-stu-id="974e1-132">Restrict app execution</span></span>](restrict-code-execution.md)              | [<span data-ttu-id="974e1-133">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-133">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-134">응용 프로그램 실행을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-134">Restrict application execution.</span></span>                             |
| [<span data-ttu-id="974e1-135">앱 제한 제거</span><span class="sxs-lookup"><span data-stu-id="974e1-135">Remove app restriction</span></span>](unrestrict-code-execution.md)            | [<span data-ttu-id="974e1-136">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-136">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-137">응용 프로그램 실행 제한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-137">Remove application execution restriction.</span></span>                   |
| [<span data-ttu-id="974e1-138">바이러스 백신 검사 실행</span><span class="sxs-lookup"><span data-stu-id="974e1-138">Run antivirus scan</span></span>](run-av-scan.md)                              | [<span data-ttu-id="974e1-139">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-139">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-140">해당되는 경우 Windows Defender 사용하여 AV 스캔을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-140">Run an AV scan using Windows Defender (when applicable).</span></span>    |
| [<span data-ttu-id="974e1-141">컴퓨터 오프보딩</span><span class="sxs-lookup"><span data-stu-id="974e1-141">Offboard machine</span></span>](offboard-machine-api.md)                       | [<span data-ttu-id="974e1-142">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-142">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-143">[끝점용](machine.md) Microsoft Defender에서 컴퓨터 오프보드.</span><span class="sxs-lookup"><span data-stu-id="974e1-143">Offboard [machine](machine.md) from Microsoft Defender for Endpoint.</span></span> |
| [<span data-ttu-id="974e1-144">파일을 중지하고 격리</span><span class="sxs-lookup"><span data-stu-id="974e1-144">Stop and quarantine file</span></span>](stop-and-quarantine-file.md)           | [<span data-ttu-id="974e1-145">컴퓨터 작업</span><span class="sxs-lookup"><span data-stu-id="974e1-145">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="974e1-146">컴퓨터의 파일 실행을 중지하고 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-146">Stop execution of a file on a machine and delete it.</span></span>        |

<br>

## <a name="properties"></a><span data-ttu-id="974e1-147">특성</span><span class="sxs-lookup"><span data-stu-id="974e1-147">Properties</span></span>

| <span data-ttu-id="974e1-148">속성</span><span class="sxs-lookup"><span data-stu-id="974e1-148">Property</span></span>            | <span data-ttu-id="974e1-149">유형</span><span class="sxs-lookup"><span data-stu-id="974e1-149">Type</span></span>           | <span data-ttu-id="974e1-150">설명</span><span class="sxs-lookup"><span data-stu-id="974e1-150">Description</span></span>                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="974e1-151">ID</span><span class="sxs-lookup"><span data-stu-id="974e1-151">ID</span></span>                  | <span data-ttu-id="974e1-152">Guid</span><span class="sxs-lookup"><span data-stu-id="974e1-152">Guid</span></span>           | <span data-ttu-id="974e1-153">[Machine Action 엔터티의 ID입니다.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="974e1-153">Identity of the [Machine Action](machineaction.md) entity.</span></span>                                                                                                                                                     |
| <span data-ttu-id="974e1-154">type</span><span class="sxs-lookup"><span data-stu-id="974e1-154">type</span></span>                | <span data-ttu-id="974e1-155">Enum</span><span class="sxs-lookup"><span data-stu-id="974e1-155">Enum</span></span>           | <span data-ttu-id="974e1-156">작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-156">Type of the action.</span></span> <span data-ttu-id="974e1-157">가능한 값은 "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" 및 "UnrestrictCodeExecution"입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-157">Possible values are: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" and "UnrestrictCodeExecution"</span></span> |
| <span data-ttu-id="974e1-158">scope</span><span class="sxs-lookup"><span data-stu-id="974e1-158">scope</span></span>               | <span data-ttu-id="974e1-159">문자열</span><span class="sxs-lookup"><span data-stu-id="974e1-159">string</span></span>         | <span data-ttu-id="974e1-160">작업의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-160">Scope of the action.</span></span> <span data-ttu-id="974e1-161">바이러스 백신 검사의 경우 "전체" 또는 "선택적" 및 "빠른" 또는 "전체"입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-161">"Full" or "Selective" for Isolation, "Quick" or "Full" for Anti-Virus scan.</span></span>                                                                                                   |
| <span data-ttu-id="974e1-162">requestor</span><span class="sxs-lookup"><span data-stu-id="974e1-162">requestor</span></span>           | <span data-ttu-id="974e1-163">String</span><span class="sxs-lookup"><span data-stu-id="974e1-163">String</span></span>         | <span data-ttu-id="974e1-164">작업을 실행한 사람의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-164">Identity of the person that executed the action.</span></span>                                                                                                                                                               |
| <span data-ttu-id="974e1-165">requestorComment</span><span class="sxs-lookup"><span data-stu-id="974e1-165">requestorComment</span></span>    | <span data-ttu-id="974e1-166">String</span><span class="sxs-lookup"><span data-stu-id="974e1-166">String</span></span>         | <span data-ttu-id="974e1-167">작업을 실행할 때 작성된 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-167">Comment that was written when issuing the action.</span></span>                                                                                                                                                              |
| <span data-ttu-id="974e1-168">status</span><span class="sxs-lookup"><span data-stu-id="974e1-168">status</span></span>              | <span data-ttu-id="974e1-169">Enum</span><span class="sxs-lookup"><span data-stu-id="974e1-169">Enum</span></span>           | <span data-ttu-id="974e1-170">명령의 현재 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-170">Current status of the command.</span></span> <span data-ttu-id="974e1-171">가능한 값은 "보류 중", "InProgress", "Succeeded", "Failed", "TimeOut" 및 "Canceled"입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-171">Possible values are: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" and "Canceled".</span></span>                                                                                 |
| <span data-ttu-id="974e1-172">machineId</span><span class="sxs-lookup"><span data-stu-id="974e1-172">machineId</span></span>           | <span data-ttu-id="974e1-173">String</span><span class="sxs-lookup"><span data-stu-id="974e1-173">String</span></span>         | <span data-ttu-id="974e1-174">작업이 실행된 컴퓨터의 ID입니다. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="974e1-174">ID of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                              |
| <span data-ttu-id="974e1-175">machineId</span><span class="sxs-lookup"><span data-stu-id="974e1-175">machineId</span></span>           | <span data-ttu-id="974e1-176">String</span><span class="sxs-lookup"><span data-stu-id="974e1-176">String</span></span>         | <span data-ttu-id="974e1-177">작업이 [실행된](machine.md) 컴퓨터의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-177">Name of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                            |
| <span data-ttu-id="974e1-178">creationDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="974e1-178">creationDateTimeUtc</span></span> | <span data-ttu-id="974e1-179">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="974e1-179">DateTimeOffset</span></span> | <span data-ttu-id="974e1-180">작업을 만든 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-180">The date and time when the action was created.</span></span>                                                                                                                                                                 |
| <span data-ttu-id="974e1-181">lastUpdateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="974e1-181">lastUpdateTimeUtc</span></span>   | <span data-ttu-id="974e1-182">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="974e1-182">DateTimeOffset</span></span> | <span data-ttu-id="974e1-183">작업 상태가 업데이트된 마지막 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-183">The last date and time when the action status was updated.</span></span>                                                                                                                                                     |
| <span data-ttu-id="974e1-184">relatedFileInfo</span><span class="sxs-lookup"><span data-stu-id="974e1-184">relatedFileInfo</span></span>     | <span data-ttu-id="974e1-185">클래스</span><span class="sxs-lookup"><span data-stu-id="974e1-185">Class</span></span>          | <span data-ttu-id="974e1-186">두 속성이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-186">Contains two Properties.</span></span> <span data-ttu-id="974e1-187">string , Enum 값으로 ```fileIdentifier``` ```fileIdentifierType``` "Sha1", "Sha256" 및 "Md5"를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="974e1-187">string ```fileIdentifier```, Enum ```fileIdentifierType``` with the possible values: "Sha1", "Sha256" and "Md5".</span></span>                                                                         |


## <a name="json-representation"></a><span data-ttu-id="974e1-188">Json 표현</span><span class="sxs-lookup"><span data-stu-id="974e1-188">Json representation</span></span>

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
