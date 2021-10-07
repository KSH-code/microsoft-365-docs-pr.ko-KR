---
title: Windows 10 위치 서비스
description: 디바이스에 대해 Windows 위치 서비스를 설정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 76b6778d68fe5ed12034e3350170cf017093584e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170082"
---
# <a name="windows-10-location-service"></a>Windows 10 위치 서비스

디바이스의 Microsoft Managed Desktop Autopilot을 사용하여 Windows 등록됩니다. 이 프로세스를 통해 사용자 및 사용자 Azure Active Directory 관리할 Microsoft Intune. 기본적으로 Windows 10 동안 개인 정보 설정에서 이 기능을 사용하도록 설정하지 않는 한 장치를 처음 켜면 Windows 10 위치 서비스를 사용할 수 없습니다. 이러한 설정은 2016년 8월에 Autopilot 등록 중에 Microsoft Managed Desktop. Autopilot을 설정하는 방법에 대한 자세한 내용은 [Autopilot의](esp-first-run.md)첫 실행 환경 및 등록 상태 페이지를 참조하세요.

따라서 Microsoft Managed Desktop 장치 위치를 얻을 수 없습니다. 이로 인해 표준 시간대와 같은 여러 Windows 기능의 기능이 제한됩니다. Windows 10 위치 서비스에 대한 자세한 내용은 Windows 10 위치 서비스 및 개인 정보를 [참조하세요.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

위치 서비스에 참여하기 위해 위치 서비스를 사용할 Microsoft Managed Desktop 사용자 환경은 제한됩니다. 예를 들어 디바이스는 사용자가 다른 표준 시간대로 작업할 때 해당 표준 시간대를 자동으로 확인할 수 없습니다.

## <a name="enable-the-location-service"></a>위치 서비스 사용

장치를 Microsoft Managed Desktop 서비스에 등록할 때 위치 서비스를 옵트인하거나 등록 후 서비스를 켜거나 해제할 수 있습니다.

### <a name="opt-in-during-enrollment"></a>등록 중 옵트인

서비스에서 위치 Microsoft Managed Desktop 사용하도록 설정할 수 있습니다. 등록 시퀀스 중에 디바이스에서 Windows 10 위치 서비스를 사용하도록 허용할지 여부를 선택해야 합니다.

### <a name="control-the-location-service-after-enrollment"></a>등록 후 위치 서비스 제어

관리 포털을 통해 지원 요청을 제출하여 위치 서비스를 설정하거나 해제할 [수 있습니다.](access-admin-portal.md) [](../working-with-managed-desktop/admin-support.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Microsoft Managed Desktop 위치 서비스를 구성하는 Windows 10 방법

위치 서비스를 사용하기로 옵트인하는 경우 사용자의 개인 정보 보호에 영향을 주지 않고 필요한 최소 설정을 사용합니다. 자세한 내용은 Windows 10 [위치 서비스 및 개인 정보를 참조하세요.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Microsoft Managed Desktop 설정의  위치 개인 정보 설정을 이 **Windows** 위치에 대한 액세스를 허용하도록 **설정할 수 있습니다.** 사용자 인터페이스는 다음과 같습니다.

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="기본 설정의 Windows 설정입니다.":::

> [!NOTE]
> 위치 서비스를 사용 옵트인(opt in)하는 경우 이 설정은 Windows 운영 체제 자체에만 적용됩니다. 앱은 위치 서비스를 사용할 수 없습니다. 각 사용자는 앱이 자신의 위치에 액세스할 수 있도록 허용할지 여부를 선택할 수 있습니다.