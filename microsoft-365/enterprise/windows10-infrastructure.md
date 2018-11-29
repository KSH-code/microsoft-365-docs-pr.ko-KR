---
title: Microsoft 365 Enterprise에 대 한 Windows 10 엔터프라이즈 인프라
description: Microsoft 365 Enterprise의 일부로 Pc에서 Windows 10 엔터프라이즈 배포에 필요한 단계에 대 한 고급 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise Microsoft 365 설명서, Windows 10 엔터프라이즈 배포
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869723"
---
# <a name="phase-3-windows-10-enterprise"></a>3단계: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise 많은 작업을 할 보안을 유지 하는 도구를 제공 하는 Windows 10 엔터프라이즈를 포함 합니다. Windows 10 엔터프라이즈:

- **간단 하 게 통합 되어** -오늘날 관리의 복잡성을 줄일 수 있도록 클라우드 기능 테스트 프로그램의 크기에 관계 없이 현대 IT 장치 환경입니다.
- **지능형 보안이** -는 것이 가장 안전한 Windows 릴리스 적이 하 고, 기능을 보다 효과적으로 함께 작동 하도록 설계 된 지능형 보안이 포함 된 조직을 보호 합니다.
- **창의 성과 더욱 원활 수 있도록** -잠금을 해제 하는 창의 성과 가장 생산적인 제공 하기 위해 더욱 원활 발생 하는 사용자와 선호 하는 것입니다.

Windows 10 운영 체제를 배포 하 고 조직에 적합 한 선택 다양 한 방법을 이해 해야 합니다. Microsoft 365 Enterprise 구독에 따라 밖에도 Windows 10 서비스 및 보안 기능을 최대한 활용 Windows 10을 구성 해야 합니다.

이러한 전략적 비즈니스 시나리오를 수행할 수 있도록 Microsoft 365 Enterprise에 대 한 Windows 10:

- 사용자가 조직에서 파일, 정보 및 아이디어를 검색하고, 공유하고, 진행하도록 지원하여 통합적인 지식 및 전문 정보 활용
- 유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리
- 업계에서 인증된 방식으로 제어 및 가시성에 대한 전역 표준을 준수하여 안심하고 작업 가능
- 사용자의 정보 보호 및 데이터 손실 위험 최소화
- 검색 및 외부 위협-모니터 보고서 보호 조직의 보안을 제공 하려면 신속 하 게 대처 하는 작업을 분석
- 사용자와 자신의 계정 보호
- 개인 정보 보호 및 규정 준수로 조직이 GDPR(일반 데이터 보호 규정)을 준수하도록 지원
- 보안 위험을 줄이고 IT 효율성을 극대화하면서 데스크톱 소프트웨어 및 장치를 최신 상태로 유지

자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요. 

