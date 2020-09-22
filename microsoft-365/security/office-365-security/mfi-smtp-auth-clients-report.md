---
title: SMTP 인증 클라이언트의 메일 흐름 대시보드 이해 및 보고
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 SMTP 인증 통찰력 및 보고서를 사용 하 여 인증 된 SMTP (SMTP 인증)를 사용 하는 조직의 전자 메일 보낸 사람을 모니터링 하 여 전자 메일 메시지를 보내는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 7ca673e5ecc92c28996a976c26a38ae570f16203
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199244"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>SMTP 인증 클라이언트에서 보안 & 준수 센터의 통찰력 및 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드](mail-flow-insights-v2.md) 및 연결 된 [smtp 인증 클라이언트 보고서](#smtp-auth-clients-report) 에 있는 **smtp 인증 클라이언트** 는 조직의 사용자 또는 시스템 계정에의 한 smtp 인증 클라이언트 전송 프로토콜 사용을 강조 합니다. 끝점 smtp.office365.com를 사용 하는이 레거시 프로토콜은 기본 인증만 제공 하며 손상 된 계정에서 전자 메일을 보내기 위해 사용 하는 것이 취약 합니다. 통찰력 및 보고서를 사용 하면 SMTP 인증 전자 메일 전송에 대 한 비정상적인 활동을 확인할 수 있습니다. 또한 SMTP 인증을 사용 하는 클라이언트나 장치에 대 한 TLS 사용 현황 데이터를 보여줍니다.

위젯은 지난 7 일 이내에 SMTP 인증 프로토콜을 사용한 사용자 또는 서비스 계정 수를 나타냅니다.

![보안 & 준수 센터의 메일 흐름 대시보드에 있는 SMTP 인증 클라이언트 위젯](../../media/mfi-smtp-auth-clients-report-widget.png)

위젯의 메시지 수를 클릭 하면 **SMTP 인증 클라이언트** 플라이 아웃이 나타납니다. 플라이 아웃은 지난 주에 대 한 TLS 사용 및 볼륨의 집계 된 보기를 제공 합니다.

![메일 흐름 대시보드에서 SMTP 인증 클라이언트 위젯을 클릭 한 후의 세부 정보 플라이 아웃](../../media/mfi-smtp-auth-clients-report-details.png)

**Smtp 인증 클라이언트 보고서** 링크를 클릭 하 여 다음 섹션에 설명 된 대로 smtp 인증 클라이언트 보고서로 이동할 수 있습니다.

## <a name="smtp-auth-clients-report"></a>SMTP 인증 클라이언트 보고서

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP 인증 클라이언트 보고서에 대 한 보고서 보기

기본적으로 보고서에는 최근 7 일 동안의 데이터가 표시 되지만 최근 90 일 동안 데이터를 사용할 수 있습니다.

Overview (개요) 섹션에는 다음 차트가 포함 됩니다.

- **데이터 보기 기준: 보내는 볼륨**: 기본적으로 차트에는 모든 도메인에서 전송 된 SMTP 인증 클라이언트 메시지의 수가 표시 됩니다 (기본적으로**모든 보낸 사람 도메인** 을 선택 합니다. 드롭다운 목록에서 **데이터 표시** 를 클릭 하 고 보낸 사람 도메인을 선택 하 여 결과를 특정 보낸 사람 도메인으로 필터링 할 수 있습니다. 특정 데이터 요소 (일)를 가리키면 메시지 수가 표시 됩니다.

  ![보안 & 준수 센터의 SMTP 인증 클라이언트 보고서에서 보내는 볼륨 보기](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **데이터 보기 기준: TLS 사용**: 차트에는 선택한 기간 동안 모든 SMTP 인증 클라이언트 메시지의 TLS 사용 백분율이 표시 됩니다. 이 차트에서는 이전 버전의 TLS를 계속 사용 하는 사용자 및 시스템 계정을 식별 하 고 작업을 수행할 수 있습니다.

  ![보안 & 준수 센터의 SMTP 인증 클라이언트 보고서의 TLS 사용 보기](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

자세한 보고서 버전을 전자 메일 메시지로 받으려면 **요청 보고서** 를 클릭 합니다. 보고서를 받을 날짜 범위 및 받는 사람을 지정할 수 있습니다.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP 인증 클라이언트 보고서에 대 한 세부 정보 테이블 보기

**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.

- **데이터 보기 기준: 보내는 볼륨**: 다음 정보가 테이블에 표시 됩니다.

  - **보낸 사람 주소**
  - **메시지 수**

  행을 선택 하면 같은 세부 정보가 플라이 아웃에 표시 됩니다.

- **데이터 보기 기준: TLS 사용**: 테이블에 다음 정보가 표시 됩니다.

  - **보낸 사람 주소**
  - **TLS 1.0%**<sup>\*</sup>
  - **TLS 1.1%**<sup>\*</sup>
  - **TLS 1.2%**<sup>\*</sup>
  - **메시지 수**

  <sup>\*</sup> 이 열에는 보낸 사람의 메시지 비율과 수와 개수가 모두 표시 됩니다.

세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

행을 선택 하는 경우 플라이 아웃에 다음과 유사한 세부 정보가 표시 됩니다.

![SMTP 인증 클라이언트 보고서의 TLS 사용 보기 세부 정보 테이블에서 정보 플라이 아웃](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

자세한 보고서 버전을 전자 메일 메시지로 받으려면 **요청 보고서** 를 클릭 합니다. 보고서를 받을 날짜 범위 및 받는 사람을 지정할 수 있습니다.

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.
