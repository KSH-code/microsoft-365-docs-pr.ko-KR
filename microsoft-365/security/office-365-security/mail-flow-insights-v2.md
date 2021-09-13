---
title: 메일 흐름 대시보드의 메일 흐름 인사이트
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 사용할 수 있는 인사이트 및 & 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6c960b34933c6a90dcf4a1675ced63dd43f00c07
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211675"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>보안 및 준수 센터의 메일 흐름 파악

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

관리자는 보안 및 준수 & 메일 흐름 대시보드를 사용하여 추세, 통찰력을 검색하고 조직의 메일 흐름과 관련된 문제를 해결하기 위한 조치를 취할 수 있습니다.

![보안 및 준수 센터의 메일 & 대시보드입니다.](../../media/mail-flow-dashboard-v2.png)

사용 가능한 인사이트는 다음을 제공합니다.

- [자동 전달 메시지 인사이트](mfi-auto-forwarded-messages-report.md)

- [가능한 메일 루프 인사이트](mfi-mail-loop-insight.md)<sup>1 수정</sup>

- [느린 메일 흐름 규칙 인사이트](mfi-slow-mail-flow-rules-insight.md)<sup>1 수정</sup>

- [메일 흐름 지도](mfi-mail-flow-map-report.md)

- [새 도메인이 전달되는](mfi-new-domains-being-forwarded-email.md)전자 메일 인사이트<sup>2</sup>

- [새 사용자 전달 전자 메일 인사이트](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [비허용 도메인 보고서](mfi-non-accepted-domain-report.md)

- [미실행 보고서](mfi-non-delivery-report.md)

- [아웃바운드 및 인바운드 메일 흐름 인사이트](mfi-outbound-and-inbound-mail-flow.md)

- [대기열 인사이트](mfi-queue-alerts-and-queues.md)

- [SMTP 인증 클라이언트 인사이트 및 보고](mfi-smtp-auth-clients-report.md)

- [최상위 도메인 메일 흐름 상태 정보](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> 이 인사이트는 문제가 감지된 후에만 메일 흐름 대시보드의 권장 영역에 표시됩니다.  그렇지 않으면 볼 수 없습니다.

<sup>2</sup> 이 인사이트는 메일 흐름 대시보드에 표시되지 않지만 [](view-mail-flow-reports.md#forwarding-report) 문제가 감지된 후 전달 보고서 페이지에 표시됩니다. 그렇지 않으면 볼 수 없습니다.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 보는 데 필요한 사용 권한

메일 흐름 대시보드는 다음 역할 그룹의 구성원이 사용할 수 있습니다.

- **보안 및** 준수 센터의 & 관리(전역 관리자).

- **[Exchange 관리자](/azure/active-directory/roles/permissions-reference#exchange-administrator)** Azure Active Directory.

- **보안 및 준수** 센터의 메일 흐름 &. 계정이 조직 관리 또는 관리자 역할 Exchange 구성원이 아닌 경우 다음 문제를 고려하세요.
  - 사용자는 에서 직접 보안 및 & 로그인해야 <https://protection.office.com> 합니다.
  - 사용자에게 메일 흐름 대시보드에 대한 읽기 전용 권한만 있습니다.
  - 사용자는 사용자에게 액세스 권한이 Microsoft 365 관리 센터.

사용 권한에 대한 자세한 내용은 [Security & Compliance Center의](permissions-in-the-security-and-compliance-center.md) 사용 권한 및 사용자에게 보안 및 준수 센터에 대한 액세스 [& 참조하세요.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 찾을 수 있는 위치

에서 보안 & 준수 센터를 열고 메일 흐름을 <https://protection.office.com> **확장한** 다음 대시보드 를 **선택합니다.**

메일 흐름 대시보드로 직접 이동하기 위해 를 를 <https://protection.office.com/mailflow/dashboard> 습니다.