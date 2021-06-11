---
title: 장치에서 라이브 응답 명령 실행
description: 디바이스에서 일련의 라이브 응답 명령을 실행하는 방법을 확인합니다.
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879703"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="cfc29-104">장치에서 라이브 응답 명령 실행</span><span class="sxs-lookup"><span data-stu-id="cfc29-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cfc29-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="cfc29-105">**Applies to:**</span></span>
- [<span data-ttu-id="cfc29-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfc29-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="cfc29-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="cfc29-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cfc29-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="cfc29-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="cfc29-109">API description</span></span>

<span data-ttu-id="cfc29-110">디바이스에서 일련의 라이브 응답 명령 실행</span><span class="sxs-lookup"><span data-stu-id="cfc29-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="cfc29-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="cfc29-111">Limitations</span></span>

1.  <span data-ttu-id="cfc29-112">이 API에 대한 속도 제한은 분당 10통입니다(추가 요청은 HTTP 429로 응답).</span><span class="sxs-lookup"><span data-stu-id="cfc29-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="cfc29-113">25개 세션을 동시 실행합니다(제한 제한을 초과하는 요청은 "429 - 요청 수가 너무 많음" 응답이 수신됩니다).</span><span class="sxs-lookup"><span data-stu-id="cfc29-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="cfc29-114">머신을 사용할 수 없는 경우 세션은 최대 3일 동안 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="cfc29-115">RunScript 명령 시간 제한은 10분 후입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="cfc29-116">라이브 응답 명령이 실패하면 모든 후속 작업이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="cfc29-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="cfc29-117">Permissions</span></span>

<span data-ttu-id="cfc29-118">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cfc29-119">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cfc29-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="cfc29-120">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="cfc29-120">Permission type</span></span>                    | <span data-ttu-id="cfc29-121">사용 권한</span><span class="sxs-lookup"><span data-stu-id="cfc29-121">Permission</span></span>           | <span data-ttu-id="cfc29-122">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="cfc29-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="cfc29-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="cfc29-123">Application</span></span>                        | <span data-ttu-id="cfc29-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="cfc29-124">Machine.LiveResponse</span></span> | <span data-ttu-id="cfc29-125">특정 컴퓨터의 실시간 응답 실행</span><span class="sxs-lookup"><span data-stu-id="cfc29-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="cfc29-126">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="cfc29-126">Delegated (work or school account)</span></span> | <span data-ttu-id="cfc29-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="cfc29-127">Machine.LiveResponse</span></span> | <span data-ttu-id="cfc29-128">특정 컴퓨터의 실시간 응답 실행</span><span class="sxs-lookup"><span data-stu-id="cfc29-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="cfc29-129">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="cfc29-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="cfc29-130">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="cfc29-130">Request headers</span></span>

| <span data-ttu-id="cfc29-131">이름</span><span class="sxs-lookup"><span data-stu-id="cfc29-131">Name</span></span>      | <span data-ttu-id="cfc29-132">유형</span><span class="sxs-lookup"><span data-stu-id="cfc29-132">Type</span></span> | <span data-ttu-id="cfc29-133">설명</span><span class="sxs-lookup"><span data-stu-id="cfc29-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="cfc29-134">권한 부여</span><span class="sxs-lookup"><span data-stu-id="cfc29-134">Authorization</span></span> | <span data-ttu-id="cfc29-135">String</span><span class="sxs-lookup"><span data-stu-id="cfc29-135">String</span></span>   | <span data-ttu-id="cfc29-136">Bearer\<token>\.</span><span class="sxs-lookup"><span data-stu-id="cfc29-136">Bearer\<token>\.</span></span> <span data-ttu-id="cfc29-137">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-137">Required.</span></span>   |
| <span data-ttu-id="cfc29-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cfc29-138">Content-Type</span></span>  | <span data-ttu-id="cfc29-139">문자열</span><span class="sxs-lookup"><span data-stu-id="cfc29-139">string</span></span>   | <span data-ttu-id="cfc29-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="cfc29-140">application/json.</span></span> <span data-ttu-id="cfc29-141">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-141">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="cfc29-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="cfc29-142">Request body</span></span>

| <span data-ttu-id="cfc29-143">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfc29-143">Parameter</span></span> | <span data-ttu-id="cfc29-144">유형</span><span class="sxs-lookup"><span data-stu-id="cfc29-144">Type</span></span> | <span data-ttu-id="cfc29-145">설명</span><span class="sxs-lookup"><span data-stu-id="cfc29-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="cfc29-146">Comment</span><span class="sxs-lookup"><span data-stu-id="cfc29-146">Comment</span></span>       | <span data-ttu-id="cfc29-147">String</span><span class="sxs-lookup"><span data-stu-id="cfc29-147">String</span></span>   | <span data-ttu-id="cfc29-148">작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="cfc29-149">명령</span><span class="sxs-lookup"><span data-stu-id="cfc29-149">Commands</span></span>      | <span data-ttu-id="cfc29-150">배열</span><span class="sxs-lookup"><span data-stu-id="cfc29-150">Array</span></span>    | <span data-ttu-id="cfc29-151">실행할 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-151">Commands to run.</span></span> <span data-ttu-id="cfc29-152">허용되는 값은 PutFile, RunScript, GetFile입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="cfc29-153">명령:</span><span class="sxs-lookup"><span data-stu-id="cfc29-153">Commands:</span></span>

| <span data-ttu-id="cfc29-154">명령 유형</span><span class="sxs-lookup"><span data-stu-id="cfc29-154">Command Type</span></span> | <span data-ttu-id="cfc29-155">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfc29-155">Parameters</span></span>                                                                          | <span data-ttu-id="cfc29-156">설명</span><span class="sxs-lookup"><span data-stu-id="cfc29-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cfc29-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="cfc29-157">PutFile</span></span>      | <span data-ttu-id="cfc29-158">키: FileName</span><span class="sxs-lookup"><span data-stu-id="cfc29-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="cfc29-159">값: \<file name\></span><span class="sxs-lookup"><span data-stu-id="cfc29-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="cfc29-160">라이브러리에서 장치로 파일을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="cfc29-161">파일은 작업 폴더에 저장되고 장치가 기본적으로 다시 시작될 때 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="cfc29-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="cfc29-162">RunScript</span></span>    | <span data-ttu-id="cfc29-163">키: ScriptName</span><span class="sxs-lookup"><span data-stu-id="cfc29-163">Key: ScriptName</span></span><br><span data-ttu-id="cfc29-164">값: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="cfc29-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="cfc29-165">키: Args</span><span class="sxs-lookup"><span data-stu-id="cfc29-165">Key: Args</span></span>  <br> <span data-ttu-id="cfc29-166">값: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="cfc29-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="cfc29-167">디바이스의 라이브러리에서 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="cfc29-168">Args 매개 변수는 스크립트로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="cfc29-169">10분 후의 시간 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="cfc29-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="cfc29-170">GetFile</span></span>      | <span data-ttu-id="cfc29-171">키: Path</span><span class="sxs-lookup"><span data-stu-id="cfc29-171">Key: Path</span></span> <br> <span data-ttu-id="cfc29-172">값: \<File path\></span><span class="sxs-lookup"><span data-stu-id="cfc29-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="cfc29-173">장치에서 파일을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-173">Collect file from a device.</span></span> <span data-ttu-id="cfc29-174">참고: 경로의 백슬래시를 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="cfc29-175">응답</span><span class="sxs-lookup"><span data-stu-id="cfc29-175">Response</span></span>

-   <span data-ttu-id="cfc29-176">성공하면 이 메서드는 200, 확인을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="cfc29-177">작업 엔터티.</span><span class="sxs-lookup"><span data-stu-id="cfc29-177">Action entity.</span></span> <span data-ttu-id="cfc29-178">지정한 ID가 있는 머신을 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="cfc29-179">예시</span><span class="sxs-lookup"><span data-stu-id="cfc29-179">Example</span></span>

<span data-ttu-id="cfc29-180">**요청**</span><span class="sxs-lookup"><span data-stu-id="cfc29-180">**Request**</span></span>

<span data-ttu-id="cfc29-181">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="cfc29-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="cfc29-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="cfc29-183">**응답**</span><span class="sxs-lookup"><span data-stu-id="cfc29-183">**Response**</span></span>

<span data-ttu-id="cfc29-184">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="cfc29-185">콘텐츠 형식: application/json</span><span class="sxs-lookup"><span data-stu-id="cfc29-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="cfc29-186">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cfc29-186">Related topics</span></span>
- [<span data-ttu-id="cfc29-187">컴퓨터 작업 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc29-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="cfc29-188">라이브 응답 결과 얻기</span><span class="sxs-lookup"><span data-stu-id="cfc29-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="cfc29-189">컴퓨터 작업 취소</span><span class="sxs-lookup"><span data-stu-id="cfc29-189">Cancel machine action</span></span>](cancel-machine-action.md)
