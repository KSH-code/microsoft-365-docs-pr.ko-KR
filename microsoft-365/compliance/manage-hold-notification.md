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
description: Advanced eDiscovery의 통신 워크플로를 사용하여 법적 보유 알림의 상태를 추적하고 필요한 경우 업데이트하고 다시 전송합니다.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280116"
---
# <a name="manage-hold-notifications"></a>보류 알림 관리

법적 보유 알림 워크플로를 시작한 후 Advanced eDiscovery의 통신 워크플로를 사용하여 통신 상태를 추적할 수 있습니다. 통신 탭에는 Advanced eDiscovery 사례 내의 모든 알림 목록이 포함되어 있습니다. 할당되거나 통지를 확인한 수와 같은 세부 정보를 볼 수 있습니다.

## <a name="monitor-acknowledgments"></a>인정 모니터링

통신 탭에서 통신을  선택한 후 보류 통지를 인정한 보유자 목록을 볼 수 있습니다. 

1. 준수 센터에서 고급 **eDiscovery > eDiscovery로 이동합니다.**

2. 사례를 선택하고 통신 **탭을** 클릭합니다.

3. **Custodian** 통신 플라이아웃 페이지를 표시하는 통신을 선택합니다.

선택한 통신과 연결된 보전자 목록이 통신 플라이아웃 페이지에 표시됩니다. 또한 이 페이지에는 받은 확인의 수와 미해결한 수에 대한 정보도 표시됩니다. 이 페이지에는 보류 알림을 받은 확인을 보낸 보유자도 표시됩니다.

## <a name="re-send-a-hold-notice"></a>보류 알림 다시 보내기

경우에 따라, 수호자들이 매일 업무에서 전자 메일 메시지를 추적하지 못합니다. 또는 오랫동안 실행되는 소송의 경우, 양도인은 사용자나 다른 사용자에 연락하여 알림 다시 보내기 요청이 있을 수 있습니다. 법적 보유 알림에 대한 통신 워크플로를 관리할 때 알림 메시지를 다시 보내 "사용자의 사서함 맨 위"로 다시 보내야 할 수 있습니다.

보유자에게 보류 통지를 다시 보내기:

1. Advanced eDiscovery에서 사례를 선택하고 통신 **탭을** 클릭합니다.

2. **Custodian** 통신 플라이아웃 페이지를 표시하는 통신을 선택합니다.

3. 다시 **보류 > 추가 정보를 클릭합니다.**

4. 다시 **보내기** 보류 알림 플라이아웃 페이지에서 통지를 다시 보낼 대상인 보유자(선택 사항)를 선택하고 선택적 이유를 입력합니다.

5. 다시 **보내기(다시** 보내기)를 클릭하여 선택한 보전자에게 통지를 보낼 수 있습니다.

보유자에서 보류 알림을 인정하지 않은 경우 미리 알림 및 에스컬레이터 워크플로가 다시 시작됩니다. 보유자에 대한 보류 알림이 인정된 경우 보유자는 원래 보류 알림 사본을 받게됩니다.

> [!NOTE]
> 법적 보유 알림을 통신에 할당된 보유자에게만 다시 전송할 수 있습니다. 

## <a name="update-preservation-requirements"></a>보존 요구 사항 업데이트
  
사례가 진행될 때, 이전에 지시한 것보다 추가 데이터 또는 적은 데이터를 보존해야 할 수 있습니다. eDiscovery 용어의 경우 업데이트된 콘텐츠로 보류 통지를 다시 발급해야 합니다.

초기 보류 알림의 내용을 업데이트하는 경우:

1. Advanced eDiscovery에서 사례를 선택하고 통신 **탭을** 클릭합니다.

2. 업데이트할 보류 공지를 선택하고  **보유자** 통신 플라이아웃 페이지에서 편집을 클릭합니다.

3. 통신 **편집 마법사에서** 마법사의 왼쪽 창에서 포털 콘텐츠 정의를 클릭하고 알림의 내용을 업데이트합니다. 

4. **저장** 을 클릭합니다.

다시 발행 알림은 법적 보유 알림에 할당된 모든 보유자에게 전송됩니다. 또한 미리 알림 또는 에스컬레이터 알림이 사용하도록 설정되어 있는 경우 해당 유형의 알림에 대한 워크플로가 다시 시작됩니다.

## <a name="update-legal-hold-notifications-and-settings"></a>법적 보유 알림 및 설정 업데이트

발행, 릴리스, 다시 전달, 미리 알림 또는 에스컬레이터 알림의 콘텐츠 또는 설정을 업데이트하면 이러한 변경 내용은 워크플로에서 생성되는 향후 모든 통신에 적용됩니다.

## <a name="more-information"></a>추가 정보

- [보유자를 사례에 추가](add-custodians-to-case.md)

- [법적 보유 알림 만들기](create-hold-notification.md)

- [보류 알림 승인](acknowledge-hold-notification.md)
