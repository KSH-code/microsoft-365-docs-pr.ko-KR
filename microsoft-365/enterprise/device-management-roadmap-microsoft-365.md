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
ms.openlocfilehash: 0efe7098f90064184f222acb671ae6f96c1b38d5
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384755"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365에 대 한 장치 관리 로드맵

엔터프라이즈에 대 한 Microsoft 365에는 조직 내에서 장치 및 해당 앱을 관리 하는 데 도움이 되는 기능이 포함 되어 있습니다. 모바일 장치 관리는 조직의 리소스를 보호 하 고 보호 하는 데 도움이 됩니다.

장치 관리에는 다음과 같은 두 가지 옵션이 있습니다.

- [Microsoft Intune](#microsoft-intune)
- [기본 이동성 및 보안](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune을 사용 하 여 모바일 장치 관리 또는 모바일 응용 프로그램 관리를 통해 조직에 대 한 액세스를 관리할 수 있습니다. 모바일 장치 관리는 사용자가 Intune에서 장치를 "등록" 하는 것입니다. 장치를 등록 한 후에는 관리 되는 장치입니다. 따라서 조직의 정책, 규칙 및 설정을 받을 수 있습니다. 예를 들어 특정 앱을 설치 하 고, 암호 정책을 만들고, VPN 연결을 설치 하는 등의 작업을 수행할 수 있습니다.

개인 장치를 사용 하는 사용자는 장치를 등록 하거나 Intune 및 조직의 정책에 따라 관리 하지 않을 수 있습니다. 하지만 여전히 조직의 리소스 및 데이터를 보호 해야 합니다. 이 시나리오에서는 모바일 응용 프로그램 관리를 사용 하 여 앱을 보호할 수 있습니다. 예를 들어 사용자가 장치에서 SharePoint Online에 액세스할 때 PIN을 입력 해야 하는 모바일 응용 프로그램 관리 정책을 사용할 수 있습니다.

또한 개인 장치 및 조직 소유 장치를 관리 하는 방법을 결정 합니다. 사용 방식에 따라 장치를 다르게 처리할 수도 있습니다.

## <a name="basic-mobility-and-security"></a>기본 이동성 및 보안

이는 Microsoft 365에 기본적으로 제공 되며, Iphone, Ipad, Androids 및 Windows 휴대폰 같은 사용자의 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다. 디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.

## <a name="choose-between-the-two-options"></a>두 옵션 중에서 선택 합니다.

사용자에 게 가장 적합 한 장치 관리 옵션을 보다 쉽게 평가할 수 있도록 [기본 Mobility Security And Intune 사이](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)에 있는 선택을 참조 하세요.

평가에 따라 다음을 사용 하 여 장치 관리를 시작 합니다.

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [기본 이동성 및 보안](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>ID 및 장치 액세스 권장 사항

Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. 장치 액세스용으로 다음 문서의 권장 사항 및 설정을 사용 합니다.

- [필수 구성 요소](identity-access-prerequisites.md)
- [일반 ID 및 장치 액세스 정책](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso에서 Microsoft 365에 대 한 장치 관리를 수행 하는 방법

가상의 대표적인 다국적 기업이 Microsoft 365 클라우드 서비스와 함께 모바일 장치 관리 인프라를 배포 하는 방법에 대 한 자세한 내용은 [모바일 장치 관리 Contoso](contoso-mdm.md)를 참조 하십시오.
