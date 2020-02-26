---
title: 보류 알림 관리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery의 통신 워크플로를 사용 하 여 법적 보존 알림의 상태를 추적 하 고, 필요한 경우 업데이트를 다시 보냅니다.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280116"
---
# <a name="manage-hold-notifications"></a>보류 알림 관리

법적 보존 알림 워크플로를 시작한 후에는 Advanced eDiscovery의 통신 워크플로를 사용 하 여 통신 상태를 추적할 수 있습니다. Communications 탭에는 고급 eDiscovery 사례 내의 모든 알림 목록이 포함 되어 있습니다. 할당 된 custodians 수 또는 통지를 승인 받은 시간 등의 세부 정보를 볼 수 있습니다.

## <a name="monitor-acknowledgments"></a>승인 모니터링

**통신** 탭에서 통신을 선택한 후에는 보존 알림을 승인 하는 custodians 목록을 볼 수 있습니다. 

1. 준수 센터에서 **eDiscovery > Advanced ediscovery**로 이동 합니다.

2. 사례를 선택 하 고 **통신** 탭을 클릭 합니다.

3. 통신을 선택 하 여 **Custodian 통신** 플라이 아웃 페이지를 표시 합니다.

선택한 통신에 연결 된 custodians 목록이 통신 플라이 아웃 페이지에 표시 됩니다. 또한이 페이지에는 정보를 표시 하 고 수신 된 승인 수와 미해결의 수를 보여 줍니다. 또한이 페이지에는 보류 알림을 수신한 custodians가 표시 됩니다.

## <a name="re-send-a-hold-notice"></a>보류 알림 다시 보내기

경우에 따라 custodians에서 일상적인 작업을 수행 하는 동안 전자 메일 메시지를 추적 하지 못하게 됩니다. 또는 장기간 실행 되는 소송에 대해 custodian에서 사용자에 게 연락 하 여 알림을 다시 보내도록 요청할 수 있습니다. 법적 보존 알림의 통신 워크플로를 관리할 때 알림 메시지를 다시 보내 "사용자 사서함의 맨 위로"로 다시 전송 해야 할 수 있습니다.

보존 알림을 custodian으로 다시 보내려면 다음을 수행 합니다.

1. 고급 eDiscovery에서 사례를 선택 하 고 **통신** 탭을 클릭 합니다.

2. 통신을 선택 하 여 **Custodian 통신** 플라이 아웃 페이지를 표시 합니다.

3. **추가 > 다시 보내기 알림을**클릭 합니다.

4. **보존 공지 플라이 아웃 다시 보내기** 페이지에서 공지 사항을 다시 보낼 custodians을 선택 하 고 선택적 이유를 입력 합니다.

5. **다시 보내기를** 클릭 하 여 선택한 custodians에 게 알림을 보냅니다.

Custodian가 보존 알림을 승인 하지 않은 경우 미리 알림 및 에스컬레이션 워크플로가 다시 시작 됩니다. Custodian가 보존 알림을 승인 하면 custodian가 원래 보존 알림의 복사본을 받습니다.

> [!NOTE]
> 통신에 할당 된 custodians에만 법적 보존 알림을 다시 보낼 수 있습니다. 

## <a name="update-preservation-requirements"></a>업데이트 보존 요구 사항
  
사례가 진행 됨에 따라 custodians는 이전에 지시 된 것 보다 더 많은 데이터를 보존 해야 할 수 있습니다. EDiscovery 용어를 사용 하는 경우 업데이트 된 콘텐츠로 보존 알림을 다시 발행 해야 합니다.

초기 보존 알림의 내용을 업데이트 하려면 다음을 수행 합니다.

1. 고급 eDiscovery에서 사례를 선택 하 고 **통신** 탭을 클릭 합니다.

2. 업데이트할 보존 알림을 선택 하 고 **Custodian 통신** 플라이 아웃 페이지에서 **편집** 을 클릭 합니다.

3. **통신 편집** 마법사에서 마법사 왼쪽 창에서 **포털 콘텐츠 정의** 를 클릭 하 고 알림의 내용을 업데이트 합니다.

4. **저장**을 클릭합니다.

재발급 통지는 법적 보존 알림에 할당 된 모든 custodians 전송 됩니다. 또한 미리 알림 또는 에스컬레이션 알림을 사용 하도록 설정 된 경우 해당 알림 유형에 대 한 워크플로가 다시 시작 됩니다.

## <a name="update-legal-hold-notifications-and-settings"></a>법적 보존 알림 및 설정 업데이트

발급, 릴리스, 재발급, 미리 알림 또는 에스컬레이션 알림의 콘텐츠 또는 설정을 업데이트할 때 이러한 변경 내용은 워크플로에서 생성 되는 모든 이후 통신에 적용 됩니다.

## <a name="more-information"></a>추가 정보

- [보유자를 사례에 추가](add-custodians-to-case.md)

- [법적 보존 알림 만들기](create-hold-notification.md)

- [보류 알림 승인](acknowledge-hold-notification.md)
