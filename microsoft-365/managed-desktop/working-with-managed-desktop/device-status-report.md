---
title: 디바이스 상태 보고서
description: 장치 상태에 대해 설명
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3e91a329799528eebf9de53b197c7439644b98fb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215195"
---
# <a name="device-status-report"></a>디바이스 상태 보고서

이 보고서는 등록된 모든 장치의 상태를 집계하여 Microsoft Managed Desktop 서비스를 사용 중입니다. 지난 28일 동안의 활동 및 장치를 업데이트된 유지 능력에 따라 장치를 분류합니다. 가능한 한 Windows 업데이트를 통해 업데이트하려면 장치가 인터넷에 연결되어 있어야 합니다. 최소 6시간 동안 최대 최대 6시간 동안 일시 중지하거나 일시 중지하지 말아야 합니다. 이 중 2회는 연속해야 합니다. 이러한 요구 사항을 충족하지 않는 장치가 업데이트될 수도 있습니다. 그러나 해당 장치를 충족하는 장치는 업데이트될 가능성이 가장 높습니다.

:::image type="content" source="../../media/mmd-device-status.png" alt-text="왼쪽 위에 있는 장치 활동 상태의 도넛 그래프, 보고서를 생성하는 단추가 있는 오른쪽 위에 있는 필터 보기, 아래쪽의 세부 정보 표를 보여주는 보고서":::

다음 레이블을 사용하여 장치 상태를 보고합니다. 

- **사용자 준비:** 서비스에 등록되어 사용자에게 제공될 준비가 된 장치 
- **활성:** 사용 중이고 최신 보안 업데이트 릴리스에 대한 활동 기준(6시간, 연속 2개)을 충족하고 지난 5일 동안 Microsoft Intune 한 번 이상 체크 인한 장치입니다. 
- **동기화:** 지난 28일 이내에 Intune에서 사용 중이고 체크 인한 장치 
- **동기화 중:** 지난 28일 동안 Intune으로 체크 인하지 않은 장치 
- **기타:** 범주는 일반적으로 장치 등록 중에 발생할 수 있는 여러 오류 상태로 집계됩니다. 자세한 내용은 장치 등록 [문제 해결을 참조하세요.](../get-started/register-devices-self.md#troubleshooting-device-registration)