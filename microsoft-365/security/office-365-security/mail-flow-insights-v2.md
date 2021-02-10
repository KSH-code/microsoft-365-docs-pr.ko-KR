---
title: 메일 흐름 대시보드의 메일 흐름 정보
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
ms.openlocfilehash: b65e235e3446fa62bca1c9f8aef73f2387b1140b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167098"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>보안 및 준수 센터의 메일 흐름 파악

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

관리자는 보안 및 준수 센터의 메일 흐름 대시보드를 & 추세, 인사이트를 검색하고 조직의 메일 흐름과 관련된 문제를 해결하기 위한 조치를 취할 수 있습니다.

![보안 및 준수 센터의 & 흐름 대시보드](../../media/mail-flow-dashboard-v2.png)

사용 가능한 인사이트는 다음을 제공합니다.

- [자동 전달 메시지 인사이트](mfi-auto-forwarded-messages-report.md)

- [가능한 메일 루프 인사이트](mfi-mail-loop-insight.md)<sup>1 수정</sup>

- [느린 메일 흐름 규칙 정보](mfi-slow-mail-flow-rules-insight.md)<sup>1 수정</sup>

- [메일 흐름 지도](mfi-mail-flow-map-report.md)

- [새 도메인이 전달되는 전자 메일 정보](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [새 사용자 전달 전자 메일 정보](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [비허용 도메인 보고서](mfi-non-accepted-domain-report.md)

- [미실행 보고서](mfi-non-delivery-report.md)

- [아웃바운드 및 인바운드 메일 흐름 인사이트](mfi-outbound-and-inbound-mail-flow.md)

- [대기열 인사이트](mfi-queue-alerts-and-queues.md)

- [SMTP 인증 클라이언트 인사이트 및 보고](mfi-smtp-auth-clients-report.md)

- [최상위 도메인 메일 흐름 상태 정보](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> 이 인사이트는 문제가 검색된 후에만 메일 흐름 대시보드의 권장 영역에 표시됩니다.  그렇지 않으면 볼 수 없습니다.

<sup>2</sup> 이 인사이트는 메일 흐름 대시보드에 표시되지 않지만 [](view-mail-flow-reports.md#forwarding-report) 문제가 검색된 후 전달 보고서 페이지에 표시됩니다. 그렇지 않으면 볼 수 없습니다.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 보는 데 필요한 사용 권한

메일 흐름 대시보드는 다음 역할 그룹의 구성원이 사용할 수 있습니다.

- **보안 및** 준수 &(전역 관리자)의 조직 관리

- **[Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** Active Directory의 Exchange 관리자

- **보안 및** 준수 센터의 메일 &. 계정이 조직 관리 또는 Exchange 관리자 역할 그룹의 구성원이 아닌 경우 다음 문제를 고려하십시오.
  - 사용자는 에서 직접 보안 & 준수 센터에 로그인해야 <https://protection.office.com> 합니다.
  - 사용자에게 메일 흐름 대시보드에 대한 읽기 전용 권한만 있습니다.
  - 사용자는 Microsoft 365 관리 센터에 액세스할 수 없습니다.

사용 권한에 대한 자세한 내용은 Security & Compliance [Center의](permissions-in-the-security-and-compliance-center.md) 사용 권한을 참조하고 사용자에게 보안 및 준수 센터에 [대한 액세스 & 참조하세요.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 찾을 수 있는 위치

보안 및 & 센터를 열고 메일 흐름을 확장한 다음 <https://protection.office.com> 대시보드를 **선택합니다.** 

메일 흐름 대시보드로 직접 이동하기 위해 를 <https://protection.office.com/mailflow/dashboard> 열습니다.
