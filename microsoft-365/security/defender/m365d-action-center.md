---
title: 자동화된 조사 및 조치 작업을 보고 승인하려면 알림 센터로 이동합니다.
description: 관리 센터를 사용하여 자동화된 조사에 대한 세부 정보를 보고 보류 중인 작업 승인
keywords: 알림 센터, 위협 방지, 조사, 경고, 보류 중인, 자동화된, 감지
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: a0f705fd63f8a613a48f86efcdcef37059037caf
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914359"
---
# <a name="the-action-center"></a>알림 센터

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

알림 센터는 인시던트 및 경고 작업에 대해 "단일 창 창" 환경을 제공합니다.

- 보류 중인 수정 작업 승인
- 이미 승인된 수정 작업의 감사 로그 보기
- 완료된 수정 작업을 검토

관리 센터는 직장에서 작업하는 Microsoft 365 Defender 보기를 제공하기 때문에 보안 운영 팀이 보다 효율적이고 효율적으로 작업할 수 있습니다.

## <a name="the-unified-action-center"></a>통합된 동작 센터

통합 알림 센터()에는 장치에 대한 보류 중 및 완료된 수정 작업, 전자 메일 & 공동 작업 콘텐츠 및 ID가 한 위치에 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 나열됩니다.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="통합된 포털의 Microsoft 365 Defender 센터입니다." lightbox="../../media/m3d-action-center-unified.png":::

예시: 

