---
title: 올바른 설정을 사용하여 고급 헌팅 범위 확장
description: 고급 헌팅에서 Windows 및 기타 설정에 대한 감사 설정을 확인하여 가장 포괄적인 데이터를 얻을 수 있도록 합니다.
keywords: 고급 헌팅, 인시던트, 피벗, 엔터티, 감사 설정, 사용자 계정 관리, 보안 그룹 관리, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dd61fa434eaf2130f0fcb0f28df9a20d696e04ec
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60665360"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>올바른 설정을 사용하여 고급 헌팅 범위 확장

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender

[고급 헌팅은](advanced-hunting-overview.md) 장치, 사용자 장치, Office 365 작업 영역, Azure AD 및 ID용 Microsoft Defender를 비롯한 다양한 소스에서 오는 데이터를 활용합니다. 가능한 가장 포괄적인 데이터를 얻습니다. 해당 데이터 원본에 올바른 설정이 적용되도록 합니다.

## <a name="advanced-security-auditing-on-windows-devices"></a>디바이스에서 고급 Windows 감사
이러한 고급 감사 설정을 켜서 로컬 계정 관리, 로컬 보안 그룹 관리 및 서비스 만들기를 비롯한 장치의 활동에 대한 데이터를 얻을 수 있도록 합니다.

| 데이터 | 설명 | Schema 테이블 | 구성 방법 |
| --- | --- | --- | --- |
| 계정 관리 | 로컬 계정 생성, 삭제 및 기타 계정 관련 활동을 나타내는 다양한 값으로 `ActionType` 캡처된 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [사용자 계정 관리 감사](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [고급 보안 감사 정책에 대한 자세한 정보](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 보안 그룹 관리 | 로컬 보안 그룹 만들기 및 기타 로컬 그룹 관리 활동을 나타내는 다양한 `ActionType` 값으로 캡처된 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [보안 그룹 관리 감사](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [고급 보안 감사 정책에 대한 자세한 정보](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 서비스 설치 | 값이 으로 `ActionType` 캡처된 이벤트는 서비스가 `ServiceInstalled` 생성되었음을 나타내는 이벤트입니다. | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [보안 시스템 확장 감사](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [고급 보안 감사 정책에 대한 자세한 정보](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>도메인 컨트롤러의 Id에 대한 Microsoft Defender 센서
Active Directory를 사내에서 실행하는 경우 도메인 컨트롤러에 Id용 Microsoft Defender 센서를 설치하여 Id용 Microsoft Defender에 대한 데이터를 다운로드해야 합니다. 설치 및 올바르게 구성된 경우 이 데이터는 ID에 대한 Microsoft Defender를 통해 고급 헌팅에 공급하고 네트워크에서 ID 정보 및 이벤트에 대한 보다 전체적인 그림을 제공합니다. 또한 이 데이터를 통해 ID에 대한 Microsoft Defender가 고급 헌팅에서 다루는 관련 경고를 생성할 수 있습니다. 

| 데이터 | 설명 | Schema 테이블 | 구성 방법 |
| --- | --- | --- | --- |
| 도메인 컨트롤러  | ID를 위해 Microsoft Defender로 전송되는 사내 Active Directory의 데이터, 계정 세부 정보, 로그온 활동 및 Active Directory 쿼리와 같은 ID 관련 정보 보강 | [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)및 [IdentityQueryEvents를](advanced-hunting-identityqueryevents-table.md) 비롯한 여러 테이블  | - [Id용 Microsoft Defender 센서 설치](/azure-advanced-threat-protection/install-atp-step4)<br>- [관련 이벤트 Windows 켜기](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다. [더 많은 Microsoft 365 Defender](m365d-enable.md) 사용하여 위협을 헌팅할 수 있습니다. Endpoint용 Microsoft Defender에서 고급 헌팅 Microsoft 365 Defender [Microsoft Defender에서](advanced-hunting-migrate-from-mde.md)고급 헌팅 쿼리 마이그레이션의 단계를 수행하여 고급 헌팅 워크플로를 끝점으로 이동할 수 있습니다.

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [스키마에 대한 이해](advanced-hunting-schema-tables.md)