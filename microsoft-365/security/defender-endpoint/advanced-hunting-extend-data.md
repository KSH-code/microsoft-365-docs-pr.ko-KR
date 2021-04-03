---
title: 올바른 설정을 사용하여 고급 헌팅 범위 확장
description: Windows 장치 및 기타 설정의 감사 설정을 확인하여 고급 헌팅에서 가장 포괄적인 데이터를 얻을 수 있도록 합니다.
keywords: 고급 헌팅, 인시던트, 피벗, 엔터티, 감사 설정, 사용자 계정 관리, 보안 그룹 관리, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, mdatp, Microsoft Defender ATP, 끝점용 Microsoft Defender, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500612"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>올바른 설정을 사용하여 고급 헌팅 범위 확장

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[고급 헌팅은](advanced-hunting-overview.md) 조직 전체에서 데이터를 제공해야 합니다. 가능한 가장 포괄적인 데이터를 얻습니다. 해당 데이터 원본에 올바른 설정이 적용되도록 합니다.

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 장치의 고급 보안 감사

이러한 고급 감사 설정을 켜서 로컬 계정 관리, 로컬 보안 그룹 관리 및 서비스 만들기를 비롯한 장치의 활동에 대한 데이터를 얻을 수 있도록 합니다.

데이터 | 설명 | Schema 테이블 | 구성 방법
-|-|-|-
계정 관리 | 로컬 계정 생성, 삭제 및 기타 계정 관련 활동을 나타내는 다양한 값으로 `ActionType` 캡처된 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [사용자 계정 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [고급 보안 감사 정책에 대한 자세한 정보](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
보안 그룹 관리 | 로컬 보안 그룹 만들기 및 기타 로컬 그룹 관리 활동을 나타내는 다양한 `ActionType` 값으로 캡처된 이벤트 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [보안 그룹 관리 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [고급 보안 감사 정책에 대한 자세한 정보](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
서비스 설치 | 값이 으로 `ActionType` 캡처된 이벤트는 서비스가 `ServiceInstalled` 생성되었음을 나타내는 이벤트입니다. | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 고급 보안 감사 정책 배포: [보안 시스템 확장 감사](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [고급 보안 감사 정책에 대한 자세한 정보](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>관련 항목

- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마에 대한 이해](advanced-hunting-schema-reference.md)
- [쿼리 결과로 작업](advanced-hunting-query-results.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](overview-custom-detections.md)
