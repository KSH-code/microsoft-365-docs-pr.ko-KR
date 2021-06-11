---
title: 라이브 응답 결과 얻기
description: 인덱스로 특정 라이브 응답 명령 결과를 검색하는 방법을 배워야 합니다.
keywords: api, 그래프 api, 지원되는 api, 라이브러리에 업로드
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879729"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="2f2df-104">라이브 응답 결과 얻기</span><span class="sxs-lookup"><span data-stu-id="2f2df-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f2df-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2f2df-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f2df-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f2df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="2f2df-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2f2df-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f2df-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2f2df-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="2f2df-109">API description</span></span>

<span data-ttu-id="2f2df-110">인덱스로 특정 라이브 응답 명령 결과를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="2f2df-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="2f2df-111">Limitations</span></span>

1.  <span data-ttu-id="2f2df-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="2f2df-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2f2df-113">Permissions</span></span>

<span data-ttu-id="2f2df-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2f2df-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2f2df-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="2f2df-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="2f2df-116">Permission type</span></span>                    | <span data-ttu-id="2f2df-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="2f2df-117">Permission</span></span>           | <span data-ttu-id="2f2df-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="2f2df-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="2f2df-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2f2df-119">Application</span></span>                        | <span data-ttu-id="2f2df-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="2f2df-120">Machine.LiveResponse</span></span> | <span data-ttu-id="2f2df-121">특정 컴퓨터의 실시간 응답 실행</span><span class="sxs-lookup"><span data-stu-id="2f2df-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="2f2df-122">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="2f2df-122">Delegated (work or school account)</span></span> | <span data-ttu-id="2f2df-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="2f2df-123">Machine.LiveResponse</span></span> | <span data-ttu-id="2f2df-124">특정 컴퓨터의 실시간 응답 실행</span><span class="sxs-lookup"><span data-stu-id="2f2df-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="2f2df-125">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="2f2df-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="2f2df-126">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="2f2df-126">Request headers</span></span>

| <span data-ttu-id="2f2df-127">이름</span><span class="sxs-lookup"><span data-stu-id="2f2df-127">Name</span></span>      | <span data-ttu-id="2f2df-128">유형</span><span class="sxs-lookup"><span data-stu-id="2f2df-128">Type</span></span> | <span data-ttu-id="2f2df-129">설명</span><span class="sxs-lookup"><span data-stu-id="2f2df-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="2f2df-130">권한 부여</span><span class="sxs-lookup"><span data-stu-id="2f2df-130">Authorization</span></span> | <span data-ttu-id="2f2df-131">String</span><span class="sxs-lookup"><span data-stu-id="2f2df-131">String</span></span>   | <span data-ttu-id="2f2df-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2f2df-132">Bearer {token}.</span></span> <span data-ttu-id="2f2df-133">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-133">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="2f2df-134">요청 본문</span><span class="sxs-lookup"><span data-stu-id="2f2df-134">Request body</span></span>

<span data-ttu-id="2f2df-135">비어 있음</span><span class="sxs-lookup"><span data-stu-id="2f2df-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2f2df-136">응답</span><span class="sxs-lookup"><span data-stu-id="2f2df-136">Response</span></span>

<span data-ttu-id="2f2df-137">성공하면 이 메서드는 명령 결과에 대한 링크를 보유하는 개체가 있는 200, 확인 응답 코드를 반환합니다. </span><span class="sxs-lookup"><span data-stu-id="2f2df-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="2f2df-138">이 링크는 30분 동안 유효하며 로컬 저장소에 패키지를 다운로드하는 데 즉시 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="2f2df-139">만료된 링크를 다른 호출로 다시 만들 수 있으며 라이브 응답을 다시 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="2f2df-140">*런스크립트 전사 속성:*</span><span class="sxs-lookup"><span data-stu-id="2f2df-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="2f2df-141">속성</span><span class="sxs-lookup"><span data-stu-id="2f2df-141">Property</span></span>  | <span data-ttu-id="2f2df-142">설명</span><span class="sxs-lookup"><span data-stu-id="2f2df-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="2f2df-143">name</span><span class="sxs-lookup"><span data-stu-id="2f2df-143">name</span></span>          | <span data-ttu-id="2f2df-144">실행된 스크립트 이름</span><span class="sxs-lookup"><span data-stu-id="2f2df-144">Executed script name</span></span>                  |
| <span data-ttu-id="2f2df-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="2f2df-145">exit_code</span></span>     | <span data-ttu-id="2f2df-146">실행된 스크립트 종료 코드</span><span class="sxs-lookup"><span data-stu-id="2f2df-146">Executed script exit code</span></span>             |
| <span data-ttu-id="2f2df-147">script_output</span><span class="sxs-lookup"><span data-stu-id="2f2df-147">script_output</span></span> | <span data-ttu-id="2f2df-148">실행된 스크립트 표준 출력</span><span class="sxs-lookup"><span data-stu-id="2f2df-148">Executed script standard output</span></span>       |
| <span data-ttu-id="2f2df-149">script_error</span><span class="sxs-lookup"><span data-stu-id="2f2df-149">script_error</span></span>  | <span data-ttu-id="2f2df-150">실행된 스크립트 표준 오류 출력</span><span class="sxs-lookup"><span data-stu-id="2f2df-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="2f2df-151">예시</span><span class="sxs-lookup"><span data-stu-id="2f2df-151">Example</span></span>

<span data-ttu-id="2f2df-152">**요청**</span><span class="sxs-lookup"><span data-stu-id="2f2df-152">**Request**</span></span>

<span data-ttu-id="2f2df-153">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="2f2df-154">**응답**</span><span class="sxs-lookup"><span data-stu-id="2f2df-154">**Response**</span></span>

<span data-ttu-id="2f2df-155">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-155">Here is an example of the response.</span></span>

<span data-ttu-id="2f2df-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="2f2df-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="2f2df-157">콘텐츠 형식: application/json</span><span class="sxs-lookup"><span data-stu-id="2f2df-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="2f2df-158">*파일 콘텐츠:*</span><span class="sxs-lookup"><span data-stu-id="2f2df-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="2f2df-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2f2df-159">Related topics</span></span>

- [<span data-ttu-id="2f2df-160">컴퓨터 작업 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2df-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="2f2df-161">컴퓨터 작업 취소</span><span class="sxs-lookup"><span data-stu-id="2f2df-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="2f2df-162">라이브 응답 실행</span><span class="sxs-lookup"><span data-stu-id="2f2df-162">Run live response</span></span>](run-live-response.md) 
