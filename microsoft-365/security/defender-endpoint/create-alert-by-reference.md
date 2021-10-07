---
title: 이벤트 API에서 경고 만들기
description: 경고 만들기 API를 사용하여 끝점용 Microsoft Defender의 이벤트 위에 새 경고를 만드는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, alert, information, id
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
ms.openlocfilehash: fb30a5dbc2d5a6859343a1b382cdbd0106819cd2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191950"
---
# <a name="create-alert-api"></a>경고 API 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명

이벤트 의 [맨](alerts.md) 위에 새 **경고를 만듭니다.**

- **경고를 생성하려면 Microsoft Defender for Endpoint** 이벤트가 필요합니다.
- 요청에서 이벤트의 매개 변수 3개(이벤트 **시간,** 컴퓨터 ID 및 **보고서 ID)를 제공해야 합니다.**  아래 예제를 참조하세요.
- 고급 헌팅 API 또는 포털에 있는 이벤트를 사용할 수 있습니다.
- 동일한 Title을 사용하여 동일한 디바이스에 열려 있는 경고가 기존에 있는 경우 새로 만든 경고가 해당 경고와 병합됩니다.
- API를 통해 생성된 경고에 대한 자동 조사가 자동으로 시작됩니다.

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 15개 호출입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 | 사용 권한 | 사용 권한 표시 이름
:---|:---|:---
응용 프로그램 | Alert.ReadWrite.All | '모든 경고 읽기 및 쓰기'
위임(직장 또는 학교 계정) | Alert.ReadWrite | '경고 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '경고 조사'와 같은 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
> - 사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여 | String | Bearer {token}. **필수입니다**.
Content-Type | String | application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에 다음 값을 제공합니다(모두 필수).

속성 | 유형 | 설명
:---|:---|:---
eventTime | DateTime(UTC) | 고급 헌팅에서 얻은 이벤트의 정확한 시간(문자열)입니다. 예: 필수 ```2018-08-03T16:45:21.7115183Z``` .
reportId | String | 고급 헌팅에서 얻은 이벤트의 reportId입니다. **필수입니다**.
machineId | String | 이벤트를 식별한 장치의 ID입니다. **필수입니다**.
심각도 | String | 경고의 심각도입니다. 속성 값은 'Low', 'Medium' 및 'High'입니다. **필수입니다**.
title | String | 경고의 제목입니다. **필수입니다**.
설명 | String | 경고에 대한 설명입니다. **필수입니다**.
recommendedAction| String | 경고를 분석할 때 보안 담당자가 권장하는 작업입니다. **필수입니다**.
category| String | 경고 범주입니다. 속성 값은 "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required입니다.**

## <a name="response"></a>응답

성공하면 이 메서드는 200 OK를 [](alerts.md) 반환하고 응답 본문에 새 경고 개체를 반환합니다. 지정된 _속성(reportId,_ _eventTime_ 및 _machineId)이_ 있는 이벤트를 찾을 수 없는 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
