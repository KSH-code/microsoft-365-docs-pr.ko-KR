---
title: 3단계 - Office 및 LOB 앱 배달
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
description: Office 및 LOB 앱을 배달하는 방법을 알아봅니다.
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870373"
---
# <a name="step-3-office-and-lob-app-delivery"></a>3단계: Office 및 LOB 앱 배달

이제 Office 및 LOB(기간 업무) 앱을 전달할 준비가 되었습니다. 이 작업을 수행하는 방법은 다양하며 이중에는 몇 가지 흥미로운 새 옵션도 포함되어 있습니다. 이러한 방법들을 차근차근 검토하고 현재 요구에 가장 적합한 방법을 선택하세요.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>3단계: Office 및 LOB 앱 배달</strong></p>
<p>앱이 패키지되고 자동 방식으로 설치할 준비가 되었는지 확인합니다. Office 365 ProPlus가 포함된 간편 실행 패키지에 어떻게 Office 앱을 구성하고, 전달하고, 최신 상태로 유지하는 새 옵션이 포함되어 있는지 알아봅니다.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>Office 및 LOB 앱 준비는 Office 및 LOB를 설치 및 관리하기 위한 옵션을 설명하는 권장 배포 프로세스 사이클의 세 번째 단계입니다. 성공적인 배포를 위해서는 처음 두 단계를 건너뛰지 않도록 합니다. 전체 데스크톱 배포 프로세스를 보려면 [최신 데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.
>

32비트 또는 64비트 컴파일 버전으로만 사용할 수 있는 응용 프로그램도 있고(예: Office 365 ProPlus), 32비트 및 64비트 네이티브 컴파일 코드로 사용할 수 있는 응용 프로그램도 있지만 가장 중대한 결정 사항은 어떤 버전을 배포할지입니다. 새 장치에서 추가적인 계산 성능 및 RAM을 사용하려면 64비트 버전을 사용할 수 있지만, 그 전에 발생할 수 있는 추가 기능 또는 파일 관련 호환성 문제를 해결해야 합니다. 이를 위해 계속하기 전에 1단계 장치 및 앱 준비를 다시 방문해야 할 수 있습니다.

방해 요인이 없는 경우 Microsoft Office를 비롯한 모든 앱을 64비트 버전으로 배포하는 것이 좋습니다. 64비트 네이티브 컴파일 앱은 최상의 성능을 제공하며 향후에도 사용할 수 있는 옵션입니다.

Windows에 앱을 설치하는 데 사용할 수 있는 여러 방법과 모델이 있으며 전달 옵션을 살펴보겠습니다.

[Windows 10 응용 프로그램 관리](https://docs.microsoft.com/ko-KR/windows/application-management/)

## <a name="msi-based-deployments"></a>MSI 기반 배포

LOB(기간 업무) 앱의 경우 MSI 기반 패키지 또는 실행 파일을 사용하고, 앱을 OS 배포 작업 시퀀스의 일부로 설치하게 됩니다. Windows 10은 이러한 패키지에서 계속 작동합니다.

System Center Configuration Manager 및 Microsoft Intune 등의 소프트웨어 배포 도구 또한 MSI 패키징 앱을 전달하도록 최적화됩니다. Windows 10에서 앱의 유효성을 검사하고 나면, 앱 전달을 위해 System Center Configuration Manager(현재 분기)를 사용할 수 있습니다. Microsoft Intune에서 회사 포털을 사용하는 경우 조직에서 사용할 수 있는 IT 승인 앱의 선택 범위를 최신 응용 프로그램을 포함하도록 확장할 수 있으며 사용자가 필요한 항목을 자체 선택하도록 할 수 있습니다.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>PC 이미징

다른 인기 있는 앱 전달 방법은 PC 이미징입니다. 이 경우 응용 프로그램은 작업 시퀀스를 통해 설치되거나 샘플 PC에 수동으로 설치된 후, 필요한 응용 프로그램이 미리 설치된 시스템 이미지가 캡처됩니다. 빌드 및 캡처하는 이미징 접근 방법은 새 PC를 프로비전할 때는 시간을 절약할 수 있지만 이미지 내의 운영 체제 및 앱을 빠르게 사용 중지될 수 있습니다. Windows 10 및 Office 365 ProPlus의 누적 업데이트 모델은 이 문제를 해결하는 데 도움이 되지만 완전히 해결하지는 못합니다. 이때문에 응용 프로그램이 배포 시에 이미지 외부에서 설치되는 씬 이미지 방법이 권장됩니다.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

Office 365 ProPlus를 이미지에 포함하지 않으려는 경우 이 기능이 사용자 기반 활성화라는 점을 기억하도록 합니다. 즉, 시스템 관리자가 미리 활성화할 수 없습니다. Office 배포 도구를 사용하여 이미징하는 장치에 Office를 미리 설치하고 사용자 로그인을 건너뜁니다. 사용자는 로그인할 수 있고, 해당 활성화가 할당되며, 처음 사용할 때 로그인을 활용하는 다른 기능을 활용할 수 있습니다.

[운영 체제를 설치하는 작업 시퀀스 만들기](https://docs.microsoft.com/ko-KR/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a>간편 실행 

Office 365 ProPlus는 간편 실행을 통해 설치되며, 간편 실행은 향후 출시될 Windows용 Office 2019의 모든 버전에서 MSI 기반 패키징을 대신합니다. 이 기능은 더 빠른 설치, 더 빠르고 효율적인 업데이트 및 더 깔끔한 제거를 비롯한 다양한 이점을 제공합니다.

간편 실행을 통해 전달되는 프로그램은 컴퓨터의 가상 응용 프로그램 환경에서 실행되므로, 충돌 없이 다른 응용 프로그램과 공존합니다. 또한 MSI 기반 패키지에 필요한 디스크 공간의 절반 정도만 차지합니다. 그뿐 아니라 간편 실행은 프로그램 스트리밍을 지원하므로, 사용자는 처음부터 Office가 완전히 설치될 때까지 기다리지 않고, 가장 일반적으로 사용하는 기능을 먼저 스트리밍하여 몇 분 안에 Office 응용 프로그램 사용을 시작할 수 있습니다. 이러한 기능은 초기 배포에서만 중요한 것이 아닙니다. 사용자에게 최소한의 영향을 미치면서 백그라운드에서 업데이트를 원활하게 스트리밍할 수도 있습니다.

System Center Configuration Manager를 사용하는 경우 Office 365 ProPlus의 브로드 배포에도 사용할 수 있습니다. System Center Configuration Manager(현재 분기)는 업데이트된 Office 사용자 지정 도구에 대한 네티이브 지원, 간편 실행을 위한 설치 시 패키지 사용자 지정, 설치 후 소프트웨어 업데이트 관리에 대한 네이티브 지원도 제공합니다.

[Office 365 ProPlus 배포 가이드](https://docs.microsoft.com/ko-KR/deployoffice/deployment-guide-for-office-365-proplus)

[Office 365 ProPlus로 업그레이드하는 경우 기존 MSI 버전의 Office 제거](https://docs.microsoft.com/ko-KR/deployoffice/upgrade-from-msi-version)

[Configuration Manager를 사용하여 Office 365 ProPlus 관리](https://docs.microsoft.com/ko-KR/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[Microsoft Intune을 사용하여 Office 365 앱을 Windows 10 장치에 할당](https://docs.microsoft.com/ko-KR/intune/apps-add-office365)

## <a name="browser-based-apps"></a>브라우저 기반 앱

브라우저 기반 응용 프로그램이 예상대로 계속 작동하도록 하기 위해 고려해야 할 몇 가지 사항이 있습니다. Microsoft Edge와의 호환성 문제가 알려져 있는 특정 웹 사이트 및 앱이 있는 경우 해당 웹 사이트가 자동으로 Internet Explorer 11을 사용하여 열리도록 Enterprise Mode 사이트 목록을 사용할 수 있습니다.

또한 인트라넷 사이트가 Microsoft Edge에서 제대로 작동하지 않는 것으로 확인될 경우 모든 인트라넷 사이트가 자동으로 Internet Explorer 11을 사용하여 열리도록 설정할 수 있습니다. 이 프로세스는 XML 파일을 사용하여 각 사이트에 IE11이 사용되는지 여부를 제어하며 그룹 정책을 사용하여 설정을 적용합니다.

지금까지 잘 알려진 배포 방법을 살펴보았습니다. 하지만 앱 배포에 대해 다음과 같은 두 가지가 새로운 방법을 고려할 수 있습니다.

[엔터프라이즈 모드란?](https://docs.microsoft.com/ko-KR/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>비즈니스용 Microsoft Store 

비즈니스용 Microsoft Store는 대규모의 무료 및 유료 앱을 검색, 확보, 관리하고 Windows 10 장치에 배포하는 유연한 방법을 제공합니다. IT 관리자의 경우 사용자 고유의 앱과 함께 선택한 Microsoft 스토어 앱을 자체 개인 저장소에 게시하고, 필요에 따라 라이선스를 할당하고 재사용할 수 있습니다. 따라서 사용자는 이 스토어로만 이동되므로, 승인된 앱만 찾아서 설치할 수 있습니다.

스토어 앱은 기본적으로 UWP 앱으로 빌드될 수 있고, 데스크톱 브리지를 사용하여 기존 앱을 스토어용으로 다시 패키지한 후 Windows 10용 최신 환경을 추가할 수 있습니다. Windows 10 환경을 향상시키는 데 사용하는 코드 외에는 앱은 변경되지 않은 상태를 유지하며, 전체 신뢰 사용자 모드에서 계속 실행됩니다.

## <a name="msix-containerization"></a>MSIX 컨테이너화

응용 프로그램 패키지에 대한 새 옵션은 MSIX입니다. MSIX는 Windows에서 사용할 수 있는 컨테이너화 기술을 사용하며, 간편 실행, UWP 및 MSI 패키징의 유용한 측면을 함께 제공합니다. 기존 설치 관리자를 MSIX로 직접 마이그레이션하는 도구(예: EXE, MSI, APPV 및 APPX)를 사용해보면 MSIX 컨테이너화는 오늘날 사용되는 많은 설치 기술에 대해 통합된 경로를 제공한다는 것을 알 수 있습니다. 현재 버전의 Windows에 포함 된 MSIX 지원인 최신 버전의 Windows에 포함되어 있습니다. Windows 10 RS5 이상을 실행하는 모든 장치에는 MSIX 패키징 앱을 설치 및 실행하는 데 필요한 모든 항목이 포함되어 있습니다. Windows 10은 응용 프로그램을 운영 체제와는 별도로 유지하면서 받은 MSIX 컨테이너를 동적으로 통합합니다.

컨테이너화는 시스템에서 항목을 남겨둘 수 있는 오늘날의 많은 MSI 및 EXE 기반 패키지와 달리, 패키지를 완전히 제거함을 의미합니다. 또한 응용 프로그램을 설치하기 위해 표준 사용자 자격 증명만 있으면 되며, MSIX 컨테이너를 설치하기 위해 관리자 자격 증명이 필요하지 않습니다. MSIX 컨테이너는 업데이트하는 데도 좀 더 효율적입니다. 업데이트가 게시될 때 블록 수준의 차이를 사용하여 새로운 이진 파일만 적용되므로 업데이트 페이로드가 감소하며, 더 적은 네트워크 대역폭을 사용하면서 배포는 더 빨라집니다.

[MSIX 기술 커뮤니티 사이트](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)를 통해 MSIX에 대한 추가 정보를 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[4단계: 사용자 파일 및 설정](https://aka.ms/mdd4)

## <a name="previous-step"></a>이전 단계

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[2단계: 디렉터리 및 네트워크 준비](https://aka.ms/mdd2) 