---
title: '1단계: Microsoft 365 Enterprise에 대한 네트워킹 인프라'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise에 대한 네트워킹 인프라를 배포하는 단계입니다.
ms.openlocfilehash: d575d8c3156ac1fc1a8a2bca96c875d4587ebf05
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869980"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>1단계: Microsoft 365 Enterprise에 대한 네트워킹 인프라

![](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 Enterprise에는 Office 365 및 Windows Intune이 EMS(Enterprise Management + Security)의 일부로 포함되어 있습니다. 이러한 클라우드 기반 서비스는 둘 다 인터넷 또는 전용 회로를 통한 클라이언트 장치 연결의 보안, 성능 및 안정성을 기반으로 합니다. 이러한 서비스를 호스팅하고 전 세계 고객에게 제공하기 위해 Microsoft는 성능 및 통합을 강조하는 네트워킹 인프라를 설계했습니다. 

이 단계에서는 Microsoft 365 Enterprise의 클라우드 서비스에 대한 뛰어난 성능의 연결을 만들기 위한 주요 고려 사항을 안내합니다. 개요는 [Office 365 네트워킹 원칙](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)을 참조하세요.

>[!Note]
>네트워킹 인프라를 이미 배포한 경우 이 단계에 대한 [종료 조건](networking-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인합니다.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Microsoft 365 Enterprise 네트워킹 인프라 계획 및 배포 

다음 단계를 사용하여 Microsoft 365 Enterprise의 요구 사항 및 기능에 적합한 네트워킹 인프라를 구축할 수 있습니다.

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Microsoft 365에 맞게 네트워크 준비](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[각 사무실에 대해 로컬 인터넷 연결 구성](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[네트워크 헤어핀 방지](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[트래픽 바이패스 구성](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[클라이언트 및 Office 365 서비스 성능 최적화](networking-optimize-tcp-performance.md)|


이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](networking-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise으로의 마이그레이션을 수행하는 방법

Microsoft 내부 상황을 살펴보고 [Microsoft Office 365에 대한 네트워크 성능 최적화](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)에서 Microsoft가 Office 365 클라우드 서비스를 위해 Microsoft 네트워크를 준비하고 최적화한 방식을 알아봅니다.

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso의 Microsoft 365 Enterprise 사용 방식

가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스에 맞게 [네트워크를 최적화](contoso-networking.md)한 방식을 알아봅니다.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Microsoft 365에 맞게 네트워크 준비](networking-provide-bandwidth-cloud-services.md)|

