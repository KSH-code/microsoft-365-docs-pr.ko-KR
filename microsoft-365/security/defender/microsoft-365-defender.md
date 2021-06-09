---
title: Microsoft 365 Defender
description: Microsoft 365 Defender는 장치, ID, 데이터 및 응용 프로그램을 보호하도록 설계된 조정된 위협 보호 솔루션입니다.
keywords: MMicrosoft 365 Defender 소개, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 21a80abd36fd8e7e33f0ccf9b145d409119205ec
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842653"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험해 보고 싶으신가요? [랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

Microsoft 365 Defender는 기본적으로 엔드포인트, ID, 전자 메일 및 응용프로그램 전반에서 탐지, 방지, 조사 및 응답을 조정하여 정교한 공격에 대한 통합 보호를 제공하는 통합된 위반 전 및 위반 후 엔터프라이즈 보안 제품군입니다.

통합된 Microsoft 365 Defender 솔루션을 사용하여 보안 전문가는 이러한 각 제품이 수신하는 위협 신호를 통합하고 위협의 전체 범위와 영향을 확인할 수 있습니다. 환경이 환경에 들어오고 있는 방법, 영향을 받는 방법 및 현재 조직에 미치는 영향 Microsoft 365 Defender는 공격을 방지하거나 중지하고 영향을 받는 사서함, 끝점 및 사용자 ID를 자체적으로 고치기 위한 자동 조치를 취합니다.  


<center><h2>Microsoft 365 Defender 서비스</center></h2>
<table><tr><td><center><b><a href="/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>끝점용 Microsoft Defender</b></center></a></td>
<td><center><b><a href="/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/azure-advanced-threat-protection/"><b>Id용 Microsoft Defender</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender 대화형 가이드

이 대화형 가이드에서는 Defender를 통해 조직을 보호하는 Microsoft 365 있습니다. Defender가 어떻게 Microsoft 365 위험을 감지하고, 조직에 대한 공격을 조사하고, 유해한 활동을 자동으로 방지하는 데 도움이 되는 방법을 알 수 있습니다.

[대화형 가이드 확인](https://aka.ms/M365Defender-InteractiveGuide)



Microsoft 365 Defender 제품군은 다음을 보호합니다. 
- **Endpoint용 Microsoft Defender의** 끝점 - 끝점용 Microsoft Defender는 예방적 보호, 사후 위반 감지, 자동화된 조사 및 대응을 위한 통합된 끝점 플랫폼입니다. 
- **Microsoft Defender와의** 전자 메일 및 공동 Office 365 - Office 365 메시지, 링크(URL) 및 공동 작업 도구로 위협되는 악의적인 위협에 대해 조직을 보호합니다. 
- **ID에 대한 Microsoft Defender 및 Azure AD ID** 보호를 사용하는 ID - ID용 Microsoft Defender는 Active Directory 신호를 사용하여 조직에 대한 고급 위협, 손상된 ID 및 악의적인 내부자 작업을 식별, 감지 및 조사합니다. 
- **Microsoft Cloud App security를** 사용하는 응용 프로그램 - Microsoft Cloud App security는 클라우드 앱에 심층 가시성, 강력한 데이터 제어 및 향상된 위협 보호를 가져오는 포괄적인 교차 SaaS 솔루션입니다. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender의 고유한 제품 간 계층은 개별 제품군 구성 요소를 다음으로 향상합니다.
- 신호 공유 및 자동화된 작업을 통해 제품군 전체에서 공격으로부터 보호하고 방어 대응을 조정합니다.
- 경고, 의심스러운 이벤트 및 영향을 미치는 자산을 '인시던트'에 가입하여 보안 팀의 제품 경고, 동작 및 컨텍스트 전반에 걸쳐 공격의 전체 스토리를 내레이션합니다.
- 자동화된 수정을 통해 영향을 미치는 자산에 대한 자동 복구를 트리거하여 손상에 대한 대응 자동화
- 보안 팀이 끝점 및 데이터 전체에서 세부적이고 효과적인 위협 헌팅을 Office 수 있습니다.

![인시던트 개요 페이지 이미지](../../media/overview-incident.png) <br>
제품 간 인시던트(개요)

![경고 큐의 이미지](../../media/incident-list.png)<br>
제품군 제품 전반에 걸쳐 단일 인시던트로 상호 연관된 모든 관련 경고(경고 보기)

![인시던트 큐 이미지](../../media/advanced-hunting.png)<br>
전자 메일 및 끝점 원시 데이터를 기반으로 쿼리 기반 헌팅


Microsoft 365 Defender 제품 간 기능은 다음과 같습니다. 
- **제품 간** 단일 창 - 검색, 영향을 미치는 자산, 수행된 자동화된 작업 및 단일 큐의 관련 증거에 대한 모든 정보를 중앙에서 볼 수 [security.microsoft.com.](https://security.microsoft.com) 
- **결합된** 인시던트 큐 - 전체 공격 범위를 보장하여 보안 전문가가 중요한 작업에 집중할 수 있도록 영향을 미치는 자산 및 자동화된 수정 작업이 그룹화되어 시기적합한 방식으로 표시됩니다. 
- **위협에 대한** 자동 대응 - 공격의 진행을 중지하는 데 도움이 Microsoft 365 위험 위협 정보가 실시간으로 공유됩니다. 예를 들어 끝점용 Microsoft Defender가 보호하는 끝점에서 악성 파일이 감지되면 Defender에 모든 전자 Office 365 파일을 검사하고 제거합니다. 이 파일은 전체 보안 제품군에 의해 Microsoft 365 차단됩니다.
- **손상된 장치,** 사용자 ID 및 사서함에 대한 자체 복구 - Microsoft 365 Defender는 AI 기반 자동 작업 및 플레이북을 사용하여 영향을 받는 자산을 안전한 상태로 다시 수정합니다. Microsoft 365 Defender는 제품군 제품의 자동 수정 기능을 활용하여 인시던트와 관련된 모든 영향을 미치는 자산이 가능한 경우 자동으로 수정되도록 합니다.
- **제품** 간 위협 헌팅 - 보안 팀은 다양한 보호 제품에서 수집한 원시 데이터에 대해 자체 사용자 지정 쿼리를 만들어 고유한 조직 지식을 활용하여 손상 징후를 찾을 수 있습니다. Microsoft 365 Defender는 30일 동안의 기록 원시 신호 및 경고 데이터에 대한 쿼리 기반 액세스를 제공합니다. 끝점에서 경고 데이터와 데이터 보호를 위한 Microsoft Defender Office 365 제공합니다. 


## <a name="get-started"></a>시작
Microsoft 365 의 Microsoft 365 보안 센터에서 서비스를 사용하도록 설정하려면 먼저 Defender 라이선스 요구 사항을 [security.microsoft.com.](https://security.microsoft.com) 자세한 내용은 다음을 참조하십시오.
- [라이선스 요구 사항](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender 켜기](m365d-enable.md)


## <a name="see-also"></a>참고 항목
- [여러 보안 기능으로 위협 방지 Microsoft 365 E5](/microsoft-365/solutions/deploy-threat-protection)
