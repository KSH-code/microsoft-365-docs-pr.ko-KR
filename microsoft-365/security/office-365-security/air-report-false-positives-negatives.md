---
title: Office 365 자동 조사 및 응답에서 가양성 또는 거짓 네거티브를 보고 하는 방법
description: Office 365 Advanced Threat Protection에서 누락 되었거나 검색 된 지워지는 있습니까? 분석을 위해 Microsoft에 가양성 또는 거짓 네거티브를 전송 하는 방법을 알아봅니다.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 66b81a474ff81df57c0b2a59672b17061f7235cb
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196086"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>자동화 된 조사 및 응답 기능에서 가양성/네거티브를 보고 하는 방법

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**적용 대상:**
- Office 365 Advanced Threat Protection

Office 365 누락 또는 지워지는 [의 검색에 대 한 자동화 된 조사 및 응답 (AIR) 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) 이 문제를 해결 하기 위해 수행할 수 있는 몇 가지 단계가 있습니다. 다음을 수행할 수 있습니다.
- [허위 긍정/음수를 Microsoft에 보고 합니다](#report-a-false-positivenegative-to-microsoft-for-analysis).
- 필요한 경우 [경고를 조정 합니다](#adjust-an-alert-to-prevent-false-positives-from-recurring) . 한 
- [수행한 수정 작업을 취소](#undo-a-remediation-action)합니다. 

이 문서를 참조 하십시오. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>분석을 위해 Microsoft에 가양성/음수 보고

Office 365 AIR에 전자 메일 메시지, 전자 메일 첨부 파일, 전자 메일 메시지의 url 또는 Office 파일의 URL이 누락 된 경우 [의심 스러운 스팸, 피싱, url 및 파일을 office 365 검색을 위해 Microsoft에 제출할](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)수 있습니다.

[맬웨어 분석을 위해 Microsoft에 파일을 제출할](https://www.microsoft.com/wdsi/filesubmission)수도 있습니다.

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>경고를 조정 하 여 가양성이 되풀이 되지 않도록 설정

합법적인 사용을 통해 경고가 트리거된 경우 또는 경고가 부정확 한 경우 [Cloud App Security 포털에서 알림을 관리할](https://docs.microsoft.com/cloud-app-security/managing-alerts)수 있습니다.

조직에서 Office 365 외에 [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) 을 사용 하는 경우 파일, IP 주소, URL 또는 도메인을 장치에서 맬웨어로 취급 해도 안전한 경우 [에도 장치에 대해 "허용" 작업을 사용 하 여 사용자 지정 표시기를 만들](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)수 있습니다.

## <a name="undo-a-remediation-action"></a>수정 작업 실행 취소

대부분의 경우 전자 메일 메시지, 전자 메일 첨부 파일 또는 URL에 대해 수정 작업을 수행 했지만 해당 항목이 실제로 위협이 되지 않는 경우 보안 운영 팀에서 수정 작업을 실행 취소 하 고 가양성을 반복 하지 않도록 조치를 취할 수 있습니다. 확인을 위해 [위협 탐색기나](#undo-an-action-using-threat-explorer) [작업 탭](#undo-an-action-using-the-actions-tab-for-an-investigation) 을 사용 하 여 작업을 취소할 수 있습니다. 

> [!IMPORTANT]
> 다음 작업을 수행 하기 전에 필요한 사용 권한이 있는지 확인 합니다.

### <a name="undo-an-action-using-threat-explorer"></a>위협 탐색기를 사용 하 여 작업 실행 취소

위협 탐색기를 사용 하는 경우 보안 운영 팀은 작업의 영향을 받는 전자 메일을 찾아 작업을 취소할 수 있습니다.

****

|시나리오|실행 취소 옵션|자세한 정보|
|---|---|---|
|전자 메일 메시지가 사용자의 정크 메일 폴더로 라우팅 됨|-메시지를 사용자의 지운 편지함 폴더로 이동 합니다.<br/>-사용자의 받은 편지 함으로 메시지를 이동 합니다. <br/>-메시지 삭제|[Office 365에서 제공 된 악성 전자 메일 찾기 및 조사](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|전자 메일 메시지 또는 파일이 격리 됨|-전자 메일 또는 파일을 릴리스 합니다. <br/>-전자 메일 또는 파일 삭제|[Office 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>조사에 대 한 작업 탭을 사용 하 여 작업 실행 취소

관리 센터에서 수행 된 재구성 작업을 확인 하 고 작업을 실행 취소할 수 있습니다.

1. [https://protection.office.com](https://protection.office.com)으로 이동하여 로그인합니다. 그러면 보안 & 준수 센터로 이동 합니다.

2. **위협 관리**  >  **조사**로 이동 합니다.

3. 조사 목록에서 항목 ID 옆에 **있는 새 창에서 열기** 아이콘을 선택 합니다.

4. **작업** 탭을 선택 합니다.

5. 상태가 **완료**됨 인 항목을 선택 하 고 **의사 결정** 열에서 **승인**됨과 같은 링크를 찾습니다. 그러면 작업에 대 한 자세한 정보가 포함 된 플라이 아웃이 열립니다.

6. 작업을 실행 취소 하려면 **수정 관리 삭제**를 선택 합니다.

## <a name="related-articles"></a>관련 문서

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Office 365에서 자동화 된 조사 및 응답 (AIR) 사용 시작](office-365-air.md)
