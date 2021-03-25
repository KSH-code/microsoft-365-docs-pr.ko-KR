---
title: Windows의 정보 보호 개요
ms.reviewer: ''
description: Windows에서 정보 보호가 작동하는 방식에 대해 알아보고 중요한 정보를 식별하고 보호합니다.
keywords: 정보, 보호, dlp, 데이터, 손실, 방지, 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 733f86ed48b9cc7a68fb0cd346c7b15fdcc3ce65
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187508"
---
# <a name="information-protection-in-windows-overview"></a>Windows의 정보 보호 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

정보 보호는 Microsoft 365 Enterprise 제품군의 중요한 부분으로, 작업 공간에서 생산성을 유지하면서 중요한 데이터를 안전하게 보호하는 지능형 보호 기능을 제공합니다.


>[!TIP]
> [Microsoft Defender ATP가 Microsoft Information Protection과](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)통합되어 Windows 장치에서 중요한 데이터를 검색, 보호 및 모니터링하는 방법에 대한 블로그 게시물을 읽어 읽습니다.

Endpoint용 Defender는 다음 방법을 적용하여 데이터를 검색, 분류 및 보호합니다.

- **데이터 검색** - 위험에 노출된 Windows 장치에서 중요한 데이터 식별
- **데이터 분류** - Office 365 보안 및 준수 센터에서 관리되는 일반적인 MIP(Microsoft Information Protection) 정책을 & 분류합니다. 자동 분류를 사용하면 최종 사용자가 중요한 데이터를 수동으로 분류하지 않은 경우에도 보호할 수 있습니다.


## <a name="data-discovery-and-data-classification"></a>데이터 검색 및 데이터 분류

Endpoint용 Defender는 민감도 레이블이 있는 파일과 중요한 정보 유형이 포함된 파일을 자동으로 검색합니다.

민감도 레이블은 중요한 콘텐츠를 분류하고 보호하는 데 도움이 됩니다.

Office 365 DLP(데이터 손실 방지) 구현의 중요한 정보 유형은 다음 두 가지 범주로 분류됩니다.

- 기본
- 사용자 지정

기본 중요한 정보 유형에는 은행 계좌 번호, 주민 번호 또는 국가 번호와 같은 정보가 포함됩니다. 자세한 내용은 중요한 정보 [유형이 를 찾아보는 것을 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)

사용자 지정 유형은 정의하는 유형으로, 다른 유형의 중요한 정보(예: 직원의 신분증 또는 프로젝트 번호)를 보호하도록 디자인되어 있습니다. 자세한 내용은 사용자 지정 중요한 정보 [유형 만들기를 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)

Windows 장치에서 파일을 만들거나 편집하면 Endpoint용 Defender는 콘텐츠를 검사하여 중요한 정보가 포함되어 있는지 평가합니다.

레이블 또는 정보 유형이 있는 경우 끝점용 Defender에서 중요한 정보를 포함하는 파일을 검색할 때 장치에서 Azure Information Protection에 자동으로 전달될 수 있도록 Azure Information Protection 통합을 켜야 합니다.

![Azure Information Protection이 있는 설정 페이지의 이미지](images/atp-settings-aip.png)

보고된 신호는 Azure Information Protection - 데이터 검색 대시보드에서 볼 수 있습니다.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection - 데이터 검색 대시보드

이 대시보드에서는 Endpoint용 Defender 및 Azure Information Protection에서 검색한 데이터의 요약된 검색 정보를 제공합니다. 끝점용 Defender의 데이터는 위치 유형 - 끝점으로 표시됩니다.

![Azure Information Protection의 이미지 - 데이터 검색](images/azure-data-discovery.png)

오른쪽의 장치 위험 열에서 이 장치 위험은 Endpoint용 Defender에서 직접 파생됩니다. 이는 끝점에 대한 Defender에서 감지된 활성 보안 위협에 따라 파일이 검색된 보안 장치의 위험 수준을 나타내는 것입니다.

디바이스를 클릭하여 민감도 레이블 및 정보 유형으로 이 디바이스에서 관찰된 파일 목록을 확인합니다.

>[!NOTE]
>Azure Information Protection 대시보드 검색에서 검색된 파일을 반영하도록 약 15-20분을 허용하세요.

## <a name="log-analytics"></a>Log Analytics

끝점용 Defender를 기반으로 하는 데이터 검색은 [Azure Log Analytics에서도](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)사용할 수 있습니다. 여기서 원시 데이터에 대해 복잡한 쿼리를 수행할 수 있습니다.

Azure Information Protection 분석에 대한 자세한 내용은 Azure Information Protection에 대한 [중앙 보고를 참조하세요.](https://docs.microsoft.com/azure/information-protection/reports-aip)

Azure Portal에서 Azure Log Analytics를 열고 쿼리 작성기(표준 또는 클래식)를 여십시오.

끝점 데이터에 대한 Defender를 보기 위해 다음을 포함하는 쿼리를 수행하십시오.

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**필수 구성 요소:**

- 고객은 Azure Information Protection 구독이 있어야 합니다.
- Microsoft Defender 보안 센터에서 Azure Information Protection 통합을 사용하도록 설정:
    - Microsoft Defender 보안 **센터의** 설정으로 이동하여 일반 아래의 **고급 설정을** **클릭합니다.**



