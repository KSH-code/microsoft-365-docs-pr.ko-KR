---
title: Windows 및 Office 배포 랩 키트
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows 및 Office 배포 랩 키트에 액세스하는 방법 및 위치에 대해 알아보세요.
ms.openlocfilehash: a19c9d2de0cb4cb5436a8c3364bab0e24bb866ee
ms.sourcegitcommit: 6cabf0226de1c95bff6ddb1852dac5ecdb2d6b96
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "35830506"
---
# <a name="windows-and-office-deployment-lab-kit"></a>Windows 및 Office 배포 랩 키트

이러한 다운로드 가능 실무 중심 랩은 관련된 구성 및 배포 후 관리 고려 사항과 Windows 10 배포 및 Office 365 배포를 중점적으로 다룹니다. 이 교육 과정은 Windows 7 수명 종료를 대비하는 조직에 반드시 권장되며, 현재 Windows 10 및 Office 365 Plus 또는 Office 2019를 사용하는 경우에도 적용됩니다. 여기에는 Windows 10, Office 365 ProPlus, Enterprise Mobility + Security, 관련된 제품 및 서비스에 대한 가이드가 포함됩니다.

이 랩은 Windows 10 Enterprise 및 Office 365 ProPlus를 실행하는 데스크톱의 배포 및 관리를 계획, 테스트 및 검증하는 데 도움을 주기 위해 만들어졌습니다. 이 랩에서는 System Center Configuration Manager, Desktop Analytics, Office 사용자 지정 도구, OneDrive, Windows Autopilot 등의 데스크톱 배포 도구에 설명된 단계와 도구를 다룹니다.

