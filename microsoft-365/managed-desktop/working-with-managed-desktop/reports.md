---
title: 보고서 작업
description: 이 보고서에서 사용할 수 있는 다양한 Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771888"
---
# <a name="work-with-reports"></a>보고서 작업

Microsoft Managed Desktop 조직의 IT 관리자가 디바이스의 다양한 측면을 이해하는 데 사용할 수 있는 여러 보고서 및 대시보드를 제공합니다. 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

Microsoft Endpoint Manager 콘솔은 여러 제품의 보고를 단일 위치로 통합하여 Azure AD 조직("테넌트") 구성 및 장치에 대한 문제를 모니터링하고 조사하는 데 도움이 됩니다. Microsoft Managed Desktop에는  주 메뉴의 보고서 아래에 등록한 장치의 관리와 Microsoft Managed Desktop 보고서를 찾을 수 있는 섹션이 있습니다.

이러한 보고서에는 다음이 포함됩니다.
- **관리되는 장치**  >  **기능 업데이트:** 이 보기는 사용자 장치 전반에 걸쳐 기능 업데이트의 전반적인 상태를 Microsoft Managed Desktop 표시됩니다.
- **관리되는 장치**  >  **Office 업데이트:** 이 보기에는 전체 Office 업데이트의 전체 Microsoft Managed Desktop 표시됩니다.

또한 전체 Microsoft Endpoint Manager 여러 위치에서 다른 제품 그룹에서 보고서를 필터링하여 다른 제품 그룹에서 관리하는 장치를 구체적으로 포함하거나 제외할 수 Microsoft Managed Desktop. 이러한 보고서에는 다음 필터링 기능이 통합되어 있습니다.

- [모든 장치](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [장치 준수](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [비호위 장치](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 사용자 Microsoft Managed Desktop 역할은 보고서에 대한 액세스만 Microsoft Managed Desktop 보장합니다. 모든 장치와 같은 Microsoft Endpoint Manager 다른 부분에 액세스하는 경우 를 사용하여 역할 기반 액세스 [제어를 Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control) 

## <a name="endpoint-analytics"></a>끝점 분석
Microsoft Managed Desktop 끝점 [분석과 통합됩니다.](/mem/analytics/overview) 이러한 보고서는 조직이 작업하는 방식과 사용자에게 전달된 환경의 품질을 측정하는 데 필요한 정보를 제공합니다. 끝점 분석은 의 **보고서** [메뉴에 Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) 모든 보고서로 이동하여 관리되는 장치만 포함하려면 Microsoft Managed Desktop 필터 드롭다운을  선택한 다음 장치 Microsoft Managed Desktop **선택합니다.**

등록 중에 Azure AD 조직("테넌트")에 대해 끝점 분석이 자동으로 구성되지 않은 경우 직접 구성할 수 있습니다. 자세한 내용은 Endpoint 분석 [포털의 온보드를 참조하세요.](/mem/analytics/enroll-intune#bkmk_onboard) 모든 장치를 등록할 수도 있으며, 장치만 포함하려는 Microsoft Managed Desktop 테스트,  첫 번째, 빠르기 및 광범위에 대한 최신 작업 공간 장치 그룹을 선택합니다. 이러한 보고서에는 다른 사용 권한이 필요할 수 있습니다. 자세한 내용은 [사용 권한을](/mem/analytics/overview#permissions) 참조하여 역할을 적절하게 할당할 수 있습니다.

> [!NOTE]
> 개인 정보 보호 사용자 개인 정보를 보다 잘 활용하려면 이 필터를 사용하려면 Microsoft Managed Desktop 등록된 디바이스가 10개 Microsoft Managed Desktop 있어야 합니다.

 ## <a name="inventory-data"></a>인벤토리 데이터

다른 보고서 외에도 다른 보고서에 의해 관리되는 장치에 대한 정보를 내보낼 수 Microsoft Managed Desktop. 장치 **영역의** 장치  보기에서 Microsoft Endpoint Manager 모두 내보내기  탭을 사용하여 자세한 인벤토리 보고서를 [다운로드합니다.](device-inventory-report.md)
