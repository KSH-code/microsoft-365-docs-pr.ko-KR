---
title: 바이러스 백신 검사 실행 API
description: 이 API를 사용하여 장치에서 바이러스 백신 검사 실행과 관련된 호출을 만들 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, 장치 분리
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
ms.openlocfilehash: df66a35cdce846ba9ca00e323f7c78e7d4d0ee73
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204004"
---
# <a name="run-antivirus-scan-api"></a>바이러스 백신 검사 실행 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

장치에서 Microsoft Defender 바이러스 백신 시작하세요.

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - 이 작업은 버전 1709 이상에서 Windows 10 장치에 사용할 수 있습니다.
> - A Microsoft Defender 바이러스 백신 (Microsoft Defender AV) 검사는 활성 바이러스 백신 솔루션인지 여부에 Microsoft Defender 바이러스 백신 다른 바이러스 백신 솔루션과 함께 실행할 수 있습니다. Microsoft Defender 바이러스 백신 수동 모드일 수 있습니다. 자세한 내용은 호환성 [Microsoft Defender 바이러스 백신 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md)

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Machine.Scan|'스캔 컴퓨터'
위임(직장 또는 학교 계정)|Machine.Scan|'스캔 컴퓨터'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
> - 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|String|Bearer {token}. **필수입니다**.
Content-Type|문자열|application/json

## <a name="request-body"></a>요청 본문

요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수|유형|설명
:---|:---|:---
Comment|String|작업과 연결되는 설명입니다. **필수입니다**.
ScanType|String|스캔 유형을 정의합니다. **필수입니다**.

**ScanType은** 수행할 검사 유형을 제어하며 다음 중 하나일 수 있습니다.

- **빠른**: 장치에서 빠른 검사 수행
- **전체:** 장치에서 전체 검사 수행

## <a name="response"></a>응답

성공하면 이 메서드는 응답 본문에 201, 만든 응답 코드 및 _MachineAction_ 개체를 반환합니다.

동일한 장치에 대해 바이러스 백신 검색을 실행하기 위해 여러 API 호출을 보내는 경우 "작업이 이미 진행 중입니다."라는 메시지가 있는 "컴퓨터 작업 보류 중" 또는 HTTP 400이 반환됩니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```
