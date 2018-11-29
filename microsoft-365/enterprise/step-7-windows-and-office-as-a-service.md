---
title: '7단계: Windows 및 Office as a Service'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 사용자 환경에서 Windows 및 Office as a Service를 준비하는 방법을 알아봅니다.
ms.openlocfilehash: 5c3eb54e07b1cc5492a6d938e97286283fc47ca7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870113"
---
# <a name="step-7-windows-and-office-as-a-service"></a>7단계: Windows 및 Office as a Service

System Center Configuration Manager 현재 분기의 관리 도구 업데이트와 함께 Windows 10 및 Office 365 ProPlus의 새 기능을 포함하는 반기 채널 업데이트를 준비합니다.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>7단계: Windows 및 Office as a Service 준비</strong></p>
<p>Windows 10 및 Office 365 ProPlus는 사용자 환경 및 보안을 최신 혁신 상태로 유지하기 위해 지속적으로 새 기능을 추가하고 있습니다. 반기 및 월별 업데이트를 통해 최신 상태를 유지하는 방법, 새 서비스 모델이 작동하는 방식 및 보유하고 있는 도구와 옵션에 대해 알아봅니다.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows 및 Office as a Service는 기능에 대한 반기 업데이트를 준비하는 계획 과정을 포함하는 권장 배포 프로세스 사이클의 7번째 단계입니다. 전체 데스크톱 배포 프로세스를 보려면 [최신 데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.
>

Windows 10 및 Office 365 ProPlus 둘 다 새 서비스 옵션, 지원 모델 및 업데이트 타임라인을 도입합니다. 이러한 변화를 통해 최신 기능을 최신 상태로 유지하는 프로세스가 간소화됩니다. 이러한 업데이트와 함께, 사용자 요구를 충족하는 서비스 계획을 지원하는 새로운 구성 옵션도 제공됩니다.

[고객의 최신 데스크톱으로의 전환 지원](https://www.microsoft.com/ko-KR/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>업데이트 유형

업데이트는 두 가지 주요 범주, 즉 기능 업데이트와 누적 보안, 안정성 및 버그 픽스를 포함하는 보안 업데이트로 구분됩니다. 케이던스 측면에서, Windows와 Office는 둘 다 매년 2번, 3월 및 9월 경에 새 기능을 전달하는 반기 채널을 전달하며, 품질 및 보안 업데이트는 매월 진행됩니다. 또한 Office 365 앱의 경우에만 완전히 지원되며 새 기능과 품질 업데이트를 둘 다 포함하는 월별 채널 업데이트를 전달합니다.

데스크톱 OS 및 앱 업데이트 사이의 주기가 더 긴 경우 다음과 같은 의문이 생길 수 있습니다.

  - 업데이트가 서로 호환되나요?

  - 사용자를 계속해서 재교육해야 하나요?

  - 어떤 위험 요소가 있나요?

이러한 질문에 답변하고 새로운 기능을 좀 더 자주 전달해야 할 근거를 뒷받침하기 위해 이러한 접근 방법의 몇 가지 이점을 알아보겠습니다.

### <a name="feature-update-benefits"></a>기능 업데이트 혜택

첫째, 우리는 3년 정도마다 거대한 변화의 물결을 소개하는 과거의 모델에서 매년 2번 기능 업데이트를 포함하는 좀 더 작은 규모의 증분 변경 방식으로 전환했습니다. 보안 위협이 빠르게 진화할 뿐만 아니라 기술 추세가 빠르게 변화하는 가운데, 이러한 방식은 환경 및 보호 기능을 최신 상태로 유지하도록 합니다. 예를 들어 일부 보안 관련 업데이트는 월별 보안 업데이트 또는 바이러스 백신 서명 파일만으로는 전달할 수 없으며, 가상화 기반 보안과 같은 하위 수준의 변경 플랫폼 방식을 따를 수 있습니다.

[Windows as a service에 대한 빠른 가이드](https://docs.microsoft.com/ko-KR/windows/deployment/update/waas-quick-start)

[Windows 10 보안 기능을 사용하여 위협 완화](https://docs.microsoft.com/ko-KR/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>누적 업데이트 모델 혜택

둘째, 품질 및 보안 업데이트를 누적 업데이트 패키지로 전달하면 과거의 많은 문제점이 해결됩니다. 과거에는 매월 Windows 및 Office에 대한 수십 가지 이상의 업데이트 중에서 일부를 선택할 수 있었습니다. 짐작할 수 있는 것처럼 이러한 방식에서는 거의 불가능한 수준의 테스트 지원 매트릭스가 생성됩니다. 또한 1년 이전의 Windows 또는 Office 버전을 설치하는 경우 해당 버전이 릴리스된 이래로 전달된 모든 업데이트를 적용하는 데 수 시간이 걸릴 수 있습니다.

누적 모델을 사용하는 경우 최신 업데이트보다 항상 1 이전 버전을 사용하게 되며, 이를 통해 배포해야 하는 월별 업데이트 수는 줄어듭니다. 각 업데이트는 이전 달의 업데이트 위에 구축되며, 최신 상태로 유지해야 하는 모든 픽스를 포함합니다. 누적 업데이트는 다른 사용자에게 다시 할당되기 위해 저장소에서 대기해야 하므로 PC를 몇 달 동안 꺼둔 경우에 특히 도움이 됩니다.

[Windows as a Service 개요](https://docs.microsoft.com/ko-KR/windows/deployment/update/waas-overview)

### <a name="expanded-validation-of-updates"></a>확장된 업데이트 유효성 검사

또 다른 장점은 브로드 배포를 위해 업데이트를 롤아웃하기 전에 먼저 [Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) 및 [Windows](https://insider.windows.com/ko-KR/)의 참가자 프로그램을 통해 빌드를 릴리스하게 되며, 이를 통해 업데이트를 광범위하게 릴리스하기 전에 원격 분석 및 피드백을 수집할 수 있습니다. 참가자 프로그램은 현재, 누구에게나 열려 있으므로 업데이트를 먼저 알아볼 수 있는 기회가 됩니다. 업데이트를 출시한 다음, 수백만 가지 구성에 대한 원격 분석이 수신되므로, 업데이트를 롤아웃할 때 좀 더 예측 가능한 품질이 구현됩니다.

아울러, Office 365 ProPlus 참가자 빌드는 월별 채널 업데이트를 반영하기 때문에 Office의 반기 채널을 사용하여 Windows에 맞춰 1년에 2번 기능 업데이트를 전달할 경우, 반기 채널 대상 릴리스를 사용할 때처럼 해당 빌드도 조기에 유효성을 검사할 수 있습니다.

### <a name="supporting-management-tools"></a>관리 도구 지원

또한 Microsoft는 사용자에게 원활하게 업데이트를 배포하는 방법을 고민해왔습니다. Windows 및 Office에 대한 이러한 업데이트 및 새 기능의 롤아웃을 지원하기 위해 System Center Configuration Manager 현재 분기는 자주 업데이트됩니다.

[System Center Configuration Manager를 사용하여 Windows 10 업데이트 배포](https://docs.microsoft.com/ko-KR/windows/deployment/update/waas-manage-updates-configuration-manager)

[Configuration Manager를 사용하여 Office 365 ProPlus 관리](https://docs.microsoft.com/ko-KR/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="phased-deployment-of-updates"></a>단계별 업데이트 배포

이제 이러한 업데이트 배포를 롤아웃하는 방법을 살펴보겠습니다. 모든 릴리스에 대해, IT 부서에 3개 이상의 배포 작업 단계, 즉 유효성 검사, 파일럿 및 브로드 프로덕션 배포를 권장합니다. 일단 Windows 10 및 Office 365 ProPlus에서 시작 및 실행될 경우 월별 서비스를 사용하여 중요한 보안 및 품질 업데이트로 최신 상태를 유지한 다음, 새 기능에 대한 반기 서비스로 전환합니다.

### <a name="monthly-updating"></a>월별 업데이트

이 서비스 모델에서는 새 기능의 롤아웃을 1년에 2번으로 제한하도록 선택할 수 있으며, 필요한 경우 반기 업데이트를 건너뛰고 품질 및 보안 업데이터를 계속 받을 수 있습니다. 앞서 언급한 것처럼 월별 업데이트는 누적되므로 매월 크기가 커집니다.

#### <a name="express-updates"></a>빠른 업데이트

Windows의 “빠른 업데이트”, Office의 이진 델타 압축이라는 기술을 사용하여 다운로드 크기를 획기적으로 줄일 수 있습니다. 두 가지 방법에서 업데이트 엔진은 PC에 있는 항목을 비교하고, 해당 항목을 업데이트하는 데 필요한 차등 기능만 찾습니다.

[Windows 10 품질 업데이트 및 델타 업데이트 종료](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

비즈니스용 Windows 업데이트 및 Windows Server Update Services는 오랫 동안 빠른 업데이트를 지원했지만, 현재는 System Center Configuration Manager로 지원을 확장하고 있습니다. 따라서 여기서도 빠른 업데이트를 사용할 수 있습니다.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>이진 델타 압축

Office의 이진 델타 압축은 가장 최근의 Office 365 ProPlus 버전에서 업데이트하는 경우에만 사용됩니다. 따라서 이 방법을 사용하려면 이전 빌드에서 업데이트해야 하며 업데이트를 건너뛸 수 없습니다.

Windows 및 Office 업데이트 채널은 Configuration Manager를 통해 표준 승인 및 타기팅 프로세스를 사용하여 관리할 수 있습니다. 또한 Office 및 Windows의 정책 설정을 사용하여 관련 설정 뿐만 아니라 사용되는 업데이트 채널을 적용할 수 있습니다.

### <a name="semi-annual-updates"></a>반기 업데이트

지금까지 월별 업데이트에 대한 이러한 고려 사항을 살펴보았으므로 이제 좀 더 큰 규모의 반기 업데이트에 대해 알아보겠습니다.

장치 및 앱 준비 상태에서 살펴본 것처럼, 배포 프로세스 사이클의 1단계에서 설정한 동일한 준비 도구를 사용하여 이러한 좀 더 큰 규모의 업데이트를 준비할 수 있습니다.

비즈니스용 Windows 업데이트를 사용하는 정책 설정, System Center Configuration Manager를 통한 소프트웨어 업데이트 관리, WSUS(Windows Server 업데이트 서비스) 또는 Microsoft Intune에서 설정되는 업데이트 정책을 도구로 사용할 수 있습니다. 네트워크 대역폭이 걱정된다면 2단계: 디렉터리 및 네트워크 준비를 참조하여 장치 최적화 및 기타 피어 투 피어 캐싱 기술을 통해 네트워크 트래픽을 줄이는 옵션에 대해 알아보세요.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Windows 반기 채널](https://docs.microsoft.com/ko-KR/windows/deployment/update/waas-overview#semi-annual-channel)

[Office 365 ProPlus에 대한 반기 채널](https://docs.microsoft.com/ko-KR/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>업그레이드 작업 시퀀스

표준 소프트웨어 업데이트 관리 루틴을 통해 더 큰 기능 업데이트를 설치할 수 있지만, 많은 조직에서는 System Center Configuration Manager 또는 Microsoft Deployment Toolkit를 통해 업그레이드 작업 시퀀스를 사용하도록 선택합니다.

작업 시퀀스를 사용하면 기능 업데이트를 설치하기 전에 사용자 지정 검사 또는 작업을 만들고, 업데이트 설치 자체가 완료된 후에 사용자 지정 작업을 수행할 수 있습니다. 업데이트 후 작업에는 필요한 경우 업데이트, 드라이버 설치 및 교체, 응용 프로그램 업그레이드나 작업 표시줄 및 Windows 10 시작 개인 설정 중에 서비스를 일시적으로 중단하는 작업이 포함될 수 있습니다.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

Windows 7 컴퓨터를 Windows 10으로 마이그레이션하는 작업 시퀀스를 이미 사용 중이며 해당 도구에 대해 잘 아는 경우, 작업 시퀀스로 시작하면 좋으며 작업을 적절히 제어할 수 있습니다. 전체 업그레이드에 대해 단일 작업 시퀀스를 사용할 수 있지만 조직에서는 일반적으로 2개의 작업 시퀀스를 사용합니다. 하나는 컴퓨터의 업그레이드 준비가 되었는지 확인하는 것으로, 대상 컴퓨터에서 모든 필수 설치 파일을 사전에 준비하는 시퀀스이며, 다른 하나는 실제 업그레이드를 수행하는 시퀀스입니다. 이러한 방식을 통해 사용자 생산성이 영향을 덜 받습니다.

[Configuration Manager에서 OS를 업그레이드하는 작업 시퀀스 만들기](https://docs.microsoft.com/ko-KR/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>기능 업데이트에 대한 반기 채널 지원

[2018년 9월에 발표된 것처럼](https://www.microsoft.com/ko-KR/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), 반기 채널 업데이트의 지원 타임라인은 다음 모델을 사용합니다.

  - 버전 1607부터 시작해서 Windows 10 Enterprise 및 Education의 지원되는 모든 기능 업데이트는 원본 릴리스 날로부터 30개월 동안 지원됩니다.

  - 9월에 예정된 1809부터 시작하는 모든 향후 기능 업데이트는 릴리스 날로부터 30개월 동안 지원됩니다.

  - 3월에 예정되어 있고 1903에서 시작되는 향후 기능 업데이트는 릴리스 날로부터 18개월 동안 계속 지원됩니다.

  - Office 365 ProPlus 반기 업데이트는 18개월 동안 계속 지원됨

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>작업 시퀀스 외부의 추가 설치 자동화 옵션

업그레이드 작업 시퀀스를 사용하지 않는 경우, 설치 전 단계(설치 프로그램이 호환성 검사를 실행하기 전) 또는 커밋 전 단계(업그레이드가 적용되기 전)에 기능 업데이트 동안 사용자 지정 작업을 실행하거나 드라이버 파일을 실행할 수 있습니다.

[Windows 10 설치, 버전 1803의 새로운 기능](https://docs.microsoft.com/ko-KR/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>다음 단계 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a>[8단계: 사용자 커뮤니케이션 및 교육](https://aka.ms/mdd8)

## <a name="previous-step"></a>이전 단계 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[6단계: 운영 체제 배포 및 기능 업데이트](https://aka.ms/mdd6)