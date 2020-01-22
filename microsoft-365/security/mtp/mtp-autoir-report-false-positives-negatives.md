---
title: Microsoft Threat Protection의 AIR에서 가양성 또는 거짓 네거티브를 보고 하는 방법
description: Microsoft Threat Protection의 AIR에서 누락 되었거나 지워지는이 감지 되었습니까? 분석을 위해 Microsoft에 가양성 또는 거짓 네거티브를 전송 하는 방법을 알아봅니다.
keywords: 자동, 조사, 경고, 트리거, 작업, 재구성, 거짓 긍정, 거짓 음수
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260196"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>자동화 된 조사 및 응답 기능에서 가양성/네거티브를 보고 하는 방법

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection에 대 [한 자동화 된 조사 및 응답 기능이](mtp-autoir.md) 없거나 지워지는에서 감지 되었습니까? 이를 Microsoft에 보고 하거나 필요한 경우 경고를 조정할 수 있습니다. 다음 표를 참조 하십시오. 


|항목  |검색 기준  |보고 방법  |
|---------|---------|---------|
|전자 메일 메시지 <br/>전자 메일 첨부 파일 <br/>전자 메일 메시지 또는 Office 파일의 URL      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[의심 스러운 스팸, 피싱, Url 및 파일을 Microsoft에 Office 365 검색에 제출](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|장치에 있는 파일 또는 앱    |[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)         |[맬웨어 분석을 위해 Microsoft에 파일 제출](https://www.microsoft.com/wdsi/filesubmission)         |
|합법적인 사용에 의해 트리거되는 경고 <br/>부정확 한 경고    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 또는 <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Cloud App Security 포털에서 알림 관리](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>다음 단계

- [자동화된 조사 및 대응과 관련된 조치 승인 또는 거부](mtp-autoir-actions.md)
- [알림 센터에 대한 자세한 정보](mtp-action-center.md)
- [Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응](advanced-hunting-overview.md)
