---
title: Office 365용 Microsoft Defender에서 자동화된 조사 후 가짓 긍정 또는 거짓 부정을 보고하는 방법
description: Office 365용 Microsoft Defender에서 AIR에서 누락되거나 잘못 감지된 것입니까? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
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
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 8a91a55d9598b5e780474315ddf1f7019e593fed
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406165"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>자동화된 조사 및 응답 기능에서 가짓 긍정/부정을 보고하는 방법

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Office 365의 자동화된](automated-investigation-response-office.md) 조사 및 대응(AIR) 기능이 누락되거나 잘못 감지된 경우 보안 운영 팀에서 이를 해결하기 위해 취할 수 있는 단계가 있습니다. 이러한 작업은 다음과 같습니다.

- [Microsoft에 가짓 긍정/음수 보고](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우) 및
- [수행된](#undo-a-remediation-action)수정 작업 취소

이 문서를 가이드로 사용하세요.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>분석을 위해 Microsoft에 가짓 긍정/음수 보고

Office 365용 Microsoft Defender에서 전자 메일 메시지, 전자 메일 첨부 파일, 전자 메일 메시지의 URL 또는 Office 파일의 URL이 누락된 경우 Office [365](admin-submission.md)검색을 위해 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출할 수 있습니다.

맬웨어 분석을 위해 Microsoft에 파일을 [제출할 수 있습니다.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>가식이 재발하지 않도록 경고 조정

합법적인 사용으로 경고가 트리거되거나 경고가 부정확한 경우 Cloud App Security 포털에서 경고를 [관리할 수 있습니다.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

조직에서 Office 365 외에 [끝점용 Microsoft Defender를](https://docs.microsoft.com/windows/security/threat-protection) 사용하고 파일, IP 주소, URL 또는 도메인이 안전한 경우에도 장치에서 맬웨어로 처리되는 경우 장치에 [대해 "허용"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)작업이 있는 사용자 지정 표시기를 만들 수 있습니다.

## <a name="undo-a-remediation-action"></a>수정 작업 실행 취소

대부분의 경우 전자 메일 메시지, 전자 메일 첨부 파일 또는 URL에 대해 수정 작업을 수행한 경우 항목이 실제로 위협이 아닌 경우 보안 운영 팀은 수정 작업을 실행 취소하고 가짓 긍정이 재발하지 않도록 조치를 취할 수 있습니다. 조사를 위해 [위협](#undo-an-action-using-threat-explorer) 탐색기 또는 [작업](#undo-an-action-in-the-action-center) 탭을 사용하여 작업을 실행 취소할 수 있습니다.

> [!IMPORTANT]
> 다음 작업을 수행하기 전에 필요한 사용 권한이 있는지 확인

### <a name="undo-an-action-using-threat-explorer"></a>위협 탐색기를 사용하여 작업 실행 취소

위협 탐색기를 사용하여 보안 운영 팀은 작업의 영향을 받는 전자 메일을 찾아 작업을 실행 취소할 수 있습니다.

|시나리오|옵션 취소|자세히 알아보기|
|---|---|---|
|전자 메일 메시지가 사용자의 정크 메일 폴더로 라우팅되었습니다.|- 메시지를 사용자의 지우기 항목 폴더로 이동<br/>- 메시지를 사용자의 받은 편지함으로 이동<br/>- 메시지 삭제|[Office 365에서 배달된 악성 전자 메일 찾기 및 조사](investigate-malicious-email-that-was-delivered.md)|
|전자 메일 메시지 또는 파일이 고지된 경우|- 전자 메일 또는 파일 해제<br/>- 전자 메일 또는 파일 삭제|[관리자로 quarantined messages 관리](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>동작 센터에서 작업 실행 취소

관리 센터에서 수행된 수정 작업을 보고 작업을 실행 취소할 수 있습니다.

1. Microsoft 365 보안 센터()로 <https://security.microsoft.com> 이동하십시오.
2. 탐색 창에서 작업 센터 **를 선택합니다.**
3. 완료된 **작업 목록을** 표시하려면 사용 기록 탭을 선택합니다.
4. 항목을 선택합니다. 플라이아웃 창이 열립니다.
5. 플라이아웃 창에서 **취소를 선택합니다.** (취소할 수 있는 작업만 취소 **단추가** 있습니다.)

## <a name="see-also"></a>참고 항목

- [Office 365용 Microsoft Defender](office-365-atp.md)
- [Microsoft Defender for Office 365의 자동화된 조사](office-365-air.md)
