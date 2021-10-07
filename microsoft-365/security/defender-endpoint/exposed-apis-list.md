---
title: 지원되는 엔드포인트용 Microsoft Defender API
ms.reviewer: ''
description: API 호출을 만들 수 있는 끝점 엔터티에 대해 지원되는 특정 Microsoft Defender에 대해 자세히 알아보습니다.
keywords: api, 지원되는 api, 배우, 경고, 장치, 사용자, 도메인, ip, 파일, 고급 쿼리, 고급 헌팅
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8623a4932c23748e35af480613c1e5baac3bbcf6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191902"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>지원되는 엔드포인트용 Microsoft Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>끝점 URI 및 버전

### <a name="endpoint-uri"></a>끝점 URI

> 서비스 기본 URI는 다음입니다. [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> 쿼리 기반 OData에는 '/api' prefix가 있습니다. 예를 들어 알림을 얻기 위해 GET 요청을 보낼 수 있습니다. [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>버전 관리

> API는 버전 관리가 지원됩니다.
>
> 현재 버전은 **V1.0입니다.**
>
> 특정 버전을 사용 하도록 다음 형식을 사용 `https://api.securitycenter.microsoft.com/api/{Version}` 합니다. . 예: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> 버전(예: )을 지정하지 않으면 최신 `https://api.securitycenter.microsoft.com/api/alerts` 버전으로 변경됩니다.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

API 호출을 실행할 수 있는 지원되는 개별 엔터티 및 HTTP 요청 값, 요청 헤더 및 예상 응답과 같은 세부 정보를 자세히 알아보습니다.

## <a name="in-this-section"></a>이 섹션의 내용

항목 | 설명
:---|:---
[지능형 헌팅](run-advanced-query-api.md) | API에서 쿼리를 실행합니다.
[경고 방법 및 속성](alerts.md) | 경고 다운로드, 경고 만들기, 경고 업데이트 등의 API \- 호출을 실행합니다.
[장치당 평가 방법 및 속성 내보내기](get-assessment-methods-properties.md) | API 호출을 실행하여 보안 구성 평가 내보내기, 소프트웨어 인벤토리 평가 내보내기, 소프트웨어 취약점 평가 내보내기 및 델타 내보내기 소프트웨어 취약성 평가와 같은 장치 기준에 따라 취약점 평가를 \- 수집합니다.
[자동화된 조사 방법 및 속성](investigation.md) | 조사 컬렉션을 수집하는 등의 API \- 호출을 실행합니다.
[도메인 관련 경고 가져오기](get-domain-related-alerts.md) | 도메인 관련 장치, 도메인 통계 등의 API \- 호출을 실행합니다.
[파일 방법 및 속성](files.md) | 파일 정보 다운로드, 파일 관련 경고, 파일 관련 장치 및 파일 통계와 같은 API \- 호출을 실행합니다.
[지표 방법 및 속성](ti-indicator.md) | 표시기 get, Indicator 만들기, 표시기 삭제 등의 API \- 호출을 실행합니다.
[IP 관련 경고 가져오기](get-ip-related-alerts.md) | IP 관련 경고를 수집하고 IP 통계를 수집하는 \- 등의 API 호출을 실행합니다.
[컴퓨터 방법 및 속성](machine.md) | 장치 검색, ID로 장치 검색, 로그온한 사용자에 대한 정보, 태그 편집 등의 API \- 호출을 실행합니다.
[컴퓨터 작업 방법 및 속성](machineaction.md) | ISOLATION, 바이러스 백신 검사 실행 등의 API \- 호출을 실행합니다.
[권장 방법 및 속성](recommendation.md) | ID로 추천 등의 API \- 호출을 실행합니다.
[수정 작업 방법 및 속성](get-remediation-methods-properties.md) | 모든 재구성 작업을 시작하고, 노출된 장치 수정 작업을 시작하고, ID로 하나의 재구성 작업을 수행하는 등의 API \- 호출을 실행합니다.
[점수 방법 및 속성](score.md) | 노출 점수 얻기 또는 장치 보안 점수 얻기 등의 API \- 호출을 실행합니다.
[소프트웨어 방법 및 속성](software.md) | 소프트웨어의 목록 \- 취약점과 같은 API 호출을 실행합니다.
[사용자 방법](user.md) | 사용자 관련 알림 및 사용자 관련 장치와 같은 API \- 호출을 실행합니다.
[취약성 방법 및 속성](vulnerability.md) | 취약성으로 목록 장치와 같은 API \- 호출을 실행합니다.

## <a name="see-also"></a>참고 항목

- [끝점 API용 Microsoft Defender](apis-intro.md)

- [끝점용 Microsoft Defender API 릴리스 정보](api-release-notes.md)
