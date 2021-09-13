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
ms.openlocfilehash: 4e52906cda48314967e40039caabfd81e38514c1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210342"
---
# <a name="get-live-response-results"></a>라이브 응답 결과 얻기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

인덱스로 특정 라이브 응답 명령 결과를 검색합니다.

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="minimum-requirements"></a>최소 요구 사항

장치에서 세션을 시작하려면 먼저 다음 요구 사항을 충족해야 합니다.

- 지원되는 버전의 를 실행 **중인지 Windows.**

  장치에서 다음 버전의 디바이스 중 하나를 실행해야 Windows

  - **Windows 10**
    - [버전 1909](/windows/whats-new/whats-new-windows-10-version-1909) 이상
    - [버전 1903(KB4515384)](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384) [](/windows/whats-new/whats-new-windows-10-version-1903)
    - [KB4537818이](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) 있는 버전 [1809(RS 5)](/windows/whats-new/whats-new-windows-10-version-1809)
    - [KB4537795가](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795) 있는 버전 [1803(RS 4)](/windows/whats-new/whats-new-windows-10-version-1803)
    - [KB4537816이](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816) 있는 버전 [1709(RS 3)](/windows/whats-new/whats-new-windows-10-version-1709)

  - **Windows Server 2019 - 공개 미리 보기에만 해당**
    - 버전 1903 또는 이후 [버전(KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)사용)
    - 버전 [1809(KB4537818)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)

|사용 권한 유형|사용 권한|사용 권한 표시 이름|
|---|---|---|
응용 프로그램|Machine.Read.All|''모든 컴퓨터 프로필 읽기''
응용 프로그램|"Machine.ReadWrite.All|'모든 컴퓨터 정보 읽기 및 쓰기'
|위임(직장 또는 학교 계정)|Machine.LiveResponse|특정 컴퓨터의 실시간 응답 실행|

## <a name="http-request"></a>HTTP 요청

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>요청 헤더

|이름|유형|설명|
|---|---|---|
|권한 부여|String|Bearer {token}. 필수 특성입니다.|

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공하면 이 메서드는 명령 결과에 대한 링크를 보유하는 개체가 있는 200, 확인 응답 코드를 반환합니다.  이 링크는 30분 동안 유효하며 로컬 저장소에 패키지를 다운로드하는 데 즉시 사용해야 합니다. 만료된 링크를 다른 호출로 다시 만들 수 있으며 라이브 응답을 다시 실행할 필요가 없습니다.

*런스크립트 전사 속성:*

|속성|설명|
|---|---|
|script_name|실행된 스크립트 이름|
|exit_code|실행된 스크립트 종료 코드|
|script_output|실행된 스크립트 표준 출력|
|script_errors|실행된 스크립트 표준 오류 출력|

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

HTTP/1.1 200 Ok

콘텐츠 형식: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*파일 콘텐츠:*

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_errors":""
}
```

## <a name="related-topics"></a>관련 항목

- [컴퓨터 작업 API를 얻습니다.](get-machineaction-object.md)
- [컴퓨터 작업 취소](cancel-machine-action.md)
- [실시간 응답 실행](run-live-response.md) 
