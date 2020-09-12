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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dc641d22432e245980b905051bddd3b7dd4ed07
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547989"
---
# <a name="the-action-center"></a>알림 센터

**적용 대상:**
- Microsoft Threat Protection

알림 센터를 사용하여 조직의 장치 및 사서함 전체에서 현재 및 과거 조사의 결과를 확인할 수 있습니다. 위협 유형 및 결과 결과에 따라 [업데이트 관리 작업](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) 은 조직의 보안 운영 팀의 승인을 받을 때 자동으로 수행 됩니다. 모든 수정 작업이 승인이 보류 중이든 이미 승인되었든 알림 센터에 통합되어 있습니다. 

![알림 센터 ](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>"단일 창 방식" 환경

알림 센터를 통해 다음과 같은 작업에 대한 "단일 창 방식" 환경을 제공합니다.
- 보류 중인 수정 작업 승인.
- 이미 승인된 수정 작업의 감사 로그 보기. 그리고
- 완료된 수정 작업을 검토

알림 센터를 통해 회사에서 Microsoft Threat Protection를 종합적으로 볼 수 있기 때문에 보안 운영팀이 보다 효과적이고 효율적으로 운영될 수 있습니다.

## <a name="go-to-the-action-center"></a>알림 센터로 이동합니다.

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **작업 센터**를 선택합니다. 

3. 작업 센터에는 **보류 중** 및 **기록**이라는 두 개의 탭이 표시 됩니다.

    - **보류 중** 탭에는 보안 운영팀의 누군가가 계속 진행하기 위해 검토하고 승인해야 하는 조사가 나열됩니다. 여기에 표시되는 보류 중인 항목을 검토하여 조치를 취해야 합니다.

    - **기록** 탭에는 자동으로 수행된 과거 조사와 수정 작업이 표시됩니다. 지난 일, 주, 월 또는 6개월에 대한 데이터를 볼 수 있습니다.

4. 원하는 열만 표시하려면 **열 사용자 정의**를 선택합니다.<br/>![Microsoft Threat Protection의 알림 센터](../../media/mtp-action-center.png)

5. 목록에서 항목을 선택하여 조사에 대한 자세한 정보를 확인합니다. 조사 세부 정보 보기가 열립니다.<br/>![조사 세부 정보](../../media/mtp-air-investdetails.png)

    - 조사가 전자 메일 콘텐츠와 관련 된 경우 (예: 엔터티가 사서함 인 경우) 보안 & 준수 센터 ()에서 조사 세부 정보를 엽니다 [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) . 

    - 조사가 장치에 관련된 경우 조사 세부 정보는 보안 센터([https://security.microsoft.com](https://security.microsoft.com))에서 열립니다. 

> [!TIP]
> Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요. [Microsoft Threat Protection에서 자동 조사 및 응답 (AIR) 기능을 통해 허위 긍정/네거티브를 보고 하는 방법을](mtp-autoir-report-false-positives-negatives.md)참조 하세요.

## <a name="available-actions"></a>사용 가능한 작업

재구성 작업이 수행 됨에 따라 작업 센터의 히스토리 탭에 나열 됩니다. 이러한 작업에는 다음이 포함 됩니다.

- 수집 조사 패키지 
- 장치 격리 (이 작업은 실행 취소할 수 있음) 
- Offboard 컴퓨터 
- 릴리스 코드 실행 
- 격리에서 릴리스 
- 요청 샘플 
- 코드 실행 제한 (이 작업을 실행 취소할 수 있음) 
- 바이러스 검사 실행 
- 중지 및 격리 

## <a name="required-permissions-for-action-center-tasks"></a>알림 센터 작업에 필요한 사용 권한

알림 센터에서 보류 중인 작업을 승인하거나 거부하려면 다음 표에 나열된 대로 사용 권한이 할당되어 있어야 합니다.

|수정 작업 |필요한 역할 및 사용 권한 할당 |
|--|----|
|Microsoft Defender ATP 수정(장치) |Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 보안 관리자 역할<br/>--- 또는 ---<br/>Microsoft Defender ATP에서 할당된 활성 수정 작업 역할 <br/> <br/> 자세한 내용은 다음 리소스를 참조하세요. <br/>- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [역할 기반 액세스 제어(Microsoft Defender ATP)를 위한 역할 만들기 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP 수정(Office 콘텐츠 및 전자 메일)  |Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 보안 관리자 역할<br/>--- 및 --- <br/>보안 & 준수 센터 ()가 할당 된 검색 및 제거 역할 [https://protection.office.com](https://protection.office.com) <br/><br/>**중요**: 보안 관리자 역할이 보안 & 준수 센터에만 할당 된 경우에는 작업 센터 또는 Microsoft Threat Protection 기능에 액세스할 수 없습니다. Azure Active Directory 또는 Microsoft 365 관리 센터에 할당된 보안 관리자 역할이 있어야 합니다. <br/><br/>자세한 내용은 다음 리소스를 참조하세요. <br/>- [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [보안 & 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Azure Active Directory에서 전역 관리자 역할이 할당된 사용자는 알림 센터에서 대기 중인 모든 작업을 승인하거나 거부할 수 있습니다. 그러나 조직에서 전역 관리자 역할이 할당된 사용자 수를 제한하는 것이 가장 좋습니다. 알림 센터 사용 권한에 대해 위에 나열한 보안 관리자, 활성 수정 작업, 검색 및 제거 역할을 사용하는 것이 좋습니다.

## <a name="next-steps"></a>다음 단계 

- [Microsoft Threat Protection에 관해 자세히 알아보기](incidents-overview.md)

- [자동화된 조사 결과 보기](mtp-autoir-results.md)

- [Microsoft Threat Protection의 헌팅에 대해 알아보기](advanced-hunting-overview.md)

