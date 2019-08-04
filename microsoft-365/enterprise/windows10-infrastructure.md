---
title: Microsoft 365 Enterprise 용 Windows 10 Enterprise 인프라
description: Microsoft 365 Enterprise의 일부로 Pc에 Windows 10 Enterprise를 배포 하는 데 필요한 단계에 대 한 간략 한 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, Windows 10 Enterprise, 배포
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 450b14fb82483bd83e0c83dace173540d0281868
ms.sourcegitcommit: 12fbb429dba7517220191d90816e235583943fe0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33623132"
---
# <a name="phase-3-windows-10-enterprise"></a>3단계: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise에는 더 많은 작업을 수행 하 고 보안을 유지 하는 도구를 제공 하는 Windows 10 Enterprise가 포함 되어 있습니다. Windows 10 Enterprise:

- **는 간단한 기능을 위해 통합 되어** 오늘 최신 IT 장치 환경을 관리 하는 복잡성을 줄이는 데 도움을 줄 수 있습니다 (크기에 관계 없음).
- **지능형 보안** 기능을 사용 하는 것이 가장 안전한 Windows 릴리스가 며, 함께 작동 하도록 설계 된 지능형 보안 기능을 통해 조직을 보다 효율적으로 보호할 수 있습니다.
- **팀 작업** 및 팀 작업의 향상 된 기능을 사용 하 여 사용자와 공동으로 작업할 수 있는 가장 생산적인 환경을 제공 합니다.

Windows 10 운영 체제를 배포 하 고 조직에 적합 한 시스템을 선택할 수 있는 다양 한 방법을 이해 해야 합니다. Microsoft 365 Enterprise 구독에 따라 Windows 10 서비스 및 보안 기능을 구성 하는 데 필요한 windows 10 서비스가 제공 됩니다.

Windows 10에서는 Microsoft 365 Enterprise에 대 한 다음과 같은 전략적 비즈니스 시나리오를 사용할 수 있습니다.

- 사용자가 조직에서 파일, 정보 및 아이디어를 검색하고, 공유하고, 진행하도록 지원하여 통합적인 지식 및 전문 정보 활용
- 유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리
- 업계에서 인증된 방식으로 제어 및 가시성에 대한 전역 표준을 준수하여 안심하고 작업 가능
- 사용자의 정보 보호 및 데이터 손실 위험 최소화
- 외부 위협에 대 한 감지 및 보호--조직 보안을 제공 하기 위한 신속한 대응 활동을 모니터링 하 고 보고서를 작성 하 고 분석 합니다.
- 사용자 및 계정 보호
- 개인 정보 보호 및 규정 준수로 조직이 GDPR(일반 데이터 보호 규정)을 준수하도록 지원
- 보안 위험을 줄이고 IT 효율성을 극대화하면서 데스크톱 소프트웨어 및 장치를 최신 상태로 유지

자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요. 

