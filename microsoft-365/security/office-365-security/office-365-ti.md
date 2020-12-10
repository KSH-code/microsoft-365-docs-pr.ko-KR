---
title: 위협 조사 & 대응 기능 - Office 365 계획 2용 Microsoft Defender
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
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Office 365 계획용 Microsoft Defender의 위협 조사 및 대응 기능에 대해 자세히 알아보는 방법을 설명하는 정보를 제공합니다.
ms.openlocfilehash: cbda50dacd6b892c976ce55632c8fc35813839b7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614777"
---
# <a name="threat-investigation-and-response"></a>위협 조사 및 응답

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365용 Microsoft Defender의](office-365-atp.md) 위협 조사 및 대응 기능은 보안 분석가 및 관리자가 다음을 통해 조직의 비즈니스용 Microsoft 365 사용자를 보호하는 데 도움이 됩니다.

- 사이버 공격을 쉽게 식별, 모니터링 및 이해
- Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 위협을 빠르게 해결
- 보안 운영에서 조직에 대한 사이버 공격을 방지하는 데 도움이 되는 인사이트 및 지식 제공
- Office [365에서](automated-investigation-response-office.md) 중요한 전자 메일 기반 위협에 대한 자동화된 조사 및 대응 사용

위협 조사 및 대응 기능은 보안 및 준수 센터에서 사용할 수 있는 위협 및 관련 & 정보를 제공합니다. 이러한 인사이트는 조직의 보안 팀이 전자 메일 또는 파일 기반 공격으로부터 사용자를 보호하는 데 도움이 될 수 있습니다. 이 기능은 신호를 모니터링하고 사용자 활동, 인증, 전자 메일, 손상된 PC 및 보안 인시던트와 같은 여러 원본에서 데이터를 수집하는 데 도움이 됩니다. 비즈니스 의사 결정권자 및 보안 운영 팀은 이 정보를 사용하여 조직에 대한 위협을 이해하고 대응하고 지적 재산을 보호할 수 있습니다.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>위협 조사 및 응답 도구에 대해 잘 아는 경우

위협 조사 및 대응 기능은 보안 & 준수 센터에 다음과 같은 도구 및 응답 워크플로 집합으로 사용됩니다.

