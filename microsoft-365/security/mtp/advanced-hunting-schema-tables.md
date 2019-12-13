---
title: Microsoft Threat Protection 고급 헌팅 스키마의 데이터 표
description: 고급 헌팅 스키마의 표에 대해 알아보고 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석,
keywords: 스키마 참조, kusto, 표, 데이터에 대한 위협 헌팅 쿼리를 실행할 수 있는 데이터를 이해합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1803445dfd9b46fce23b0dcc9585ea543f1b0347
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911411"
---
# <a name="understand-the-advanced-hunting-schema"></a>고급 헌팅 스키마 이해

**적용 대상:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

[고급 헌팅](advanced-hunting-overview.md) 스키마는 이벤트 정보나 컴퓨터 및 엔터티에 대한 정보를 제공하는 여러 표로 구성됩니다. 여러 표를 포괄하는 쿼리를 효과적으로 작성하려면 고급 헌팅 스키마에서 표 및 열을 이해해야 합니다.

## <a name="schema-tables"></a>스키마 표

다음 참조는 스키마에서 모든 표를 나열합니다. 각 표 이름은 해당 표의 열 이름을 설명하는 페이지에 연결됩니다. 표 및 열 이름은 고급 헌팅 화면에서 스키마 표현의 일부로 보안 센터에도 나열됩니다.

| 테이블 이름 | 설명 |
|------------|-------------|
| **[MachineInfo](advanced-hunting-machineinfo-table.md)** | 컴퓨터 정보(OS 정보 포함) |
| **[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)** | 연결된 네트워크 및 도메인뿐만 아니라 어댑터, IP 및 MAC 주소를 비롯한 컴퓨터의 네트워크 속성 |
| **[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)** | 프로세스 생성 및 관련 이벤트 |
| **[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)** | 네트워크 연결 및 관련 이벤트 |
| **[FileCreationEvents](advanced-hunting-filecreationevents-table.md)** | 파일 생성, 수정 및 기타 파일 시스템 이벤트 |
| **[RegistryEvents](advanced-hunting-registryevents-table.md)** | 레지스트리 항목 생성 및 수정 |
| **[LogonEvents](advanced-hunting-logonevents-table.md)** | 로그인 및 기타 인증 이벤트 |
| **[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)** | DLL 로딩 이벤트 |
| **[MiscEvents](advanced-hunting-miscevents-table.md)** | Windows Defender Antivirus 및 익스플로잇 보호와 같은 보안 컨트롤에서 트리거되는 이벤트를 포함한 여러 이벤트 유형 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | 전자 메일 배달과 차단 이벤트를 포함한 Office 365 전자 메일 이벤트 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Office 365 전자 메일에 첨부된 파일에 대한 정보 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Office 365 전자 메일의 URL에 대한 정보 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | 이러한 소프트웨어 제품의 알려진 모든 취약점과 함께 장치의 소프트웨어 인벤터리 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | 익스플로잇 코드를 공개적으로 사용할 수 있는지를 포함하여 공개적으로 보고된 취약성에 대한 기술 자료 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | 장치에서 다양한 보안 구성의 상태를 나타내는 위협 및 취약성 관리 평가 이벤트 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | 위협 및 취약성 관리에서 장치를 평가하기 위해 사용하는 다양한 보안 구성에 대한 기술 자료. 다양한 표준과 벤치 마크에 대한 매핑 포함  |

## <a name="related-topics"></a>관련 항목
- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
