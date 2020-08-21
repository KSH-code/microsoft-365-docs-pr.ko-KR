---
title: 메일 흐름 대시보드의 SMTP 인증 클라이언트 정보 및 보고
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 SMTP 인증 인사이트를 사용하고 보고서에 대해 SMTP AUTH(인증된 SMTP)를 사용하여 전자 메일 메시지를 보내는 조직의 전자 메일 보낸 사람을 모니터링하는 방법을 알아보세요.
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826872"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>보안 장치 준수 센터에서 SMTP & 보고

메일 **흐름 대시보드 및** 관련 SMTP [Mail flow dashboard](mail-flow-insights-v2.md) 인증 클라이언트 보고서는 [조직의](#smtp-auth-clients-report) 사용자 또는 시스템 계정별 SMTP AUTH 클라이언트 전송 프로토콜 사용을 강조합니다. smtp.office365.com 끝점을 사용하는 이 레거시 프로토콜은 기본 인증만 제공하며, 해커뮤니티에서 전자 메일을 보내는 데 사용된다는 의심이 있습니다. 인사이트 및 보고서를 통해 SMTP AUTH 전자 메일 전송에 대한 비정상적 활동을 확인할 수 있습니다. 또한 SMTP AUTH를 사용하는 클라이언트 또는 장치에 대한 TLS 사용 현황 데이터도 표시합니다.

위록은 지난 7일 동안 SMTP Auth 프로토콜을 사용한 사용자 또는 서비스 계정의 수를 나타냅니다.

![준수 센터의 보안 흐름 대시보드에서 SMTP & 위산](../../media/mfi-smtp-auth-clients-report-widget.png)

위쪽에서 메시지 수를 클릭하면 SMTP Auth **클라이언트 플라이아웃이** 표시됩니다. 플라이아웃에서는 지난 한 주 동안의 TLS 사용량 및 볼륨을 집계적으로 보여 줍니다.

![메일 흐름 대시보드에서 SMTP 인증 클라이언트 위산을 클릭한 후의 세부 정보 플라이아웃](../../media/mfi-smtp-auth-clients-report-details.png)

다음 섹션에 **설명된 바와 같이 SMTP** 인증 클라이언트 보고서 링크를 클릭하여 SMTP 인증 클라이언트 보고서로 이동합니다.

## <a name="smtp-auth-clients-report"></a>SMTP 인증 클라이언트 보고서

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP 인증 클라이언트 보고서 보고서 보기

기본적으로 보고서는 지난 7일간의 데이터를 표시하지만 지난 90일 동안 데이터를 사용할 수 있습니다.

개요 섹션에는 다음 차트가 포함됩니다.

- **데이터 보기: 보내는 사람:** 기본적으로 차트는 모든 도메인에서 보낸 SMTP Auth 클라이언트**Show data for: All sender domains** 메시지 수를 표시합니다(기본적으로 모든 보낸 사람 도메인이 선택됨). 특정 보낸 사람 도메인에 대한 표시 **Show data for** 데이터를 클릭하고 드롭다운 목록에서 보낸 사람 도메인을 선택하여 결과를 특정 보낸 사람 도메인으로 필터링할 수 있습니다. 특정 데이터 요소(일)를 가리치면 메시지 수가 표시됩니다.

  ![보안 및 준수 센터의 SMTP 인증 클라이언트 & 보내기](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **데이터 보기: TLS 사용**: 이 차트는 선택한 기간 동안 모든 SMTP 인증 클라이언트 메시지에 대한 TLS 사용 비율을 표시합니다. 이 차트를 통해 아직 이전 버전의 TLS를 사용하는 사용자 및 시스템 계정에 대해 확인하고 작업을 수행할 수 있습니다.

  ![준수 센터의 보안 서비스 테이블에 있는 SMTP Auth 클라이언트의 TLS 사용 &](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

요청 **보고서를 클릭하여** 자세한 버전의 보고서를 전자 메일 메시지로 받습니다. 날짜 범위 및 보고서를 받을 받는 사람을 지정할 수 있습니다.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP 인증 클라이언트 보고서의 세부 정보 표 보기

세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.

- **데이터 가져오기: 전송:** 테이블에 다음 정보가 표시됩니다.

  - **보낸 사람 주소**
  - **메시지 수**

  행을 선택하면 동일한 세부 정보가 플라이아웃에 표시됩니다.

- **데이터 보기: TLS 사용 현황:** 표에는 다음정보가 나와 있습니다.

  - **보낸 사람 주소**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **메시지 수**

  <sup>\*</sup> 이 열에는 보낸 사람이 보낸 메시지의 백분율과 개수가 모두 표시됩니다.

세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

행을 선택하는 경우 다음과 유사한 세부 정보가 플라이아웃에 표시됩니다.

![SMTP 인증 클라이언트 보고서의 TLS 사용 현황 보기에 대한 세부 정보 표에서 가기 플라이아웃](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

요청 **보고서를 클릭하여** 자세한 버전의 보고서를 전자 메일 메시지로 받습니다. 날짜 범위 및 보고서를 받을 받는 사람을 지정할 수 있습니다.

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)