>[!Note]
>Windows 10 Enterprise 및 Office 365 ProPlus를 함께 배포하고 [최신 데스크톱](https://www.microsoft.com/microsoft-365/modern-desktop)으로 전환하려면 [최신 데스크톱 배포 센터](http://aka.ms/howtoshift)를 참조하세요.
>

## <a name="windows-10-deployment"></a>Windows 10 배포

조직에 Windows 10 Enterprise를 배포 하는 방법에는 여러 가지가 있습니다. 여기서는 이러한 최신 배포 시나리오를 통해 Windows 10 Enterprise 이미지를 구성 및 배포 하는 방법에 대해 중점적으로 설명 합니다.

| 배포 시나리오 | 사용 하는 경우 |
|:--- |:--- |
| [현재 위치 업그레이드로 System Center Configuration Manager 사용](windows10-deploy-inplaceupgrade.md) | Windows 7 또는 Windows 8.1 컴퓨터를 <a href="https://aka.ms/windows-10-release-information" target="_blank">현재 버전</a> 의 Windows 10 Enterprise로 업그레이드 해야 하 고 컴퓨터가 현재 <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (현재 분기)</a>를 사용 하 여 관리 되는 경우이 옵션을 선택 합니다. |
| [Windows Autopilot 사용](windows10-deploy-autopilot.md) | Windows 10 Enterprise, 버전 1703 이상 사전 설치 된 새 Windows 컴퓨터를 설정 하는 경우이 옵션을 선택 합니다. 최종 사용자는 회사 또는 학교 계정 자격 증명을 입력 하 여 원하는 구성을 사용 하 여 설치 프로그램을 시작 합니다. |

이러한 배포 시나리오가 조직의 요구 사항에 적합 하지 않은 경우에는 다른 시나리오에 대해 알아보고 [Windows 10 배포 시나리오](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)에서 각각의 기능과 제한 사항을 이해할 수 있습니다. 또한 직접 <a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 배포를 계획할</a> 수 있습니다.

다음 문서를 사용 하 여 Windows 10에 대 한 자세한 내용을 확인할 수 있습니다.

- [Microsoft 365 Enterprise 제품 페이지](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Windows 10 배포 및 업데이트](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>추가 서비스 및 기능
Windows 10 Enterprise 배포의 일환으로 이러한 추가 서비스와 기능을 추가할 수 있습니다.

### <a name="windows-analytics"></a>Windows Analytics

Windows는 진단 데이터를 사용 하 여 사용자 환경에서 Windows 10 장치의 운영 효율성과 상태를 심층적으로 파악할 수 있도록 다양 한 작업 가능 정보를 제공 합니다.

* 업그레이드 준비 상태-업그레이드 준비 상태는 Windows 10으로 이동 하 고 새로운 Windows 10 기능 업데이트를 최신 상태로 유지 하는 데 도움이 됩니다. 
* 업데이트 준수-업데이트 준수는 추가 인프라 요구 사항 없이 모든 Windows 10 장치를 전체적으로 확인 하려는 IT 관리자를 대상으로 합니다.
* 장치 상태-장치 상태를 사용 하 여 최종 사용자에 게 영향을 주는 문제를 사전에 검색 하 고 수정할 수 있습니다.

자세한 내용은 [Windows 분석 개요](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) 를 참조 하세요.

### <a name="windows-security"></a>Windows 보안

Windows 10에서는 위협 으로부터 보호 하 고, 장치를 보호 하 고, 액세스 제어에 도움을 주는 기능을 제공 합니다. Windows 10을 사용 하는 경우 시작에서 바로 장치를 보호 하는 중요 한 보안 기능을 얻게 됩니다. Microsoft 365 E3 Windows Hello for Business, Windows Defender Application Control 및 Windows Information Protection과 같은 보안 기능을 추가 합니다. Microsoft 365 E5를 사용 하면 Microsoft 365 E3 보안의 모든 보호 기능과 클라우드 기반 보안 기능 및 Windows Defender Advanced Threat Protection이 제공 됩니다. 

Windows 10 Enterprise에서 제공 하는 보안 기능에 대 한 자세한 내용을 알아보고 3 가지 주요 ecurity 기능을 배포, 관리, 구성 및 문제를 해결 하는 방법에 대 한 지침을 확인 하려면 [5 단계: Windows 10 Enterprise 보안 기능 배포](windows10-enable-security-features.md)를 참조 하세요.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

Microsoft 내부를 살펴보고 회사에서 [windows 10 Enterprise를 배포 하 고 강력한 인증, Intune 및 Windows DEFENDER ATP를 사용](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6)하는 방법을 알아보세요.

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso의 Microsoft 365 Enterprise 사용 방식

Contoso Corporation (가상의 대표적인 다국적 기업 비즈니스)과 [Windows 10 Enterprise를 배포](contoso-win10.md)하는 방법을 참조 하세요.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Windows 10 Enterprise에 대 한 조직 준비](windows10-prepare-your-org.md) |
