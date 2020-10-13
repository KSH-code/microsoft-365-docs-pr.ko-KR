---
title: Microsoft Threat Protection의 AIR에서 가양성 또는 거짓 네거티브 처리
description: Microsoft Threat Protection의 AIR에서 누락 되었거나 지워지는이 감지 되었습니까? 분석을 위해 Microsoft에 가양성 또는 거짓 네거티브를 전송 하는 방법을 알아봅니다.
keywords: 자동, 조사, 경고, 트리거, 작업, 재구성, 거짓 긍정, 거짓 음수
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ecfd1bb9e5ff548c08aea322d12d626fa7fb6120
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429638"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>자동화 된 조사 및 응답 기능에서 가양성/네거티브 처리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

Microsoft Threat Protection에 대 [한 자동화 된 조사 및 응답 기능이](mtp-autoir.md) 없거나 지워지는에서 감지 되었습니까? 이 문제를 해결 하기 위해 수행할 수 있는 몇 가지 단계가 있습니다. 다음을 수행할 수 있습니다.

- [허위 긍정/음수를 Microsoft에 보고 합니다](#report-a-false-positivenegative-to-microsoft-for-analysis).

- 필요한 경우 [경고를 조정 합니다](#adjust-an-alert-to-prevent-false-positives-from-recurring) . 한 

- [장치에 대해 수행 된 재구성 작업을 실행 취소](#undo-a-remediation-action-that-was-taken-on-a-device)합니다. 

이 문서를 참조 하십시오. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>분석을 위해 Microsoft에 가양성/음수 보고

|누락 된 항목 또는 지워지는 검색 |서비스  |수행할 작업  |
|---------|---------|---------|
|-전자 메일 메시지 <br/>-전자 메일 첨부 파일 <br/>-전자 메일 메시지의 URL<br/>-Office 파일의 URL      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[검색을 위해 Microsoft에 의심 스러운 스팸, 피싱, Url 및 파일 제출](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|장치에 있는 파일 또는 앱    |[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)         |[맬웨어 분석을 위해 Microsoft에 파일 제출](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>경고를 조정 하 여 가양성이 되풀이 되지 않도록 설정

|시나리오 |서비스 |수행할 작업 |
|--------|--------|--------|
|-합법적인 사용을 통해 알림이 트리거되는 경우 <br/>-경고가 부정확 함    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 또는 <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Cloud App Security 포털에서 알림 관리](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|파일, IP 주소, URL 또는 도메인은 안전한 경우에도 장치에서 맬웨어로 취급 됩니다.|[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) |["허용" 작업을 사용 하 여 사용자 지정 표시기 만들기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>장치에서 수행한 수정 작업 실행 취소

장치에서 수정 작업을 수행 하는 경우 (예: Windows 10 장치) 해당 항목이 실제로 위협이 되지 않으면 보안 운영 팀이 [작업 센터](mtp-action-center.md)에서 수정 작업을 실행 취소할 수 있습니다.

> [!IMPORTANT]
> 다음 작업을 수행 하기 전에 [필요한 사용 권한이](mtp-action-center.md#required-permissions-for-action-center-tasks) 있는지 확인 합니다.

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **작업 센터**를 선택합니다. 

3. **기록** 탭에서 취소할 작업을 선택 합니다. 플라이 아웃이 열립니다.<br/>
    > [!TIP]
    > 필터를 사용 하 여 결과 목록의 범위를 좁힐 수 있습니다. 

4. 선택한 항목에 대 한 플라이 아웃에서 **열기 조사 페이지**를 선택 합니다.

5. 조사 세부 정보 보기에서 **작업** 탭을 선택 합니다.

6. 상태가 **완료**됨 인 항목을 선택 하 고 **결정 사항** 열에서 **승인**됨과 같은 링크를 찾습니다. 그러면 작업에 대 한 자세한 정보가 포함 된 플라이 아웃이 열립니다.

7. 작업을 실행 취소 하려면 **수정 관리 삭제**를 선택 합니다.

## <a name="see-also"></a>참고 항목

- [자동화 조사 세부정보 및 결과 보기](mtp-autoir-results.md)
- [Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응](advanced-hunting-overview.md)