>[!Note]
>Windows 10 Enterprise 및 Office 365 ProPlus를 함께 배포하고 [최신 데스크톱](https://www.microsoft.com/microsoft-365/modern-desktop)으로 전환하려면 [최신 데스크톱 배포 센터](http://aka.ms/howtoshift)를 참조하세요.
>

## <a name="windows-10-deployment"></a>Windows 10 배포

여러 가지 방법으로 조직에 대 한 Windows 10 Enterprise를 배포할 수 있습니다. 여기에에 대해 중점적 방법을 구성할 수 있으며 이러한 현대 배포 시나리오를 통해 Windows 10 Enterprise 이미지를 배포 합니다.

| 배포 시나리오 | 사용 하는 경우 |
|:--- |:--- |
| [System Center Configuration Manager를 사용 하 여으로 전체 업그레이드](windows10-deploy-inplaceupgrade.md) | Windows 7을 업그레이드 해야 하거나 <a href="https://aka.ms/windows-10-release-information" target="_blank">현재 버전</a> 의 Windows 10 엔터프라이즈에 Windows 8.1 컴퓨터 및 컴퓨터에서 <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (현재 분기)</a>와 현재 관리 하는 경우이 옵션을 선택 합니다. |
| [Windows 작업을 자동화할을 사용 하 여](windows10-deploy-autopilot.md) | Windows 10 Enterprise, 1703 또는 나중에 미리 설치 된 버전을 포함 하는 새 Windows 컴퓨터를 설정 하는 경우이 옵션을 선택 합니다. 최종 사용자가 작업을 입력 하 여 원하는 구성을 사용 하 여 설치를 시작 되거나 계정 자격 증명을 학교 됩니다. |

이러한 배포 시나리오는 조직의 요구 사항에 맞지 않는 하는 경우에 다른 시나리오에 대 한 설명 수 있으며 [Windows 10 배포 시나리오](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)에서 각각의 제한 사항 및 기능을 이해 수 있습니다. 사용자가 직접 <a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 배포 계획을</a> 수도 있습니다.

이러한 문서와 함께 Windows 10에 대 한 자세한를 확인할 수 있습니다.

- [Microsoft 365 Enterprise 제품 페이지](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [배포 및 Windows 10 업데이트](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>추가 서비스 및 기능
Windows 10 엔터프라이즈 배포의 일부로, 이러한 추가 서비스 및 기능을 추가할 수 있습니다.

### <a name="windows-analytics"></a>Windows Analytics

Windows 진단 데이터를 사용 하 여 작업의 효율성과 환경의 Windows 10 장치의 상태에 세부 정보 파악 하는데 도움이 되는 다양 하 고 이들 정보를 제공 합니다.

* 업그레이드 준비-업그레이드 준비 Windows 10으로 이동 하 고 새 Windows 10 기능 업데이트를 통해 최신 상태를 유지 하는데 도움이 됩니다. 
* IT 관리자가 모든 추가 인프라 요구 사항 없이 모든 Windows 10 장치를 전체적으로 볼 수 있는 업데이트 규정 준수-업데이트 준수 예정입니다.
* 장치 상태-사전 검색 및 최종 사용자 영향을 받는 문제를 수정 하려면 장치 상태를 사용할 수 있습니다.

자세한 내용은 [Windows 분석 개요 (영문)을](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) 참조 하십시오.

### <a name="windows-security"></a>Windows 보안

Windows 10 위협 으로부터, 도움말 장치로, 보안 및 액세스 제어를 도와줄를 보호 하는 기능을 제공 합니다. Windows 10과 함께 시작 부분에서 장치 오른쪽을 보호 하는 중요 한 보안 기능 얻을 수 있습니다. Microsoft 365 E3 비즈니스, Windows Defender 응용 프로그램 제어 및 Windows 정보 보호에 대 한 Windows Hello 등의 보안 기능을 추가합니다. Microsoft 365 e 5와 Microsoft 365 E3 보안 및 클라우드 기반 보안 기능 및 Windows Defender 고급 위협 보호에서 모든 보호를 가져옵니다. 

Windows 10 Enterprise 및 배포, 관리, 구성 하는 방법 세 주요 보안 기능 문제해결에 대 한 get 지침 얻을 수 있는 보안 기능에 대 한 자세한 내용은 참조 하십시오. [5 단계: Windows 10 엔터프라이즈 배포 보안 기능](windows10-enable-security-features.md)합니다.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

Microsoft 내의 내밀기 고 회사를에 대 한 계획, 배포 및 Windows 10에 대 한 업데이트를 관리 하는 방법에 대해 알아봅니다 참조 하십시오.

- [조직의 원활한 Windows 10 배포 준비](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Microsoft에서 Windows를 서비스로 채택](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Microsoft의 Windows 10dmf 현재 위치 업그레이드 방식으로 배포](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [비즈니스용 Windows Hello를 통해 강력한 사용자 인증 구현](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Windows 10 배포: Microsoft IT의 팀과 트릭](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)(비디오)
- [Windows Defender ATP로 정교한 위협 감지 지원](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Windows Defender 및 Windows Defender ATP로 최신 엔터프라이즈 보안 유지](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)(비디오)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso의 Microsoft 365 Enterprise 사용 방식

Contoso Corporation, 가상의 하지만 전형적인 다국적 비즈니스, [Windows 10 Enterprise를 배포](contoso-win10.md)하는 방법을 참조 하십시오.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Windows 10 Enterprise에 대 한 조직 준비](windows10-prepare-your-org.md) |
