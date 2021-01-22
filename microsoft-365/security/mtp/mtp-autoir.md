---
title: Microsoft 365 Defender의 자동화된 조사 및 대응
description: Microsoft 365 Defender에서 자동 조사 및 응답 기능(자동 복구라고도 하는)에 대한 개요를 얻습니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 자체 복구
search.appverid: met150
ms.prod: m365-security
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930333"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender의 자동화된 조사 및 대응

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험하고 싶나요? 랩 [환경에서 평가하거나](https://aka.ms/mtp-trial-lab) 프로덕션 [환경에서 파일럿](https://aka.ms/m365d-pilotplaybook)프로젝트를 실행할 수 있습니다.
>

## <a name="how-automated-investigation-and-self-healing-works"></a>자동화된 조사 및 자동 복구 작동 방식

보안 경고가 트리거되면 보안 운영 팀이 이러한 경고를 보고 조직을 보호하기 위한 단계를 수행합니다. 조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다. 보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다. Microsoft 365 Defender에서 자동 복구를 통해 자동화된 조사 및 대응 기능을 통해 도움을 줄 수 있습니다.

다음 비디오를 시청하여 자동 복구가 작동하는 방법을 볼 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Microsoft 365 Defender에서 자동 조사 및 자동 복구 기능을 통해 장치, 전자 메일 & 및 ID에서 작동합니다.
 
> [!TIP]
> 이 문서에서는 자동화된 조사 및 대응의 작동 방식에 대해 설명하고 있습니다. 이러한 기능을 구성하는 내용은 [Microsoft 365 Defender에서](mtp-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.

## <a name="your-own-virtual-analyst"></a>자체 가상 분석가

계층 1/계층 2 보안 운영팀에 가상 분석가가 있다고 가정합니다. 가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다. 가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다. 이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다. 이 시나리오가 공상 과학 소설처럼 들리면 그렇지 않습니다! 이러한 가상 분석가가 Microsoft 365 Defender 제품군의 일부이자 해당 이름은 자동화된 조사 및 *응답입니다.*

자동화된 조사 및 대응을 통해 보안 운영 팀이 보안 경고 및 인시던트 처리를 위한 조직의 용량을 크게 늘려 줄 수 있습니다. 자동화된 조사 및 대응을 통해 조사 및 수정 활동을 다루는 비용을 줄이고 위협 방지 제품군을 가장 많이 사용할 수 있습니다. 자동화된 조사 및 대응은 보안 운영 팀에 도움이 됩니다.

1. 위협이 조치를 요구하는지 여부 확인
2. 필수 수정 조치 수행(또는 권장)
3. 어떤 추가 조사가 수행되어야 하는지 결정
4. 다른 경고가 발생하면 필요한 프로세스를 반복

## <a name="the-automated-investigation-process"></a>자동화된 조사 프로세스

**경고** > **인시던트** > **자동화된 조사** > **판단** > **수정 작업**

트리거된 경고는 자동화된 조사를 시작할 수 있는 인시던트가 생성됩니다. 이 조사를 수행하면 하나 이상의 수정 작업이 발생할 수 있습니다. Microsoft 365 Defender에서 각 자동화된 조사는 다음 표에 요약된 ID용 Microsoft Defender, 끝점용 Microsoft Defender 및 Office 365용 Defender의 신호와 상관 관계가 있습니다. 

|엔터티 |위협 보호 서비스  |
|---------|---------|
|장치(끝점이라고도 함)     |[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[ID용 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|전자 메일 콘텐츠(사서함의 파일 및 메시지)     |[Office 365용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

각 조사는 조사된각 증거에 대한 판정(악성, 의심스러운 또는 위협 없음)을 생성합니다.  위협 유형 및 결과 결과에 따라 수정 작업이 자동으로 수행되거나 조직의 보안 운영 팀의 승인에 따라 수행됩니다. 보류 중인 동작과 완료된 작업은 [알림 센터](mtp-action-center.md)에 나열되어 있습니다.

조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다. 문제가 있는 엔터티가 다른 곳에서 발견되는 경우에는 자동화된 조사가 해당 엔터티를 포함하도록 범위를 확장하고 일반적인 보안 플레이 북이 실행됩니다. 

> [!NOTE]
> 모든 경고가 자동화된 조사를 트리거하는 것은 아니며, 모든 조사에서 자동화된 수정 작업이 수행되지는 않습니다. 이 모든 구성은 조직에 대한 자동화된 조사 및 응답이 구성된 방식에 따라 달라 습니다. [Microsoft 365 Defender에서](mtp-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.


## <a name="next-steps"></a>다음 단계

- [Microsoft 365 Defender의 자동화된 조사 및 대응을 위한 선행 준비를 참조](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [조직에 대한 자동화된 조사 및 대응 구성](mtp-configure-auto-investigation-response.md)
- [알림 센터에 대한 자세한 정보](mtp-action-center.md)
