---
title: 보낸 사람 도메인 정보 문제 해결
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 보낸 사람 도메인에 대 한 정보를 수정 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: a416b4d15ff52a611f00a88de8440c749ff08ad3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635175"
---
# <a name="fix-sender-domain-insight"></a>보낸 사람 도메인 정보 문제 해결

Microsoft 365에서는 특정 보안 기준을 충족 하기 위해 내부 온-프레미스 전자 메일 환경에서 Microsoft 365로 메시지를 전송 해야 합니다.

- Microsoft 365에서 인바운드 커넥터를 만들어 원본 IP 주소 또는 인증서를 사용 하 여 온-프레미스 전자 메일 서버에서 SMTP 연결을 인증 합니다.

- Microsoft 365을 통해 외부 세계를 통해 전자 메일을 릴레이 하도록 온-프레미스 전자 메일 서버를 구성 해야 합니다.

- 구성에서 다음 문 중 하나에 해당 하는 경우:

  - 보낸 사람의 전자 메일 도메인이 조직에 등록 됩니다. 자세한 내용은 Office 365에서 도메인 추가를 참조 하세요.

  - 온-프레미스 전자 메일 서버는 인증서를 사용 하 여 microsoft 365에 전자 메일을 보내거나, 인증서가 Microsoft 365에 등록 한 도메인 이름과 정확히 일치 하거나, 해당 도메인을 사용 하 여 Microsoft 365에 인증서 기반 커넥터를 만들었다고 구성 되어 있습니다. 

조건을 충족 하지 않는 메시지는 조직에 대 한 특성을 사용 하지 않으며 거부할 수 있습니다.

**Fix sender domain** 통찰력은 온-프레미스 환경에서 조건을 충족 하지 않는 전자 메일을 표시 하 고, 온-프레미스 전자 메일 환경에서 잠재적으로 손상 된 컴퓨터와 사용자 계정을 식별 하 고, 수정 작업을 수행 하는 데 도움이 됩니다.

![보안 & 준수 센터의 메일 흐름 대시보드에서 보낸 사람 도메인 통찰력 수정](../../media/sender-domain-insight-selected.png)

**자세히 보기**를 클릭 하면 다음 다이어그램에 나와 있는 것과 같이 다른 widget이 표시 됩니다.

![보낸 사람 도메인 문제 해결의 세부 정보 위젯](../../media/sender-domain-view-details.png)

메시지를 Office 365로 배달 하는 데 사용 된 인바운드 커넥터가 표시 됩니다. **예제 메시지 id 보기** 를 클릭 하 여 온-프레미스 전자 메일 환경에서 전송 된 메시지에 대 한 세부 정보를 볼 수도 있습니다. 이러한 메시지는 Office 365에서 거부 되었기 때문에 메시지 추적을 사용할 수는 없지만, 샘플 메시지 id를 사용 하 여 온-프레미스 전자 메일 환경에서 메시지를 추적할 수도 있습니다.

![보낸 사람 도메인 정보 수정에서 예제 메시지 id 보기](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 메일 흐름 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.
