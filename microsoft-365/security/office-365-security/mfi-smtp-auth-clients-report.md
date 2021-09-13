---
title: 메일 흐름 대시보드의 SMTP Auth 클라이언트 인사이트 및 보고서
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 SMTP 인증 인사이트를 사용하여 보고를 통해 조직의 전자 메일 보낸 사람이 SMTP AUTH(인증된 SM & TP AUTH)를 사용하여 전자 메일 메시지를 보내는지 모니터링하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d4c39e722ed7d9853a4fb328a8e87aac535bea9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59217965"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>보안 및 준수 센터의 SMTP & 인사이트 및 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

보안 및 준수 센터의 메일 [](mail-flow-insights-v2.md) 흐름 대시보드 및 관련 SM & TP 인증 클라이언트 [보고서의](https://protection.office.com) **SMTP** 인증 클라이언트 인사이트는 조직의 사용자 또는 시스템 계정이 SMTP AUTH 클라이언트 전송 프로토콜을 사용하는 방법을 강조합니다. [](#smtp-auth-clients-report) 이 레거시 프로토콜(끝점 smtp.office365.com 사용)은 기본 인증만 제공하며 손상된 계정에서 전자 메일을 보내기 위해 사용될 수 있습니다. 인사이트 및 보고서를 통해 SMTP AUTH 전자 메일 전송에 대한 비정상적인 활동을 확인할 수 있습니다. 또한 SMTP AUTH를 사용하는 클라이언트 또는 장치에 대한 TLS 사용 데이터도 보여 줍니다.

위젯은 지난 7일 동안 SMTP 인증 프로토콜을 사용한 사용자 또는 서비스 계정의 수를 나타냅니다.

![보안 및 준수 센터의 메일 흐름 대시보드에 있는 SMTP & 위젯](../../media/mfi-smtp-auth-clients-report-widget.png)

위젯에서 메시지 수를 클릭하면 **SMTPAuth 클라이언트** 플라이아웃이 나타납니다. 플라이아웃은 지난 주에 대한 TLS 사용량 및 볼륨의 집계 보기를 제공합니다.

![메일 흐름 대시보드에서 SMTPAuth 클라이언트 위젯을 클릭한 후 플라이아웃에 대한 세부 정보](../../media/mfi-smtp-auth-clients-report-details.png)

다음 섹션에 설명된 **SMTPAuth** 클라이언트 보고서 링크를 클릭하여 SMTP Auth 클라이언트 보고서로 이동하면 됩니다.

## <a name="smtp-auth-clients-report"></a>SMTP 인증 클라이언트 보고서

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTPAuth 클라이언트 보고서에 대한 보고서 보기

기본적으로 보고서에는 지난 7일간의 데이터가 표시되지만 지난 90일 동안 데이터를 사용할 수 있습니다.

개요 섹션에는 다음 차트가 포함되어 있습니다.

- **데이터 보기:** 볼륨 보내기: 기본적으로 차트에는 모든 도메인에서 보낸 SMTPAuth 클라이언트 메시지 수가 표시됩니다(**데이터 표시:** 모든 보낸 사람 도메인은 기본적으로 선택되어 있습니다. 데이터 표시를 클릭하고 드롭다운 목록에서  보낸 사람 도메인을 선택하여 결과를 특정 보낸 사람 도메인으로 필터링할 수 있습니다. 특정 데이터 포인트(일)를 마우스로 마우스로 대면 메시지 수가 표시됩니다.

  ![보안 및 준수 센터의 SMTP Auth 클라이언트에서 볼륨 & 보고합니다.](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **다음을 통해 데이터 보기: TLS** 사용법: 차트는 선택한 기간 동안 모든 SMTPAuth 클라이언트 메시지에 대한 TLS 사용률을 보여 줍니다. 이 차트를 사용하면 이전 버전의 TLS를 계속 사용하는 사용자 및 시스템 계정을 식별하고 조치를 취할 수 있습니다.

  ![SMTP Auth 클라이언트의 TLS 사용 현황 보기는 보안 및 준수 & 보고합니다.](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**

보고서 **요청을 클릭하여** 전자 메일 메시지에 보고서의 자세한 버전을 수신합니다. 보고서를 받을 날짜 범위와 받는 사람을 지정할 수 있습니다.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTPAuth 클라이언트 보고서에 대한 세부 정보 테이블 보기

세부 정보 **표 보기를** 클릭하면 표시되는 정보가 보고 있는 차트에 따라 다를 수 있습니다.

- **데이터 보기: 볼륨 보내기:** 표에 다음 정보가 표시됩니다.

  - **보낸 사람 주소**
  - **메시지 수**

  행을 선택하면 플라이아웃에 동일한 세부 정보가 표시됩니다.

- **다음을 통해 데이터 보기: TLS 사용법:** 표에 다음 정보가 나와 있습니다.

  - **보낸 사람 주소**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **메시지 수**

  <sup>\*</sup> 이 열에는 보낸 사람이 보낸 메시지의 백분율과 수가 모두 표시됩니다.

세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**

행을 선택하면 플라이아웃에 유사한 세부 정보가 표시됩니다.

![SMTPAuth 클라이언트 보고서의 TLS 사용 현황 보기의 세부 정보 표에서 플라이아웃에 대한 세부 정보를 제공합니다.](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

보고서 **요청을 클릭하여** 전자 메일 메시지에 보고서의 자세한 버전을 수신합니다. 보고서를 받을 날짜 범위와 받는 사람을 지정할 수 있습니다.

보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)
