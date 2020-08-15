---
title: Microsoft 365에 대 한 장치 관리 로드맵
keywords: Microsoft 365, enterprise for microsoft 365, Microsoft 365 설명서, 모바일 장치 관리, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Microsoft 365에 대 한 장치 관리를 설정 하기 위한 로드맵
ms.openlocfilehash: 1c5a06c75ede11697e2ecf17c47eb035e78dcd27
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692520"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365에 대 한 장치 관리 로드맵


엔터프라이즈에 대 한 Microsoft 365에는 조직 내에서 장치 및 해당 앱을 관리 하는 데 도움이 되는 기능이 포함 되어 있습니다. 모바일 장치 관리는 조직의 리소스를 보호 하 고 보호 하는 데 도움이 됩니다.

장치 관리에는 두 가지 옵션이 있습니다.

## <a name="microsoft-intune"></a>Microsoft Intune

Intune에서는 MDM (모바일 장치 관리) 또는 MAM (모바일 응용 프로그램 관리)를 사용 하 여 조직에 대 한 액세스를 관리할 수 있는 옵션을 제공 합니다. MDM은 사용자가 Intune에서 장치를 "등록" 하는 경우입니다. 등록 된 사용자는 관리 되는 장치 이며 조직에서 사용 하는 모든 정책, 규칙 및 설정을 받을 수 있습니다. 예를 들어 특성 앱을 설치 하 고 암호 정책을 만들고 VPN 연결을 설치 하는 등의 다양 한 방법을 사용할 수 있습니다.

개인 장치를 사용 하는 사용자는 장치를 등록 하거나 Intune 및 정책으로 관리 하지 않을 수 있습니다. 하지만 여전히 조직의 리소스 및 데이터를 보호 해야 합니다. 이 시나리오에서는 MAM을 사용 하 여 앱을 보호할 수 있습니다. 예를 들어 장치에서 SharePoint에 액세스할 때 사용자가 PIN을 입력 해야 하는 MAM 정책을 사용할 수 있습니다.

또한 개인 또는 조직 소유 장치를 관리 하는 방법을 결정 합니다. 사용 방식에 따라 장치를 다르게 처리할 수도 있습니다. 

[여기](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)에서 시작 합니다.

## <a name="basic-mobility-and-security"></a>기본 이동성 및 보안
 
이는 Microsoft 365에 기본적으로 제공 되며, Iphone, Ipad, Androids 및 Windows 휴대폰 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다. 디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다. 

[여기](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)에서 시작 합니다.
 
## <a name="identity-and-device-access-recommendations"></a>ID 및 장치 액세스 권장 사항

Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. 장치 액세스용으로이 단계에 나와 있는 단계와 함께 다음 문서의 권장 사항과 설정을 사용 합니다.

- [필수 구성 요소](identity-access-prerequisites.md)
- [일반 ID 및 장치 액세스 정책](identity-access-policies.md)

## <a name="how-microsoft-does-device-management-for-microsoft-365"></a>Microsoft에서 microsoft 365 장치 관리를 수행 하는 방법

Microsoft의 IT 전문가가 [EMS를 사용 하 여 장치를 관리](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)하는 방법을 알아봅니다.

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso에서 Microsoft 365에 대 한 장치 관리를 수행 하는 방법

Contoso Corporation (가상의 대표적인 다국적 기업)이 Microsoft 365 클라우드 서비스와 함께 [모바일 장치 관리 인프라를 배포](contoso-mdm.md) 하는 방법을 알아봅니다.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)
