---
title: 위협 조사 & 응답 기능-Office 365 ATP 계획 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 Advanced Threat Protection 계획의 위협 조사 및 응답 기능에 대해 알아봅니다.
ms.openlocfilehash: 6c009a756b30d4b35159b98b145b19b72c9ab541
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656674"
---
# <a name="threat-investigation-and-response"></a>위협 조사 및 응답

위협 조사 및 응답 기능 [Office 365 Advanced Threat Protection](office-365-atp.md) 은 다음과 같은 방법으로 보안 분석가와 관리자에 게 조직의 Microsoft 365 비즈니스 사용자를 보호 하는 데 도움을 제공 합니다.
- 고 사이버 공격를 쉽게 식별, 모니터링 및 이해할 수 있도록 설정
- Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀의 위협에 빠르게 문제를 해결 하는 데 도움을 줍니다.
- 보안 작업에 도움이 되는 통찰력 및 지식을 제공 하 여 조직에 대 한 고 사이버 공격 방지
- 중요 전자 메일 기반 위협에 대 한 [Office 365의 자동화 된 조사 및 응답](automated-investigation-response-office.md) 채택
    
위협 조사 및 응답 기능은 보안 및 준수 센터에서 사용할 수 있는 위협 및 관련 된 응답 작업에 대 한 정보를 제공 &amp; 합니다. 이러한 통찰력은 조직의 보안 팀이 전자 메일 또는 파일 기반 공격 으로부터 사용자를 보호 하는 데 도움이 될 수 있습니다. 이 기능은 사용자 활동, 인증, 전자 메일, 손상 된 Pc 및 보안 인시던트와 같은 여러 원본의 데이터를 수집 하 고 신호를 모니터링 하는 데 도움이 됩니다. 비즈니스 의사 결정권자 및 보안 운영 팀은이 정보를 사용 하 여 조직에 대 한 위협을 파악 하 고 대응 하 고 지적 재산을 보호할 수 있습니다.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>위협 조사 및 응답 도구 익히기

보안 & 준수 센터의 위협 조사 및 응답 기능으로, 다음을 비롯 한 도구 및 응답 워크플로 집합으로 제공 됩니다.

