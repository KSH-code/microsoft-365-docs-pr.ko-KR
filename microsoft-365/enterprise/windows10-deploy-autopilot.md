---
title: Windows Autopilot를 사용 하 여 새 장치에 Windows 10 Enterprise 배포
description: Windows Autopilot를 사용 하 여 Windows 10 Enterprise를 구성 및 배포 하기 위한 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, Windows 10 Enterprise, deployment, Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 244aa9a2749c41471760c5263a6df6d745e5ade6
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302945"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>3 단계: Windows Autopilot를 사용 하 여 새 장치에 Windows 10 Enterprise 배포

*이 문서는 Microsoft 365 Enterprise E3 및 E5 버전에 모두 적용 됩니다.*

![3단계: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

새 Windows 10 Pc가 있는 경우 Windows Autopilot을 사용 하 여 조직의 OOBE (기본 제공 경험)를 사용자 지정 하 고 앱 및 설정이 이미 구성 된 새 시스템을 배포할 수 있습니다. 배포할 이미지, 주입할 드라이버 및 관리할 인프라가 없습니다. 사용자는 IT 관리자에 게 문의 하지 않아도 배포 프로세스를 독립적으로 진행할 수 있습니다.

새 Windows 10 장치를 설정 하 고 사전 구성할 수 있으며 Windows Autopilot을 사용 하 여 생산적으로 사용할 준비가 되었습니다. 혜택 및 Windows Autopilot 시나리오를 비롯 한 Windows Autopilot에 대 한 자세한 내용은 [Overview For Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)를 참조 하십시오. 준비가 되 면 다음 부분에 따라 새 장치 설정을 시작 합니다.

## <a name="the-windows-autopilot-deployment-process-poster"></a>Windows Autopilot 배포 프로세스 포스터

Windows Autopilot 포스터는 세로 모드 (11x17)의 두 페이지로 되어 있습니다. 아래 이미지를 클릭 하면 브라우저에서 PDF를 볼 수 있습니다. 

[![Autopilot 포스터를 사용하여 Windows 10 배포](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=RWOcP%2BhJZYpYcGKMhuTUEL6lcuWdBFefqR%2BQQfmj6IM%3D&st=2019-11-12T23%3A48%3A59Z&se=2019-11-13T23%3A58%3A59Z&sp=r)

[PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf)나 [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx) 형식으로도 포스터를 다운로드 할 수 있습니다.

## <a name="part-1-start-windows-autopilot-deployment"></a>1 부: Windows Autopilot 배포 시작
[Windows Autopilot 개요](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) 를 참조 하세요.

1. Windows Autopilot 배포에 대 한 필수 구성 요소 및 완료 방법을 설명 합니다. 필수 구성 요소는 다음과 같습니다.
    - **장치 등록 및 OOBE 사용자 지정**

        장치를 등록 하려면 하드웨어 ID를 취득 하 여 등록 해야 합니다. Microsoft는 다양 한 하드웨어 공급 업체와 협력 하 여 필요한 정보를 제공 하거나 대신 업로드 하도록 합니다. 장치의 하드웨어 ID와 함께 .csv 파일을 생성 하는 PowerShell 스크립트를 사용 하 여이 정보를 직접 캡처할 수도 있습니다.

        장치를 등록 한 후에는 개인 정보 설정 및 EULA 건너뛰기를 포함 하 여 구성할 수 있는 OOBE 사용자 지정 옵션이 있습니다.

    - **OOBE에 대한 회사 브랜딩**

        이를 통해 장치 OOBE 중에 표시 되는 브랜딩을 추가할 수 있습니다.

    - **Microsoft Intune에서 MDM 자동 등록**
        
        자동 등록을 사용 하면 사용자가 장치를 Azure AD에 연결할 때 Intune에서 Windows 10 장치를 등록 하 여 장치를 관리할 수 있습니다. 등록 하려면 사용자가 자신의 회사 계정을 개인 소유 장치에 추가 하거나 회사 소유의 장치를 Azure AD에 가입 합니다. 백그라운드에서는 Intune을 사용 하 여 장치에 대 한 관리도 등록 됩니다.

    - **Windows Autopilot에서 사용되는 클라우드 서비스에 대한 네트워크 연결**

        Windows Autopilot 배포 프로그램은 다양 한 클라우드 서비스를 사용 하 여 장치를 생산적 상태로 가져오고, 이러한 서비스는 Windows Autopilot 장치로 등록 된 장치에서 액세스할 수 있어야 합니다. 

    - **장치에는 Windows 10, 버전 1703 이상이 미리 설치되어 있어야 합니다.**

2. 조직의 Windows Autopilot 배포 프로그램에 대해 설명 하 고 선택 합니다. 다음 배포 프로그램 중에서 선택할 수 있습니다.
    - **비즈니스용 Microsoft Store**
    - **Microsoft Intune**
    - **파트너 센터**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>2 부: Microsoft 365 용 Windows 10 장치 설정
Microsoft 365 사용자를 위해 Windows 장치를 설정 하기 전에 모든 Windows 장치가 Windows 10, 버전 1703 (크리에이터 업데이트) 이상을 실행 하 고 있는지 확인 합니다.

조직의 모든 Windows 장치가 Windows 10 크리에이터 업데이트로 업그레이드 되었거나 이미 Windows 10 크리에이터 업데이트를 실행 하 고 있는 경우 이러한 장치를 조직의 Azure Active Directory에 연결할 수 있습니다.

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>새로운 또는 새로 업그레이드 된 Windows 10 장치 설치
Windows 10 크리에이터 업데이트 (또는 이상)를 실행 하는 새 장치 또는 Windows 10 크리에이터 업데이트 이상으로 업그레이드 한 장치에서 windows 10 OOBE를 사용 하 여 장치를 설정 하려면 다음 단계를 수행 합니다.

1. 무선 네트워크가 구성 되어 있지 않은 경우 유선 또는 이더넷 연결을 통해 장치를 인터넷에 연결 해야 합니다.
2. Windows 장치 설치 환경을 진행 합니다. 새로 만들거나 다시 설정 하는 장치에서는 설정 환경이 **Let의 시작 지역으로 시작 합니다. 적절 하나요?** 화면의.
3. **어떻게 설정하시겠어요?** 페이지에 도달할 때까지 Windows 10 장치 설정을 진행합니다. 여기에서 **조직에 대해 설정을**선택 합니다.
4. Microsoft 365 사용자 계정 및 암호를 사용 하 여 로그인 합니다. 사용자 암호 설정에 따라 암호를 업데이트 하 라는 메시지가 표시 될 수 있습니다. 
5. Windows 10 장치 설정을 완료합니다.

작업이 완료 되 면 디바이스가 조직의 Azure AD에 연결 됩니다.

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>기본 설치가 이미 완료 된 장치 설정
장치에 Windows 10 크리에이터 업데이트 (또는 이상)가 있고 기본 설정 설정이 이미 완료 된 경우에는 다음 단계를 수행 합니다.

1. Windows 10을 실행 하는 사용자의 Windows PC, 버전 1703 (작성자 업데이트)에서 **windows** 로고를 선택 하 고 **설정** 아이콘을 선택 합니다.
2. **설정**에서 **계정**으로 이동합니다.
3. **정보** 페이지에서 **회사 또는 학교** > **연결**액세스를 선택 합니다.
4. **회사 또는 학교 계정 설정** 대화 상자의 **대체 작업**에서 **Azure Active Directory에이 장치 가입**을 선택 합니다.
5. **로그인 시작** 페이지에서 회사 또는 학교 계정을 입력 하 고 **다음**을 선택 합니다.
6. **암호 입력** 페이지에서 암호를 입력 하 고 **로그인**을 선택 합니다.
7. **조직** 확인 페이지에서 정보가 올바른지 확인 하 고 **참가**를 선택 합니다.
8. **완료 되었습니다!** 페이지에서 **완료**를 선택 합니다.

작업을 마치면 사용자가 조직의 Azure AD에 연결 됩니다.

### <a name="verify-the-device-is-connected-to-azure-ad"></a>장치가 Azure AD에 연결되었는지 확인
다음 단계에 따라 Azure AD에서 장치의 동기화 상태를 확인 한 다음 장치에서 Microsoft 365 계정을 사용 하기 시작 합니다. 

1. **설정을**엽니다.
2. **회사 또는 학교 액세스** 페이지에서 **연결 <organization name> ** 프로그램 영역을 선택 하 여 단추 **정보** 를 표시 하 고 **연결을 끊습니다**.
3. **정보** 를 선택 하 여 동기화 상태를 가져옵니다.
4. **동기화 상태** 페이지에서 **동기화** 를 선택 하 여 PC에 최신 모바일 장치 관리 정책을 가져옵니다.
5. Microsoft 365 계정을 사용 하려면 Windows **시작** 단추로 이동 하 여 현재 계정 사진을 마우스 오른쪽 단추로 클릭 한 다음 계정 **전환을** 선택 합니다.
6. 조직 전자 메일 및 암호를 사용 하 여 로그인 합니다.

엔터프라이즈 환경에서 Windows 10을 사용할 때 문제가 발생 하면 [가장 일반적인 문제에 대 한 주요 Microsoft 지원 솔루션](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)을 참조할 수 있습니다. 이러한 리소스에는 기술 자료 문서, 업데이트 및 라이브러리 아티클이 포함 됩니다.

중간 검사점으로 이 단계에 해당하는 [종료 조건](windows10-exit-criteria.md#crit-windows10-step3)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![4단계](./media/stepnumbers/Step4.png)| [장치 상태 및 준수 모니터링](windows10-enable-windows-analytics.md) |
