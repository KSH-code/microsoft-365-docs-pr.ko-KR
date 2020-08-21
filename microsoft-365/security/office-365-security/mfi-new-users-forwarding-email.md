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
description: 관리자는 보안 & 준수 센터에서 새 사용자를 전달하는 인사이트를 사용하여 조직의 사용자가 새 도메인으로 메시지를 전달하는 시기를 조사하는 방법을 알아볼 수 있습니다.
ms.openlocfilehash: cb2e16d321e181916219e3425c26e59ebe31b866
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826984"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>보안 보안 및 준수 센터에서 전자 메일을 전달하는 & 정보

조직의 새 사용자 계정이 외부 도메인으로 전자 메일 메시지 전달을 과도하게 시작하면 의심스러운 것입니다.

전달되는 **전자 메일 인사이트인** 새 도메인은 조직의 새로 만든 사용자가 외부 도메인으로 메시지를 전달하는 경우 해당 정보를 알리게 됩니다. 이 조건은 차단된 관리자 계정이 새 사용자를 만드는 데 사용됨을 나타냅니다. 계정이 손상되었다고 의심되는 경우 [손상된 이메일 계정에 대한 응답을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)

이 인사이트는 문제가 검색될 때만 나타나며 전달 보고서 [페이지에 표시됩니다.](view-mail-flow-reports.md#forwarding-report)

![전자 메일을 전달하는 새 사용자](../../media/mfi-new-users-forwarding-email.png)

위로 창을 클릭하면 이 항목의 뒷부분에 설명된 것과 같이 전달된 메시지에 대한 자세한 정보를 [찾을](#forwarding-modifications-report) 수 있는 플라이 아웃이 표시됩니다.

![새 사용자를 전달하는 전자 메일 인사이트를 클릭한 후 표시되는 세부 정보 플라이아웃](../../media/mfi-new-users-forwarding-email-details.png)

또한 상위 인사이트 보기 영역(보고서 대시보드 또는)에서 **View all** **모든 정보 보기를 클릭하면 이 & 세부 정보 페이지에** **나타나도록** \> **할 수** <https://protection.office.com/insightdashboard> 있습니다.

정보 **링크와 연결된 See report insight** link를 클릭하면 다음 섹션에 설명된 바라면 **서정 수정 보고서로** 이동할 수 있습니다.

## <a name="forwarding-modifications-report"></a>문제 해결 보고서

**전달 수정 보고서에는 조직의 보낸 사람으로부터** 자동으로 전달되는 메시지에 대한 세부 정보가 표시됩니다.

- 외부 도메인으로 메시지를 전달하는 새로 만든 계정입니다.
- 외부 도메인으로 메시지를 전달하는 계정(조직 내 다른 사람이 전달되지 않은 경우).

전달된 이러한 유형의 메시지는 보안 또는 규정 준수 위험에 부합될 수 있기이하며, 위험에 노출된 계정을 나타내기도 합니다.

보고서에는 최대 90일 동안의 데이터가 포함됩니다. 기본적으로 보고서는 지난 7일간의 데이터를 표시합니다.

이 보고서는 메일 흐름 대시보드 또는 [보고서 대시보드에서](mail-flow-insights-v2.md) 직접 사용할 [수 없습니다.](view-mail-flow-reports.md) 새 사용자를 전달하는 **전자 메일 정보에서** 인사이트 **New users forwarding email** 보기 링크를 클릭하는 하는 외에도 다음을 통해 보고서에 액세스합니다.

- 전달 알림 **보고서 링크를** 클릭하여 전달된 전자 [메일인 경우의 세부 정보에서 전달 알림 보고서 링크를 클릭합니다.](mfi-new-domains-being-forwarded-email.md)
- 여는 <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 중 .

### <a name="report-view-for-the-forwarding-modifications-report"></a>전달 수정 보고서에 대한 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **데이터 표시: 새 전달 사용자:**

  ![전달 수정 보고서의 새 전달 사용자 보기](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **데이터 표시: 새 전달 도메인:**

  ![전달 수정 보고서의 새로운 도메인 보기](../../media/forwarding-modifications-report-new-forwarded-domains.png)

보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>전달 수정 보고서에 대한 세부 정보 표 보기

세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.

- **데이터 표시: 새 전달 사용자:**

  - **이름:** 보낸 사람의 전자 메일 주소입니다.
  - **전달 유형**
  - **받는 사람 주소**
  - **세부 정보**
  - **개수**
  - **첫 번째 전달 날짜**

- **데이터 표시: 새 전달 도메인:**

  - **이름:** 보낸 사람의 전자 메일 도메인입니다.
  - **전달 유형**
  - **받는 사람 주소**
  - **세부 정보**
  - **개수**
  - **첫 번째 전달 날짜**

세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

표에서 행을 선택하면 다음 정보와 함께 **세부** 정보 플라이아웃이 표시됩니다.

- **이름:** 이 주소는 보낸 사람의 전자 메일 주소(표시 데이터 **보기: 새** 전달 사용자 보기) 또는 보낸 사람의 전자 메일 도메인(표시 **데이터: 새 전달 도메인 보기)입니다.**
- **전달 유형**
- **받는 사람**
- **세부 정보**
- **개수**
- **시작 날짜**
- **권장 사항:** 여기서는 링크를 클릭하여 Microsoft 365 관리 센터에서 사용자를 관리할 수 있습니다.

![전달 수정 보고서의 새 전달 사용자 보기에 대한 세부 정보 표시에서 플라인 세부 정보](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)