- [위협 대시보드](#threat-dashboard)
- [탐색기](#threat-explorer)
- [인시던트](#incidents)
- [공격 시뮬레이터](#attack-simulator)
- [자동화된 조사 및 응답](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>위협 대시보드

위협 대시보드 ( [보안 대시보드](security-dashboard.md)라고도 함)를 사용 하 여 해결 된 위협을 빠르게 확인 하 고, Microsoft 365 서비스가 비즈니스를 보호 하는 방법을 비즈니스 의사 결정권자에 게 보고 하는 방법을 설명 합니다.
  
![위협 대시보드](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
이 대시보드를 보고 사용 하려면 보안 및 &amp; 준수 센터에서 **위협 관리** \> **대시보드로**이동 합니다.
  
### <a name="threat-explorer"></a>위협 탐색기

위협 [탐색기 (및 실시간 검색)](threat-explorer.md) 를 사용 하 여 위협을 분석 하 고, 시간에 따른 공격 량을 확인 하 고, 위협 계열, 침입자 인프라 등을 기준으로 데이터를 분석 합니다. 위협 탐색기 (탐색기 라고도 함)는 모든 보안 분석가의 조사 워크플로에서 시작 되는 위치입니다.

![위협 탐색기](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
이 보고서를 보고 사용 하려면 보안 및 &amp; 준수 센터에서 **위협 관리** \> **탐색기**로 이동 합니다.
  
### <a name="incidents"></a>인시던트

문제 목록 (조사가 라고도 함)을 사용 하 여 비행 보안 인시던트 목록을 확인 합니다. 인시던트는 의심 스러운 전자 메일 메시지와 같은 위협을 추적 하 고 추가 조사 및 수정을 수행 하는 데 사용 됩니다.

![Office 365의 현재 위협 인시던트 목록](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

조직의 현재 인시던트 목록을 보려면 보안 & 준수 센터에서 **위협 관리** \> **검토** \> **인시던트**로 이동 합니다.

![보안 & 준수 센터에서 위협 관리 검토를 선택 합니다. \>](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>공격 시뮬레이터

공격 시뮬레이터를 사용 하 여 조직에서 현실적인 고 사이버 공격를 설정 및 실행 하 고, 실제에서는 사이버 공격과 비즈니스에 영향을 주기 전에 취약 한 사용자를 식별 합니다. 자세한 내용은 [Office 365의 Attack 시뮬레이터](attack-simulator.md)를 참조 하세요.

### <a name="automated-investigation-and-response"></a>자동화된 조사 및 응답

자동화 된 조사 및 응답 (AIR) 기능을 사용 하 여 조직의 위협 으로부터 발생 하는 콘텐츠, 장치 및 사용자와 관련 된 시간과 노력을 절감할 수 있습니다. AIR 프로세스는 특정 알림이 트리거될 때 또는 보안 운영 팀이 시작 될 때 시작 될 수 있습니다. 자세한 내용은 [Office 365의 자동화 된 조사 및 응답](automated-investigation-response-office.md)을 참조 하세요.

## <a name="threat-intelligence-widgets"></a>위협 인텔리전스 위젯

보안 분석가는 Office 365 Advanced Threat Protection 계획 2 제공의 일부로 알려진 위협에 대 한 세부 정보를 검토할 수 있습니다. 이 기능은 사용자가 안전 하 게 유지 하기 위해 수행할 수 있는 추가 예방 조치/단계가 있는지 여부를 확인 하는 데 유용 합니다.

![최근 위협에 대 한 정보를 보여 주는 보안 경향](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>이러한 기능은 어떻게 얻을 수 있나요?

Microsoft 365 위협 조사 및 응답 기능은 Enterprise E5에 포함 되거나 특정 구독에 대 한 추가 기능으로 제공 되는 Office 365 Advanced Threat Protection 계획 2에 포함 되어 있습니다. 자세한 내용은 [Office 365 ATP 계획 1 및 계획 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2)를 참조 하세요.

## <a name="required-roles-and-permissions"></a>필요한 역할 및 사용 권한 할당

Office 365 Advanced Threat Protection은 역할 기반 액세스 제어를 사용 합니다. 사용 권한은 Azure Active Directory의 특정 역할, Microsoft 365 관리 센터 또는 보안 & 준수 센터를 통해 할당 됩니다.

> [!TIP]
> 보안 관리자와 같은 일부 역할은 보안 & 준수 센터에서 할당할 수 있지만 대신 Microsoft 365 관리 센터 또는 Azure Active Directory를 사용 하는 것이 좋습니다. 역할, 역할 그룹 및 권한에 대 한 자세한 내용은 다음 리소스를 참조 하십시오.
>
> - [보안 및 준수 센터의 사용 권한 &amp;](permissions-in-the-security-and-compliance-center.md)
>
> - [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|활동|역할 및 사용 권한|
|---|---|
|위협 대시보드 (또는 새 [보안 대시보드](security-dashboard.md)) 사용<br/> <br/>최근 또는 현재 위협에 대 한 정보 보기|다음 중 하나가 필요합니다. <br/>- **전역 관리자**  <br/> - **보안 관리자** <br/>- **보안 독자** <br/> <br/>이러한 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당할 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) .|
|[위협 탐색기 (및 실시간 검색)](threat-explorer.md) 를 사용 하 여 위협 분석|다음 중 하나가 필요합니다. <br/>- **전역 관리자**  <br/> - **보안 관리자** <br/>- **보안 독자** <br/> <br/>이러한 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당할 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) .|
|인시던트 보기 (조사가 라고도 함) <br/> 인시던트에 전자 메일 메시지 추가|다음 중 하나가 필요합니다. <br/>- **전역 관리자**  <br/> - **보안 관리자** <br/>- **보안 독자** <br/> <br/>이러한 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당할 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) .|
|인시던트에서 전자 메일 작업 트리거 <br/> <br/> 의심 스러운 전자 메일 메시지 찾기 및 삭제|다음 중 하나가 필요합니다. <br/>- **전역 관리자**  <br/> - **보안 관리자** 와 **검색 및 제거** 역할<br/><br/>**전역 관리자** 및 **보안 관리자** 역할은 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 할당 될 수 있습니다 [https://admin.microsoft.com](https://admin.microsoft.com) . <br/><br/>**검색 및 제거** 역할은 Security & 준수 센터 ()에서 할당 되어야 합니다 [https://protection.office.com](https://protection.office.com) .|
|Microsoft Defender Advanced Threat Protection과 Office 365 Advanced Threat Protection 계획 2 통합  <br/><br/> SIEM 서버를 사용 하 여 Office 365 Advanced Threat Protection 계획 2 통합|Azure Active Directory () 또는 Microsoft 365 관리 센터 ()에서 할당 된 **전역 관리자** 또는 **보안 관리자** 역할 [https://portal.azure.com](https://portal.azure.com) [https://admin.microsoft.com](https://admin.microsoft.com) 입니다.<br/>--- **기호** ---<br/>추가 응용 프로그램에서 할당 되는 적절 한 역할 (예: [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) 또는 siem server)|
|

## <a name="next-steps"></a>다음 단계

- [위협 추적기에 대해 알아보기-신규 및 중요](threat-trackers.md)

- [배달 된 악성 전자 메일 찾기 및 조사 (Office 365 위협 조사 및 응답)](investigate-malicious-email-that-was-delivered.md)

- [Microsoft Defender Advanced Threat Protection을 사용 하 여 Office 365 위협 조사 및 응답 통합](integrate-office-365-ti-with-wdatp.md)

- [공격 시뮬레이터에 대 한 자세한 정보](attack-simulator.md)
