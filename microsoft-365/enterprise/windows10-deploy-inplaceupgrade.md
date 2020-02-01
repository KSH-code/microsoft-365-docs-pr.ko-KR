---
title: 현재 위치 업그레이드로 기존 장치에 대 한 Windows 10 Enterprise 배포
description: Microsoft Endpoint Configuration Manager를 사용 하 여 전체 업그레이드로 Windows 10 Enterprise 이미지를 구성 및 배포 하는 방법에 대 한 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, Windows 10 Enterprise, 배포, 전체 업그레이드, 구성 관리자, Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 0078931be23039dac3a323f4747494803d1acd4d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602855"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>2 단계: 현재 위치 업그레이드로 기존 장치에 대 한 Windows 10 Enterprise 배포

*이 문서는 Microsoft 365 Enterprise E3 및 E5 버전에 모두 적용 됩니다.*

![3단계: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

현재 Windows 7 또는 Windows 8.1를 실행 하는 Pc를 Windows 10으로 업그레이드 하는 가장 간단한 경로는 전체 업그레이드를 사용 하는 것입니다. 구성 관리자 (Configuration Manager) 작업 시퀀스를 사용 하 여 프로세스를 완벽 하 게 자동화할 수 있습니다. 

Windows 7 또는 Windows 8.1을 실행 하는 기존 컴퓨터가 있는 경우 조직에서 Windows 10을 배포 하는 경우이 경로를 권장 합니다. 이렇게 하면 Windows 설치 프로그램 (setup.exe)을 활용 하 여 기존 운영 체제 버전에서 모든 데이터, 설정, 응용 프로그램 및 드라이버를 자동으로 보존 하는 전체 업그레이드를 수행할 수 있습니다. 이렇게 하면 복잡 한 배포 인프라가 필요 하지 않으므로 최소한의 IT 노력이 필요 합니다.

다음 단계에 따라 Microsoft Endpoint Configuration Manager를 사용 하 여 전체 업그레이드로 Windows 10 Enterprise 이미지를 구성 하 고 배포 합니다.

## <a name="the-windows-10-deployment-with-configuration-manager-poster"></a>Configuration Manager 포스터를 사용하여 Windows 10 배포

구성 관리자 포스터는 가로 모드 (17x11)의 한 페이지입니다. 아래 이미지를 클릭 하면 브라우저에서 PDF를 볼 수 있습니다. 

[![Configuration Manager 포스터를 사용 하 여 Windows 10 배포](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://docs.microsoft.com/windows/deployment/media/Windows10DeploymentConfigManager.pdf)

[PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf)나 [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) 형식으로도 포스터를 다운로드 할 수 있습니다.

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>1 부: Windows 업그레이드 준비 상태 확인

먼저, Windows Analytics의 업그레이드 준비 기능을 사용 하 여 추가 비용을 제외 하 고 추가적인 인프라 요구 사항 없이 조직의 컴퓨터, 응용 프로그램 및 드라이버에 대 한 강력한 통찰력 및 권장 사항을 제공 합니다. 이 새로운 서비스는 Microsoft 권장 사례를 기반으로 하는 워크플로를 사용 하 여 업그레이드 및 기능 업데이트 프로젝트를 안내 합니다. 최신 재고 데이터를 통해 업그레이드 프로젝트의 비용 및 위험을 분산할 수 있습니다.

업그레이드 준비 상태에 대 한 자세한 내용은 [업그레이드 준비를 통해 Windows 업그레이드 관리](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) 를 참조 하세요.

그런 다음 가이드에 따라 Configuration Manager (현재 분기)를 사용 하 여 Windows 7 이상 운영 체제를 Windows 10으로 업그레이드 합니다. 위험도가 높은 배포와 마찬가지로, 계속 하기 전에 사용자 데이터를 백업 하는 것이 좋습니다. OneDrive 클라우드 저장소는 라이선스가 있는 Microsoft 365 사용자에 게 사용할 준비가 되었으며 파일을 안전 하 게 저장 하는 데 사용할 수 있습니다. 자세한 내용은 [OneDrive 빠른 시작 가이드](https://aka.ms/ODfBquickstartguide)를 참조 하세요. 이 페이지에 액세스 하려면 Office 365 또는 Microsoft 365 테 넌 트에서 테 넌 트 관리자 또는 전역 관리자로 로그인 해야 합니다.

지원 되는 Windows 10 클라이언트 버전 및 구성 관리자 버전 목록은 [Configuration manager에 대 한 Windows 10 지원을](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10)참조 하십시오.

**Windows 업그레이드 준비 상태를 확인 하려면**

Windows 10 배포를 시작 하기 전에 다음 요구 사항을 검토 하십시오.

- **Windows** 10 Enterprise로 업그레이드 하는 데 사용할 수 있는 버전의 windows 7 또는 windows 8.1 버전이 실행 되 고 있어야 합니다. 지원 되는 버전 목록은 [Windows 10 업그레이드 경로](https://aka.ms/win10upgradepaths)를 참조 하세요. 
- **지원 되는 장치** -windows 8.1과 호환 되는 대부분의 컴퓨터는 windows 10과 호환 됩니다. 장치를 올바르게 작동 하려면 Windows 10에서 업데이트 된 드라이버를 설치 해야 할 수 있습니다. 자세한 내용은 [Windows 10 사양을](https://aka.ms/windows10specifications) 참조 하세요.
- **배포 준비** -배포 구성을 시작 하기 전에 다음을 확인 해야 합니다.
    - Windows 10 설치 미디어-설치 미디어는 ISO가 이미 탑재 된 별도의 드라이브에 있어야 합니다. [MSDN 구독자 다운로드](https://aka.ms/msdn-subscriber-downloads) 에서 ISO를 구하거 나 [볼륨 라이선스 서비스 센터](https://aka.ms/mvlsc)에서 다운로드할 수 있습니다.
    - 사용자 데이터 백업-사용자 데이터가 업그레이드에서 마이그레이션될 수 있지만 백업 시나리오를 구성 하는 것이 가장 좋습니다. 예를 들어 모든 사용자 데이터를 OneDrive 계정, BitLocker에서 이동 암호화 USB 플래시 드라이브 또는 네트워크 파일 서버로 내보냅니다. 자세한 내용은 [Windows에서 데이터 백업 또는 전송을](https://aka.ms/backuptransferdatawindows)참조 하세요.
- **환경 준비** -기존 Configuration Manager 서버 구조를 사용 하 여 운영 체제 배포를 준비 합니다. 기본 설정 외에도 Configuration Manager 환경에서 다음과 같은 구성을 수행 해야 합니다.
    1. [Active Directory 스키마를 확장](https://aka.ms/extendadschema) 하 고 [시스템 관리 컨테이너를 만듭니다](https://aka.ms/createsysmancontainer).
    2. Active Directory 포리스트 검색 및 Active Directory 시스템 검색을 사용 하도록 설정 합니다. 자세한 내용은 [Configuration Manager에 대 한 검색 방법 구성](https://aka.ms/configurediscoverymethods)를 참조 하세요.
    3. 콘텐츠 및 사이트 할당에 대 한 IP 범위 경계 및 경계 그룹을 만듭니다. 자세한 내용은 [Configuration Manager에 대 한 사이트 경계 및 경계 그룹 정의](https://aka.ms/definesiteboundaries)를 참조 하세요.
    4. Configuration Manager reporting services 지점 역할을 추가 하 고 구성 합니다. 자세한 내용은 [Configuration Manager에서 보고](https://aka.ms/configurereporting)구성을 참조 하세요.
    5. 패키지에 대 한 파일 시스템 폴더 구조를 만듭니다.
    6. 패키지에 대 한 Configuration Manager 콘솔 폴더 구조를 만듭니다.
    7. Configuration Manager (현재 분기) 업데이트 및 추가 Windows 10 필수 구성 요소를 설치 합니다.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>2 부: Configuration Manager를 사용 하 여 Windows 10 OS 이미지 추가
이제 전체 Windows 10 설치 미디어를 포함 하는 운영 체제 업그레이드 패키지를 만들어야 합니다. 다음 단계에서는 Configuration Manager를 사용 하 여 Windows 10 Enterprise x64 용 업그레이드 패키지를 만듭니다.

**Configuration Manager를 사용 하 여 Windows 10 OS 이미지를 추가 하려면**

1. Configuration Manager 콘솔을 사용 하 여 **소프트웨어 라이브러리** 작업 영역에서 **운영 체제 업그레이드 패키지** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **운영 체제 업그레이드 패키지 추가**를 선택 합니다.
2. **데이터 원본** 페이지에서 Windows 10 Enterprise x64 미디어에 대 한 UNC 경로를 지정 하 고 **다음**을 선택 합니다.
3. **일반** 페이지에서 **Windows 10 Enterprise x64 업그레이드**를 지정 하 고 **다음**을 선택 합니다. 
4. **요약** 페이지에서 **다음**을 선택 하 고 **닫기를**선택 합니다. 
5. 만들어진 **Windows 10 Enterprise X64 업데이트** 패키지를 마우스 오른쪽 단추로 클릭 한 다음 **콘텐츠 배포**를 선택 합니다. 
6. 배포 지점을 선택 합니다.

## <a name="part-3-configure-deployment-settings"></a>3 부: 배포 설정 구성
이 단계에서는 Windows 10 업그레이드에 대 한 설정을 포함 하는 업그레이드 작업 시퀀스를 구성 합니다. 그런 다음 업그레이드할 장치를 확인 하 고 해당 장치에 작업 순서를 배포 합니다.

### <a name="create-a-task-sequence"></a>작업 시퀀스 만들기
업그레이드 작업 시퀀스를 만들려면 다음 단계를 수행 합니다.
  
1. Configuration Manager 콘솔의 **소프트웨어 라이브러리** 작업 영역에서 **운영 체제**를 확장 합니다. 
2. **작업 순서** 노드를 마우스 오른쪽 단추로 클릭 하 고 **작업 순서 만들기**를 선택 합니다.
3. **새 작업 시퀀스 만들기** 페이지에서 **업그레이드 패키지에서 운영 체제 업그레이드**를 선택 하 고 **다음**을 선택 합니다.
4. **작업 순서 정보** 페이지에서 **Windows 10 Enterprise x64 업그레이드**를 지정 하 고 **다음**을 선택 합니다.
5. **Windows 운영 체제 업그레이드** 페이지에서 **찾아보기를** 선택 하 고 **windows 10 Enterprise x64 Upgrade 운영 체제 업그레이드 패키지**를 선택한 후 **확인**을 선택 하 고 **다음**을 선택 합니다.
6. 나머지 마법사 페이지를 계속 진행 하 고 Close ( **닫기**)를 선택 합니다.

### <a name="create-a-device-collection"></a>장치 컬렉션 만들기
업그레이드 작업 시퀀스를 만든 후에는 업그레이드할 장치를 포함 하는 컬렉션을 만들어야 합니다.

> [!NOTE]
> 다음 설정을 사용 하 여 단일 장치에서 배포를 테스트 합니다. 준비가 되 면 다른 멤버 자격 규칙을 사용 하 여 장치 그룹을 포함할 수 있습니다. 자세한 내용은 [Configuration Manager에서 컬렉션을 만드는 방법을](https://docs.microsoft.com/configmgr/core/clients/manage/collections/create-collections)참조 하세요.

1. Configuration Manager 콘솔의 **자산 및 준수** 작업 영역에서 **장치 모음**을 마우스 오른쪽 단추로 클릭 한 다음 **장치 모음 만들기**를 선택 합니다. 
2. 장치 컬렉션 만들기 마법사의 **일반** 페이지에서 다음 설정을 입력 하 고 **다음**을 선택 합니다.
    - 이름: Windows 10 Enterprise x64 업그레이드
    - 제한 컬렉션: 모든 시스템
3. **멤버 자격 규칙** 페이지에서 직접 구성원 규칙 만들기 마법사를 시작 하려면 **규칙** > **다이렉트 규칙** 추가를 선택 합니다.
4. 직접 구성원 규칙 만들기 마법사의 **시작** 페이지에서 **다음**을 선택 합니다.
5. **리소스 검색** 페이지에서 다음 설정을 입력 하 고 자리 표시자 **값** 텍스트를 업그레이드 하려는 장치의 이름으로 바꿉니다. 
    - 리소스 클래스: 시스템 리소스
    - 특성 이름: 이름
    - 값: *PC0003*
6. **리소스 선택** 페이지에서 장치를 선택 하 고 **다음**을 선택 합니다.
7. 직접 멤버 자격 규칙 만들기 마법사 및 장치 컬렉션 만들기 마법사를 완료 합니다.  
8. Windows 10 Enterprise x64 Upgrade 컬렉션을 검토 합니다. 컬렉션에 추가한 컴퓨터가 표시 될 때까지 계속할 수 없습니다.

### <a name="create-an-operating-system-deployment"></a>운영 체제 배포 만들기
작업 시퀀스에 대 한 배포를 만들려면 다음 단계를 수행 합니다.

1. Configuration Manager 콘솔의 **소프트웨어 라이브러리** 작업 영역에서 이전 단계에서 만든 작업 시퀀스를 마우스 오른쪽 단추로 클릭 하 고 **배포**를 선택 합니다.
2. **일반** 페이지에서 **Windows 10 Enterprise x64 업그레이드** 모음을 선택 하 고 **다음**을 선택 합니다.
3. **콘텐츠** 페이지에서 **다음**을 선택 합니다.
4. **배포 설정** 페이지에서 다음 설정을 선택 하 고 **다음**을 선택 합니다.

    > [!NOTE]
    > 이 테스트 배포에서는 배포를 시작 하기 위해 사용자 작업을 수행 해야 하는 용도를 **사용 가능**으로 설정 합니다. 프로덕션 환경에서는 배포가 실행 되는 시기와 같은 추가 옵션을 구성 하는 데 필요한 목적을 사용 하 여 배포를 자동화 하는 것이 좋습니다. 

    - 작업: 설치
    - 목적: 사용 가능

5. **일정** 페이지에서 기본 설정을 수락 하 고 **다음**을 선택 합니다.
6. **사용자 환경** 페이지에서 기본 설정을 수락 하 고 **다음**을 선택 합니다.
7. **알림** 페이지에서 기본 설정을 수락 하 고 **다음**을 선택 합니다.
8. **요약** 페이지에서 **다음**을 선택 하 고 **닫기를**선택 합니다.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>4 부: Windows 10 업그레이드 작업 순서 시작
업그레이드 하려는 장치에서 Windows 10 업그레이드 작업 순서를 시작 하려면 다음 단계를 수행 합니다.
 
1. Windows 컴퓨터에 로그온 하 고 **소프트웨어 센터**를 시작 합니다.
2. 이전 단계에서 만든 작업 순서를 선택 하 고 **설치**를 선택 합니다.
3. 작업 시퀀스가 시작 되 면 필요한 명령줄 매개 변수로 Windows 설치 프로그램 (setup.exe)을 호출 하 여 전체 업그레이드 프로세스를 자동으로 시작 하 여 자동 업그레이드를 수행 하 고 모든 데이터, 설정, 앱 및 정보를 보존 합니다. 드라이버용.
4. 작업 시퀀스가 성공적으로 완료 되 면 컴퓨터가 Windows 10으로 완전히 업그레이드 됩니다.

엔터프라이즈 환경에서 Windows 10을 사용할 때 문제가 발생 하면 [가장 일반적인 문제에 대 한 주요 Microsoft 지원 솔루션](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)을 참조할 수 있습니다. 이러한 리소스에는 기술 자료 문서, 업데이트 및 라이브러리 아티클이 포함 됩니다.

조직 전체에서 업데이트를 배포 하는 동안 Windows Analytics의 업데이트 준수 기능을 사용 하 여 OS 업데이트 준수, 업데이트 배포 진행률 및 Windows 10 장치에 대 한 오류 해결을 전체적으로 확인할 수 있습니다. 이 새 서비스는 설치 진행 상황, Windows Update 구성 및 기타 정보를 사용 하 여 추가 비용 없이 추가 인프라 요구 사항 없이도 이러한 통찰력을 제공 합니다. Windows Update for Business 또는 기타 관리 도구와 함께 사용 되는 경우에는 장치가 제대로 업데이트 되었는지 확인할 수 있습니다.

업데이트 준수를 [통해 Windows 업데이트 및 Windows Defender 바이러스 백신 모니터링](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) 을 참조 하 고, 시작 하 고, 업데이트 준수를 사용 하도록 합니다.

중간 검사점으로 이 단계에 해당하는 [종료 조건](windows10-exit-criteria.md#crit-windows10-step2)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![3단계](./media/stepnumbers/Step3.png)| [Windows Autopilot를 사용 하 여 새 장치에 Windows 10 Enterprise 배포](windows10-deploy-autopilot.md) |
