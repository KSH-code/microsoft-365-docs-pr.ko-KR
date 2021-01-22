---
title: Microsoft 365 Defender에서 AIR에서 가긍성 또는 거짓 부정 처리
description: Microsoft 365 Defender에서 AIR에서 누락되거나 잘못 감지된 것이 있나요? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 가짓 긍정, 거짓 부정
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930357"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>자동화된 조사 및 응답 기능에서 가짓 긍정/부정 처리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

Microsoft [](mtp-autoir.md) 365 Defender의 자동화된 조사 및 대응 기능이 누락되거나 잘못된 것을 감지했습니까? 이를 해결하기 위해 취할 수 있는 단계가 있습니다. 다음을 수행할 수 있습니다.

- [Microsoft에 가짓 긍정/거짓 보고](#report-a-false-positivenegative-to-microsoft-for-analysis)

- [경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우) 및 

- 장치에서 수행된 재구성 [작업을 취소합니다.](#undo-a-remediation-action-that-was-taken-on-a-device) 

이 문서를 가이드로 사용하세요. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>분석을 위해 Microsoft에 가짓 긍정/부정 보고

|누락되거나 잘못 검색된 항목 |서비스  |수행할 작업  |
|---------|---------|---------|
|- 전자 메일 메시지 <br/>- 전자 메일 첨부 파일 <br/>- 전자 메일 메시지의 URL<br/>- Office 파일의 URL      |[Office 365용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[의심되는 스팸, 피싱, URL 및 파일을 검사하기 위해 Microsoft에 제출](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|디바이스의 파일 또는 앱    |[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[맬웨어 분석을 위해 Microsoft에 파일 제출](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>가식이 재발하지 않도록 경고 조정

|시나리오 |서비스 |수행할 작업 |
|--------|--------|--------|
|- 합법적인 사용에 의해 경고가 트리거됩니다. <br/>- 경고가 부정확합니다.    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 또는 <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Cloud App Security 포털에서 경고 관리](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|안전한 경우에도 파일, IP 주소, URL 또는 도메인은 장치에서 맬웨어로 처리됩니다.|[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) |["허용" 작업을 사용하여 사용자 지정 표시기 만들기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>장치에서 수행된 수정 작업 실행 취소

디바이스(예: Windows 10 장치)에서 수정 작업이 수행된 경우 항목이 실제로 위협이 아닌 경우 보안 운영 팀은 관리 센터에서 수정 작업을 실행 취소할 [수 있습니다.](mtp-action-center.md)

> [!IMPORTANT]
> 다음 작업을 수행하기 전에 [필요한](mtp-action-center.md#required-permissions-for-action-center-tasks) 권한이 있는지 확인하십시오.

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **작업 센터** 를 선택합니다. 

3. 사용 기록 **탭에서** 실행 취소할 작업을 선택합니다. 그러면 플라이아웃이 열립니다.<br/>
    > [!TIP]
    > 필터를 사용하여 결과 목록의 범위를 좁힐 수 있습니다. 

4. 선택한 항목에 대한 플라이아웃에서 조사 **열기 페이지를 선택합니다.**

5. 조사 세부 정보 보기에서 작업 **탭을** 선택합니다.

6. 완료 상태인 항목을 선택하고 결정 열에서 승인됨과 같은 링크를 **검색합니다.** 그러면 동작에 대한 자세한 정보가 있는 플라이아웃이 열립니다.

7. 작업을 실행 취소하려면 수정 **삭제를 선택합니다.**

## <a name="see-also"></a>기타 참고 항목

- [자동화 조사 세부정보 및 결과 보기](mtp-autoir-results.md)
- [Microsoft 365 Defender에서 고급 헌팅을 통해 위협을 사전 예방적으로 헌팅](advanced-hunting-overview.md)
