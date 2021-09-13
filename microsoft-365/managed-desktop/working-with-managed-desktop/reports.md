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
ms.openlocfilehash: 2a28112c8afe9165453153d2d23752325ae2e6d8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215152"
---
# <a name="work-with-reports"></a>보고서 작업

Microsoft Endpoint Manager 콘솔은 여러 제품의 보고를 단일 위치로 통합하여 Azure AD 조직("테넌트") 구성 및 장치에 대한 문제를 모니터링하고 조사하는 데 도움이 됩니다. Microsoft Managed Desktop에는 등록한 디바이스의 관리와 Microsoft Managed Desktop 보고서를 찾을 수 있는 보고서 메뉴에 섹션이 있습니다.  또한 전체 Microsoft Endpoint Manager 여러 위치에서 다른 제품 그룹에서 보고서를 필터링하여 다른 제품 그룹에서 관리하는 장치를 구체적으로 포함하거나 제외할 수 Microsoft Managed Desktop. 

## <a name="microsoft-managed-desktop-reports"></a>Microsoft Managed Desktop 보고서
Microsoft Managed Desktop 조직의 IT 관리자가 디바이스의 다양한 측면을 이해하는 데 사용할 수 있는 여러 보고서 및 대시보드를 제공합니다.이러한 보고서는 보고서 메뉴의 Microsoft Managed Desktop  섹션에서 관리되는 장치로 Microsoft Endpoint Manager.   

요약 **탭에서** 장치 업데이트에 대한 빠른 메트릭을 찾을 수 있습니다. 메트릭의 **세부** 정보 보기를 선택하면 메트릭에 대한 원본 데이터 집합을 포함하여 오프라인 분석에 대한 추가 정보를 다운로드할 수 있습니다.

보고서 **탭을 선택하면** 사용 가능한 자세한 보고서에 대한 설명이 표시됩니다. 이러한 보고서는 보다 포괄적이고 지원되는 데이터 시각화 및 필터링뿐만 아니라 오프라인 분석 또는 배포를 위한 원본 데이터를 내보낼 수 있습니다. 현재 다음과 같은 보고서를 사용할 수 있습니다.
- 장치 [ **상태 보고서(미리**](device-status-report.md) 보기)는 장치 활동 및 사용량에 따라 Microsoft Managed Desktop 서비스 사용을 보여 줍니다. 
- 장치 상태  추세(미리보기)를 사용하여 장치 장치에 대한 지난 60일 동안의 장치 상태 추세를 Microsoft Managed Desktop 있습니다. 추세는 장치 상태를 시간이 경과에 따라 다른 변경 내용(예: 새 배포)과 연결하는 데 도움이 될 수 있습니다. 
- Windows 보안 업데이트보고서(미리 보기)는 Windows 보안 업데이트가 여러 장치에서 릴리스되는 Microsoft Managed Desktop 보여줍니다. [  ](security-updates-report.md)


## <a name="endpoint-analytics"></a>끝점 분석
Microsoft Managed Desktop 끝점 [분석과 통합됩니다.](/mem/analytics/overview) 이러한 보고서는 조직이 작업하는 방식과 사용자에게 전달된 환경의 품질을 측정하는 데 필요한 정보를 제공합니다. 끝점 분석은 의 **보고서** [메뉴에 Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) 모든 보고서로 이동하여 관리되는 장치만 포함하려면 Microsoft Managed Desktop 필터 드롭다운을  선택한 다음 장치 Microsoft Managed Desktop **선택합니다.**

등록 중에 Azure AD 조직("테넌트")에 대해 끝점 분석이 자동으로 구성되지 않은 경우 직접 구성할 수 있습니다. 자세한 내용은 Endpoint 분석 [포털의 온보드를 참조하세요.](/mem/analytics/enroll-intune#bkmk_onboard) 모든 장치를 등록할 수도 있으며, 장치만 포함하려는 Microsoft Managed Desktop 테스트,  첫 번째, 빠르기 및 광범위에 대한 최신 작업 공간 장치 그룹을 선택합니다. 이러한 보고서에는 다른 사용 권한이 필요할 수 있습니다. 자세한 내용은 [사용 권한을](/mem/analytics/overview#permissions) 참조하여 역할을 적절하게 할당할 수 있습니다.

> [!NOTE]
> 사용자 개인 정보를 보다 잘 활용하려면 이 필터를 사용하려면 끝점 Microsoft Managed Desktop 등록된 디바이스가 10개 이상 있어야 합니다.

## <a name="intune-reports"></a>Intune 보고서
Microsoft Intune 장치를 관리하는 데 사용하는 서비스 중 하나입니다. Intune 보고서를 사용하여 사용자 장치 관리에 대해 구체적으로 모니터링하는 Microsoft Managed Desktop 있습니다. 또는 다른 장치를 관리하는 데 사용하는 보고서에서 관리하는 장치를 제외할 수 있습니다. 다음 보고서를 사용하면 여러 장치를 포함하거나 제외하는 기능을 Microsoft Managed Desktop 있습니다.

- [모든 장치](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [장치 준수](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [비호위 장치](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 사용자 Microsoft Managed Desktop 역할은 보고서에 대한 액세스만 Microsoft Managed Desktop 보장합니다. 모든 장치와 같은 Microsoft Endpoint Manager 다른 부분에 액세스하는 경우 를 사용하여 역할 기반 액세스 [제어를 Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control) 

## <a name="microsoft-managed-desktop-inventory-data"></a>Microsoft Managed Desktop 인벤토리 데이터

다른 보고서 외에도 다른 보고서에 의해 관리되는 장치에 대한 정보를 내보낼 수 Microsoft Managed Desktop. 장치 **영역의** 장치  보기에서 Microsoft Endpoint Manager 모두 내보내기  탭을 사용하여 자세한 인벤토리 보고서를 [다운로드합니다.](device-inventory-report.md)
