---
title: 전자 메일을 전달하는 새 사용자
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 관리자는 보안 및 준수 센터에서 새 사용자 전달 전자 메일 정보를 사용하여 조직의 사용자가 메시지를 새 도메인으로 전달하는 & 조사하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d517b5f9a7146d7256b89ae4e4d4d5f4aa6fc14f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59217992"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>보안 및 준수 센터에서 전자 메일 정보를 전달하는 & 사용자

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

조직의 새 사용자 계정이 갑자기 외부 도메인에 전자 메일 메시지를 전달하기 시작하면 의심스러운 일입니다.

보안 **&** 준수 센터에서 전달되는 [](https://protection.office.com) 새 도메인은 조직에서 새로 만든 사용자가 외부 도메인으로 메시지를 전달할 때 이를 사용자에게 통보합니다. 이 조건은 손상된 관리자 계정을 사용하여 새 사용자를 만들었다는 것을 나타낼 수 있습니다. 계정이 손상된 것으로 의심되는 경우 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)

이 인사이트는 문제가 검색된 경우만 표시되고 전달 보고서 페이지에 [표시됩니다.](view-mail-flow-reports.md#forwarding-report)

![새 사용자가 전자 메일 인사이트를 전달합니다.](../../media/mfi-new-users-forwarding-email.png)

위젯을 클릭하면 이 문서 나중에 설명된 전달 수정 보고서에 대한 링크를 포함하여 전달된 [](#forwarding-modifications-report) 메시지에 대한 자세한 정보를 찾을 수 있는 플라이아웃이 나타납니다.

![새 사용자 전달 전자 메일 정보를 클릭한 후 나타나는 플라이아웃에 대해 자세히 설명](../../media/mfi-new-users-forwarding-email-details.png)

또한 ( 보고서 대시보드 또는 **)의** 상위 인사이트 및 추천 영역에 있는 모든 정보 보기를 클릭한 & 세부 정보 페이지로 이동될 **수도**  \>  <https://protection.office.com/insightdashboard> 있습니다.

다음 섹션에  설명된 바와 같이 인사이트와 연결된 보고서 보기 링크를 클릭하여 전달 수정 보고서로 이동하면 됩니다. 

## <a name="forwarding-modifications-report"></a>수정 내용 전달 보고서

전달 **수정 보고서에는** 조직의 보낸 사람이 자동으로 전달하는 메시지에 대한 세부 정보가 표시됩니다.

- 외부 도메인으로 메시지를 전달하는 새로 만든 계정입니다.
- 조직의 다른 보낸 사람이 전달한 적이 없는 외부 도메인으로 메시지를 전달하는 계정입니다.

이러한 유형의 전달된 메시지는 보안 또는 규정 준수 위험을 내포할 수 있으며 계정 손상을 나타낼 수 있습니다.

보고서에는 최대 90일간의 데이터가 포함되어 있습니다. 기본적으로 보고서에는 지난 7일간의 데이터가 표시됩니다.

이 보고서는 메일 흐름 [](mail-flow-insights-v2.md) 대시보드 또는 보고서 대시보드에서 직접 사용할 [수 없습니다.](view-mail-flow-reports.md) 새 사용자 전달  전자 메일 인사이트에서  인사이트와 연결된 보고서 보기 링크를 클릭하는 것 외에도 다음을 통해 보고서에 연결됩니다.

- 전달되는  새 도메인의 세부 정보에서 전달 알림 보고서 [링크를 클릭합니다.](mfi-new-domains-being-forwarded-email.md)
- 를 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 열기.

### <a name="report-view-for-the-forwarding-modifications-report"></a>전달 수정 보고서에 대한 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **데이터 표시: 새** 전달 사용자:

  ![새 전달 사용자는 전달 수정 내용 보고서에서 볼 수 있습니다.](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **데이터 표시: 새** 전달 도메인 :

  ![전달 수정 내용 보고서의 새 전달된 도메인 보기입니다.](../../media/forwarding-modifications-report-new-forwarded-domains.png)

보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>전달 수정 보고서의 세부 정보 테이블 보기

세부 정보 **표 보기를** 클릭하면 표시되는 정보가 보고 있는 차트에 따라 다를 수 있습니다.

- **데이터 표시: 새** 전달 사용자:

  - **이름:** 보낸 사람 전자 메일 주소입니다.
  - **전달 유형**
  - **받는 사람 주소**
  - **세부 정보**
  - **개수**
  - **첫 번째 전달 날짜**

- **데이터 표시: 새** 전달 도메인 :

  - **이름:** 보낸 사람에 대한 전자 메일 도메인입니다.
  - **전달 유형**
  - **받는 사람 주소**
  - **세부 정보**
  - **개수**
  - **첫 번째 전달 날짜**

세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**

표에서 행을 선택하면 세부  정보 플라이아웃이 다음 정보와 함께 표시됩니다.

- **이름:** 이 주소는 보낸 사람 전자 메일  주소(데이터 표시: 새 전달 사용자 보기에서) 또는 보낸 사람 전자 메일 도메인(데이터 **표시:** 새 전달 도메인 보기에서)입니다.
- **전달 유형**
- **받는 사람**
- **세부 정보**
- **개수**
- **시작 날짜**
- **권장 사항:** 여기에서 링크를 클릭하여 사용자 관리 Microsoft 365 관리 센터.

![전달 수정 보고서의 새 전달 사용자 보기의 세부 정보 표에서 플라이아웃에 대한 세부 정보입니다.](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)
