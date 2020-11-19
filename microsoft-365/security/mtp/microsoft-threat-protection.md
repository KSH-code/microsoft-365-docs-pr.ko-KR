---
title: Microsoft 365 Defender
description: Microsoft 365 Defender는 장치, id, 데이터 및 응용 프로그램을 보호 하기 위한 조정 된 위협 보호 솔루션입니다.
keywords: Microsoft Threat Protection 소개, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화 된 조사 및 개선, 고급 구하기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 573f30dc3d8a43a337a4333dbaf05baf916857fa
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357906"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험해 원하십니까? [랩 환경에서이를 평가](https://aka.ms/mtp-trial-lab) 하거나 [프로덕션에서 파일럿 프로젝트를 실행할](https://aka.ms/m365d-pilotplaybook)수 있습니다.
>

Microsoft 365 Defender는 끝점, id, 전자 메일 및 응용 프로그램 간의 검색, 예방, 조사 및 응답을 고유 하 게 조정 하 고 복잡 한 공격에 대 한 통합 된 보호 기능을 제공 하는 통합 사전 및 사후 위반 엔터프라이즈 방어 제품군입니다.

통합 된 Microsoft 365 Defender 솔루션을 통해 보안 전문가는 이러한 각 제품이 수신 하 고 위협의 모든 범위와 영향을 결정 하는 위협 신호를 함께 연결할 수 있습니다. 환경의 진입 방식, 영향을 받는 대상 및 현재 조직에 영향을 주는 방법 Microsoft 365 Defender는 자동 작업을 수행 하 여 공격을 방지 하거나 중지 하 고 영향을 받는 사서함, 끝점 및 사용자 id를 자체 치유 합니다.  


<center><h2>Microsoft 365 Defender services</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>끝점에 대 한 Microsoft Defender</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Id 용 Microsoft Defender</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>이 [Microsoft 365 Defender interactive 가이드](https://aka.ms/MTP-Interactive-Guide)를 확인 하세요.


Microsoft 365 Defender suite는 다음을 보호 합니다. 
- 끝점에 대 한 **Microsoft defender** for endpoint-microsoft Defender for Endpoints는 예방적 보호, 위반 감지, 자동화 된 조사 및 응답을 위한 통합 끝점 플랫폼입니다. 
- **전자 메일 및 공동 작업-Microsoft defender For office 365** -Defender for office 365-전자 메일 메시지, 링크 (url) 및 공동 작업 도구를 통해 야기 되는 악의적인 위협 으로부터 조직을 보호 합니다. 
- Id **및 AZURE AD Id 보호를 위한 Microsoft defender를 포함** 하는 id-microsoft Defender for Identity는 Active Directory 신호를 사용 하 여 고급 위협, 손상 된 id 및 조직에서 보낸 악성 참가자 작업을 식별, 감지 및 조사 합니다. 
- **Microsoft Cloud app security를 사용 하는 응용 프로그램** -Microsoft cloud app security는 클라우드 앱에 대 한 심층 가시성, 강력한 데이터 제어 및 향상 된 위협 보호를 가져오는 포괄적인 공동 SaaS 솔루션입니다. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender의 고유한 교차 제품 계층은 다음과 같은 기능을 위해 개별 제품군 구성 요소를 보완 합니다.
- 공격 으로부터 보호 하 고 신호 공유 및 자동화 된 작업을 통해 도구 모음 전체의 방어 응답을 조정 합니다.
- 경고, 의심 스러운 이벤트 및 영향을 받는 자산에 대 한 정보를 ' 인시던트 '에 가입 시켜 보안 팀에 대 한 전체 공격 텍스트를 제품 경고, 동작 및 컨텍스트 간에 내레이션 합니다.
- 자동 수정을 통해 영향을 받는 자산에 대해 자동 복구를 트리거하여 손상에 대 한 대응 자동화
- 보안 팀이 끝점 및 Office 데이터에서 상세 하 고 효과적으로 위협을 수행할 수 있도록 설정

![인시던트 개요 페이지의 이미지](../../media/overview-incident.png) <br>
제품 간 인시던트 (개요)

![경고 큐 이미지](../../media/incident-list.png)<br>
단일 인시던트 (알림 보기)로 상호 연결 된 제품군 제품의 모든 관련 알림

![인시던트 큐의 이미지](../../media/advanced-hunting.png)<br>
전자 메일 및 끝점 원시 데이터의 맨 위에 쿼리 기반 검색


Microsoft 365 Defender 제품 간 기능은 다음과 같습니다. 
- **제품 간 단일 창에는** 검색, 영향을 받는 자산, 자동 작업 및 단일 큐에 있는 관련 증거, [security.microsoft.com](https://security.microsoft.com)의 단일 창에 대 한 모든 정보가 표시 됩니다. 
- 보안 전문가 들이 **결합 된 인시던트 큐** -전체 공격 범위를 보장 하 여 중요 한 사항, 즉 영향을 받는 자산과 자동화 된 재구성 작업을 적시에 그룹화 하 여 표시 합니다. 
- 위협에 중요 한 위협 정보 **에 대 한 자동 응답** 은 공격 진행을 중지 하는 데 도움이 되도록 Microsoft 365 Defender 제품 간에 실시간으로 공유 됩니다. 예를 들어 Microsoft Defender for Endpoint를 통해 보호 되는 끝점에서 악성 파일이 검색 되는 경우 Defender for Office 365에서 모든 전자 메일 메시지의 파일을 검색 하 고 제거 하 라고 지시 합니다. 이 파일은 전체 Microsoft 365 보안 제품군에 의해 차단 됩니다.
- **손상 된 장치, 사용자 id 및 사서함에 대 한 자동 복구** -Microsoft 365 Defender에서는 AI 기반 자동 작업 및 playbook 사용 하 여 영향을 받는 자산을 안전한 상태로 다시 수정 합니다. Microsoft 365 Defender는 도구 모음 제품의 자동 수정 기능을 활용 하 여 문제와 관련 된 모든 영향을 받는 자산이 가능한 경우 자동으로 재구성 되도록 합니다.
- **제품 간 위협 사냥** -보안 팀은 다양 한 보호 제품에서 수집한 원시 데이터에 대 한 고유한 사용자 지정 쿼리를 만들어 해당 조직의 고유한 정보를 활용 하 여 손상의 징후를 검색할 수 있습니다. Microsoft 365 Defender에서는 쿼리 기반 액세스를 30 일 동안 기록 하며, 끝점 간 및 Microsoft Defender for Office 365 데이터에 대 한 정보를 제공 합니다. 


## <a name="get-started"></a>시작
Microsoft 365 Defender 라이선스 요구 사항을 충족 해야 [security.microsoft.com](https://security.microsoft.com)의 microsoft 365 보안 센터에서 서비스를 사용 하도록 설정할 수 있습니다. 자세한 내용은 다음을 참조 하세요.
- [라이선스 요구 사항](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender 켜기](mtp-enable.md)