Windows 10 및 Office 365 ProPlus의 [데스크톱 배포](http://www.aka.ms/howtoshift) 프로세스의 일환으로 배포 도구 업데이트를 탐색하고 배포 관련 자동화를 테스트 할 때 샌드박스 또는 격리된 랩 환경을 만드는 것이 좋습니다.

랩 키트는 무료로 다운로드할 수 있으며 평가판 소프트웨어를 사용합니다.

### <a name="download-the-windows-and-office-deployment-lab-kithttpswwwmicrosoftcomevalcenterevaluate-lab-kit"></a>[**Windows 및 Office 배포 랩 키트 다운로드**](https://www.microsoft.com/evalcenter/evaluate-lab-kit)

## <a name="a-complete-lab-environment"></a>**전체 랩 환경**

이러한 랩은 도메인에 가입된 데스크톱 클라이언트, 도메인 컨트롤러, 인터넷 게이트웨이 및 완전히 구성된 ConfigMgr 인스턴스를 포함하여 자동으로 프로비전된 가상 랩 환경을 제공합니다. 랩에는 다음 제품의 평가판이 포함되어 있습니다.

  - Windows 10 Enterprise, Version 1903
  - Windows 7 Enterprise
  - System Center Configuration Manager, 버전 1902
  - Windows 10용 Windows Assessment and Deployment Kit, 버전 1903
  - Microsoft Deployment Toolkit
  - Microsoft Application Virtualization(App-V) 5.1
  - Microsoft BitLocker Administration and Monitoring 2.5 SP1
  - Windows Server 2019
  - Microsoft SQL Server 2017

또한, 이 랩은 다음에 대한 평가판에 연결되도록 디자인되어 있습니다. 

  - Microsoft 365 Enterprise E5

또는
  - Office 365 Enterprise E5
  - Enterprise Mobility + Security

## <a name="step-by-step-labs"></a>**단계별 랩**

자세한 랩 가이드는 다음을 포함하는 여러 배포 및 관리 시나리오를 안내합니다.

### <a name="device-and-app-readiness"></a>**장치 및 앱 준비**

  - Desktop Analytics
  - Internet Explorer용 엔터프라이즈 모드 및 엔터프라이즈 모드 사이트 목록

### <a name="directory-and-network-readiness"></a>**디렉터리 및 네트워크 준비**

  - Azure Active Directory 및 Microsoft 365에 대한 기본 설정
  - 배달 최적화, ConfigMgr의 피어 캐시 및 LEDBAT를 사용한 네트워크 최적화
  - ConfigMgr 및 Microsoft Intune 공동 관리
  - 원격 액세스(VPN)

### <a name="office-and-lob-app-delivery"></a>**Office 및 LOB 앱 배달**

  - System Center Configuration Manager를 사용하여 Office 365 ProPlus 배포
  - Microsoft Intune을 사용하여 Office 365 ProPlus 배포
  - Microsoft Intune을 사용하여 앱 배포 및 관리
  - 비즈니스용 Microsoft Store를 사용하여 앱 배포 및 셀프 서비스 설치
  - UWP로 데스크톱 브리지 응용 프로그램 변환
  - Windows 응용 프로그램 인증 키트
  - IE용 엔터프라이즈 모드를 사용하여 브라우저 호환성 향상

### <a name="user-file-and-settings-migration"></a>**사용자 파일 및 설정 마이그레이션**

  - ConfigMgr 및 MDT에서 PC 새로 고침 및 대체 작업 순서의 일부로 사용되는 사용자 상태 마이그레이션 도구
  - OneDrive의 알려진 폴더 이동
  - Enterprise State Roaming

### <a name="security-and-compliance"></a>**보안 및 규정 준수**

  - BitLocker 장치 암호화
  - Windows Defender Antivirus
  - 비즈니스용 Windows Hello
  - 가상화 기반 보안 사용을 위한 BIOS-UEFI 변환
  - Windows Defender Credential Guard
  - Windows Defender Application Guard
  - Windows Defender Exploit Guard
  - Windows Defender Application Control
  - Windows Defender Advanced Threat Protection

### <a name="os-deployment-and-feature-updates"></a>**운영 체제 배포 및 기능 업데이트**

  - OS 이미지 만들기
  - ConfigMgr의 OS 배포 작업 순서
      - 완전 복구
      - 새로 고침
      - 대체
      - 업그레이드
  - MDT의 OS 배포 작업 순서
  - ConfigMgr에서 업그레이드 작업 순서를 사용하여 기능 업데이트
  - Windows Autopilot

### <a name="windows-and-office-servicing"></a>**Windows 및 Office 서비스**

  - Configuration Manager를 사용한 소프트웨어 업데이트 관리
  - Configuration Manager에서 Office 365 ProPlus 업데이트 관리
  - Microsoft Intune을 사용하여 Windows 10에 적용되는 모바일 장치 관리

### <a name="download-the-windows-and-office-deployment-lab-kithttpswwwmicrosoftcomevalcenterevaluate-lab-kit"></a>[**Windows 및 Office 배포 랩 키트 다운로드**](https://www.microsoft.com/evalcenter/evaluate-lab-kit)

*광대역폭을 통해 이 콘텐츠를 다운로드하여 다운로드 환경을 개선하고 자동 프로비전을 위해 30-45분을 허용하세요. 이 랩 환경에는 최소 16GB의 사용 가능한 메모리와 150GB의 사용 가능한 디스크 공간이 필요합니다. 최적의 성능을 위해 32GB의 사용 가능한 메모리가 있는 것이 좋습니다. 이 랩은 2019년 8월 27일에 만료됩니다. 만료 전에 새 버전이 게시됩니다.*

## <a name="additional-guidance"></a>**추가 지침**

  - [데스크톱 배포 센터](http://www.aka.ms/howtoshift)

  - [Microsoft Mechanics의 데스크톱 배포 시리즈 비디오](http://www.aka.ms/watchhowtoshift)

  - [System Center Configuration Manager OS 배포](https://docs.microsoft.com/ko-KR/sccm/osd/understand/introduction-to-operating-system-deployment)

  - [<span class="underline">Windows 10 배포 계획</span>](https://docs.microsoft.com/windows/deployment/planning/index)

  - [<span class="underline">Office 365 ProPlus 배포 가이드</span>](https://docs.microsoft.com/deployoffice/deployment-guide-for-office-365-proplus)

  - [<span class="underline">Intune 시작</span>](https://docs.microsoft.com/intune/get-started-evaluation)

## <a name="related-resources"></a>**관련 리소스**

  - [<span class="underline">Microsoft 365 소개</span>](https://www.microsoft.com/microsoft-365/default.aspx)

  - [<span class="underline">Office 365 비즈니스 에디션</span>](https://products.office.com/business/office)

  - [<span class="underline">Introducing Enterprise Mobility + Security</span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

  - [<span class="underline">Windows 10 엔터프라이즈 에디션</span>](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)

  - [<span class="underline">Windows 10 중소기업용 에디션</span>](https://www.microsoft.com/WindowsForBusiness/windows-for-small-business)
