---
title: 보고서 작업
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921353"
---
# <a name="work-with-reports"></a>보고서 작업

Microsoft Managed Desktop은 조직의 IT 관리자가 장치 인구의 다양한 측면을 이해하는 데 사용할 수 있는 여러 보고서 및 대시보드를 제공합니다.Microsoft [Endpoint Manager와 Microsoft](https://endpoint.microsoft.com) [365 관리](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)센터의 두 위치에서 보고서를 찾을 수 있습니다. 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager의 보고서

Microsoft Endpoint Manager 콘솔은 여러 제품의 보고를 단일 위치로 통합하여 Azure AD 조직("테넌트") 구성 및 장치에 대한 문제를 모니터링하고 조사하는 데 도움이 됩니다. Microsoft Managed Desktop에는  등록한 디바이스의 Microsoft Managed Desktop 관리와 관련한 보고서를 찾을 수 있는 주 메뉴의 보고서 아래에 섹션이 있습니다.

이러한 보고서에는 다음이 포함됩니다.
- **관리되는 장치**  >  **기능 업데이트:** 이 보기는 Microsoft Managed Desktop 장치에서 기능 업데이트의 전체 상태를 보여줍니다.
- **관리되는 장치**  >  **Office 업데이트:** 이 보기에는 Microsoft Managed Desktop 장치에서 Office 업데이트의 전체 상태가 표시됩니다.

또한 Microsoft Endpoint Manager 전체의 여러 위치에서 다른 제품 그룹의 보고서를 필터링하여 Microsoft Managed Desktop에서 관리하는 장치를 구체적으로 포함하거나 제외할 수 있습니다. 이러한 보고서에는 다음 필터링 기능이 통합되어 있습니다.

- [모든 장치](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [장치 준수](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [비호정 장치](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 사용자 지정 Microsoft Managed Desktop 역할은 Microsoft Managed Desktop 보고서에 대한 액세스만 보장합니다. 모든 장치와 같은 Microsoft Endpoint Manager의 다른 부분에 액세스하는 경우 Microsoft Intune을 사용하여 역할 기반 [액세스 제어를 참조합니다.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 관리 센터의 보고서

[Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)관리 센터를 연 다음 보고서로 나타났다가 **Microsoft Managed Desktop을** 선택하여 Microsoft Managed Desktop 인사이트 보고서를 찾을 수 있습니다.  Microsoft [Endpoint Manager](https://endpoint.microsoft.com)홈페이지의 Microsoft **Managed Desktop** 탭에서 이러한 보고서에 대한 직접 링크를 따라가도 됩니다. 

이러한 보고서에는 다음이 포함됩니다. 

- [사용 현황 정보](usage-insights.md) - 이 보기는 Microsoft Managed Desktop 디바이스에 대한 사용 메트릭을 제공합니다.
- [안정성 인사이트](reliability-insights.md) - 이 보기는 관리되는 장치의 상태 요약을 제공합니다.
- [배터리 정보](battery-insights.md) - 이 보기는 환경의 디바이스에 대해 앱의 에너지 소비 및 배터리 사용 시간으로 계획된 정보를 보여 줍니다.
- [Windows 보안 업데이트 인사이트](security-update-insights.md) - 이 보기에는 Microsoft Managed Desktop 장치의 보안 업데이트 상태에 대한 정보가 표시됩니다.

 ## <a name="inventory-data"></a>인벤토리 데이터

다른 보고서 외에도 Microsoft Managed Desktop에서 관리하는 장치에 대한 정보를 내보낼 수 있습니다. Microsoft **Endpoint** Manager의 장치 영역의 장치 보기에서 모든 내보내기 탭을 사용하여 자세한 인벤토리 보고서를 [다운로드합니다.](device-inventory-report.md)  