- [위협 대시보드](#threat-dashboard)
- [탐색기](#threat-explorer)
- [인시던트](#incidents)
- [공격 시뮬레이터](#attack-simulator)
- [자동화된 조사 및 응답](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>위협 대시보드

위협 대시보드(보안 대시보드라고도 지칭)를 사용하여 해결된 위협을 빠르게 확인할 수 있으며, Microsoft 365 서비스가 비즈니스를 보호하는 방법을 비즈니스 의사 결정권자에게 시각적으로 보고할 수 있습니다. [](security-dashboard.md)

![위협 대시보드](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

이 대시보드를 보고 사용하세요. 보안 및 준수 & 위협 관리 **대시보드로** \> **이동하세요.**

### <a name="threat-explorer"></a>위협 탐색기

위협 탐색기(및 [실시간](threat-explorer.md) 검색)를 사용하여 위협을 분석하고, 시간의 따라 공격의 양을 보고, 위협 패밀리, 공격자 인프라 등에서 데이터를 분석합니다. 위협 탐색기(탐색기라고도 지칭)는 보안 분석가의 조사 워크플로를 위한 시작점입니다.

![위협 탐색기](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

이 보고서를 보고 사용하려면 보안 및 준수 & 위협 관리 **탐색기로** \> **이동해야 합니다.**

### <a name="incidents"></a>인시던트

인시던트 목록(조사라고도 합니다)을 사용하여 진행 보안 인시던트 목록을 볼 수 있습니다. 인시던트는 의심스러운 전자 메일 메시지와 같은 위협을 추적하고 추가 조사 및 수정을 수행하기 위해 사용됩니다.

![Office 365의 현재 위협 인시던트 목록](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

조직의 현재 인시던트 목록을 확인하면 보안 및 준수 & 위협 **관리** 검토 인시던트로 \>  \> **이동하십시오.**

![보안 및 & 센터에서 위협 관리 \> 검토를 선택](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>공격 시뮬레이터

공격 시뮬레이터를 사용하여 조직에서 현실적인 사이버 공격을 설정하고 실행하고 실제 사이버 공격이 비즈니스에 영향을 미치기 전에 취약한 사용자 식별 자세한 내용은 [Office 365의 공격 시뮬레이터를 참조하세요.](attack-simulator.md)

### <a name="automated-investigation-and-response"></a>자동화된 조사 및 응답

자동화된 조사 및 대응(AIR) 기능을 사용하여 조직에서 위협으로부터 콘텐츠, 장치 및 사용자와 관련한 시간과 노력을 절약할 수 있습니다. AIR 프로세스는 특정 경고가 트리거될 때마다 또는 보안 운영 팀에서 시작할 때 시작할 수 있습니다. 자세한 내용은 [Office 365의](automated-investigation-response-office.md)자동화된 조사 및 응답을 참조합니다.

## <a name="threat-intelligence-widgets"></a>위협 인텔리전스 위젯

Microsoft Defender for Office 365 계획 2 제공의 일부로 보안 분석가가 알려진 위협에 대한 세부 정보를 검토할 수 있습니다. 이는 사용자를 안전하게 유지하기 위해 추가로 예방 조치/단계가 있는지 여부를 확인하는 데 유용합니다.

![최근 위협에 대한 정보를 보여주는 보안 추세](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>이러한 기능을 어떻게 얻을 수 있나요?

Microsoft 365 위협 조사 및 응답 기능은 Enterprise E5 또는 특정 구독의 추가 기능으로 포함된 Microsoft Defender for Office 365 계획 2에 포함되어 있습니다. 자세한 내용은 Office 365 계획 1 및 계획 [2용 Defender를 참조합니다.](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="required-roles-and-permissions"></a>필요한 역할 및 사용 권한 할당

Office 365용 Microsoft Defender는 역할 기반 액세스 제어를 사용 합니다. 사용 권한은 Azure Active Directory, Microsoft 365 관리 센터 또는 보안 및 준수 센터의 특정 역할을 & 할당됩니다.

> [!TIP]
> 보안 관리자와 같은 일부 역할은 보안 및 준수 센터에서 할당할 수 & Microsoft 365 관리 센터 또는 Azure Active Directory를 대신 사용하는 것이 좋습니다. 역할, 역할 그룹 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조하십시오.
>
> - [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)
>
> - [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|활동|역할 및 사용 권한|
|---|---|
|위협 대시보드(또는 새 [보안](security-dashboard.md)대시보드) 사용 <p> 최근 또는 현재 위협에 대한 정보 보기|다음 중 하나가 필요합니다. <ul><li>**전역 관리자**</li><li>**보안 관리자**</li><li>**보안 읽기**</li></ul> <p> 이러한 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다.|
|[위협 탐색기(및 실시간 검색)를](threat-explorer.md) 사용하여 위협 분석|다음 중 하나가 필요합니다. <ul><li>**전역 관리자**</li><li>**보안 관리자**</li><li>**보안 읽기**</li></ul> <p> 이러한 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다.|
|인시던트 보기(조사라고도 지칭) <p> 인시던트에 전자 메일 메시지 추가|다음 중 하나가 필요합니다. <ul><li>**전역 관리자**</li><li>**보안 관리자**</li><li>**보안 읽기**</li></ul> <p> 이러한 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다.|
|인시던트에서 전자 메일 작업 트리거 <p> 의심스러운 전자 메일 메시지 찾기 및 삭제|다음 중 하나가 필요합니다. <ul><li>**전역 관리자**</li><li>**보안 관리자** 및 **검색 및 제거 역할**</li></ul> <p> 전역 **관리자** **및** 보안 관리자 역할은 Azure Active Directory() 또는 Microsoft 365 관리 센터()에서 할당할 <https://portal.azure.com> 수 <https://admin.microsoft.com> 있습니다. <p> 검색 **및** 제거 역할은 보안 & 준수 센터()에 할당해야 <https://protection.office.com> 합니다.|
|Microsoft Defender for Office 365 계획 2와 끝점용 Microsoft Defender 통합  <p> Microsoft Defender for Office 365 계획 2와 SIEM 서버 통합|Azure Active  Directory()  또는 Microsoft 365 관리 센터()에 할당된 전역 관리자 또는 보안 관리자 <https://portal.azure.com> <https://admin.microsoft.com> 역할. <p> --- **plus** --- <p> 추가 응용 [프로그램(예: Microsoft Defender 보안](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) 센터 또는 SIEM 서버)에 할당된 적절한 역할|
|

## <a name="next-steps"></a>다음 단계

- [위협 트래커에 대한 자세한 내용은 신규 및 참고 사항](threat-trackers.md)

- [배달된 악성 전자 메일 찾기 및 조사(Office 365 위협 조사 및 대응)](investigate-malicious-email-that-was-delivered.md)

- [Office 365 위협 조사 및 대응을 끝점용 Microsoft Defender와 통합](integrate-office-365-ti-with-wdatp.md)

- [공격 시뮬레이터에 대해 자세히 알아보십시오.](attack-simulator.md)
