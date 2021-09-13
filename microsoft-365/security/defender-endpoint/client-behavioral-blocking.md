---
title: 클라이언트 행동적 차단
description: 클라이언트 동작 차단은 끝점용 Microsoft Defender의 동작 차단 및 포함 기능의 일부입니다.
keywords: 동작 차단, 신속한 보호, 클라이언트 동작, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 5afa8ec7fc6d4adeef5a099a18e335b7a9e68f5b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212325"
---
# <a name="client-behavioral-blocking"></a>클라이언트 행동적 차단

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>개요

클라이언트 동작 차단은 끝점용 Defender의 동작 차단 및 포함 기능의 구성 요소입니다. [](behavioral-blocking-containment.md) 의심스러운 동작이 장치(클라이언트 또는 끝점이라고도 지칭)에서 감지되면 아티팩트(예: 파일 또는 응용 프로그램)가 자동으로 차단, 확인 및 수정됩니다.

:::image type="content" alt-text="클라우드 및 클라이언트 보호." source="images/pre-execution-and-post-execution-detection-engines.png" lightbox="images/pre-execution-and-post-execution-detection-engines.png":::

바이러스 백신 보호는 클라우드 보호와 함께 사용할 때 가장 잘 작동합니다.

## <a name="how-client-behavioral-blocking-works"></a>클라이언트 동작 차단의 작동 방식

[Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md) 의심스러운 동작, 악성 코드, 파일 없는 및 메모리 내 공격을 장치에서 감지할 수 있습니다. 의심스러운 동작이 감지되면 Microsoft Defender 바이러스 백신 의심스러운 동작과 프로세스 트리를 모니터링하여 클라우드 보호 서비스로 전송합니다. 기계 학습은 악성 응용 프로그램과 좋은 동작을 밀리초 내에 차별화하고 각 아티팩트를 분류합니다. 거의 실시간으로 아티팩트가 악성으로 발견되는 즉시 디바이스에서 차단됩니다.

의심스러운 동작이 감지될 때마다 경고가 [](alerts-queue.md) 생성되고 Microsoft 365 Defender 포털(이전의 [](microsoft-defender-security-center.md) Microsoft 365 Defender)에 표시됩니다.

클라이언트 동작 차단은 공격이 시작되지 않도록 하는 데 도움이 될 뿐만 아니라 실행을 시작한 공격을 중지하는 데 도움이 될 수 있기 때문에 효과적입니다. 또한 [피드백](feedback-loop-blocking.md) 루프 차단(동작 차단 및 방지의 또 다른 기능)을 사용하여 조직의 다른 디바이스에서 공격을 방지할 수 있습니다.

## <a name="behavior-based-detections"></a>동작 기반 검색

동작 기반 검색 이름은 에 대한 [MITRE ATT&CK Matrix에 Enterprise.](https://attack.mitre.org/matrices/enterprise) 이름 규칙은 악의적인 동작이 관찰된 공격 스테이지를 식별하는 데 도움이 됩니다.

|전술|검색 위협 이름|
|---|---|
|초기 액세스|`Behavior:Win32/InitialAccess.*!ml`|
|실행|`Behavior:Win32/Execution.*!ml`|
|지속성|`Behavior:Win32/Persistence.*!ml`|
|권한 상승|`Behavior:Win32/PrivilegeEscalation.*!ml`|
|방어 회피|`Behavior:Win32/DefenseEvasion.*!ml`|
|자격 증명 액세스|`Behavior:Win32/CredentialAccess.*!ml`|
|검색|`Behavior:Win32/Discovery.*!ml`|
|측면 이동|`Behavior:Win32/LateralMovement.*!ml`|
|컬렉션|`Behavior:Win32/Collection.*!ml`|
|명령 및 제어|`Behavior:Win32/CommandAndControl.*!ml`|
|유출|`Behavior:Win32/Exfiltration.*!ml`|
|영향|`Behavior:Win32/Impact.*!ml`|
|Uncategorized|`Behavior:Win32/Generic.*!ml`|

> [!TIP]
> 특정 위협에 대한 자세한 내용은 최근 전역 **[위협 활동을 참조합니다.](https://www.microsoft.com/wdsi/threats)**

## <a name="configuring-client-behavioral-blocking"></a>클라이언트 동작 차단 구성

조직에서 끝점에 Defender를 사용하는 경우 클라이언트 동작 차단은 기본적으로 사용하도록 설정됩니다. 그러나 동작 차단 및 포함을 비롯한 모든 [](behavioral-blocking-containment.md)Endpoint용 Defender 기능을 사용 가능하도록 끝점용 Defender의 다음 기능을 사용하도록 설정하고 구성해야 합니다.

- [끝점 기준에 대한 Defender](configure-machines-security-baseline.md)
- [Endpoint용 Defender에 온보딩된 장치](onboard-configure.md)
- [차단 모드의 EDR](edr-in-block-mode.md)
- [공격 표면 감소](attack-surface-reduction.md)
- [차세대 보호(바이러스](configure-microsoft-defender-antivirus-features.md) 백신, 맬웨어 방지 및 기타 위협 방지 기능)
