---
title: Microsoft 365 보안 센터에서 ServiceNow 티켓 만들기 및 추적
description: Microsoft 365 보안 센터에서 ServiceNow의 티켓을 만들고 추적 하는 방법에 대해 알아봅니다.
keywords: 보안, Microsoft 365, M365, 보안 점수, 보안 센터, ServiceNow, 티켓, 작업
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769678"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Microsoft 365 보안 센터에서 ServiceNow 티켓 만들기 및 추적

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
>**ServiceNow 커넥터의 미리 보기 기간이 끝나고**<br>
>이 기능은 11 월 2020 끝에 더 이상 제공 되지 않습니다. 다음 단계를 확인 하는 동안 의견을 보내주셔서 사용자에 게 지속적인 지원을 주셔서 감사 합니다.

[Microsoft 365 보안 센터](overview-security-center.md) 는 ServiceNow에서 티켓을 기본적으로 만들고 추적할 수 있도록 향상 되었습니다. [ServiceNow에 대해 자세히 알아보기](https://www.servicenow.com/)

보안 센터에서 보안 관리자는 [Microsoft 보안 점수](microsoft-secure-score.md) 향상 작업을 ServiceNow로 직접 전송 하 고 티켓을 만들 수 있습니다. 인시던트 관리 및 변경 관리 티켓을 모두 만들 수 있습니다. 보안 센터 홈 페이지 및 ServiceNow의 티켓을 추적 합니다.

- [**필수 구성 요소, 데이터 교환 및 문제 해결 방법 알아보기**](tickets.md)
- **준수 센터에서 ServiceNow 티켓 관리** (사용할 수 없음)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>ServiceNow에 Microsoft 365 보안 센터 연결

Microsoft 365 보안 센터 홈 페이지로 이동 하 여 ServiceNow 연결 카드를 확인 합니다.

![ServiceNow 사용](../../media/do-you-use-servicenow-250.png)

"ServiceNow에 연결"을 선택 하 여 ServiceNow 설정 페이지로 이동 합니다. 지침에 따라 Microsoft 365 커넥터 앱에 권한을 부여 합니다.

> [!NOTE]
> Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하기 전에 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다. 개인 자격 증명은 사용 하지 마십시오.

지침을 따르고 연결에 대 한 인증을 받은 후에는 Microsoft 365 보안 센터 연결 페이지 및 ServiceNow Microsoft 365 티켓 커넥터 앱 환경에서 연결 상태를 확인 합니다. 이제 작업 만들기를 시작 하도록 설정 되었습니다.

### <a name="troubleshooting"></a>문제 해결

연결 프로세스에서 발생할 수 있는 일반적인 오류 및 [문제 해결 섹션](tickets.md#troubleshooting)에서이를 완화 하는 방법에 대해 알아봅니다.

## <a name="create-a-task-and-share-it-to-servicenow"></a>작업 만들기 및 ServiceNow에 공유

통합이 설정 되 면 특정 [Microsoft 보안 점수](microsoft-secure-score.md) 향상 작업을 기반으로 ServiceNow 작업을 만듭니다. Microsoft 365 보안 센터의 보안 점수 향상 작업으로 이동한 후 **공유** 를 선택 합니다. 드롭다운 옵션 중 하나는 ServiceNow입니다.

우선 순위를 설정 하 고 이름, 설명 또는 기한을 편집할 수 있는 작업이 생성 됩니다. 필수 필드를 모두 입력 한 후에는 해당 작업을 ServiceNow로 보냅니다.

이 작업은 Microsoft 365 보안 및 구성 변경 요청으로 ServiceNow에 표시 됩니다.

## <a name="track-tickets"></a>티켓 추적

ServiceNow 변경 관리 및 인시던트 관리 티켓이 만들어지면 Microsoft 365 보안 센터 홈 페이지의 명함에 표시 됩니다. 이러한 카드에서 티켓을 만들거나, 모든 티켓을 보거나, ServiceNow 구성을 관리할 수 있습니다.

![ServiceNow 변경 관리 티켓](../../media/change-management-375.png)  ![ServiceNow 인시던트 관리 티켓](../../media/incident-management-375.png)

Microsoft 365 보안 센터에서 ServiceNow 통합을 다시 구축 하거나 관리 하려면 카드 중 하나에서 **servicenow 구성 관리** 를 선택 합니다. 현재 ServiceNow 연결을 제거 하 고 티켓 상태 이름을 사용자 지정 합니다.

Microsoft 365 보안 센터에 ServiceNow 티켓이 표시 되 면 작업은 다른 보안 대시보드 항목과 함께 추적 하 고 작동할 수 있는 위치에 살고 있습니다.

## <a name="resources"></a>리소스

- [필수 구성 요소, 데이터 교환 및 문제 해결 방법 알아보기](tickets.md)
- [Microsoft 보안 점수](microsoft-secure-score.md)
