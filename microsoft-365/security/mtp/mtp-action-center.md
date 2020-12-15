---
title: 자동화된 조사 및 조치 작업을 보고 승인하려면 알림 센터로 이동합니다.
description: 자동화된 검사에 대한 세부 정보를 확인하고 보류 중인 작업을 승인하도록 알림 센터를 사용합니다.
keywords: 알림 센터, 위협 방지, 조사, 경고, 보류 중, 자동, 탐지
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683322"
---
# <a name="the-action-center"></a>알림 센터

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

관리 센터()를 사용하여 조직의 장치 및 사서함에서 현재 및 과거의 조사 결과를 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 볼 수 있습니다. 위협의 유형 및 결과 판정에 [](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) 따라 수정 작업이 자동으로 또는 조직의 보안 운영 팀의 승인에 따라 발생할 수 있습니다. 모든 수정 작업이 승인이 보류 중이든 이미 승인되었든 알림 센터에 통합되어 있습니다. 

![알림 센터 ](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>"단일 창 방식" 환경

알림 센터를 통해 다음과 같은 작업에 대한 "단일 창 방식" 환경을 제공합니다.
- 보류 중인 수정 작업 승인.
- 이미 승인된 수정 작업의 감사 로그 보기. 그리고
- 완료된 수정 작업을 검토

관리 센터는 직장에서 Microsoft 365 Defender에 대한 포괄적인 보기를 제공하기 때문에 보안 운영 팀이 더 효율적이고 효율적으로 운영될 수 있습니다.

## <a name="go-to-the-action-center"></a>알림 센터로 이동합니다.

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **작업 센터** 를 선택합니다. 

3. 작업 센터에는 보류 중인 탭과 기록의 **두 탭이** **표시됩니다.**

    - **보류 중** 탭에는 보안 운영팀의 누군가가 계속 진행하기 위해 검토하고 승인해야 하는 조사가 나열됩니다. 여기에 표시되는 보류 중인 항목을 검토하여 조치를 취해야 합니다.

    - **기록** 탭에는 자동으로 수행된 과거 조사와 수정 작업이 표시됩니다. 지난 일, 주, 월 또는 6개월에 대한 데이터를 볼 수 있습니다.

4. 원하는 열만 표시하려면 **열 사용자 정의** 를 선택합니다.<br/>![Microsoft 365 Defender의 관리 센터](../../media/mtp-action-center.png)

5. 목록에서 항목을 선택하여 조사에 대한 자세한 정보를 확인합니다. 조사 세부 정보 보기가 열립니다.<br/>![조사 세부 정보](../../media/mtp-air-investdetails.png)

    - 조사가 전자 메일 콘텐츠(예: 엔터티가 사서함)와 관련이 있는 경우 조사 세부 정보는 보안 & 준수 센터()에서 [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) 열립니다. 

    - 조사가 장치에 관련된 경우 조사 세부 정보는 보안 센터([https://security.microsoft.com](https://security.microsoft.com))에서 열립니다. 

> [!TIP]
> Microsoft 365 Defender의 자동화된 조사 및 응답 기능으로 누락되거나 잘못 감지된 것으로 생각되면 알려주세요! [Microsoft 365 Defender의 자동화된](mtp-autoir-report-false-positives-negatives.md)조사 및 응답(AIR) 기능에서 가음성/부정을 보고하는 방법을 참조합니다.

## <a name="available-actions"></a>사용 가능한 작업

수정 작업이 수행된 경우 관리 센터의 기록 **탭에** 나열됩니다. 이러한 작업에는 다음이 포함됩니다.

- 조사 패키지 수집 
- 장치 격리(이 작업은 실행을 실행하지 않습니다.) 
- 컴퓨터 오프보드 
- 릴리스 코드 실행 
- 릴리스 
- 요청 샘플 
- 코드 실행 제한(이 작업은 실행을 실행 중지할 수 있습니다.) 
- 바이러스 백신 검사 실행 
- 중지 및 Quarantine 

> [!NOTE]
> 보안 운영 팀은 자동으로 수행되는 수정 작업 외에도 감지된 위협을 해결하기 위한 수동 작업을 수행할 수 있습니다. 자동 및 수동 수정 작업에 대한 자세한 내용은 수정 [작업을 참조하세요.](mtp-remediation-actions.md)

## <a name="action-source"></a>작업 원본

(**NEW!**) 아시다시피 Microsoft 365 Defender는 끝점용 Microsoft Defender 및 [Office 365용 Microsoft](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) [Defender와](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 같은 여러 서비스에서 자동화된 조사 및 응답 기능을 통합합니다. 이제 새로운 관리 센터와 향상된  관리 센터에는 각 수정 작업이 어디에서 시작된 위치를 알려는 작업 원본 열이 포함되어 있습니다. 

다음 표에서는 가능한 **작업 원본 값에 대해** 설명하고 있습니다.

| 작업 원본 값 | 설명 |
|:-----|:---|
| **수동 장치 작업** | 디바이스에서 수행된 수동 작업입니다. [예로는 장치 고리 또는](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) 파일 [Quarantine이 있습니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **수동 전자 메일 작업** | 전자 메일에 대한 수동 작업입니다. 전자 메일 메시지의 소프트 삭제 또는 전자 메일 메시지 [수정을 예로 들 수 있습니다.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **자동화된 장치 작업** | 파일 또는 프로세스와 같은 엔터티에 대한 자동화된 작업입니다. 자동화된 작업의 예로는 파일을 분리하기 위한 파일 보내기, 프로세스 중지, 레지스트리 키 제거가 있습니다. [(끝점에 대한 Microsoft Defender의](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions)수정 작업을 참조합니다.) |
| **자동화된 전자 메일 작업** | 전자 메일 메시지, 첨부 파일 또는 URL과 같은 전자 메일 콘텐츠에 대한 자동화된 작업입니다. 자동화된 작업의 예로는 전자 메일 메시지의 소프트 삭제, URL 차단, 외부 메일 전달 해제가 있습니다. (Office [365용 Microsoft Defender의](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)수정 작업을 참조합니다.) |
| **고급 헌팅 작업** | 고급 헌팅이 있는 장치 또는 전자 [메일에 대해 수행되는 작업입니다.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **탐색기 동작** | 탐색기를 사용하여 전자 메일 콘텐츠에 대해 수행되는 [작업입니다.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) |
| **수동 실시간 응답 작업** | 라이브 응답이 있는 [디바이스에서 수행된 작업입니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 예를 들어 파일 삭제, 프로세스 중지, 예약된 작업 제거가 있습니다. |
| **라이브 응답 작업** | 끝점 API용 [Microsoft Defender를 사용하여 디바이스에서 수행한 작업입니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) 작업의 예로는 장치 차단, 바이러스 백신 검사 실행, 파일에 대한 정보 보기가 있습니다. |

## <a name="required-permissions-for-action-center-tasks"></a>알림 센터 작업에 필요한 사용 권한

알림 센터에서 보류 중인 작업을 승인하거나 거부하려면 다음 표에 나열된 대로 사용 권한이 할당되어 있어야 합니다.

|수정 작업 |필요한 역할 및 사용 권한 할당 |
|--|----|
|끝점 수정용 Microsoft Defender(장치) |Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 보안 관리자 역할<br/>--- 또는 ---<br/>끝점용 Microsoft Defender에 할당된 활성 수정 작업 역할 <br/> <br/> 자세한 내용은 다음 리소스를 참조하세요. <br/>- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [역할 기반 액세스 제어에 대한 역할 만들기 및 관리(끝점용 Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 수정용 Microsoft Defender(Office 콘텐츠 및 전자 메일)  |Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 보안 관리자 역할<br/>--- 및 --- <br/>보안 및 준수 센터가 할당된 & 제거 [https://protection.office.com](https://protection.office.com) 역할( ) <br/><br/>**중요:** 보안 관리자 역할만 보안 & 준수 센터에 할당된 경우 관리 센터 또는 Microsoft 365 Defender 기능에 액세스할 수 없습니다. Azure Active Directory 또는 Microsoft 365 관리 센터에 할당된 보안 관리자 역할이 있어야 합니다. <br/><br/>자세한 내용은 다음 리소스를 참조하세요. <br/>- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [보안 및 준수 & 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Azure Active Directory에서 전역 관리자 역할이 할당된 사용자는 알림 센터에서 대기 중인 모든 작업을 승인하거나 거부할 수 있습니다. 그러나 조직에서 전역 관리자 역할이 할당된 사용자 수를 제한하는 것이 가장 좋습니다. 알림 센터 사용 권한에 대해 위에 나열한 보안 관리자, 활성 수정 작업, 검색 및 제거 역할을 사용하는 것이 좋습니다.

## <a name="next-steps"></a>다음 단계 

- [자동화된 조사 후 보류 중인 작업 승인 또는 거부](mtp-autoir-actions.md)
- [자동화된 조사 결과 보기](mtp-autoir-results.md)

