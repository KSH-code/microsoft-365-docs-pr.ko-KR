---
title: Windows 및 Office 배포 랩 키트
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows 및 Office 배포 랩 키트에 액세스하는 방법 및 위치에 대해 알아보세요.
ms.openlocfilehash: f7f6dcaa9c1e007f6b83f897539bdabe9faa0b96
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780559"
---
# <a name="windows-and-office-deployment-lab-kit"></a>Windows 및 Office 배포 랩 키트

Windows 및 Office 배포 랩 키트는 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱을 실행하는 데스크톱의 배포 및 관리를 계획, 테스트 및 유효성을 검사하는 데 도움이 하도록 디자인되어 있습니다. 키트의 랩에서는 Microsoft Endpoint Configuration Manager, Desktop Analytics, Office 사용자 지정 도구, OneDrive, Windows Autopilot 등 다양한 기능을 제공합니다.

이 키트는 Windows 10으로의 Windows 8.1 업그레이드를 준비하는 조직에 권장됩니다. 또한 현재 Windows 10, 엔터프라이즈용 Microsoft 365 앱(이전의 Office 365 ProPlus) 또는 Office 2019를 사용 중인 경우 적용됩니다. 격리된 환경인 결과 랩은 배포 도구 업데이트를 탐색하고 배포 관련 자동화를 테스트하는 데 이상적입니다.

[Windows 및 Office 배포 랩 키트 다운로드](https://www.microsoft.com/evalcenter/evaluate-lab-kit)

## <a name="a-complete-lab-environment"></a>전체 랩 환경

이 키트는 도메인에 가입된 데스크톱 클라이언트, 도메인 컨트롤러, 인터넷 게이트웨이 및 완전히 구성된 Configuration Manager 인스턴스를 포함하여 자동으로 프로비전된 가상 랩 환경을 제공합니다. 이 키트에는 다음 제품의 최신 평가판 버전이 포함되어 있습니다.

  - 새로운 기능! Windows 10 Enterprise, 버전 20H2
  - Windows 7 Enterprise
  - Microsoft Endpoint Configuration Manager, 버전 2010*
  - Windows 10용 Windows 평가 및 배포 키트
  - Microsoft Deployment Toolkit
  - Microsoft Application Virtualization(App-V)
  - Microsoft BitLocker 관리 및 모니터링 
  - Windows Server 
  - Microsoft SQL Server 

결과 랩은 다음에 대한 평가판에 연결하도록 디자인됩니다. 

  - Microsoft 365 E5
  - EmS(Enterprise Mobility + Security) Office 365 E5

## <a name="step-by-step-labs"></a>단계별 랩

자세한 랩 가이드는 여러 배포 및 관리 시나리오를 안내합니다. 최신 버전의 Intune 및 Configuration Manager에 대한 랩이 업데이트되었습니다. 

### <a name="plan-and-prepare-infrastructure"></a>인프라 계획 및 준비 
- Desktop Analytics 
- 클라우드 관리 게이트웨이 & 배포 지점 
- 테넌트 연결, 공동 관리 및 전환 워크로드 
- 원격 액세스(VPN) 

### <a name="prepare-configuration"></a>구성 준비   

- Windows 10 업데이트 배달 최적화   
- 그룹 정책을 사용하여 Windows 10 서비스
- Microsoft Intune을 사용하여 Windows 10 서비스   
- Configuration Manager를 통해 Windows 10 서비스   
- Configuration Manager를 사용하여 엔터프라이즈용 Microsoft 365 앱 서비스   
- Intune을 사용하여 엔터프라이즈용 Microsoft 365 앱 서비스  
- 보안 및 규정 준수   

### <a name="prepare-applications"></a>응용 프로그램 준비    

- Office용 Toolkit 준비  
- WIN32 응용 프로그램의 MSIX 패키징 및 변환   

### <a name="deploy-windows-10"></a>Windows 10 배포   

- Configuration Manager의 OS 배포 작업 순서
- MDT(Microsoft Deployment Toolkit)의 OS 배포 작업 순서
- Windows Autopilot
- 새 Microsoft Edge 배포 및 관리  

### <a name="deploy-microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱 배포    

- 클라우드 관리 배포  
- 로컬 관리 배포    
- 비 AD 가입 장치에 엔터프라이즈용 Microsoft 365 앱 배포 
- Configuration Manager를 사용하여 엔터프라이즈 관리 배포
- Microsoft Intune을 사용하여 엔터프라이즈 관리 배포  
- Microsoft Intune을 통해 LOB 배포 및 관리
- Microsoft Teams 배포

### <a name="deploy-windows-virtual-desktop"></a>Windows 가상 데스크톱 배포  

- 준비, 배포, 최적화
 
## <a name="where-to-find-the-windows-and-office-deployment-lab-kit"></a>Windows 및 Office 배포 랩 키트를 찾을 수 있는 위치

[Windows 및 Office 배포 랩 키트 다운로드](https://www.microsoft.com/evalcenter/evaluate-lab-kit)

* 설치된 기준 버전 2002는 콘솔 내 업데이트를 사용하여 버전 2010으로 업데이트할 수 있습니다. 이 콘텐츠를 다운로드하고 자동 프로비전을 위해 30-45분을 허용하려면 광범위한 대역폭 인터넷 연결을 사용하세요. 랩 환경에는 최소 16GB의 사용 가능한 메모리와 150GB의 사용 가능한 디스크 공간이 필요합니다. 최적의 성능을 위해 32GB의 사용 가능한 메모리와 300GB의 사용 가능한 공간이 권장됩니다. 키트는 2021년 2월 7일 만료됩니다. 만료 전에 새 버전이 게시됩니다.

## <a name="additional-guidance"></a>추가 안내

  - [Microsoft Mechanics의 데스크톱 배포 시리즈 비디오](https://www.aka.ms/watchhowtoshift)

  - [Microsoft Endpoint Configuration Manager OS 배포](https://docs.microsoft.com/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)

  - [Windows 10 배포 계획](https://docs.microsoft.com/windows/deployment/planning/index)

  - [Microsoft 365 앱 배포 가이드](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

  - [Intune 시작](https://docs.microsoft.com/intune/get-started-evaluation)

## <a name="related-resources"></a>관련 리소스

  - [Microsoft 365 소개](https://www.microsoft.com/microsoft-365/default.aspx)

  - [비즈니스용 Office 365](https://products.office.com/business/office)

  - [Introducing Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

  - [Windows 10 엔터프라이즈 에디션](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)

  - [Windows 10 중소기업용 에디션](https://www.microsoft.com/WindowsForBusiness/windows-for-small-business)
