---
title: Microsoft 365 Defender의 자동화 된 조사 및 응답
description: Microsoft 365 Defender에서 자동 조사 및 응답 기능의 개요 (자동 복구 라고도 함)에 대해 알아봅니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 재구성, 자동 복구
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356706"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender의 자동화 된 조사 및 응답

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험해 원하십니까? [랩 환경에서이를 평가](https://aka.ms/mtp-trial-lab) 하거나 [프로덕션에서 파일럿 프로젝트를 실행할](https://aka.ms/m365d-pilotplaybook)수 있습니다.
>

보안 알림이 트리거되면 해당 경고를 확인 하 고 조직을 보호 하기 위한 단계를 수행 하는 보안 운영 팀이 진행 됩니다. 조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다. 보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다. Microsoft 365 Defender에서 자가 치유를 통해 자동화 된 조사 및 응답 기능은 도움이 될 수 있습니다.

다음 비디오를 시청 하 여 자동 복구 작동 방식을 알아봅니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Microsoft 365 Defender에서는 자체 복구 기능이 포함 된 자동 조사 및 응답이 장치, 전자 메일 & 콘텐츠 및 id에서 작동 합니다. Microsoft 365 Defender는 다음과 같은 기능을 제공 합니다. 
- [끝점에 대 한 Microsoft Defender의 자동화 된 조사 및 재구성](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Microsoft Defender for Office 365의 자동화 된 조사 및 응답](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Azure advanced threat detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
이 문서에서는 자동화 된 조사 및 응답이 작동 하는 방식을 설명 합니다. 이러한 기능을 구성 하려면 [Microsoft 365 Defender의 자동화 된 조사 및 응답 기능 구성을](mtp-configure-auto-investigation-response.md)참조 하세요.

## <a name="your-virtual-analyst"></a>가상 분석가

계층 1/계층 2 보안 운영팀에 가상 분석가가 있다고 가정합니다. 가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다. 가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다. 이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다. 이 시나리오는 과학 fiction 같이 보이지만 그렇지 않습니다. 이러한 가상 분석가는 Microsoft 365 Defender 제품군의 일부로, 해당 이름은 *자동 조사 및 응답* 입니다.

자동화 된 조사 및 응답을 통해 보안 운영 팀에서 보안 경고 및 인시던트를 처리 하기 위해 조직의 용량을 대폭 높일 수 있습니다. 자동 조사 및 응답을 통해 조사 및 업데이트 관리 작업을 처리 하는 비용을 줄이고 위협 방지 제품군을 최대한 활용할 수 있습니다. 자동화 된 조사 및 응답은 보안 운영 팀에 게 다음과 같은 도움을 줍니다.

1. 위협이 조치를 요구하는지 여부 확인
2. 필수 수정 조치 수행(또는 권장)
3. 어떤 추가 조사가 수행되어야 하는지 결정
4. 다른 경고가 발생하면 필요한 프로세스를 반복

## <a name="the-automated-investigation-process"></a>자동화된 조사 프로세스

**경고** > **인시던트** > **자동화된 조사** > **판단** > **수정 작업**

트리거된 경고는 자동화 된 조사를 시작할 수 있는 인시던트를 만듭니다. 이 조사를 수행하면 하나 이상의 수정 작업이 발생할 수 있습니다. Microsoft 365 Defender에서 각 자동화 된 조사는 다음 표에 요약 된 것 처럼 Id를 위해 Microsoft Defender에 대 한 신호, Microsoft Defender for Endpoint 및 Defender for Office 365에 따라 서로 연관 되어 있습니다. 

|엔터티 |위협 보호 서비스  |
|---------|---------|
|장치(끝점이라고도 함)     |[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[ID용 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|전자 메일 콘텐츠(사서함의 파일 및 메시지)     |[Office 365용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

각 조사에서는 조사 되는 각 증거 조각에 대해 verdicts (*악의적* 이 고 *의심 스러운* 또는 *위협이 되지 않음*)을 생성 합니다. 위협 유형 및 결과 결과에 따라 업데이트 관리 작업은 조직의 보안 운영 팀의 승인을 받을 때 자동으로 수행 됩니다. 보류 중인 동작과 완료된 작업은 [알림 센터](mtp-action-center.md)에 나열되어 있습니다.

조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다. 문제가 있는 엔터티가 다른 곳에서 발견되는 경우에는 자동화된 조사가 해당 엔터티를 포함하도록 범위를 확장하고 일반적인 보안 플레이 북이 실행됩니다. 

> [!NOTE]
> 모든 경고가 자동 조사를 트리거하는 것은 아니며, 자동 재구성 작업의 모든 조사 결과에 해당 되지 않습니다. 이러한 모든 방식은 조직에 대해 자동화 된 조사 및 응답이 구성 되는 방식에 따라 달라 집니다. [Microsoft 365 Defender의 자동화 된 조사 및 응답 기능 구성을](mtp-configure-auto-investigation-response.md)참조 하세요.


## <a name="next-steps"></a>다음 단계

- [Microsoft 365 Defender의 자동화 된 조사 및 응답에 대 한 필수 구성 요소 확인](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [조직에 대 한 자동화 된 조사 및 응답 구성](mtp-configure-auto-investigation-response.md)
- [알림 센터에 대한 자세한 정보](mtp-action-center.md)
