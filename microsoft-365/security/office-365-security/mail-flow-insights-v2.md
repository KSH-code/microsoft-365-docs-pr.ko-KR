---
title: 메일 흐름 대시보드의 메일 흐름 정보
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 제공 되는 정보 및 보고에 대해 알아볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9ac8b8b0d346d78af252a9e427d0ef2b1a4c4ea
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769021"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>보안 및 준수 센터의 메일 흐름 파악

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


관리자는 보안 & 준수 센터에서 메일 흐름 대시보드를 사용 하 여 경향 및 통찰력을 검색 하 고 조직의 메일 흐름과 관련 된 문제를 해결 하는 조치를 취할 수 있습니다.

![보안 & 준수 센터의 메일 흐름 대시보드](../../media/mail-flow-dashboard-v2.png)

사용할 수 있는 정보는 다음과 같습니다.

- [자동 전달 메시지 인사이트](mfi-auto-forwarded-messages-report.md)

- [가능한 메일 루프 통찰력](mfi-mail-loop-insight.md)<sup>1</sup> 수정

- [느린 메일 흐름 규칙 통찰력](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup> 수정

- [메일 흐름 지도](mfi-mail-flow-map-report.md)

- [전달 되는 새 도메인 전자 메일 통찰력](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [전자 메일 통찰력](mfi-new-users-forwarding-email.md)<sup>2</sup> 를 전달 하는 새 사용자

- [비허용 도메인 보고서](mfi-non-accepted-domain-report.md)

- [미실행 보고서](mfi-non-delivery-report.md)

- [아웃바운드 및 인바운드 메일 흐름 인사이트](mfi-outbound-and-inbound-mail-flow.md)

- [대기열 인사이트](mfi-queue-alerts-and-queues.md)

- [SMTP 인증 클라이언트 인사이트 및 보고](mfi-smtp-auth-clients-report.md)

- [최상위 도메인 메일 흐름 상태 정보](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> 이 통찰력은 문제가 검색 된 후에만 메일 흐름 대시보드의 **권장** 되는 영역에 표시 됩니다. 그렇지 않으면 표시 되지 않습니다.

<sup>2</sup> 이 통찰력은 메일 흐름 대시보드에는 표시 되지 않지만, 문제가 검색 된 후에는 [전달 보고서](view-mail-flow-reports.md#forwarding-report) 페이지에 표시 됩니다. 그렇지 않으면 표시 되지 않습니다.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 보는 데 필요한 사용 권한

메일 흐름 대시보드는 다음 역할 그룹의 구성원이 사용할 수 있습니다.

- Security & 준수 센터의 **조직 관리** (전역 관리자)

- Azure Active Directory의 **[Exchange 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)**

- **메일 흐름 Administrator** Security & 준수 센터:이 역할 그룹의 구성원이 전역 관리자 또는 Exchange 관리자 역할 그룹의 구성원이 아닌 경우에는 다음과 같은 문제점과 요구 사항을 확인 합니다.

  - 사용자는에서 직접 보안 & 준수 센터에 로그인 해야 합니다 <https://protection.office.com> .
  - 사용자에 게는 메일 흐름 대시보드에 대 한 읽기 전용 권한만 있습니다.
  - 사용자에 게 Microsoft 365 관리 센터에 액세스할 수 있는 권한이 없습니다.

보안 & 준수 센터의 사용 권한에 대 한 자세한 내용은 [security & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md) 참조 하 고 [사용자에 게 보안 & 준수 센터에](grant-access-to-the-security-and-compliance-center.md)대 한 액세스 권한을 부여 합니다.

## <a name="where-to-find-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 찾는 위치

보안 & 준수 센터 <https://protection.office.com> ,에서 **메일 흐름** 을 차례로 확장 하 고 **대시보드** 를 선택 합니다.

메일 흐름 대시보드로 직접 이동 하려면을 엽니다 <https://protection.office.com/mailflow/dashboard> .
