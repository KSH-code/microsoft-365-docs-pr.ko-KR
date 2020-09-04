---
title: 전자 메일을 전달하는 새 사용자
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 관리자는 보안 & 준수 센터에서 전자 메일을 전달 하는 새 사용자를 사용 하 여 조직의 사용자가 새 도메인으로 메시지를 전달 하는 경우 조사 하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 4d8c88cef182ab1c521d23970797e4746e188916
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357369"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>보안 & 준수 센터에서 전자 메일을 전달 하는 새 사용자

조직의 새 사용자 계정이 갑자기 외부 도메인으로 전자 메일 메시지를 전달 하기 시작 하면 의심 스러운 것입니다.

[보안 & 준수 센터](https://protection.office.com) 에 **전달 되는 새 도메인** 은 조직에서 새로 만든 사용자가 외부 도메인으로 메시지를 전달 하는 경우 사용자에 게 알려 줍니다. 이 조건은 손상 된 관리자 계정을 사용 하 여 새 사용자를 만드는 것을 나타낼 수 있습니다. 계정이 손상 된 것으로 의심 되는 경우 [손상 된 전자 메일 계정에 응답](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)을 참조 하세요.

이 통찰력은 문제가 검색 된 경우에만 나타나며 [전달 보고서](view-mail-flow-reports.md#forwarding-report) 페이지에 표시 됩니다.

![전자 메일을 전달하는 새 사용자](../../media/mfi-new-users-forwarding-email.png)

위젯을 클릭 하면이 항목의 뒷부분에 설명 된 대로 [전달 수정 보고서](#forwarding-modifications-report) 에 대 한 링크를 포함 하 여 전달 된 메시지에 대 한 자세한 정보를 확인할 수 있는 플라이 아웃이 나타납니다.

![전자 메일 통찰력을 전달 하는 새 사용자를 클릭 하면 나타나는 세부 정보 플라이 아웃](../../media/mfi-new-users-forwarding-email-details.png)

**보고서** 대시보드 또는 사이트의 **최상위 insights & 추천** 영역에서 **모두 보기** 를 클릭 한 후에는이 세부 정보 페이지로 이동할 수도 있습니다 \> **Dashboard** <https://protection.office.com/insightdashboard> .

다음 섹션에서 설명 하는 것 처럼 **전달 수정 보고서** 로 이동 하려면 **자세한 정보 표시 링크와 연결 된 보고서 보기** 를 클릭 합니다.

## <a name="forwarding-modifications-report"></a>전달 수정 보고서

**전달 수정 보고서** 에는 조직의 보낸 사람이 자동으로 전달 되는 메시지에 대 한 세부 정보가 표시 됩니다.

- 외부 도메인으로 메시지를 전달 하는 새로 만든 계정입니다.
- 조직의 다른 보낸 사람이 전달 하지 않은 외부 도메인으로 메시지를 전달 하는 계정입니다.

이러한 유형의 전달 메시지는 보안 또는 준수 위험을 초래할 수 있으며, 손상 된 계정을 나타낼 수도 있습니다.

보고서에 포함 된 데이터는 최대 90 일입니다. 기본적으로 보고서에는 최근 7 일간의 데이터가 표시 됩니다.

이 보고서는 [메일 흐름 대시보드](mail-flow-insights-v2.md) 또는 [보고서 대시보드에서](view-mail-flow-reports.md)직접 사용할 수 없습니다. **전자 메일을 전달 하는 새 사용자** 의 **통찰력 링크와 연결 된 보고서 보기** 를 클릭 하는 것 외에 다음과 같은 방법으로 보고서에 액세스할 수 있습니다.

- [전달 되는 새 도메인](mfi-new-domains-being-forwarded-email.md)의 세부 정보에서 **전달 알림 보고서** 링크를 클릭 하 여 전자 메일을 파악 합니다.
- 열기 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 입니다.

### <a name="report-view-for-the-forwarding-modifications-report"></a>전달 수정 보고서에 대 한 보고서 보기

보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.

- **데이터 표시: 새 전달 사용자**:

  ![전달 수정 보고서의 새 전달 사용자 보기](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **데이터 표시: 새 전달 도메인**:

  ![전달 수정 보고서의 새 전달 된 도메인 보기](../../media/forwarding-modifications-report-new-forwarded-domains.png)

보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>전달 수정 보고서에 대 한 세부 정보 테이블 보기

**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.

- **데이터 표시: 새 전달 사용자**:

  - **이름**: 보낸 사람의 전자 메일 주소입니다.
  - **전달 유형**
  - **받는 사람 주소**
  - **세부 정보**
  - **개수**
  - **첫 번째 전달 날짜**

- **데이터 표시: 새 전달 도메인**:

  - **이름**: 보낸 사람의 전자 메일 도메인입니다.
  - **전달 유형**
  - **받는 사람 주소**
  - **세부 정보**
  - **개수**
  - **첫 번째 전달 날짜**

세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

표에서 행을 선택 하면 다음과 같은 정보가 포함 된 **세부 정보** 플라이 아웃이 나타납니다.

- **Name**: 보낸 사람의 전자 메일 주소 ( **새 착신 전환 사용자** 보기) 또는 보낸 사람의 전자 메일 도메인 ( **데이터 표시 위치: 새 포워딩 도메인** 보기)입니다.
- **전달 유형**
- **받는 사람**
- **세부 정보**
- **개수**
- **시작 날짜**
- **권장 사항**: 여기서는 Microsoft 365 관리 센터에서 사용자를 관리 하기 위한 링크를 클릭할 수 있습니다.

![전달 수정 보고서의 새 전달 사용자 보기의 세부 정보 테이블에서 정보 플라이 아웃](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.
