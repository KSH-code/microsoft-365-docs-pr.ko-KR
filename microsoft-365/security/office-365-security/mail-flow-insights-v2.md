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
description: 관리자는 준수 센터의 보안 흐름 대시보드에서 사용할 수 있는 정보 및 보고서에 대해 & & 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e9449553d008bc383ae6f2b6098f9598cad43c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826568"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>보안 및 준수 센터의 메일 흐름 파악

관리자는 보안 & 준수 센터의 메일 흐름 대시보드를 사용하여 추세, 인사이트를 검색하고 조직의 메일 흐름과 관련된 문제를 해결하기 위한 조치를 수행할 수 있습니다.

![보안 및 준수 센터의 & 메일 흐름 대시보드](../../media/mail-flow-dashboard-v2.png)

사용 가능한 인사이트는 다음과 같습니다.

- [자동 전달 메시지 인사이트](mfi-auto-forwarded-messages-report.md)

- [가능한 메일 루프 정보 1](mfi-mail-loop-insight.md)<sup>수정</sup>

- [느린 메일 흐름 규칙 정보 1](mfi-slow-mail-flow-rules-insight.md)<sup>해결</sup>

- [메일 흐름 지도](mfi-mail-flow-map-report.md)

- [전달되는 전자 메일 정보 2의 새](mfi-new-domains-being-forwarded-email.md)<sup>도메인</sup>

- [전자 메일 인사이트를 전달하는 새](mfi-new-users-forwarding-email.md)<sup>사용자</sup>

- [비허용 도메인 보고서](mfi-non-accepted-domain-report.md)

- [미실행 보고서](mfi-non-delivery-report.md)

- [아웃바운드 및 인바운드 메일 흐름 인사이트](mfi-outbound-and-inbound-mail-flow.md)

- [대기열 인사이트](mfi-queue-alerts-and-queues.md)

- [SMTP 인증 클라이언트 인사이트 및 보고](mfi-smtp-auth-clients-report.md)

- [최상위 도메인 메일 흐름 상태 정보](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> This insight는 **문제가 감지된** 후에만 메일 흐름 대시보드의 권장 사항에 표시됩니다. 그렇지 않으면 표시되지 않습니다.

<sup>2</sup> This insight는 메일 흐름 대시보드에는 나타나지 [Forwarding report](view-mail-flow-reports.md#forwarding-report) 않지만 문제가 검색된 후에 전달 보고서 페이지에는 표시됩니다. 그렇지 않으면 표시되지 않습니다.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 보는 데 필요한 사용 권한

메일 흐름 대시보드는 다음 경로 그룹의 구성원이 사용할 수 있습니다.

- **보안 설정** 준수 센터의 & 조직 관리(전역 관리자)

- Azure **[AD의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** Exchange 관리자

- 보안 설정 준수 **센터의 메일** 흐름 &: 이 역할 그룹의 구성원이 전역 관리자 또는 Exchange 관리자 역할 그룹의 구성원이 아다면 다음과 같은 문제 및 요구 사항에 주의해야 합니다.

  - 사용자가 준수 센터에 & 다음에 직접 로그인해야 <https://protection.office.com> 합니다.
  - 사용자에게는 메일 흐름 대시보드에 대한 읽기 전용 권한만 부여됩니다.
  - 사용자에게 Microsoft 365 관리 센터 액세스할 수 없습니다.

보안 장치 규정 준수 센터의 사용 권한에 대한 & 보안 센터의 사용 [권한에 대한 자세한 내용은 보안 & 규정](permissions-in-the-security-and-compliance-center.md) 준수 센터의 사용 권한을 참조하고 사용자에게 보안 설정 준수 [센터에 대한 액세스 권한을 & 있습니다.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>메일 흐름 대시보드를 찾을 수 있는 위치

보안 그룹 & 센터를 연 <https://protection.office.com> 다음 메일 **흐름을 확장한**후 대시보드를 **선택합니다.**

메일 흐름 대시보드로 직접 이동하려면 . <https://protection.office.com/mailflow/dashboard>
