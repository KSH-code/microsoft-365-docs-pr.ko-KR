---
title: '4단계: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise에 대한 Office 365 ProPlus 인프라를 배포하는 단계입니다.
ms.openlocfilehash: 5c32257fb9066f170da1f1a3cfe4b865e383cfcb
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646403"
---
# <a name="phase-4-office-365-proplus"></a>4단계: Office 365 ProPlus

![4단계: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*이 단계는 E3 및 E5 버전의 Microsoft 365 Enterprise 및 Microsoft 365 Education에 적용됩니다.*

Microsoft 365 Enterprise에는 Office 구독 버전인 Office 365 ProPlus가 포함되어 있습니다. Office 2019와 같이 Office 365 ProPlus에는 모든 Office 응용 프로그램이 포함되어 있으며, 이러한 응용 프로그램은 클라이언트 장치에 직접 설치됩니다. Office 2019와 달리 Office 365 ProPlus는 정기적으로 새로운 기능으로 업데이트되며, 사용자가 여러 장치에 Office를 설치할 수 있도록 하는 사용자 기반 라이선싱 모델이 있습니다. 자세한 내용은 [엔터프라이즈의 Office 365 ProPlus](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)를 참조하세요.

이 단계에서는 Microsoft 365 Enterprise의 일부로 클라이언트 장치에 Office 365 ProPlus를 설치합니다. 이 지침 외에도 배포에 도움이 되는 [Microsoft Fastrack](https://fasttrack.microsoft.com/office)을 사용하는 것이 좋습니다. 

Office 365 ProPlus를 이미 배포한 경우 이 단계에 대한 [종료 조건](office365proplus-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 조건을 충족하는지 확인합니다.

>[!Note]
>Windows 10 Enterprise 및 Office 365 ProPlus를 함께 배포하려면 [데스크톱 배포 센터](desktop-deployment-center-home.md)를 참조하세요.
>

## <a name="step-1-assess-your-environment"></a>1단계: 환경 평가

Office 365 ProPlus를 배포하기 전에 [Office 365 ProPlus를 배포하기 위한 사용자 환경 및 요구 사항 평가](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)의 지침을 따르세요. 이 평가에는 시스템 요구 사항, 클라이언트 장치 정보(예: 아키텍처 및 필요한 언어), 라이선스 요구 사항, 네트워크 기능 및 응용 프로그램 호환성이 포함됩니다. 평가를 완료하면 배포 계획의 일부로 주요 결정을 내릴 수 있습니다.

## <a name="step-2-plan-your-deployment"></a>2단계: 배포 계획

사용자 환경을 평가한 후에는 [Office 365 ProPlus 배포 계획](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)의 지침에 따라 배포 계획을 만듭니다. 이 계획에는 다음과 같은 의사 결정이 포함됩니다. 

- 사용할 도구(예: System Center Configuration Manager 또는 Office 배포 도구) 및 Office 설치 위치 등 Office를 배포하는 방법
- Office에 대한 업데이트를 관리하는 방법
- 사용할 업데이트 채널(Office의 업데이트 채널에 따라 사용자에게 Office 응용 프로그램에 대한 기능 업데이트가 제공되는 빈도가 달라짐)
- 어떤 사용자에게 어떤 Office 응용 프로그램 및 언어를 설치해야 하는지를 포함하여 사용할 Office 설치 패키지 및 배포 그룹

[계획 문서](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)에는 배포 관리, 업데이트 관리, 설치 패키지 정의, 배포 그룹 만들기 등 이러한 모든 옵션에 대한 모범 사례가 포함되어 있습니다. 

## <a name="step-3-deploy"></a>3단계: 배포

배포 계획에 따라 배포할 방법을 선택합니다.

- **[System Center Configuration Manager를 사용하여 Office 365 ProPlus 배포](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Configuration Manager를 사용하여 배포를 관리하고, 네트워크의 배포 지점에서 Office를 다운로드하여 배포

- **[클라우드에서 ODT를 사용하여 Office 365 ProPlus 배포](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** ODT를 사용하여 배포를 관리하고 Office CDN에서 직접 클라이언트 장치에 Office 설치
 
- **[Office 포털에서 Office 365 ProPlus 자가 설치](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Office 포털에서 배포를 관리하고 사용자가 포털에서 직접 클라이언트 장치에 Office를 설치하도록 함

대부분의 조직에서는 다양한 사용자에 대해 이러한 옵션의 조합을 사용합니다. 예를 들어 조직에서는 Configuration Manager를 사용하여 대부분의 사용자에게 Office를 배포하지만 내부 네트워크에 자주 연결되지 않는 소규모 작업 그룹을 위해 자가 설치를 사용할 수 있습니다. 

조직에서 Configuration Manager를 사용하는 경우 현재 분기로 업그레이드하고 현재 릴리스로 업데이트하는 것이 좋습니다. 자세한 내용은 [사용해야 하는 Configuration Manager 분기](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)를 참조하세요.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

Microsoft의 전문가가 [Office 365 ProPlus의 업데이트를 배포하고 관리](https://www.microsoft.com/ko-KR/itshowcase/deploying-and-managing-microsoft-365#primaryR7)하는 방법에 대해 알아봅니다.

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso의 Microsoft 365 Enterprise 사용 방식

가상의 대표적 다국적 기업인 Contoso Corporation가 [Office 365 ProPlus를 배포](contoso-o365pp.md)한 방식을 알아봅니다.

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>다음 단계

[Office 365 ProPlus 인프라 종료 조건](office365proplus-exit-criteria.md)
