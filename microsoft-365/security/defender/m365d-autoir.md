---
title: Microsoft 365 Defender의 자동화된 조사 및 대응
description: Microsoft 365 Defender에서 자동 조사 및 응답 기능(자동 복구라고도 하는)에 대한 개요를 얻습니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 자동 복구
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: be0423b0af8251347420d9e970dcfe10db0bb72b
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591926"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender의 자동화된 조사 및 대응

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

조직에서 Microsoft [365 Defender를](microsoft-365-defender.md)사용하는 경우 보안 운영 팀은 악의적 또는 의심스러운 아티팩트가 감지될 때마다 경고를 수신합니다. 끝이 없는 것처럼 보이는 위협 흐름이 제공될 경우 보안 팀은 종종 많은 수의 경고를 해결해야 하는 과제에 직면합니다. 다행히 Microsoft 365 Defender에는 보안 운영 팀이 위협을 보다 효율적으로 처리하도록 도와주는 자동화된 조사 및 수정(AIR) 기능이 포함되어 있습니다.

이 문서에서는 AIR에 대한 개요를 제공하며 다음 단계 및 추가 리소스에 대한 링크를 제공합니다.

> [!TIP]
> Microsoft 365 Defender를 경험해 보고 싶으신가요? [랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.

## <a name="how-automated-investigation-and-self-healing-works"></a>자동화된 조사 및 자동 복구의 작동 방식

보안 경고가 트리거되면 보안 운영 팀이 해당 경고를 보고 조직을 보호하기 위한 단계를 수행해야 합니다. 조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다. 보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다. Microsoft 365 Defender에서 자동 복구를 통해 자동화된 조사 및 대응 기능이 도움이 될 수 있습니다.

다음 비디오를 시청하여 자동 복구가 작동하는 방법을 볼 수 있습니다. <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Microsoft 365 Defender에서 자동 치료 기능을 통해 자동화된 조사 및 대응이 장치, 전자 메일 & 및 ID에서 작동합니다.
 
> [!TIP]
> 이 문서에서는 자동화된 조사 및 대응이 작동하는 방식에 대해 설명하고 있습니다. 이러한 기능을 구성하기 위해 [Microsoft 365 Defender에서](m365d-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.

## <a name="your-own-virtual-analyst"></a>자체 가상 분석가

계층 1 또는 계층 2 보안 운영 팀에 가상 분석가가 있는 경우를 상상해 보아야 합니다. 가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다. 가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다. 이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다. 이 시나리오가 과학 소설처럼 들리면 그렇지 않습니다. 이러한 가상 분석가가 Microsoft 365 Defender 제품군의 일부로, 해당 이름은 자동화된 조사 및 *응답입니다.*

자동화된 조사 및 대응 기능을 통해 보안 운영 팀은 보안 경고 및 인시던트 처리를 위한 조직의 용량을 크게 늘려 줄 수 있습니다. 자동화된 조사 및 대응을 통해 조사 및 수정 활동을 처리하고 위협 방지 제품군을 가장 많이 사용할 수 있습니다. 자동화된 조사 및 대응 기능은 보안 운영 팀에 도움이 됩니다.

1. 위협이 조치를 요구하는지 여부 확인
2. 필요한 수정 작업 수행(또는 권장)
3. 조사를 진행할지 여부 및 기타 조사를 진행할지 결정 및
4. 다른 경고가 발생하면 필요한 프로세스를 반복

## <a name="the-automated-investigation-process"></a>자동화된 조사 프로세스

경고는 자동화된 조사를 시작할 수 있는 인시던트가 생성됩니다. 자동화된 조사는 각 증거 조각에 대한 결과를 얻습니다. 판정은 다음이 될 수 있습니다.
- *악성*;
- *의심스러운 ;* 또는 
- *위협이 없습니다.* 

악의적 또는 의심스러운 엔터티에 대한 수정 작업이 식별됩니다. 수정 작업의 예는 다음과 같습니다.
- 파일을 검지로 보내기
- 프로세스 중지
- 디바이스를 고리로 설정
- URL 차단 및 
- 기타 작업. (Microsoft [365 Defender의](m365d-remediation-actions.md)수정 작업을 참조합니다.)

조직에 [](m365d-configure-auto-investigation-response.md) 대해 자동화된 조사 및 대응 기능이 구성되는 방식에 따라 보안 운영 팀의 승인만 수행되거나 자동으로 수정 작업이 수행됩니다. 보류 중이든 완료 여부에 따라 모든 작업이 작업 센터 에 [나열됩니다.](m365d-action-center.md)

조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다. 다른 곳에서 인출된 엔터티가 있는 경우 자동화된 조사는 해당 엔터티를 포함하기 위해 범위를 확장하고 조사 프로세스가 반복됩니다. 

Microsoft 365 Defender에서 각 자동화된 조사는 다음 표에 요약된 ID, 끝점용 Microsoft Defender 및 Office 365용 Defender에 대한 Microsoft Defender의 신호와 상관 관계가 있습니다. 

|엔터티 |위협 보호 서비스  |
|:---------|:---------|
|장치(끝점이라고도 하지만 컴퓨터라고도 불리며)     |[엔드포인트용 Microsoft Defender](../defender-endpoint/automated-investigations.md) <br/>[ID용 Microsoft Defender](/azure-advanced-threat-protection/what-is-atp) |      
|전자 메일 콘텐츠(파일 및 URL을 포함할 수 있는 전자 메일 메시지)     |[Office 365용 Microsoft Defender](../office-365-security/defender-for-office-365.md)         |

> [!NOTE]
> 모든 경고가 자동화된 조사를 트리거하는 것은 아니며, 모든 조사가 자동화된 수정 작업을 수행하지는 않습니다. 조직에 대해 자동화된 조사 및 응답이 구성되는 방식에 따라 달라 하게 됩니다. [Microsoft 365 Defender에서](m365d-configure-auto-investigation-response.md)자동화된 조사 및 응답 기능 구성을 참조합니다.

## <a name="viewing-a-list-of-investigations"></a>조사 목록 보기

조사를 보기 위해 인시던트 **페이지로** 이동합니다. 인시던트 를 선택한 다음 조사 **탭을** 선택합니다. 자세한 내용은 [자동화된 조사의 세부](m365d-autoir-results.md)정보 및 결과를 참조합니다.


## <a name="next-steps"></a>다음 단계

- [Microsoft 365 Defender의 자동화된 조사 및 대응에 대한 선행 준비를 참조](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [조직에 대한 자동화된 조사 및 응답 구성](m365d-configure-auto-investigation-response.md)
- [알림 센터에 대한 자세한 정보](m365d-action-center.md)
