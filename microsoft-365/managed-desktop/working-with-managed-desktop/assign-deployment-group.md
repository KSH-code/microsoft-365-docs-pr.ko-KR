---
title: 배포 그룹에 장치 할당
description: 장치를 배치할 배포 그룹을 지정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191049"
---
# <a name="assign-devices-to-a-deployment-group"></a>배포 그룹에 장치 할당

Microsoft Managed Desktop 배포 그룹에 장치를 할당하지만 관리 포털을 사용하여 디바이스가 장치에 할당된 그룹을 지정하거나 변경할 수 있습니다. 디바이스가 등록된 후 또는 사용자가 등록된 후 할당을 변경합니다.

> [!IMPORTANT]
> 할당을 변경하면 해당 그룹과 관련한 정책이 장치에 적용됩니다. 변경으로 최신 버전의 업데이트가 설치될 Windows 10(모든 새로운 기능 또는 품질 업데이트 포함)가 설치될 수 있습니다. 처음에는 몇 대의 장치만 이동한 다음 결과 사용자 환경을 검사하는 것이 가장 좋은 것입니다. 특정 업데이트가 장치를 다시 시작합니다. 할당할 올바른 장치를 선택해야 합니다. 배정이 적용될 때 최대 24시간이 걸릴 수 있습니다.

배포 그룹에 장치를 할당하기 위해 다음 단계를 수행합니다. 별도의 장치를 다른 그룹으로 이동하려는 경우 각 그룹에 대해 이러한 단계를 반복합니다.

1. In Microsoft Endpoint Manager, select **Devices** in the left pane. 장치 **Microsoft Managed Desktop** 디바이스를 **선택합니다.**
2. 할당할 장치를 선택합니다. 선택한 모든 장치가 지정한 그룹에 할당됩니다.
3. 메뉴에서 **장치** 작업을 선택합니다.
4. 그룹에 **장치 할당을 선택합니다.** 플라이 인이 열립니다.
5. 드롭다운 메뉴를 사용하여 장치를 이동할 그룹을 선택한 다음 저장을 **선택합니다.** 할당한 **그룹이** 보류 **중으로 변경됩니다.**

배정이 완료되면  할당한 그룹이  관리자(변경한 것으로 표시)로 변경되어 그룹 열에 새 그룹 할당이 표시됩니다. 

> [!NOTE]
> 장치가 "오류" 또는 "보류 중" 등록 상태인 경우 다른 그룹으로 장치를 이동할 수 없습니다.
>
>장치가 제대로 제거되지 않은 경우 상태가 "준비"로 표시될 수 있습니다. 이러한 장치를 이동하면 이동이 완료되지 않는 것일 수 있습니다. 5단계에서 보류 중으로  변경하여 할당된 그룹이 표시되지 않는 경우 Intune에서 디바이스를 검색하여 사용할 수 있는지 확인합니다.  자세한 내용은 [Intune에서 장치 자세히 보기](/mem/intune/remote-actions/device-inventory)를 참조하세요.