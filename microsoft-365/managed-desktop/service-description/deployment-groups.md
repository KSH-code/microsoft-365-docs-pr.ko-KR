---
title: 디바이스 배포 그룹
description: 업데이트 및 기타 변경 내용을 관리하는 데 사용되는 배포 그룹
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215375"
---
# <a name="device-deployment-groups"></a>디바이스 배포 그룹

Microsoft Managed Desktop 배포 그룹을 사용하여 장치에 대한 업데이트 및 구성 변경 릴리스를 관리합니다. 디바이스가 배포 그룹에 등록될 때 자동으로 배포 그룹("링" 또는 "업데이트 그룹")에 Microsoft Managed Desktop. 배포 그룹을 사용하면 디바이스가 단계적 타임라인의 변경 내용을 받을 수 있습니다.

테스트 목적으로만 특정 장치를 할당하거나 변경 내용을 먼저 받을 특정 에디터를 지정할 수 있습니다. 임원이 사용하는 장치나 업무상 중요한 기능을 하는 중요한 디바이스가 있는 경우 가장 느린 케이던스에서 업데이트를 받을 그룹에 유지할 수 있습니다. Microsoft Managed Desktop 장치를 다음 그룹 중 하나에 유지해야 한다고 지정할 수 있습니다.

- **테스트**: 테스트에 사용되는 장치 또는 새로운 기능에 대한 자주 변경 및 노출을 인용하고 초기 피드백을 제공할 수 있는 사용자에게 가장 적합한 장치입니다. 이 그룹은 자주 변경을 받으며 이 그룹의 환경은 강력한 영향을 미치게 됩니다. 테스트 그룹은 확립된 서비스 수준 계약 및 사용자 지원에서 제외됩니다. 처음에는 몇 대의 장치만 이동한 다음 사용자 환경을 검사하는 것이 가장 좋은 것입니다. Microsoft Managed Desktop 디바이스를 이 그룹에 자동으로 할당하지 않습니다. 지정한 디바이스만 있습니다.
- **첫** 번째 : 변경의 유효성을 검사하고 경험에 대한 피드백을 제공할 수 있는 초기 채택자, 지원자 또는 지정된 유효성 검사자, IT Pro 또는 비즈니스 기능 대표에게 이상적입니다.
- **Broad는** 마지막으로 변경 내용을 수신합니다. 대부분의 조직은 일반적으로 이 그룹에 있습니다. 이 그룹에 속해야 하고 업무상 중요한 기능을 수행하거나 중요한 역할의 사용자에게 속하기 때문에 마지막으로 변경 내용을 수신해야 하는 장치를 지정할 수도 있습니다. 
- **자동**: 다른 그룹 중 하나에 Microsoft Managed Desktop 자동으로 할당하려면 이 옵션을 선택합니다. 디바이스를 자동으로 Test에 할당하지는 않습니다. 이전에 지정한 장치를 자동으로 다시 할당할 수 있도록 릴리스하려면 이 옵션을 선택합니다. 

Microsoft Managed Desktop 그룹을 사용하여 배포를 제어하지만 디바이스를 할당할 수 없습니다. 그러나 이러한 그룹에서 이 문서의 그룹 중 하나로 장치를 이동할 수 있습니다. 그룹에서 업데이트가 Windows 방법에 대한 자세한 내용은 에서 업데이트 처리 [방법을 Microsoft Managed Desktop.](updates.md)

장치가 지정한 그룹에 있는 경우 사용자가 할당한 **그룹이** 관리자로 **표시됩니다.** 그룹에 Microsoft Managed Desktop 할당한 경우 자동 으로 **표시됩니다.** 장치가 그룹으로 이동하는 동안 보류 **중 으로 표시됩니다.** 그룹 **필드에는** 디바이스가 현재 있는 그룹이 항상 표시하며 이동이 완료된 경우만 업데이트됩니다.

> [!IMPORTANT]
> 이러한 그룹의 구성원 자격을 직접 수정하지 않습니다. 항상 배포 그룹에 장치 [할당에 설명된 단계를 따릅니다.](../working-with-managed-desktop/assign-deployment-group.md)
