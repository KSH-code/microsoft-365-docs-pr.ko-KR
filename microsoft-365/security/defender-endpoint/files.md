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
ms.openlocfilehash: 9dffc5d2b7badba0a2f0e0b986973841ad488683
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220552"
---
# <a name="file-resource-type"></a>파일 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Defender for Endpoint의 파일 엔터티를 나타냅니다.

## <a name="methods"></a>메서드

방법|반환 형식 |설명
:---|:---|:---
[파일 다운로드](get-file-information.md) | [file](files.md) | 단일 파일 다운로드 
[파일 관련 경고 목록](get-file-related-alerts.md) | [경고](alerts.md) 컬렉션 | 파일과 [](alerts.md) 연결된 경고 엔터티를 얻습니다.
[파일 관련 컴퓨터 목록](get-file-related-machines.md) | [machine collection(컴퓨터](machine.md) 컬렉션) | 경고와 [](machine.md) 연결된 컴퓨터 엔터티를 얻습니다.
[파일 통계](get-file-statistics.md) | 통계 요약 | 지정한 파일의 보전을 검색합니다.


## <a name="properties"></a>속성

|속성 | 유형 | 설명 |
|:---|:---|:---|
|sha1 | String | 파일 콘텐츠의 Sha1 해시 |
|sha256 | String | 파일 콘텐츠의 Sha256 해시 |
|globalPrevalence | Nullable long | 조직 전체의 파일 보전 |
|globalFirstObserved | DateTimeOffset | 파일이 처음으로 관찰된 시간 |
|globalLastObserved | DateTimeOffset | 파일이 마지막으로 관찰된 시간 |
|size | Nullable long | 파일 크기 |
|fileType | String | 파일 형식 |
|isPeFile | 부울 | true이면 파일이 이식 가능한 실행 파일(예: "DLL", "EXE" 등)입니다. |
|filePublisher | 문자열 | 파일 게시자 |
|fileProductName | String | 제품 이름 |
|signer | String | 파일 서명자 |
|발급자 | String | 파일 발급자 |
|signerHash | 문자열 | 서명 인증서의 해시 |
|isValidCertificate | 부울 | Microsoft Defender for Endpoint 에이전트에서 인증서 서명이 성공적으로 확인된 경우 |
|determinationType | 문자열 | 파일의 결정 유형 |
|determinationValue | String | 결정 값 |

## <a name="json-representation"></a>Json 표현

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
