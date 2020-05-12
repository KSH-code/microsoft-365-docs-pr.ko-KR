---
title: 3단계. 장치, PC 및 기타 끝점에 대한 끝점 관리 기능 배포
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Microsoft Endpoint Manager를 사용하여 장치, PC 및 기타 끝점을 관리합니다.
ms.openlocfilehash: 388ac2b7f9f4a31d33c1f4551e215b2b32c8f85f
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160801"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>3단계. 장치, PC 및 기타 끝점에 대한 끝점 관리 기능 배포

원격 작업자의 경우 점점 늘어나는 개인 장치를 지원해야 합니다. 끝점 관리 기능은 장치에서 리소스에 대한 액세스 권한을 부여받기 전에 특정 기준을 준수해야 하는 정책 기반의 보안 방식입니다. Microsoft Endpoint Manager는 클라우드 및 온-프레미스에서 데이터를 안전하게 유지하기 위한 최신 작업 공간과 최신 관리 기능을 제공합니다. 

Endpoint Manager는 이미 알고 있고 사용하고 있는 다음 서비스를 결합하여 모바일 장치, 데스크톱 컴퓨터, 가상 머신, 내장 장치, 서버를 관리하는 서비스와 도구를 제공합니다.

![끝점 관리용 구성 요소](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Intune은 조직 데이터에 액세스하는 데 사용되는 장치를 관리하지 않는 경우 데이터를 보호하는 데 도움을 주도록 설계되었습니다. Azure AD Conditional Access와 결합하여 Intune 앱 보호 정책은 모바일 장치에서 데이터를 세부적으로 컨트롤할 수 있도록 해줍니다. Intune을 사용하면 올바른 조건을 충족하는 사용자만 회사 데이터에 액세스하도록 하는 포괄적인 정책을 정의하고, Office, Outlook 및 다른 모바일 앱에서 데이터를 사용하는 방법을 컨트롤하여 데이터를 계속해서 보호된 상태로 유지하도록 할 수 있습니다.

자세한 내용은 이 [Microsoft Intune의 개요](https://docs.microsoft.com/intune/fundamentals/what-is-intune)를 참조하세요.

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager는 온-프레미스 관리 솔루션으로서 네트워크에 있거나 또는 인터넷 기반의 데스크톱, 서버 및 노트북을 관리합니다. 클라우드를 사용하도록 설정하여 Intune, Azure AD, Microsoft Defender ATP 및 기타 클라우드 서비스와 통합할 수 있습니다. Configuration Manager를 사용하여 앱, 소프트웨어 업데이트 및 운영 체제를 배포합니다. 또한 규정 준수를 모니터링하고, 쿼리를 실행하고, 실시간으로 클라이언트에 대한 작업을 수행하는 등의 더 많은 작업을 수행할 수 있습니다.

자세한 내용은 이 [Configuration Manager 개요](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)를 참조하세요.

## <a name="co-management"></a>공동 관리

공동 관리는 Intune과 기타 Microsoft 365 클라우드 서비스를 사용하여 기존 온-프레미스 Configuration Manager 투자와 클라우드를 결합합니다. 사용자는 Configuration Manager 또는 Intune을 7개의 다양한 작업 그룹에 대한 관리 기관으로 선택할 수 있습니다.

Endpoint Manager의 일환으로 공동 관리는 조건부 액세스를 비롯한 클라우드 기능을 사용합니다. Intune을 이용하여 클라우드에서 다른 작업을 실행하는 동안 몇 가지 작업을 온-프레미스에 유지할 수 있습니다.

자세한 내용은 이 [공동 관리 개요](https://docs.microsoft.com/mem/configmgr/comanage/overview)를 참조하세요.

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics는 Configuration Manager와 통합하고 사용자에게 Windows 클라이언트에 대한 의사 결정을 내리는 데 도움이 되는 정보와 인텔리전스를 제공하는 클라우드 기반 서비스입니다. Microsoft 클라우드 서비스에 연결된 수백만 개의 장치에서 집계한 데이터를 조직의 데이터와 결합합니다. Desktop Analytics를 사용하여 조직에서 실행되는 앱의 인벤토리를 만들고, 최신 Windows 10 기능 업데이트를 통해 앱 호환성을 평가하고, 호환성 문제를 확인하고, 클라우드를 사용하는 데이터 이해를 기반으로 하는 완화 제안을 받고, 최소 장치 집합에서 전체 응용 프로그램 및 드라이버 공간을 표시하는 파일럿 그룹을 만들고 Windows 10을 파일럿 및 프로덕션 관리 장치에 배포할 수 있습니다.

자세한 내용은 이 [Desktop Analytics 개요](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)를 참조하세요.

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot은 제로터치의 셀프 서비스 Windows 배포 플랫폼입니다. 여기에는 새 장치를 설정하고 사전 구성하는 데 사용되는 기술의 컬렉션이 포함되어 있으며, 이를 통해 장치의 생산적인 활용을 위한 준비를 합니다. 또한 Windows Autopilot를 사용하여 장치를 재설정 하고 용도를 변경하며 복구를 할 수도 있습니다. 이 솔루션을 사용 시 관리해야 할 인프라가 거의 없으며 IT 부서가 쉽고 간단한 프로세스를 통해 기대 이상의 성과를 내게 해줍니다. 사용자 관점에서 보면 몇 가지 간단한 작업만 수행하면 장치를 사용할 준비가 됩니다. IT 전문가의 관점에서 보면 최종 사용자가 해야하는 작업은 네트워크에 연결하고 해당 자격 증명을 확인하는 것뿐입니다.

자세한 내용은 이 [Windows Autopilot의 개요](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)를 참조하세요.

## <a name="admin-technical-resources-for-endpoint-management"></a>끝점 관리를 위한 관리자 기술 리소스

- [보안을 위해 관리되는 장치를 등록하고, 관리되지 않는 장치에 대한 앱 설정을 활용하고, 장치 및 앱 정책을 사용합니다](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [MDM(모바일 장치 관리)에 다양한 유형의 장치를 등록하는 방법](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Microsoft Intune에 대해 최종 사용자를 교육하는 방법](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>3단계의 결과

사용자는 끝점 관리자 기능 제품군을 사용하여 모바일 장치, 데스크톱 컴퓨터, 가상 컴퓨터, 내장 장치 그리고 서버를 관리하고 있습니다.

## <a name="next-step"></a>다음 단계

[4단계](empower-people-to-work-remotely-teams-productivity-apps.md)를 계속 진행하여 온-프레미스 앱 및 서비스에 대한 원격 액세스를 제공하세요.
