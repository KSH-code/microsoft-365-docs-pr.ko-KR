---
title: Office 365 Advanced Threat Protection에서 자동화 된 조사 및 응답과 함께 손상 되는 사용자 계정을 해결 합니다.
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호, 손상
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능을 사용 하 여 공격에 노출 된 사용자 계정을 검색 하 고 해결 하는 프로세스를 빠르게 진행 하는 방법을 알아봅니다.
ms.openlocfilehash: e5444b0b628be9acba029829b6fbb275b9c2f554
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280216"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>자동 조사 및 응답을 통해 손상 된 사용자 계정 처리

[Office 365 Advanced Threat Protection 계획 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) 에는 강력한 [자동화 된 조사 및 응답](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) 기능이 포함 되어 있습니다. 이러한 기능을 통해 보안 운영 팀을 보다 많은 시간과 노력으로 위협을 처리할 수 있습니다. Microsoft는 계속 해 서 보안 기능을 개선 합니다. 최근, AIR 기능은 손상 된 사용자 보안 playbook (현재 미리 보기)를 포함 하도록 향상 되었습니다. 이 문서를 읽으면 손상 된 사용자 보안 playbook에 대해 자세히 알아볼 수 있습니다. 그리고 추가 세부 정보를 확인 하 고 [사용자 손상 및 제한 위반 범위에 응답 하 고 Office 365 ATP를 통해 침해](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 를 처리 하는 시간을 빠르게 확인할 수 있습니다.

![손상 된 사용자에 대 한 자동화 된 조사](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

손상 된 사용자 보안 playbook을 통해 조직의 보안 팀에서 다음을 수행할 수 있습니다.

- 손상 된 사용자 계정 감지 속도 향상

- 계정이 손상 되는 경우 위반 범위를 제한 합니다. 한 

- 손상 된 사용자에 게 보다 효율적이 고 효율적으로 응답 합니다.

## <a name="compromised-user-alerts"></a>손상 된 사용자 알림

사용자 계정이 손상 되 면 이례적인 또는 비정상 동작이 발생 합니다. 예를 들어 피싱 및 스팸 메시지는 신뢰할 수 있는 사용자 계정에서 내부적으로 전송 될 수 있습니다. Office 365 Advanced Threat Protection은 전자 메일 패턴 및 Office 365 내의 공동 작업 활동에서 이러한 예외를 검색할 수 있습니다. 이 경우 알림이 트리거되고 위협 완화 프로세스가 시작 됩니다.

예를 들어 의심 스러운 전자 메일 보내기로 인해 트리거된 경고는 다음과 같습니다.

![의심 스러운 전자 메일 보내기로 인해 트리거되는 알림](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

다음은 사용자에 대 한 전송 제한에 도달 했을 때 트리거되는 경고의 예입니다.

![전송 제한에 도달 하 여 트리거된 경고](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>손상 된 사용자 조사 및 응답

사용자 계정이 손상 되 면 경고가 트리거됩니다. 또한 조직의 보안 운영 팀에서 문제를 해결할 때까지 해당 사용자 계정이 차단 되 고 더 이상 전자 메일 메시지를 보내지 못할 수도 있습니다. 다른 경우에는 보안 팀에서 권장 하는 작업을 수행할 수 있는 자동화 된 조사가 시작 됩니다.

- [제한 된 사용자 보기 및 조사](#view-and-investigate-restricted-users)

- [자동화 된 조사에 대 한 세부 정보 보기](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 다음 작업을 수행 하려면 적절 한 사용 권한이 있어야 합니다. [AIR 기능을 사용 하려면 필수 권한을](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)참조 하세요.

### <a name="view-and-investigate-restricted-users"></a>제한 된 사용자 보기 및 조사

제한 된 사용자 목록으로 이동 하기 위한 몇 가지 옵션을 사용할 수 있습니다. 예를 들어 Office 365 보안 & 준수 센터에서는 **위협 관리** > **검토** > **제한 된 사용자**로 이동할 수 있습니다. 다음 절차에서는 **알림** 대시보드를 사용 하 여 탐색에 대해 설명 하므로 트리거된 것일 수 있는 다양 한 종류의 경고를 확인 하는 데 유용 합니다.

1. [https://protection.office.com](https://protection.office.com)으로 이동하여 로그인합니다.

2. 탐색 창에서 **경고** > **대시보드**를 선택 합니다.

3. **다른 경고** 위젯에 **제한 된 사용자**를 선택 합니다.<br/>
   ![기타 알림 위젯](/microsoft-365/media/office365atp-otheralertswidget.jpg)<br/>
   이렇게 하면 제한 된 사용자 목록이 열립니다.<br/>![Office 365의 제한 된 사용자](/microsoft-365/media/office365atp-restrictedusers.jpg) 

4. 목록에서 사용자 계정을 선택 하 여 세부 정보를 확인 하 고 [제한 된 사용자 해제](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam)와 같은 작업을 수행 합니다. 

### <a name="view-details-about-automated-investigations"></a>자동화 된 조사에 대 한 세부 정보 보기

자동 조사가 시작 되 면 Office 365 보안 & 준수 센터에서 해당 세부 정보와 결과를 볼 수 있습니다. **위협 관리** > **조사**로 이동한 다음 조사를 선택 하 여 세부 정보를 확인 합니다.

자세한 내용은 [조사의 세부 정보 보기](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results)를 참조 하세요.

## <a name="keep-the-following-points-in-mind"></a>다음 사항에 유의 하세요.

- **알림 맨 위에 유지**합니다. 알고 있는 것 처럼 더 긴 손상이 감지 되지 않으면 조직, 고객 및 파트너에 게 광범위 하 게 영향을 줄 수 있고 비용이 더 커집니다. 위협을 완화 하려면 조기 검색 및 적시 응답이 중요 하며, 특히 사용자의 계정이 손상 되는 경우에는 그렇습니다. 

- **자동화는 보안 운영 팀을 지원 하지만 대체 하지는 않습니다**. 자동화 된 조사 및 응답 기능은 공격에 참여 한 사용자를 일찍 검색할 수 있지만, 보안 운영 팀에서 이러한 문제를 해결 하 고 몇 가지 조사 및 관리를 수행 해야 할 수도 있습니다. 이에 대 한 도움이 필요 하세요? [작업 검토 및 승인를](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions)참조 하세요.

- **의심 스러운 로그인 알림을 유일한 지표로 사용 하지 마십시오**. 사용자 계정이 손상 되 면 의심 스러운 로그인 경고가 발생 하거나 트리거되지 않을 수 있습니다. 때로는 경고가 발생 한 계정이 손상 된 후에 발생 하는 일련의 작업입니다. 경고에 대 한 자세한 정보를 보 시겠습니까? [경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)참조 하세요.

## <a name="next-steps"></a>다음 단계

- [필요한 사용 권한을 검토 하 여 AIR 기능 사용](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Office 365에서 악성 전자 메일 찾기 및 조사](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Microsoft Defender ATP의 AIR에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 로드맵를 방문 하 여 곧 제공 되는 항목을 확인 하 고 롤아웃](https://www.microsoft.com/microsoft-365/roadmap?filters=)

