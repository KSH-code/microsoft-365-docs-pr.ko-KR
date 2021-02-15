---
title: 올바른 설정을 사용하여 고급 헌팅 범위 확장
description: Windows 장치 및 기타 설정의 감사 설정을 확인하여 고급 헌팅에서 가장 포괄적인 데이터를 얻을 수 있도록 합니다.
keywords: 고급 헌팅, 인시던트, 피벗, 엔터티, 감사 설정, 사용자 계정 관리, 보안 그룹 관리, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929589"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>올바른 설정으로 고급 헌팅 범위 확장

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[고급 헌팅은](advanced-hunting-overview.md) 장치, Office 365 작업 영역, Azure AD 및 ID용 Microsoft Defender를 비롯한 다양한 원본에서 오는 데이터를 활용합니다. 가능한 가장 포괄적인 데이터를 얻습니다. 해당 데이터 원본에 올바른 설정이 적용되도록 합니다.

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 디바이스의 고급 보안 감사
이러한 고급 감사 설정을 켜서 로컬 계정 관리, 로컬 보안 그룹 관리 및 서비스 만들기를 비롯한 장치의 활동에 대한 데이터를 얻습니다.

| 데이터 | 설명 | Schema 테이블 | 구성 방법 |
| --- | --- | --- | --- |
| 계정 관리 | 로컬 계정 만들기, 삭제 및 기타 계정 관련 활동을 나타내는 다양한 값으로 `ActionType` 캡처된 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [사용자 계정 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [고급 보안 감사 정책에 대해 자세히](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 보안 그룹 관리 | 로컬 보안 그룹 만들기 및 기타 로컬 그룹 관리 활동을 나타내는 다양한 `ActionType` 값으로 캡처된 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [보안 그룹 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [고급 보안 감사 정책에 대해 자세히](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 서비스 설치 | 서비스가 만들어졌다는 것을 나타내는 값으로 캡처된 `ActionType` `ServiceInstalled` 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [보안 시스템 확장 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [고급 보안 감사 정책에 대해 자세히](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>도메인 컨트롤러의 ID 센서용 Microsoft Defender
Active Directory를 실행 중인 경우 도메인 컨트롤러에 ID용 Microsoft Defender 센서를 설치하여 Id용 Microsoft Defender에 대한 데이터를 다운로드해야 합니다. 설치 및 적절히 구성된 경우 이 데이터는 ID용 Microsoft Defender를 통해 고급 헌팅에 대한 정보를 제공하며 네트워크에서 ID 정보 및 이벤트에 대한 보다 전체적인 그림을 제공합니다. 또한 이 데이터를 통해 ID용 Microsoft Defender가 고급 헌팅에 해당되는 관련 경고를 생성할 수 있습니다. 

| 데이터 | 설명 | Schema 테이블 | 구성 방법 |
| --- | --- | --- | --- |
| 도메인 컨트롤러 | ID를 위해 Microsoft Defender로 전송된, 계정 세부 정보, 로그온 활동 및 Active Directory 쿼리와 같은 ID 관련 정보를 보강하는 데 전송되는온-프레미스 Active Directory의 데이터 | [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)및 [IdentityQueryEvents를](advanced-hunting-identityqueryevents-table.md) 포함한 여러 테이블  | - [Id용 Microsoft Defender 센서 설치](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [관련 Windows 이벤트 켜기](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
