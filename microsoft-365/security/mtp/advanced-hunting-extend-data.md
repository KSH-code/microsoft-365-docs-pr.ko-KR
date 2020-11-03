---
title: 적절 한 설정을 사용 하 여 고급 구하기 적용 범위 확장
description: 고급 구하기에서 가장 포괄적인 데이터를 가져올 수 있도록 Windows 장치 및 기타 설정에 대 한 감사 설정을 확인 합니다.
keywords: 고급 구하기, 인시던트, 피벗, 엔터티, 감사 설정, 사용자 계정 관리, 보안 그룹 관리, 위협 검색, 사이버 위협 구하기, search, 쿼리, 원격 분석, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 82faff2599cd61fa1a4deb3129e1e6780d3f529c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842479"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>적절 한 설정을 사용 하 여 고급 구하기 적용 범위 확장

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[고급 구하기](advanced-hunting-overview.md) 는 장치, Office 365 작업 영역, Azure AD 및 Id 용 Microsoft Defender를 포함 하 여 다양 한 원본에서 가져온 데이터를 기반으로 합니다. 가능한 가장 포괄적인 데이터를 얻으려면 해당 데이터 원본에 대 한 올바른 설정이 있는지 확인 합니다.

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 장치에 대 한 고급 보안 감사
이러한 고급 감사 설정을 사용 하 여 장치에서 로컬 계정 관리, 로컬 보안 그룹 관리 및 서비스 만들기를 비롯 한 작업에 대 한 데이터를 가져올 수 있도록 합니다.

| 데이터 | 설명 | 스키마 테이블 | 구성 방법 |
| --- | --- | --- | --- |
| 계정 관리 | `ActionType`로컬 계정 만들기, 삭제 및 기타 계정 관련 활동을 나타내는 다양 한 값으로 캡처되는 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -고급 보안 감사 정책 배포: [사용자 계정 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [고급 보안 감사 정책에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 보안 그룹 관리 | `ActionType`로컬 보안 그룹 만들기 및 기타 로컬 그룹 관리 활동을 나타내는 다양 한 값으로 캡처되는 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -고급 보안 감사 정책 배포: [보안 그룹 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [고급 보안 감사 정책에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 서비스 설치 | `ActionType`서비스가 만들어짐을 나타내는 값을 사용 하 여 캡처한 이벤트 `ServiceInstalled` | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -고급 보안 감사 정책 배포: [보안 시스템 확장 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [고급 보안 감사 정책에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>도메인 컨트롤러의 Id 센서에 대 한 Microsoft Defender
Active Directory를 온-프레미스로 실행 하는 경우 Microsoft Defender for Identity에 대 한 데이터를 가져오려면 도메인 컨트롤러에 Microsoft Defender for Identity 센서를 설치 해야 합니다. 이 데이터는 설치 및 올바르게 구성 된 경우 Microsoft Defender를 통해 Id를 제공 하 고 네트워크의 id 정보 및 이벤트를 보다 광범위 하 게 보여 주는 고급 구하기도 안내 합니다. 또한이 데이터는 Id에 대 한 Microsoft Defender가 고급 구하기에도 적용 되는 관련 알림을 생성 하는 기능을 향상 시킵니다. 

| 데이터 | 설명 | 스키마 테이블 | 구성 방법 |
| --- | --- | --- | --- |
| 도메인 컨트롤러 | Id를 위해 Microsoft Defender로 전송 되는 온-프레미스 Active Directory의 데이터 (예: 계정 세부 정보, 로그온 작업 및 Active Directory 쿼리)를 enriching id 관련 정보 | [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)및 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) 를 비롯 한 여러 테이블  | - [Id 센서 용 Microsoft Defender 설치](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [관련 Windows 이벤트 켜기](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
