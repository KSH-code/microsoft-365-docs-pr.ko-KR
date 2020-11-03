---
title: Microsoft 365 Defender의 인시던트 조사
description: 장치, 사용자 및 사서함과 관련된 인시던트를 분석합니다.
keywords: 인시던트, 컴퓨터, 장치, 사용자, ID, 메일, 전자 메일, 사서함, 조사, 그래프, 증거
search.product: eADQiWindows 10XVcnh
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
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846751"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender의 인시던트 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**

- Microsoft 365 Defender

Microsoft 365 Defender는 모든 장치, 사용자 및 사서함에서 모든 관련 알림, 자산, 조사 및 증거를 집계 하 여 전체 공격 범위를 종합적으로 확인할 수 있도록 합니다.

네트워크에 영향을 미치는 알림을 조사하고, 해당 내용이 무엇인지 이해하고, 인시던트와 관련된 증거를 수집하여 효과적인 수정 계획을 세울 수 있습니다.

## <a name="investigate-an-incident"></a>인시던트 조사

1. 인시던트 대기열에서 인시던트를 선택합니다. <BR> 측면 패널이 열리고 상태, 심각도, 범주 및 영향을 받는 엔터티 같은 중요 한 정보에 대 한 미리 보기가 제공 됩니다.

    ![인시던트 사이드 패널의 이미지](../../media/incident-side-panel.png)

2. **인시던트 페이지 열기** 를 선택합니다. <BR> 그러면 자세한 정보 인시던트 정보, 설명 및 작업, 탭 (개요, 경고, 장치, 사용자, 조사, 증거)을 확인할 수 있는 문제 페이지가 열립니다.

3. 인시던트에 관련된 알림, 장치, 사용자, 기타 엔터티를 검토합니다.

## <a name="incident-overview"></a>인시던트 개요

개요 페이지에서는 인시던트에 대한 주요 정보를 볼 수 있는 스냅숏을 보여 줍니다.

![인시던트 개요 페이지의 이미지](../../media/incidents-overview.png)

공격 범주를 통해 공격이 중단 체인에 얼마나 advanced가 진행 되었는지 확인할 수 있습니다. 다른 Microsoft 보안 제품과 마찬가지로 Microsoft 365 Defender는 [MITRE at&t&접시 헤드 &trade; ](https://attack.mitre.org/) 프레임 워크에 맞춰져 있습니다.

범위 섹션에서는 이 인시던트의 일부인 영향을 받는 상위 자산 목록을 제공합니다. 위험 수준, 조사 우선 순위 및 자산에 대한 태그 지정과 같은 해당 자산에 관한 특정 정보가 있는 경우 이 섹션에도 표시됩니다.

알림 시간 표시 막대는 알림이 발생한 시간 순서와 해당 인시던트에 대해 이러한 알림이 발생한 이유에 대한 미리 보기를 제공합니다.

그리고 마지막인 증거 섹션에는 인시던트에 얼마나 많은 아티팩트가 포함되었는지와 치료 상태에 대한 요약 정보가 제공되므로 사용자 측에서 어떤 조치가 필요한지 즉시 확인할 수 있습니다.

이 개요는 사용자가 알아야 할 인시던트의 주요 특징에 대한 통찰력을 제공함으로써 인시던트의 초기 분류를 도울 수 있습니다.

## <a name="alerts"></a>알림

인시던트에 관련 된 모든 경고 및 심각도, 경고에 참여 한 엔터티, 알림 원본 (예: microsoft defender for Identity, microsoft defender for Office 365) 및 서로 연결 된 이유를 볼 수 있습니다.

![인시던트 알림 페이지 이미지](../../media/incident-alerts.png)

기본적으로 알림은 시간을 기준으로 순서대로 정렬되며, 이를 통해 시간에 따라 처음부터 공격이 진행된 방식을 확인할 수 있습니다. 각 경고를 클릭 하면 해당 경고에 대 한 심도 깊은 조사를 수행할 수 있는 관련 경고 페이지가 표시 됩니다.

## <a name="devices"></a>장치

장치 탭에는 인시던트와 관련된 알림이 표시되는 모든 장치가 표시됩니다.

공격이 수행된 컴퓨터의 이름을 클릭하면 컴퓨터 페이지로 이동하여 해당 컴퓨터에서 트리거된 알림 및 관련 이벤트를 쉽게 조사할 수 있습니다.

![인시던트의 컴퓨터 탭 이미지](../../media/incident-machines.png)

시간 표시 막대 탭을 선택하면 컴퓨터 시간 표시 막대를 스크롤하여 컴퓨터에서 관찰된 경고와 함께 시간 순서 대로 관찰된 모든 이벤트와 동작을 볼 수 있습니다.

## <a name="users"></a>사용자

주어진 인시던트의 일부로 식별되거나 이와 관련된 사용자를 참조하세요.

사용자 이름을 클릭하면 추가 조사를 수행할 수 있는 사용자의 클라우드 앱 보안 페이지로 이동합니다.

![인시던트의 사용자 탭 이미지](../../media/incident-users.png)

## <a name="mailboxes"></a>사서함

인시던트의 일부로 식별되거나 이와 관련된 사서함을 조사하세요. 추가 조사 작업을 수행 하기 위해 메일 관련 알림을 선택 하면 업데이트 관리 작업을 수행할 수 있는 Office 365 용 Microsoft Defender가 열립니다.

![인시던트의 사서함 탭 이미지](../../media/incident-mailboxes.png)

## <a name="investigations"></a>조사

이 인시던트의 경고에 의해 트리거된 모든 자동화 된 조사를 확인 하려면 **조사** 를 선택 합니다. 조사에서는 Endpoint 용 Microsoft Defender 및 Office 365 용 Defender에서 실행 되도록 자동화 된 조사를 구성한 방법에 따라 수정 작업을 수행 하거나 분석가의 작업 승인을 기다립니다.

![인시던트의 조사 탭 이미지](../../media/incident-investigations.png)

조사를 선택하여 조사 세부 사항 페이지로 이동하고 조사 및 수정 상태에 대한 전체 정보를 확인하세요. 조사 과정에서 승인을 위해 보류 중인 작업이 있는 경우 해당 작업은 보류 중인 작업 탭에 표시 됩니다. 인시던트 수정을 수행 하는 동안 조치를 취해야 합니다.

## <a name="evidence"></a>증거

Microsoft 365 Defender는 경고에서 모든 인시던트의 지원 이벤트 및 의심 스러운 엔터티를 자동으로 조사 하 여 autoresponse 및 중요 한 파일, 프로세스, 서비스, 전자 메일 등에 대 한 정보를 제공 합니다. 이를 통해 인시던트의 잠재적 위협을 신속하게 탐지하고 차단할 수 있습니다.

![인시던트의 증거 탭 이미지](../../media/incident-evidence.png)

분석된 각 엔터티에는 수정 상태뿐만 아니라 결과 (악성적임, 의심스러움, 깨끗함)가 표시됩니다. 이를 통해 전체 인시던트의 수정 상태를 파악하고 추가적인 치료를 위한 다음 단계를 확인하는 데 도움이 됩니다.

## <a name="related-topics"></a>관련 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 관리](manage-incidents.md)

