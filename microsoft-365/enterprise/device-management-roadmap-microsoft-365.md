---
title: Microsoft 365의 장치 관리 로드맵
keywords: Microsoft 365, Microsoft 365, Microsoft 365, 모바일 장치 관리, Intune
author: kelleyvice-msft
ms.author: kvice
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
description: 사용자에 대한 장치 관리를 설정하기 위한 Microsoft 365.
ms.openlocfilehash: 2155d33aa57da5bb80dbc83623ac87a94a300f28
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59167378"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365의 장치 관리 로드맵

Microsoft 365 엔터프라이즈용 앱에는 조직 내에서 장치 및 해당 앱을 관리하는 데 도움이 되는 기능이 포함되어 있습니다. 모바일 장치를 관리하면 조직의 리소스를 보호하고 보호할 수 있습니다.

장치 관리에는 두 가지 옵션이 있습니다.

- [Microsoft Intune](#microsoft-intune)
- [기본 모바일 및 보안](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

모바일 Microsoft Intune 또는 모바일 응용 프로그램 관리를 사용하여 조직에 대한 액세스를 관리할 수 있습니다. 모바일 장치 관리는 사용자가 Intune에서 장치를 "등록"하는 경우입니다. 장치가 등록된 후 관리되는 장치입니다. 따라서 조직의 정책, 규칙 및 설정을 받을 수 있습니다. 예를 들어 특정 앱을 설치하고, 암호 정책을 만들고, VPN 연결을 설치하는 등 여러 가지를 할 수 있습니다.

개인 장치를 소유한 사용자는 장치를 등록하거나 Intune 및 조직의 정책에 따라 관리하지 않을 수 있습니다. 그러나 여전히 조직의 리소스와 데이터를 보호해야 합니다. 이 시나리오에서는 모바일 응용 프로그램 관리를 사용하여 앱을 보호할 수 있습니다. 예를 들어 사용자가 디바이스에서 온라인에서 SharePoint PIN을 입력해야 하는 모바일 응용 프로그램 관리 정책을 사용할 수 있습니다.

개인 장치 및 조직 소유 장치를 관리하는 방법도 결정할 수 있습니다. 디바이스 사용에 따라 장치를 다르게 처리해야 할 수 있습니다.

## <a name="basic-mobility-and-security"></a>기본 모바일 및 보안

이 기능은 Microsoft 365 기본 제공되어 있으며 iPhone, iPad, Androids 및 Windows 휴대폰과 같은 사용자의 모바일 장치를 보호하고 관리하는 데 도움이 됩니다. 디바이스 보안 정책을 생성하고 관리하며, 원격으로 디바이스를 지우고, 자세한 디바이스 보고서를 볼 수 있습니다.

## <a name="choose-between-the-two-options"></a>두 옵션 중 선택

가장 적합한 장치 관리 옵션을 보다 잘 평가하려면 기본 모바일 보안 및 Intune 선택을 [참조하세요.](/office365/securitycompliance/choose-between-mdm-and-intune)

평가에 따라 다음을 통해 디바이스 관리를 시작하십시오.

- [Intune](/mem/intune/fundamentals/planning-guide)
- [기본 모바일 및 보안](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>ID 및 장치 액세스 권장 사항

Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](../security/office-365-security/microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. 장치 액세스의 경우 다음 문서의 권장 사항 및 설정을 사용합니다.

- [필수 구성 요소](../security/office-365-security/identity-access-prerequisites.md)
- [일반 ID 및 장치 액세스 정책](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso가 사용자에 대한 장치 관리를 Microsoft 365

대표적인 다국적 기업이 Microsoft 365 클라우드 서비스와 함께 모바일 장치 관리 인프라를 배포한 방법에 대한 자세한 내용은 [Contoso의](contoso-mdm.md)모바일 장치 관리를 참조하세요.