---
title: 보류 알림 승인
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
description: ''
ms.openlocfilehash: de542ad950fce061b63aa4b2aaf37821582d7466
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256805"
---
# <a name="acknowledge-a-hold-notification"></a>보류 알림 승인 
규정 요구 사항 또는 조사에 응답할 때 custodians에 게 알려야 하 고, ESI (전자적으로 저장 된 정보)를 보존 하 고, 활성 또는 즉시 법적 관계와 관련이 있을 수 있는 모든 자료를 유지 해야 할 수도 있습니다. 합법적인 팀이 전송 된 후에는 각 custodian에 게 제공 되 고, 읽고, 이해 했으며, 지정 된 지침을 따르는 합의를 받았는지 확인 해야 합니다.

Custodians의 시간, 비용 및 노력을 줄이기 위해 고급 eDiscovery를 사용 하면 전자 메일을 통해 법적 보존 알림을 주고 받을 수 있습니다. 전자 메일 알림 외에도 각 custodian는 개별화 준수 포털에 액세스할 수 있으며,이를 통해 custodians가 의무 상태 변경 사항에 대 한 알림을 받을 수 있습니다.

## <a name="email-notifications"></a>이메일 알림
법적 보존 알림이 실행 되 면 각 custodian는 정의 된 법적 보존 통지를 포함 하는 고유한 개인 설정 전자 메일을 수신 하 고 지침을 추가 합니다. 

> [!Tip] 
> 기본 제공 [통신 편집기](using-communications-editor.md) 를 사용 하 여 custodians에서 해당 알림을 승인 하거나 전자 메일에서 직접 준수 포털에 액세스 하도록 하는 방법을 참조 하세요.

법적 보존 알림 구성에 따라 custodians에 다음과 같은 알림이 표시 될 수 있습니다. 

- **발급 알림** -custodian로 전송 되는 첫 번째 알림입니다. 여기에는 사용자의 발급 지침 및 메시지 끝에 추가 된 보류 알림이 포함 됩니다.

- **미리 알림** -이 옵션을 사용 하도록 설정 하면 지정 된 빈도 및 간격에 따라 미리 알림 알림이 custodians로 전송 됩니다. 미리 알림은 custodian가 알림을 승인할 때까지 또는 미리 알림 수가 모두 소모 될 때까지 계속 전송 됩니다.

- **에스컬레이션 알림** -이 옵션을 사용 하도록 설정 하는 경우 미리 알림 알림이 모두 포함 된 후에는 custodian 및 관리자에 게 에스컬레이션 알림이 전송 됩니다. 시스템은 alloted 에스컬레이션이 완료 되거나 custodian가 해당 보존 알림을 받을 때까지 에스컬레이션 알림을 자동으로 보냅니다.

- **재발급 알림** -조사 과정을 진행 하는 동안 보존 공지의 내용이 업데이트 되 면 업데이트 된 공지가 자동으로 custodian로 전송 됩니다.

- **릴리스 알림** -custodian가 사례에서 출시 되 면 릴리스 알림을 받게 됩니다. 

## <a name="compliance-portal"></a>준수 포털
전자 메일 알림 외에도 각 custodian는 고유한 준수 포털에 액세스할 수 있습니다. 포털을 통해 각 custodian은 활성 보류 알림을 보고, 액세스 하 고, 승인할 수 있습니다.

![Custodian에 대 한 준수 포털](media/CustodianPortal.jpg)