- 이전에 Office 365 보안 & 준수 센터()를 사용 중이면 Microsoft 365 Defender [https://protection.office.com](https://protection.office.com) 포털()에서 통합 Microsoft 365 Defender [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 시도합니다.
- Microsoft Defender 보안 센터()에서 작업 센터를 사용하는 경우 Microsoft 365 Defender [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) 포털()에서 통합 Microsoft 365 Defender [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 시도합니다.
- 이미 Microsoft 365 Defender 포털()을 사용 중이면 작업 센터()에서 몇 가지 개선된 기능을 [https://security.microsoft.com](https://security.microsoft.com) 볼 수 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 있습니다.

통합 관리 센터는 Endpoint용 Defender 및 2016용 Defender에 대한 수정 Office 365. 모든 수정 작업에 대한 공통 언어를 정의하고 통합 조사 환경을 제공합니다. 보안 운영 팀에는 수정 작업을 보고 관리할 수 있는 "단일 창 창" 환경이 있습니다.  

적절한 사용 권한 및 다음 구독 중 하나 이상이 있는 경우 통합 관리 센터를 사용할 수 있습니다.

- [엔드포인트용 Defender](../defender-endpoint/microsoft-defender-endpoint.md)
- [Office 365용 Defender](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> 자세한 내용은 요구 사항을 [참조하세요.](./prerequisites.md)

## <a name="using-the-action-center"></a>동작 센터 사용

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 
2. 탐색 창에서 **작업 센터** 를 선택합니다. 

작업 센터를 방문하면 보류 중인 작업 및 **기록의 두 개의 탭이** **표시됩니다.** 다음 표에서는 각 탭에 표시하는 내용을 요약하여 제공합니다.

|Tab  |설명  |
|---------|---------|
|**보류 중**     | 주의가 필요한 작업 목록을 표시합니다. 작업을 한 번씩 승인하거나 거부하거나 동일한 유형의 작업(예: 파일 Quarantine file)이 있는 경우 여러 작업을 선택할 수 있습니다. <p>**팁:** 자동화된 조사가 제시간에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 검토하고 승인(또는 거부)해야 합니다.       |
|**기록**     | 다음을 수행한 작업에 대한 감사 로그 역할을 합니다. <br/>- 자동화된 조사의 결과로 수행된 수정 작업 <br/>- 의심스러우거나 악의적인 전자 메일 메시지, 파일 또는 URL에 대해 수행된 수정 작업<br/>- 보안 운영 팀에서 승인한 수정 작업 <br/>- 실행된 명령 및 라이브 응답 세션 중에 적용된 수정 작업<br/>- 바이러스 백신 보호에 의해 수행된 수정 작업 <p>특정 작업을 취소하는 방법을 제공합니다(완료된 작업 취소 [참조).](m365d-autoir-actions.md#undo-completed-actions)        |

관리 센터에서 데이터를 사용자 지정, 정렬, 필터링 및 내보낼 수 있습니다.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="관리 센터의 기능을 정렬, 필터링 및 사용자 지정합니다." lightbox="../../media/m3d-action-center-columnsfilters.png":::

- 열 제목을 선택하여 항목을 오차 또는 내선 순서로 정렬합니다.
- 기간 필터를 사용하여 지난 일, 주, 30일 또는 6개월의 데이터를 볼 수 있습니다.
- 보하려는 열을 선택 합니다.
- 각 데이터 페이지에 포함할 항목 수를 지정합니다.
- 필터를 사용하여 보 원하는 항목만 볼 수 있습니다.
- 내보내기 **를** 선택하여 결과를 파일로 .csv 선택합니다.

## <a name="actions-tracked-in-the-action-center"></a>동작 센터에서 추적된 작업

승인 보류 중이든 이미 수행되었든 관계없이 모든 작업은 알림 센터에서 추적됩니다. 사용 가능한 작업은 다음과 같습니다.

- 조사 패키지 수집 
- 장치 격리(이 작업은 실행을 실행하지 않습니다.) 
- 컴퓨터 등록 취소 
- 릴리스 코드 실행 
- 격리에서 해제 
- 샘플 요청 
- 코드 실행 제한(이 작업을 실행 중지할 수 있습니다. 
- 바이러스 백신 검사 실행 
- 중지 및 격리 

자동화된 조사의 결과로 자동으로 수행되는 수정 [](m365d-autoir.md)작업 외에도, 보안 팀이 감지된 위협을 해결하기 위해 수행한 작업과 보안 센터에서 위협 방지 기능의 결과로 수행된 작업을 Microsoft 365 Defender. 자동 및 수동 수정 작업에 대한 자세한 내용은 수정 [작업 을 참조하세요.](m365d-remediation-actions.md)

## <a name="viewing-action-source-details"></a>작업 원본 세부 정보 보기

(**NEW!**) 개선된 작업 센터에는  이제 각 작업이 시작된 위치를 알려하는 작업 원본 열이 포함되어 있습니다. 다음 표에서는 가능한 작업 **원본 값에 대해** 설명하고 있습니다.

| 작업 원본 값 | 설명 |
|:-----|:---|
| **수동 장치 작업** | 디바이스에서 수행된 수동 작업입니다. [예로는 장치 고리 또는](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) 파일 검지가 [있습니다.](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files) |
| **수동 전자 메일 작업** | 전자 메일에 대한 수동 작업입니다. 예를 들어 전자 메일 메시지를 소프트 삭제하거나 전자 메일 [메시지를 수정합니다.](../office-365-security/remediate-malicious-email-delivered-office-365.md) |
| **자동화된 장치 작업** | 파일 또는 프로세스와 같은 엔터티에 대한 자동화된 작업입니다. 자동화된 작업의 예로는 파일을 검지로 보내기, 프로세스 중지, 레지스트리 키 제거가 있습니다. [(Endpoint에 대한 Microsoft Defender의 수정 작업을 참조합니다.)](../defender-endpoint/manage-auto-investigation.md#remediation-actions) |
| **자동화된 전자 메일 작업** | 전자 메일 메시지, 첨부 파일 또는 URL과 같은 전자 메일 콘텐츠에 대한 자동화된 작업입니다. 자동화된 작업의 예로는 전자 메일 메시지의 소프트 삭제, URL 차단 및 외부 메일 전달 해제가 있습니다. (자세한 [내용은 Microsoft Defender의](../office-365-security/air-remediation-actions.md)수정 Office 365 참조). |
| **고급 헌팅 작업** | 고급 헌팅이 있는 장치 또는 전자 [메일에 대해 수행된 작업입니다.](./advanced-hunting-overview.md) |
| **탐색기 동작** | 탐색기를 사용하여 전자 메일 콘텐츠에 대해 수행한 [작업입니다.](../office-365-security/threat-explorer.md) |
| **수동 실시간 응답 작업** | 라이브 응답이 있는 [디바이스에서 수행된 작업입니다.](../defender-endpoint/live-response.md) 예를 들어 파일 삭제, 프로세스 중지 및 예약된 작업 제거가 있습니다. |
| **라이브 응답 작업** | 끝점 API용 [Microsoft Defender를 사용하여 디바이스에서 수행한 작업입니다.](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis) 작업의 예로는 장치 차단, 바이러스 백신 검사 실행, 파일에 대한 정보 보기가 있습니다. |

## <a name="required-permissions-for-action-center-tasks"></a>알림 센터 작업에 필요한 사용 권한

관리 센터에서 보류 중인 작업 승인 또는 거부와 같은 작업을 수행하려면 다음 표에 나열된 사용 권한을 할당해야 합니다.

|수정 작업 |필요한 역할 및 사용 권한 할당 |
|--|----|
|끝점 수정을 위한 Microsoft Defender(장치) |**Azure Active Directory(Azure** AD) 또는 [https://portal.azure.com](https://portal.azure.com) Microsoft 365 관리 센터()에 할당된 보안 관리자 역할 [https://admin.microsoft.com](https://admin.microsoft.com)<br/>--- 또는 ---<br/>**끝점용** Microsoft Defender에 할당된 활성 수정 작업 역할 <br/> <br/> 자세한 내용은 다음 리소스를 참조하세요. <br/>- [Azure AD 기본 제공 역할](/azure/active-directory/roles/permissions-reference)<br/>- [역할 기반 액세스 제어에 대한 역할 만들기 및 관리(끝점용 Microsoft Defender)](../defender-endpoint/user-roles.md)  |
|Microsoft Defender for Office 365 수정(Office 및 전자 메일)  |Azure **AD(** ) 또는 보안 [https://portal.azure.com](https://portal.azure.com) 관리자()에 할당된 Microsoft 365 관리 센터( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- 및 --- <br/>**보안 및 준수** 센터에서 할당된 & 제거 역할( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**중요:** Office 365 Security  & Compliance Center()에서만 보안 관리자 역할이 할당된 경우, 관리 센터 또는 Microsoft 365 Defender 액세스할 수 [https://protection.office.com](https://protection.office.com) 없습니다. Azure AD  또는 2016에서 보안 관리자 역할이 할당되어 있어야 Microsoft 365 관리 센터. <br/><br/>자세한 내용은 다음 리소스를 참조하세요. <br/>- [Azure AD 기본 제공 역할](/azure/active-directory/roles/permissions-reference)<br/>- [보안 및 준수 센터의 & 권한](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Azure AD에서 **전역** 관리자 역할이 할당된 사용자는 관리 센터에서 보류 중인 작업을 승인하거나 거부할 수 있습니다. 그러나 조직에서는 전역 관리자 역할이 할당된 사용자 수를 제한하는 것이 가장 좋은 **모범** 사례입니다. 앞의 관리 센터 권한 표에 나열된  보안 **관리자,** 활성 수정 작업 및 검색 및 제거 역할을 사용하는 것이 좋습니다.

## <a name="next-step"></a>다음 단계 

- [수정 작업 보기 및 관리](m365d-autoir-actions.md)
